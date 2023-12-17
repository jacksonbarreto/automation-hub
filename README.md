# automation-hub

## Instructions for creating a new automation

+ Expose the automation in a given port
+ The automation must have a hostname
+ Add the automation to the same network as the hub

```yaml
networks:
  service-hub:
    name: service-hub
    external: true
```

+ The automation must handle requests with the URL path being the same as the hostname: `/<automation_name>/<automation_name>/`

+ In the hub, the name of the service can be whatever you want, but the port and the hostname must be the same as the one exposed in the automation

```yaml
services:
  automation:
    image: <image>
    container_name: <container_name>
    hostname: <hostname>
    networks:
    service-hub:
        name: service-hub
        external: true
```
