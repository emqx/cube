# Quick Start

EMQ X Edge connects to Cube platform through  [emqx-cube](http://github.com/emqx/emqx-cube)  plug-in and communicates management instructions. The steps of enabling preparation and operation are as follows:

1. The emqx-edge version is greater than or equal to v3.1-rc.3 [click to download](https://www.emqx.io/downloads/emq/edge?OsType=Raspberry%20Pi#download)

2. Edge's network environment can establish communication links with [cube.emqx.io:1883](cube.emqx.io:1883)

3. Register [EMQ account](https://www.emqx.io/account?Tab=register) and create a new edge message server in [Cube](https://cube.emqx.io)

4. Fill in the configuration in Cube on Edge and start the emqx-cube plug-in

> Note: It will not affect the normal use of other Edge features without the connection of cube.


## Registration and Login



[Cube Open Platform](https://cube.emqx.io) uses [EMQ Account](https://www.emqx.io/account?Tab=register) to authenticate login. If you have not registered with the EMQ official website, please go to the registration activation.

<img src="../_assets/image-20190418174950438.png" class= "medium-size">






## Create edge



On the **Edge Message Server** page, click the New button to type in the server name and description to create the Edge Message Server.

![image-20190418180127980](../_assets/image-20190418180127980.png)





## Get the startup configuration



When a new Edge Message Server is created, the information needed to access Cube can be obtained from the Edge Message Server **Details Page**:

![image-20190418180541116](../_assets/image-20190418180541116.png)



Open the Edge emqx-cube plug-in configuration file `etc/plugins/emqx_storm.conf`, with the following modifications:

```bash
# Cube connection adress，default cube.emqx.io:1883
cube.address = cube.emqx.io:1883

# Authentication username, Username information in the usage details
cube.username = 40e02ab0-5b68-11e9-ac3b-b1515a08538d

# Authentication password, password information in the usage details
cube.password = b67aa008-c7f8-4b70-b06c-5cdba92f3ff7
```



## Start and connect



If the configuration is correct, Edge will automatically establish a connection with Cube after successful start-up. At this time, the state of the relevant server in Cube will be set to **online**. Click on the relevant Tab page to get the corresponding operation indicators.



![image-20190418180815672](../_assets/image-20190418180815672.png)





So far, you have successfully accessed Edge to Cube.



