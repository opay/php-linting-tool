<img src="https://avatars.githubusercontent.com/u/24718711?s=128" alt="OPAY" style="width: 128px; height: 128px; float: left; margin: 15px 15px 15px 0;"/>

PHP linting rules
=============================

This is PHP linting tools and rules set used by "OPAY solutions" developers to ensure we deliver maintainable and the highest quality code.

The main point of this tools set is to ensure developers write [PSR compliant code](https://www.php-fig.org/psr/). Many [additional rules](./OpaySniffs/ruleset.xml) are added to increase code quality and readability. None of our code goes to production if at least one code style error or warning is discovered.
<br clear="all"/>

Package content
---------------
- [friendsofphp/php-cs-fixer](https://github.com/FriendsOfPHP/PHP-CS-Fixer) - Powerful PHP Coding Standards tool
- [squizlabs/php_codesniffer](https://github.com/squizlabs/PHP_CodeSniffer) - Another powerful and customizable PHP Coding Standards tool
- [slevomat/coding-standard](https://github.com/slevomat/coding-standard) - Set of additional linting rules for PHP CodeSniffer
- [moxio/php-codesniffer-sniffs](https://github.com/Moxio/php-codesniffer-sniffs) - Set of additional linting rules for PHP CodeSniffer
- Custom Opay linting rules for PHP CodeSniffer

`PHP-CS-Fixer` and `PHP_CodeSniffer` are both PHP code linting tools that complement each other allowing developers to write the highest quality code.

Installation & usage
--------------------
Install as a development dependency using composer:
```
$ composer require --dev opay-dev/php-linting-tools
```
Run tools to validate your files:
```
vendor/bin/php-cs-fixer fix path/to/files --dry-run --verbose
vendor/bin/phpcs --standard=vendor/opay-dev/php-linting-tools/OpaySniffs path/to/files
```
Run tools to fix your files automatically _(not all files can be fixed, some may require manual fixing)_:
```
vendor/bin/php-cs-fixer fix path/to/files --verbose
vendor/bin/phpcbf --standard=vendor/opay-dev/php-linting-tools/OpaySniffs path/to/files
```
Setup custom config and run tools to validate your files:
```
vendor/bin/php-cs-fixer fix --config="ConfigExamples/custom_phpcsfixer_config.php" --dry-run --verbose
vendor/bin/phpcs --standard="ConfigExamples/custom_phpcs_config.xml"
```
Setup custom config and run tools to fix your files automatically:
```
vendor/bin/php-cs-fixer fix --config="ConfigExamples/custom_phpcsfixer_config.php" --verbose
vendor/bin/phpcbf --standard="ConfigExamples/custom_phpcs_config.xml"
```
Configure [bash script](./lint) or add script to `compsoer.json` and run it with single command `composer lint`:
```json
{
    "lint": [
        "vendor/bin/php-cs-fixer fix path/to/files --dry-run --verbose",
        "vendor/bin/phpcs --standard=vendor/opay-dev/php-linting-tools/OpaySniffs path/to/files"
    ]
}
```

Licence
-------
This is set of tools created by different developers teams and collected to one set by Opay developers with additional rules added. This package can be used under MIT licence as long as it does not violate the licenses of other developers.
