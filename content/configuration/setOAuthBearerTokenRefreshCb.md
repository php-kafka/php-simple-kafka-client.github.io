---
title: "setOAuthBearerTokenRefreshCb"
date: 2021-09-07T10:09:37+01:00
draft: false
geekdocCollapseSection: true
---
## Description
```php
public function setOAuthBearerTokenRefreshCb(callable $callback): void {}
```
The SASL/OAUTHBEARER token refresh callback is triggered automatically or via `poll`  
whenever OAUTHBEARER is the SASL mechanism and a token needs to be retrieved,  
typically based on the configuration defined in `sasl.oauthbearer.config`.  
   
The callback should invoke `setOauthBearerToken`  
or `setOauthBearerTokenFailure` to indicate success  
or failure, respectively.
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