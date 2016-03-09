# YahooStockQuotes
Yahoo Stock Quotes in PHP

[![Build Status](https://travis-ci.org/aensley/YahooStockQuotes.svg)](https://travis-ci.org/aensley/YahooStockQuotes) [![MIT License](https://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/aensley/YahooStockQuotes/blob/master/LICENSE)

## Requirements

There must be a `stockQuotes.json` file in the same directory as the `stockQuotes.php` file. 

`stockQuotes.json` must be **WRITABLE** by the user who owns the PHP process (apache, www-data, nginx, hhvm, etc.).

If the file does not exist or is not writable, every page view will require a new request to Yahoo's servers, which will slow down all page views drastically and get your server blocked by Yahoo.


## Example usage

```php
<?php

include 'stockQuotes.php';

?><html>
	<head>
		<title>Stock Test</title>
	</head>
	<body>
		Price: <?php echo $stockQuotes->getPrice('YHOO'); ?>
		<br/>
		Change: <?php echo $stockQuotes->getChange('YHOO'); ?>
		<br/>
		Last updated: <?php echo $stockQuotes->getUpdatedDate(); ?>
	</body>
</html>
```

----

[![Supercharged by ZenHub.io](https://raw.githubusercontent.com/ZenHubIO/support/master/zenhub-badge.png)](https://zenhub.io)
