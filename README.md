add volumes:

oc volume dc/mqtt --add --name=mqtt-config --type=emptyDir --mount-path=/mosquitto/config

oc volume dc/mqtt --add --name=mqtt-log --type=emptyDir --mount-path=/mosquitto/log

oc volume dc/mqtt --add --name=mqtt-data --type=emptyDir --mount-path=/mosquitto/data
