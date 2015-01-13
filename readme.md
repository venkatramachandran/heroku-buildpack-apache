Apache build pack
========================

This is a build pack bundling Apache for Heroku apps. It tests for the presence of an `index.html` file and then serves out of root with Apache.

Use
---

For new apps:
```bash
$ heroku create --stack cedar --buildpack https://github.com/venkatramachandran/heroku-buildpack-apache.git
```

For existing apps:
```bash
$ heroku config:add BUILDPACK_URL=https://github.com/venkatramachandran/heroku-buildpack-apache.git
```

Basic Authentication
--------------------

in .htaccess add:
```
AuthUserFile /app/.htpasswd
AuthType Basic
AuthName "Restricted Access"
Require valid-user
```

[generate](http://www.htaccesstools.com/htpasswd-generator/) and add an .htpasswd to root


Configuration
-------------

The config files are bundled with the build pack itself:

* conf/httpd.conf

Meta
----

Big thanks to the guys behind the [php buildpack](https://github.com/heroku/heroku-buildpack-php) and [stevenosloan](https://github.com/stevenosloan/heroku-buildpack-apache)

Released under the [MIT License](http://opensource.org/licenses/mit-license.php)
