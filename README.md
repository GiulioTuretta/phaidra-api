phaidra-api 
===========

Prerequisities:

* Mojolicious Plugins

  /usr/local/bin/cpanm Mojolicious::Plugin::Database
  
  /usr/local/bin/cpanm MooX::Types::MooseLike::Numeric --force
  
  /usr/local/bin/cpanm MooX::Types::MooseLike
  
  /usr/local/bin/cpanm Mojolicious::Plugin::CHI
  
  /usr/local/bin/cpanm Mojolicious::Plugin::I18N
  
  /usr/local/bin/cpanm Net::LDAPS
  
  
  (On Ubuntu: sudo apt-get install libmojolicious-plugin-i18n-perl)

* Run:

  $# morbo -w PhaidraAPI -w templates -w public -w lib api.cgi

  [debug] Reading config file "PhaidraAPI.json".

  Server available at http://127.0.0.1:3000.

* Apache/CGI

        ScriptAlias /api my_document_root/api.cgi

        RewriteEngine on
        RewriteCond %{HTTP:Authorization} ^(.+)
        RewriteRule ^(.*)$ $1 [E=HTTP_AUTHORIZATION:%1,PT]
  
