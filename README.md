# MQTT Benchmark Client for Python

## Install

* create binding on amq.topic with * key towards "test" queue
* Unistall and reinstall at every dev step

```
python setup.py install
pip uninstall mqtt-benchmark
```

## Generic Publish

```sh
mqtt-bench publish --host 192.168.99.100 --port 1883 --topic "test" --qos 0 --thread-num 10 --publish-num 50 --message "I'm test" --username hub-iot --password hub-iot
```

## Publish to mqtt bridge

```sh
mqtt-bench publish --host 127.0.0.1 --port 1883 --topic "test" --qos 0 --thread-num 10 --publish-num 10 --amplitude 5000 --message '{"senml" : [{"bn":"urn:sosa:Sensor:00sfsf08","n":"incoming","u":"count","v":1200}]}' --senml --sensors urn:sosa:Sensor:diatomicAA/incoming urn:sosa:Sensor:diatomicBB/outgoing
```

Please note that sensors have to be declared with the form `sensor_id/measure_type`.

## Subscribe

```sh
$ mqtt-bench subscribe --host 192.168.99.100 --port 1883 --topic "test" --qos 0
```
