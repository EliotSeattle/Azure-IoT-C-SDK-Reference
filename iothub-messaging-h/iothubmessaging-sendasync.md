# IoTHubMessaging_SendAsync()

Asynchronous call to send the message to a specified device.

## Syntax

\#include "[azure-iot-sdk-c/iothub_service_client/inc/iothub_messaging.h](../iothub-messaging-h.md)"  
```C
IOTHUB_MESSAGING_RESULT IoTHubMessaging_SendAsync(
  IOTHUB_MESSAGING_CLIENT_HANDLE  messagingClientHandle,
  const char *                    deviceId,
  IOTHUB_MESSAGE_HANDLE           message,
  IOTHUB_SEND_COMPLETE_CALLBACK   sendCompleteCallback,
  void *                          userContextCallback
);
```

## Parameters
* `messagingClientHandle` The handle created by a call to the create function. 

* `deviceId` The name (Id) of the device to send the message to. 

* `message` The message to send. 

* `sendCompleteCallback` The callback specified by the user for receiving confirmation of the delivery of the message. The user can specify a NULL value here to indicate that no callback is required. 

* `userContextCallback` User specified context that will be provided to the callback. This can be NULL.

**NOTE:** The application behavior is undefined if the user calls the [IoTHubMessaging_Destroy](../iothub-messaging-h/iothubmessaging-destroy.md) or IoTHubMessaging_Close function from within any callback.

## Return Value
IOTHUB_MESSAGING_OK upon success or an error code upon failure.
