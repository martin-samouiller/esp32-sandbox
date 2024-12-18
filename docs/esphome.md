# ESPHome check 

Installation instructions:
https://esphome.io/guides/installing_esphome


## Mac

Python installation:

```
brew install python
python3 -m venv /Users/{user}/esp/esphome
source /Users/{user}/esp/esphome/bin/activate
```

Esphome installation:

```
pip3 install wheel
pip3 install esphome
```

Check installation:

```
esphome --version
```

Create a new project:

```
esphome wizard automated_greenhouse.yaml
```

Select board:
upesy_wroom - uPesy ESP32 Wroom DevKit [board](https://www.upesy.fr/products/upesy-esp32-wroom-devkit-board)

setup the DHT22 sensor:

```
esphome run automated_greenhouse.yaml
```

[esphome home assistant](assets/images/homeassistant/esphome.png)



Check the dashboard:

```
pip install tornado esptool
mkdir config
esphome dashboard config
```

Open the dashboard: http://localhost:6052



FAQ with DHT22:

Problem:

```
[22:02:06][W][dht:175]: Requesting data from DHT failed!
[22:02:06][W][dht:060]: Invalid readings! Please check your wiring (pull-up resistor, pin number) and consider manually specifying the DHT model using the model option.
[22:02:06][D][sensor:094]: 'Greenhouse Temperature': Sending state nan °C with 1 decimals of accuracy
[22:02:06][D][sensor:094]: 'Greenhouse Humidity': Sending state nan % with 0 decimals of accuracy
[22:02:06][W][component:157]: Component dht.sensor set Warning flag: unspecified
```

Switch to 

model: **DHT22_TYPE2**