
薛定谔的猫文档
=====================


薛定谔的猫（cats）是**万门大学**[^万门大学]内容管理系统的代号。主要目的是对纷繁的网络知识做精选整合。现阶段主要以图书，视频，经验贴作为出发点，核心是这些内容组成的列表（如书单，视频集）。目标是能够整理出真正对求学者有用的书单/视频集/自学列表。技术上的愿景是希望列表质量和数量都能达到一定规模，这样后续可能产生很多有意思的机械学习和数据挖掘方面的探索。

----------


文档说明
---------

**薛定谔的猫Rails版** 是基于Ruby on Rails的一种实现方案。

> **注意:** 薛定谔的猫本身的实现并不拘泥于任何框架和数据库管理系统，Ruby on Rails只是其中的一种实现方案。

#### <i class="icon-file"></i> 文件构成

    cats/
        app/
            assets/ #所有素材，包括js,css,img等
            controllers/ #控制器
            helpers/ #帮助
            mailers/ #邮件
            models/ #模型
            views/ #视图
    bin/
    config/
        environments/
        initializers/
        locales/
        application.rb
        root.rb
        database.yml
        environment.rb
        routes.rb
    db/
    lib/
    log/
    public/
    test/
    tmp/
    vender/
    config.ru
    Gemfile
    Gemfile.lock
    Rakefile    
    README.md

----------

安装说明
---------

要求：

     Ruby version >= Ruby 1.9.2
     Rails Version >= Rails 4.0.0
关联包：
    # Use devise for user authentication
    用户登录系统包
    gem 'devise'
    
    # Use mysql for database mysql包
    gem 'mysql2'
    
    # in ubuntu, you will probably need to install some dependent libraries: sudo apt-get install mysql-client libmysqlclient-dev
    如果你用ubuntu，或许得先装mysql-client libmysqlclient-dev
    
    gem 'tlsmail'
    #sending mail from smtp mail servers用来发smtp邮件
    
    gem 'omniauth'
    gem 'omniauth-weibo-oauth2'
    gem 'omniauth-renren-oauth2'
    gem 'omniauth-douban-oauth2'
    # social logins用来处理社交登录

配置：

在 config/environments/development.rb中设置smtp email的信息

在config/initializers/devise.rb中设置第三方社交网站登录

    bundle install
安装以上相关的包

新建数据库：

In<code>config/database.yml</code> to configure the database criteria. Like the database names and the database user/password 更新你的数据库的信息

    rake db:schema:load
运行添加数据库

数据库初始化 

运行整个系统

    rails server

  [^万门大学]: 万门大学是