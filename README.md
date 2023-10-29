# Home Temperature Monitoring with Zigbee devices
## (But not much else in the way of home automation)
### For Ubuntu 23.10 (Likely similar for other platforms/releases)

Assuming you don't want to go all-in on one of the propriatary home automation
solutions, you have two broad options. One is to use an open source home
automation system, such as [Home Assistant](https://www.home-assistant.io/) or
[OpenHab](https://www.openhab.org/). The other is to use something more 
low-level to communicate with your zigbee devices, and glue it all together 
yourself.

Since I (currently) only want to monitor and graph the temperature in my 
house, and don't need any actions taken with it, that's the route I opted
for. The key bit of open source software I'm using is
[Zigbee2MQTT](https://www.zigbee2mqtt.io/)

## Buying some Zigbee temperature sensors

I ordered a bunch of different ones from different manufacturors. All at the 
cheaper end of pricing! So far, none of them are amazing, and none are 
terrible. Plenty of comparisons and reviews exist online!

## Buying a Zigbee adapter

Based on instructions like [Flashing the CC2531 USB stick (Zigbee2MQTT)](https://www.zigbee2mqtt.io/guide/adapters/flashing/flashing_the_cc2531.html),
I decided against getting one of the cheaper adapters that might need 
flashing / reflashing with appropriate firmware. Based on the
[Zigbee2MQTT recommended adapters list](https://www.zigbee2mqtt.io/guide/adapters/#recommended)
and some forum posts, I went for a *Sonoff Zigbee 3.0 USB Dongle PLus - 
ZBDongle-E*, which seems to be working very well.

## MQTT Broker

As the name suggests, Zigbee2MQTT will output messages to an MQTT message
broker. A lot of tutorials suggest [Mosquitto from Eclipse](https://mosquitto.org/)
which is packaged for Ubuntu, so I went with that.

```
sudo apt-get install mosquitto mosquitto-clients
sudo systemctl enable mosquitto
sudo systemctl start mosquitto
```

## Zigbee2MQTT

## Threads
https://social.earth.li/notice/Ab9larIg8eGJbapInI
