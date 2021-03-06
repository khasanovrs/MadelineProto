---
title: ping
description: ping parameters, return type and example
---
## Method: ping  
[Back to methods index](index.md)


### Parameters:

| Name     |    Type       | Required |
|----------|---------------|----------|
|ping\_id|[long](../types/long.md) | Yes|


### Return type: [Pong](../types/Pong.md)

### Can bots use this method: **YES**


### Example:


```
$MadelineProto = new \danog\MadelineProto\API();
$MadelineProto->session = 'mySession.madeline';
if (isset($token)) { // Login as a bot
    $MadelineProto->bot_login($token);
}
if (isset($number)) { // Login as a user
    $MadelineProto->phone_login($number);
    $code = readline('Enter the code you received: '); // Or do this in two separate steps in an HTTP API
    $MadelineProto->complete_phone_login($code);
}

$Pong = $MadelineProto->ping(['ping_id' => long, ]);
```

Or, if you're using the [PWRTelegram HTTP API](https://pwrtelegram.xyz):

### As a bot:

POST/GET to `https://api.pwrtelegram.xyz/botTOKEN/madeline`

Parameters:

* method - ping
* params - `{"ping_id": long, }`



### As a user:

POST/GET to `https://api.pwrtelegram.xyz/userTOKEN/ping`

Parameters:

ping_id - Json encoded long




Or, if you're into Lua:

```
Pong = ping({ping_id=long, })
```

