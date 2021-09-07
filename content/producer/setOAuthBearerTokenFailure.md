---
title: "setOauthBearerTokenFailure"
date: 2021-09-07T10:09:37+01:00
draft: false
---
## Description
```php
public function setOauthBearerTokenFailure(string $errorString): void {}
```
The SASL/OAUTHBEARER token refresh callback or event handler should invoke  
this method upon failure. `$errorString` should be a human readable error reason  
why acquiring a token failed.
## Example
```php
$conf = new SimpleKafkaClient\Configuration();
$conf->set('metadata.broker.list', getenv('TEST_KAFKA_BROKERS'));
$conf->set('security.protocol', 'SASL_PLAINTEXT');
$conf->set('sasl.mechanisms', 'OAUTHBEARER');
$conf->set('sasl.oauthbearer.config', 'principalClaimName=azp');
$conf->setOAuthBearerTokenRefreshCb(function($kafka, $oAuthBearerConfig) {
    // get the refresh token with some custom code, then act accordingly
    if ($tokenRefreshWasSucessful) {
        $kafka->setOAuthBearerToken($token, $lifetimeMs, $principalName, $extensions);
    } else {
        $kafka->setOAuthBearerTokenFailure($errorReason);
    }
});
```