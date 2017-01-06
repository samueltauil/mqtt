create the app:
```
oc new-app https://github.com/samueltauil/mqtt --strategy=docker
```

add volumes:
add log volume if needed to persist the logs
```
oc volume dc/mqtt --add --name=mqtt-log --type=emptyDir --mount-path=/mosquitto/log
```
```
oc volume dc/mqtt --add --name=mqtt-data --type=emptyDir --mount-path=/mosquitto/data```
```

create the service:
```
oc create -f service.yaml
```

port forward to access:
```
oc port-forward <podname> 1883:1883
```

install mqtt-cli:
```
sudo npm install mqtt-cli -g
```
send a message:
```
mqtt-cli 127.0.0.1:1883 test/mqtt "hi to openshift"
```

delete the app:
```
oc delete all -n app=mqtt
```
