Yii2 command extension to clean composer's vendor/ directory
===================================

This extension removes docs, tests, gits, etc from composer's vendor/ directory

It is based on <a href="https://github.com/barryvdh/composer-cleanup-plugin">barryvdh/composer-cleanup-plugin</a>

The format of the rules and the removal logic have been copied.

The main changes are:
- Callable as a Yii2 command
- Provides progress feedback
- Default rule added

Installation
------------

The preferred way to install this extension is through [composer](http://getcomposer.org/download/).

Either run

```
php composer.phar require mbrowniebytes/yii2-clean-vendors
```

or add

```json
"mbrowniebytes/yii2-clean-vendors": "*"
```

to the require section of your composer.json.


Usage
-----

To use this extension, call it from the command line 

```
/path/yii> php yii clean-vendors
Checking vendor/ to remove docs, gits, tests, etc ..
Checking 56 vendor packages ..
Done. Scanned 25 vendor packages, cleaned 10 files/dirs
```

or add to composer scripts section to always clean vendors
```
    "scripts": {
		"post-update-cmd": [
			"php yii clean-vendors"
		]
    },
```

Additional arguments
-------------------
```
-dry-run	do not delete anything
-verbose	echo rules being run, dir/file being deleted
-silent		do not echo anything
```
