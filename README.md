mandrill-api-php
================

OnePetDev fork of [`mandrill/mandrill`](https://bitbucket.org/mailchimp/mandrill-api-php/) — the official PHP client for [Mandrill's API](https://mandrillapp.com/api/docs/), republished after Mailchimp removed the package from Packagist.

This is a **byte-identical** mirror of the upstream `mandrill/mandrill` v1.0.55 source. The only changes from upstream live in `composer.json` (package name and metadata) so the library can be installed via Composer from GitHub. The public API — class names, method signatures, behaviour — is unchanged. Existing code written against `mandrill/mandrill` works without modification once the dependency is swapped.

Installation
============

Because this package is not on Packagist, add the repository to your project's `composer.json` and require it by name:

```json
{
    "require": {
        "onepetdev/mandrill-api-php": "^1.0"
    },
    "repositories": [
        {
            "type": "vcs",
            "url": "https://github.com/OnePetDev/mandrill-api-php.git"
        }
    ]
}
```

Until a tagged release exists, use `"dev-master"` in place of `"^1.0"`.

Usage
=====

Identical to the upstream library:

```php
require_once 'vendor/autoload.php';

$mandrill = new Mandrill('YOUR_API_KEY');
$result = $mandrill->messages->send([
    'subject'    => 'Hello',
    'from_email' => 'sender@example.com',
    'to'         => [['email' => 'recipient@example.com']],
    'text'       => 'Hello, world!',
]);
```

See the [Mandrill API documentation](https://mailchimp.com/developer/transactional/api/) for the full API surface.

License
=======

Apache-2.0. Copyright 2013 The Rocket Science Group, LLC. See [LICENSE](LICENSE) for full terms.
