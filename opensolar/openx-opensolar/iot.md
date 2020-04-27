# IoT

The IoT devices linked to the solar panels transmit data using the MQTT protocol. The MQTT protocol requires 

1. a **transmitter** \(the IoT devices linked to the solar panel\)
2. a **broker** to broadcast the messages received from the transmitter, and
3. a **receiver** which connects to the broker and subscribes to messages from the transmitter.

The broker can either be run alongside the platform or can be run on the IoT Hub depending on the energy specifications and capabilities of the IoT Hub. Opensolar runs an MQTT broker at mqtt.openx.solar which acts as the default broker for all projects.  
  
The platform also subscribes to teller broadcasts and accumulates data in order to display it on the recipient dashboard. Recipients can also download data from the recipient dashboard to view the teller's logs.

