# MIB Controller Guide   



### MIB Controller App Install   

1) Download and install the MIB Controller APK to the device where the MIB Miner APK is already installed.   

<img width="200" src="https://user-images.githubusercontent.com/36949510/76055038-dfff6f00-5fb5-11ea-9d37-ba72667a9ac7.png"></img><br/>


2) Enter your mining ID.   
3) Click ‘Start Miner’ button to start mining.   

It will take about 1 or 2 minutes to successfully register on the monitoring API server.   
You will see the registration number from Image B once the registration is completed.   


<img width="450" src="https://user-images.githubusercontent.com/36949510/76056283-8731d580-5fb9-11ea-8e56-3d7cd0793408.png"></img><br/>

The number next to “MIB Miner” indicates that your registration is done.   
The number shows your device control number.   
Our recommendation is that you put the label with the corresponding number on that device.   
   
   ---
   
   
### MIB Miner List   

You can download the entire list of registered miners. You can check the availability, the current hash, and the connected pool of each miner device.   

##### A) Request device status   
*https://mib-api.mibcoin.io/miner_list.php? id=[Miner ID]&ip=[Miner IP]&type=[ ] or [live_list] or [stop_list]*   
* **Miner ID** : The ID used in the MIB Controller.   
* **Miner IP** : Shows the IP of the miner.   
* **Limit and offset** : Add the following parameter with a specified number which you want for the output result. It will return the whole list if Limit and Offset are not specified. ```&offset=1&limit=50```   
* **Type** :   
  Loads miners that are separated by its status (working / not working).   
  * Miners that has not updated for 5 minutes or more are considered ‘not working’   
  * Returns a list of devices that has updated in 5 minutes by &type=live_list : lastupdate.   
  * Returns a list of devicees that has not updated for more than 5 minutes by &type=stop_list : lastupdate.   
  * Returns a list of total if &type= or the parameter is not provided.   


##### B) Result   
```{idx=49,id="test_miner_id",work_name="test_Worker48",hash_rate="75.85",pool_name="K01-MIB",lastupdate="2020-02-18 13:42:07"}```

* **Receive**   
  * idx : Device number,   
  * id : Registered Miner ID,   
  * work_name : Worker Name for the device,   
  * hash_rate : Hash status ,   
  * pool_name : Currently connected pool,   
  * lastupdate : Last updated time   

  B-1) A device with no hash_rate indicates that it has stopped working.   
  B-2) The device has not been registered successfully if it is not on the list.   
  B-3) Hash_rate will be reset by the API if the device is not responding for 5 or more minutes.   
   
   
---   

  
### Miner Start & Stop   

You can request a particular device to start or stop its mining.   

*https://mib-api.mibcoin.io/miner_action.php? id=[id]&work_name=[worker name]&action=[action]&pincode=[pin code]*   

* **[id]** : Registered Miner ID,   
* **[miner id]** : Mining ID given for the device   
* **[worker name]** : Worker name given for the device   
* **[action]** : either start or stop   
* **[pincode]** : pincode is an additional password for your Miner ID registration   

*	Result : {msg="success"} : Success   

Too many request to the API might lead to additional cost.   
Limited to three per second.   

   
   
   
   
# Instruction for Controller Monitoring Application   

The MIB Miner Controller Monitoring Application allows you to monitor the status of miners and work on them.   


#### 1. Download and install MIB_Monitoring.apk   

#### 2. Run the application and follow the steps:   
* Enter your Miner ID   
* Enter the Pincode for the Miner ID   
* Click the add button   

#### 3. Monitoring and controlling the status of miners   
*The controlling process usually takes about 1-2 minutes*   
* You can control each added miners by their ID   
* There are 'start mining' and 'exit' commands for all connected miners   
* You can also use the above commands for every single miners   
* Indicates 'count' for each working process   

