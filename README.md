# Unified Messaging
Xii Group Unified Messaging Gateway allow to send and seceive Whatsapp and SMS messages from any server through api.

## Sample PHP Usage
This sample php code send an sms message and returns the response in json. to send a whatsapp message replace sms with **whatsapp**.
Replace **DOMAIN** , **API_USERNAME** & **API_KEY** with your API user Information.

```
<?php
require_once('umgateway.php');
$umg = new umg("DOMAIN", "API_USERNAME", "API_KEY");
$payload = [
'endpoint'=>'sms', //replace sms with whatsapp to send whatsapp
'action'=>'send',
'repliable'=>true,
'type'=>'text',
'nid'=>'23',
'to'=>'2701234567',
'from'=>'2701234567', //recommended to use number provided with service
'name'=>'Sipho Selabe',
'body'=>'Dear client..'
];
$umg->payload($payload);
$response = $umg->execute();
print_r($response);
```

## Sample json response
The following response you receive after send a message using the above sample, please save the **id** and **tid** for later quering important is the message cannot be sent instant.

```json
{
  "status": "success",
  "results_count": 8,
  "results": {
    "id": "20994c0b-abce-4949-0104-04200000a61d",
    "status_code": 1,
    "status_msg": "Received",
    "parts": 1,
    "tid": "78Pe7RuIGXElgLE.5154",
    "cost": 0.28
  }
}
```

For all api payloads definitions [Check wiki](https://github.com/xiigroup/Unified-Messaging/wiki), to request your credentials [Contact sales](https://xiigroup.co.za/#contact)
