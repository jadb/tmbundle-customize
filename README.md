# Customize TextMate 2 Bundle

After the alpha release of TextMate 2, I decided to refactor my personal bundle. The goal behind this bundle is to overload
some Commands or Snippets from other bundles while adding what I couldn't find in any other bundle.

## Included Customizations

The following existing bundles have been overloaded with personal customization (which means the following bundles are
required for all the non-customized Commands, Snippets, etc.)

* Apache
* LESS
* PHP
* PHPCodeSniffer
* PHPDoc
* PHPUnit

## Prerequisites

* [Less](http://lesscss.org/#-server-side-usage)
* [LESS Bundle](https://github.com/appden/less.tmbundle)
* [PHPUnit 3.6](http://www.phpunit.de/manual/3.6/en/installation.html)
* [PHP Code Sniffer 1.3.2](http://pear.php.net/package/PHP_CodeSniffer/redirected)

### Optional

As mentioned earlier on, for the complete list of Commands, Snippets, etc. you will need to install the original bundles:

* Apache Bundle - part of TextMate core, make sure it is enabled.
* [PHPUnit Bundle](https://github.com/gargoyle/phpunit-tmbundle)

## Installing

    $ mkdir -p ~/Library/Application\ Support/Avian/Bundles
    $ cd ~/Library/Application\ Support/Avian/Bundles
    $ git clone git://github.com/jadb/tmbundle-customize.git "Customize.tmbundle"
    $ osascript -e 'tell app "TextMate" to reload bundles'

You will also need to add the following to your `~/.tm_properties` file:

    TM_PHPCS = '/path/to/phpcs'
    TM_PHPCS_OPTIONS  = '--extra-options --are-set=here'
    TM_PHPUNIT = '/path/to/phpunit'
    TM_PHPUNIT_OPTIONS = '--extra-options --are-set=here'
    TM_PHPUNIT_TESTSPATH = '$CWD/Tests'

## Known Issues

### env: node: No such file or directory

TextMate might not find `node` when trying to use LESS. In that case, add a `PATH` variable to your `~/.tm_properties` file.

    $ echo "PATH = '$PATH'" >> ~/.tm_properties


## Credits

* [Jad Bitar](https://github.com/jadb)

## Patches & Features

* Fork
* Mod, fix
* Test - this is important, so it's not unintentionally broken
* Commit - do not mess with license, todo, version, etc. (if you do change any, make them into commits of their own that I can ignore when I pull)
* Pull request - bonus point for topic branches

## Bugs & Feedback

https://github.com/jadb/customize-tmbundle/issues
