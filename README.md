create the app:

oc new-app https://github.com/samueltauil/mqtt --strategy=docker


add volumes:

add log volume if needed to persist the logs
oc volume dc/mqtt --add --name=mqtt-log --type=emptyDir --mount-path=/mosquitto/log

oc volume dc/mqtt --add --name=mqtt-data --type=emptyDir --mount-path=/mosquitto/data

create the service:
oc create -f service.yaml

delete the app:

oc delete all -n app=mqtt

