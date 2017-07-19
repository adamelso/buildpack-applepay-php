Heroku Buildpack for applepay-php Extension
====

The extension can be found at https://github.com/etsy/applepay-php

Installation
---

To add it to you Heroku PHP project, just run:


    $ heroku buildpacks:add https://github.com/adamelso/buildpack-applepay-php


You see the following message:

    Buildpack added. Next release on merchant-com-s-reiss-demo will use:
      1. heroku/php
      2. https://github.com/adamelso/buildpack-applepay-php
    Run git push heroku master to create a new release using these buildpacks.


Next, you need to make a dummy commit to allow it to be deployed on the next push.

    $ git commit
    $ git push heroku master


This will start compiling the extension from its C source and installed into PHP.

```
remote: -----> Preparing runtime environment...
remote: -----> Checking for additional extensions to install...
remote: -----> Apple Pay PHP Extension app detected
remote: -----> Cloning applepay-php extension.
remote: Cloning into 'applepay-php'...
remote: -----> Compiling applepay-php extension.
remote: Configuring for:
remote: PHP Api Version:         20160303
remote: Zend Module Api No:      20160303
remote: Zend Extension Api No:   320160303
remote: checking for grep that handles long lines and -e... /bin/grep
remote: checking for egrep... /bin/grep -E
remote: checking for a sed that does not truncate output... /bin/sed
remote: checking for cc... cc
remote: checking whether the C compiler works... yes

[truncated]

remote: ----------------------------------------------------------------------
remote: Libraries have been installed in:
remote:    /app/tmp/buildpacks/b9173a9ddc47d8e8bd35ec1f7f7be6453a2668c5c6370c00630aab0991463500dc0add050ecfea256f4ab77e55d0ba411109edd8e62007dc8c9e6f6358d5e8b4/applepay-php/modules
remote: 
remote: If you ever happen to want to link against installed libraries
remote: in a given directory, LIBDIR, you must either use libtool, and
remote: specify the full pathname of the library, or use the `-LLIBDIR'
remote: flag during linking and do at least one of the following:
remote:    - add LIBDIR to the `LD_LIBRARY_PATH' environment variable
remote:      during execution
remote:    - add LIBDIR to the `LD_RUN_PATH' environment variable
remote:      during linking
remote:    - use the `-Wl,--rpath -Wl,LIBDIR' linker flag
remote:    - have your system administrator add LIBDIR to `/etc/ld.so.conf'
remote: 
remote: See any operating system documentation about shared libraries for
remote: more information, such as the ld(1) and ld.so(8) manual pages.
remote: ----------------------------------------------------------------------
remote: 
remote: Build complete.
remote: Don't forget to run 'make test'.
remote: 
remote: -----> Installing applepay-php extension.
remote: Installing shared extensions:     /app/.heroku/php/lib/php/extensions/no-debug-non-zts-20160303/
remote: -----> Discovering process types
remote:        Procfile declares types -> web
remote: 
remote: -----> Compressing...
remote:        Done: 17.8M
remote: -----> Launching...
remote:        Released v9
remote:        https://*yourapp*.herokuapp.com/ deployed to Heroku
remote: 
remote: Verifying deploy... done.
```

