# Wikipedia

### Installation

Begin by installing this package through Composer.

```js
{
    "require": {
        "blamonet/wikipedia": "dev-master"
    },
    "repositories": [
        {
            "url": "https://github.com/blamonet/Laravel-Wikipedia.git",
            "type": "git"
        }
    ]
}
```

### Usage

**Retrieve page extract**

```php
$wikipedia = new \Casinelli\Wikipedia\Wikipedia;

return $wikipedia->search("Rome")->getSentences(5);
```

**Same with QueryBuilder**

```php
$qb = new \Casinelli\Wikipedia\QueryBuilder;

$qb->setFormat("php");
$qb->setTitles("Singapore");
$qb->setExtractsSentences(3);
$qb->setExtractsPlainText(true);

$response = unserialize( $qb->fetch() );

$page = reset( $response["query"]["pages"] );

return $page["extract"];
```

**Set Locale**
```php
$wikipedia->setLocale("fr"); // setting for French
```
