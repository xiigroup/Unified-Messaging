# Unified Messaging Gateway
UMG, Send and Receive Whatsapp and SMS messages from any system.

# Sample PHP Usage
This sample php code send a whatsapp message.
Replace **DOMAIN** , **API_USERNAME** & **API_KEY** with your API user Information.

```<?php
require_once('umg.php');
$umg = new umg("DOMAIN", "API_USERNAME", "API_KEY");
$payload = [
'endpoint'=>'whatsapp',
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

For all api payloads key and values [Check wiki](https://github.com/xiigroup/messaging/wiki)
