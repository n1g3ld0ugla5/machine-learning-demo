# machine-learning-demo


### Run the crypto-miner
```
docker run -e POOL_URL=donate.v2.xmrig.com:3333 metal3d/xmrig:latest 
```
The Image is publicly-available via Docker Hub:
```
https://hub.docker.com/layers/metal3d/xmrig/latest/images/sha256-c3c27a8b2f6beede6d9c0a7e5b79bb7a7b0002cca40565e7bfd2e447f3a2a628?context=explore)
```
The miner needs to point to a miner pool. We chose ```donate.v2.xmrig.com:3333``` via the below URL:
```
https://xmr.nanopool.org/
```
```
https://miningpoolstats.stream/monero
```



### Set CPU Limits in Linux Host
```
apt update
```
```
apt install cpulimit
```
Because tar does not use much CPU power, we only need to throttle gzip. <br/>
The -e parameter tells cpulimit to search for a process named gzip, and -l specifies the percentage of CPU allowed. <br/>
In our case, cpulimit can only use 10% of the available CPU resources.

```
cpulimit -l 10 -e metal3d/xmrig:latest 
```

<img width="827" alt="Screenshot 2022-09-29 at 07 42 03" src="https://user-images.githubusercontent.com/109959738/193022501-e9ffe3ef-6457-40c7-a04e-d4474ca82ba8.png">



### Monitoring the Miner
```
xmrig -c /root/.xmrig.json -t 1
```

Use ```Htop``` for an Interactive Process Viewer for Linux
```
sudo apt install htop
```
https://www.tecmint.com/htop-linux-process-monitoring/

![Htop-Linux-Process-Monitoring-Tool](https://user-images.githubusercontent.com/109959738/193023181-b2236ae7-4ae5-4376-beb8-a87c1a21ad3c.png)



