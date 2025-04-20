# Unified Messaging Gateway
UMG, Send and Receive Whatsapp and SMS messages from any system.

# Sample PHP Usage
This sample php code send an sms message and returns the response in json.
Replace **DOMAIN** , **API_USERNAME** & **API_KEY** with your API user Information.

```<?php
require_once('umg.php');
$umg = new umg("DOMAIN", "API_USERNAME", "API_KEY");
$payload = [
'endpoint'=>'sms',
'action'=>'send',
'nid'=>'23',
'to'=>'2701234567',
'name'=>'Selabe',
'body'=>'Dear client..'
];
$umg->payload($payload);
$response = $umg->execute();
print_r($response);
```

# Sample response
```
```json
{
  "status": "success",
  "results_count": 8,
  "results": {
    "id": "20994c0b-abce-4949-0104-04200000a61d",
    "status_code": 1,
    "status_msg": "Received",
    "parts": 1,
    "country": "ZAF",
    "network": "Vodacom",
    "transaction_id": "78Pe7RuIGXElgLE.5154",
    "transaction_cost": 0.28
  }
}
```

For all api payloads key and values [Check wiki](https://github.com/xiigroup/messaging/wiki)
