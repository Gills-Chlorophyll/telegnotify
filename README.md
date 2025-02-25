# Telegram notifications & logs
----

Although remote devices are generally reliable, there are occasions when it is necessary to monitor various parameters related to the systemctl units and the hardware health of the device. While one approach involves periodically logging into the device via SSH to retrieve all relevant statistics, we recommend implementing a service on the device that performs this task, similar to a cron job. Developing a web application could be a logical solution; however, automating this process through Telegram offers a more efficient alternative, significantly reducing the time to market.

Telgram notifications could be of

1. Vital stats 
2. GPIO status 
3. Logs and error status of services 

A systemctl unit running on the device can then via gateway provide data to the api cloud that in turn just routes the messages to telegram server as bot. Bots can be part of dedicated group where the users (who wished to be informed) can tune in just by being a part of the group.


# `main` branch is not the root
------

Keep this branch open and empty. We have 2 separate branches named x86_64_dev and armv6l_dev that form the base branch. Each of the base dev branches are meant to signify the code on `various hardware platforms`
1. x86_64 : is a branch for hosting on the cloud. - x86_64
2. armv6l : is branch for hosting code running the IoT device. - armv6l

These branches arent expected merge any further as they signify distinct hardware platforms. More so they would also have distinct CI CD pipelines.
