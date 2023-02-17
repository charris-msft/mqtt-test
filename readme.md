# mqtt-test

## To build and run the containers locally

```powershell
cd /mqtt-broker

docker build -t js/mqtt-broker . ; ./Dockerrun.ps1
```

```powershell
cd /mqtt-simulator

docker build -t js/mqtt-simulator . ; ./Dockerrun.ps1
```

## Use Mosquitto client to publish and subscribe

Using Ubuntu via bash/wsl

```bash
sudo apt install mosquitto-clients

# subscribe to all freezer events
mosquitto_sub -h localhost -p 1883 -u sensor123 -P sensor123 -t freezer/+

# publish
mosquitto_pub -h localhost -p 1883 -u sensor123 -P sensor123 -t 'freezer/my_temp' -m '32'

```
