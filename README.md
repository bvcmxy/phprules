# PHP Code Rules

Rules for PHP Coding Standard

## Install

Run `composer require --dev "bvcmxy/php-code-rules"`

## Post Install

Next packages must be installed for using the rules:
- `composer require --dev phpmd/phpmd`
- `composer require --dev sebastian/phpcpd`
- `composer require --dev squizlabs/php_codesniffer`
- `composer require --dev friendsofphp/php-cs-fixer`
- `composer require --dev phpstan/phpstan`

## Using in IDE

* ### PHP Storm
  * PHPMD: https://www.jetbrains.com/help/phpstorm/using-php-mess-detector.html
  * PHPCS: https://www.jetbrains.com/help/phpstorm/using-php-code-sniffer.html
  * PHPCS Fixer: https://www.jetbrains.com/help/phpstorm/using-php-cs-fixer.html
  * PHPStan: https://www.jetbrains.com/help/phpstorm/using-phpstan.html

* ### VS Code
  * PHPMD: https://marketplace.visualstudio.com/items?itemName=ecodes.vscode-phpmd
  * PHPCS: https://marketplace.visualstudio.com/items?itemName=ikappas.phpcs
  * PHPCS Fixer: https://marketplace.visualstudio.com/items?itemName=junstyle.php-cs-fixer
  * PHPStan: https://marketplace.visualstudio.com/items?itemName=calsmurf2904.vscode-phpstan

##Usage:
* ### Rules
  * for PHPMD: `./vendor/bvcmxy/php-code-rules/phpcs/laravel/phpcs.xml`
  * for PHPCS: `./vendor/bvcmxy/php-code-rules/phpmd/laravel/phpmd.xml`
  * for PHPCS Fixer: `./vendor/bvcmxy/php-code-rules/phpcs-fixer/laravel/.php-cs-fixer.php`
  * for PHPStan: `./vendor/bvcmxy/php-code-rules/phpstan/laravel/stan.neon`
* ###Examples (CLI)
  * PHPMD: PHPMD: `php vendor/bin/phpmd ./app text ./vendor/bvcmxy/php-code-rules/phpmd/laravel/phpmd.xml`
  * PHPCS: `php vendor/bin/phpcs --standard=vendor/bvcmxy/php-code-rules/phpcs/laravel/phpcs.xml --error-severity=1 --warning-severity=8 --extensions=php  ./app`
  * PHPCS Fixer: `vendor/bin/php-cs-fixer fix ./app/ --config=./vendor/bvcmxy/php-
    code-rules/phpcs-fixer/laravel/.php-cs-fixer.php --dry-run`
  * PHPStan: `php vendor/bin/phpstan analyse -c ./vendor/bvcmxy/php-code-rules/phpstan/laravel/stan.neon`
  * PHPCPD: `php vendor/bin/phpcpd ./app`
* ###Using in Composer
  * add in composer in script section if exists, if not add section `"scripts":{}`:
  ```composer log 
  "phpcs": [
     "@php vendor/bin/phpcs --standard=vendor/bvcmxy/php-code-rules/phpcs/laravel/phpcs.xml --error-severity=1 --warning-severity=8 --extensions=php  ./app"
   ],
   "phpmd": [
      "@vendor/bin/phpmd ./app text ./vendor/bvcmxy/php-code-rules/phpmd/laravel/phpmd.xml"
   ],
   "phpcpd": [
      "@php vendor/bin/phpcpd ./app"
   ],
   "phpstan": [
     "@php vendor/bin/phpstan analyse -c ./vendor/bvcmxy/php-code-rules/phpstan/laravel/stan.neon"
   ]
  ```

## References
* PHPMD: https://phpmd.org/rules/#clean-code-rules
* PHPCS: https://github.com/squizlabs/PHP_CodeSniffer
* PHPCS Fixer: https://github.com/FriendsOfPHP/PHP-CS-Fixer
* PHPCS Fixer Configurator: https://mlocati.github.io/php-cs-fixer-configurator/#version:3.3
* PHPStan: https://phpstan.org/user-guide/getting-started
* PHPCPD: https://github.com/sebastianbergmann/phpcpd