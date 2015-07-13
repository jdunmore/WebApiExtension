Web API Extension
=================

Installation
------------

This extension requires:

* Behat 3.0+
* PHP 5.4+

Through Composer

The easiest way to keep your suite updated is to use Composer :

1. Define dependencies in your `composer.json`:

```javascript
    {
        "require-dev": {
            ...

            "behat/web-api-extension": "~1.0@dev"
        }
    }
```


2. Install/update your vendors:

```bash
    $ composer update behat/web-api-extension
```

3. Activate extension by specifying its class in your ``behat.yml``:

```yaml
        # behat.yml
        default:
          # ...
          extensions:
            Behat\WebApiExtension: ~
```

Usage
-----

Various options:

1. Make your suite WebApiContext aware. In behat.yml

```yaml    
    #behat.yml
    default:
        suites:
            MySetOfFeatures_features:
                paths: [ %paths.base%/features/MySetOfFeatures ]
                contexts: [ Behat\WebApiExtension\Context\WebApiContext ]
```

2. Define a context and extend `Behat\WebApiExtension\Context\WebApiContext`

3. Definte a context, and implement ApiClientAwareContext (This will make you implement setClient() and you won't have any predefined steps)

Option 1 and 2 allow you to use the predefined stueps, option 3 allows you to use the tools and implement the steps using a language that makes sense to your business.


Predefined Steps
------

For options 1 and 2 above, the predefined steps are in [WebApiContext](../src/Context/WebApiContext.php) for reference they are

* iAmAuthenticatingAs
* iSetHeaderWithValue
* iSendARequest
* iSendARequestWithValues
* iSendARequestWithBody
* iSendARequestWithFormData
* theResponseCodeShouldBe
* theResponseShouldContain
* theResponseShouldNotContain
* theResponseShouldContainJson
