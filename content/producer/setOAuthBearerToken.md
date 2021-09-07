---
title: "setOauthBearerToken"
date: 2021-09-07T10:09:37+01:00
draft: false
---
## Description
```php
public function setOAuthBearerToken(string $token, int $lifetimeMs, string $principalName, ?array $extensions = null): void {}
```
The SASL/OAUTHBEARER token refresh callback or event handler should invoke  
this method upon success. The extension keys must not include the reserved  
key `auth`, and all extension keys and values must conform to the required  
format as per https://tools.ietf.org/html/rfc7628#section-3.1
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