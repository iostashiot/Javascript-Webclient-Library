
![IOStash IoT PaaS](http://iostash.io/wp-content/uploads/2016/06/iostashbeta_black.png) 

Javascript Web Client Library
===================


Javascript web Client library for IOStash IoT PaaS. Supports realtime data subscription to Devices, Data Points, Location, Channels and Custom Data sent to devices.

 **Including**
JS client is available via th JSDelivr CDN.
 

      <script type="text/javascript" src="https://cdn.jsdelivr.net/iostash/0.1/iostash.js"></script>

 
 **How To Use**

This library supports all realtime events supported by IOStash. Refer to API Docs on http://docs.iostash.io for more information and guides about using this library.

      var iostash = require('iostash')
      iostash.init('X-ACCESS-TOKEN_HERE')
      
      iostash.subscribeDevice('DEVICE-ID_HERE', function (data) {
      //Handle data here
      });  

**Example**

This example utilises a public device defined in IOStash.

    var iostash = require('iostash')
    iostash.initPublic('5734997f8680bc62de000006')
    iostash.subscribeDevice('5734997f8680bc62de000006', function (update) {
      console.log(update)
    })

**Methods**   
   

 - `init(x-access-token)` - Initialises the object with specified x-access-token.
 - `initPublic(deviceId)` - Initialises the object with a public device's ID.
 - `subscribeDevice(deviceId,cb())` - Subscribes to data changes from the specified device.
 - `unsubscribeDevice(deviceId,cb())` - Unsubscribes from the specified device.
 - `subscribeDataPoint(deviceId,datapoint,cb())` - Subscribes to specified datapoint of the specified device.
 - `unsubscribeDataPoint(deviceId,datapoint,cb())` - Unsubscribes from the specified data point.
 - `subscribeLocation(deviceId,cb())` - Subscribes to location data from the specified device.
 - `subscribeActions(deviceId,cb())` - Subscribes to device trigger action of the specified device.
 - `subscribeCustomData(deviceId,cb())` - Subscribes to custom data sent to the device.
 - `onDisconnect(cb())` - Fires when the connection to the server is lost.

**Notes**

- cb() refers to callbacks and they will be executed during updates.
- While using `initPublic()` method for initialization, channel functions are not available.
- This library does not (yet) support data pushing to IOStash.

For support or assistance, drop an email to aravind@iostash.io