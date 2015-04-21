> CPU1212C as DP-slave to CPU300 as DP-master

[create project in TIA Portal](#r1)  
[create project in STEP7](#r2)  

# <a id="r0"></a> CPU1212C with CM1242-5 as DP-slave

## <a id="r1"></a> Create project in TIA Portal

* go to devices and network,
* select 'network view'
* from hardware catalog / controllers / cpu add cpu1212C
  ![alt text](Images/addCpu.png?raw=true "add cpu")


* select 'device view'
* from hardware catalog / communication modules / profibus add CM1242-5 to the left side off the cpu

  ![alt text](Images/deviceView.png?raw=true "")
* select CM1242-5
* go to tab properties
* go to DP interface / profibus address
* create subnet and add profibus address / speed
  ![alt text](Images/profibusAddress.png?raw=true "")
* got to DP interface / operating mode
* select DP - slave and configure the transfer areas
  ![alt text](Images/OperatingMode.png?raw=true "")
[Back](#r0)

## <a id="r2"></a> Create project in STEP7

* insert simatic-300 station
* open hardware
* from hardware catalog / simatic 300 / rack-300 -> add rail
* from hardware catalog / simatic 300 / cpu 300 -> add cpu in slot 2
* X1 MPI/DP / properties / select mode DP
![alt text](Images/Step7_hw1.png?raw=true "")
* create subnet and add profibus address / speed
![alt text](Images/Step7_hw2.png?raw=true "")
* Menu options / install GSD-file -> install the 'si18e18.gsd'
* Hardware catalog / Pofibus DP / Additional Fiels Devices / S71200 / CM1242-5 -> connect to the dp-master add profibus slave address select profibus master line
![alt text](Images/Step7_hw3.png?raw=true "")
* set the inputs and outputs, like it was configured in TiaPortal, for this example it is 20bytes inputs and 20 bytes output.  Take the same addresse as it was configures in the CM1242.  Check also the parameter consistency.

  ![alt text](Images/Step7_hw4.png?raw=true "")

[Back](#r0)
