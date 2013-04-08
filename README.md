Jekyll-Rake-RSync-Deploy
========================

A rake task for RSync Deployment in [Jekyll](http://jekyllrb.com/).

Creates rake tasks for Jekyll Deploy and Launch.

Uses environments set up in `_config.yml` like so:

    environments:
      stage:
        url: http://stage.example.com
        remote:
          connection: user@example.com
          path: /var/www/
          port: 12345 #optional
      production:
        url: http://production.example.com
        remote:
          connection: user@example.com
          path: /var/www/

Usage
=====
=====

To deploy the site, run `rake deploy`

To deploy a different environment, run `rake deploy env=production`

The same applies for launch:

    rake launch
    rake launch env=production

This command will open the environment in your default browser

Defaults
========
========

`env=stage`

Notes and Thanks
================
================
================

Note: Requires 'destination' ([see Jekyll docs](https://github.com/mojombo/jekyll/wiki/Configuration)) to be set in _config.yml, or it will try to rsync "/". Do not include a trailing slash on the 'destination' variable.

Thanks to [henrik](https://github.com/henrik) for the [rsync bash script](https://github.com/henrik/henrik.nyh.se/blob/master/tasks/deploy) that I stole to make this.

*nix, mac only
