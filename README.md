# Oviyam 2 - Docker

## Build

```bash
docker build -t oviyam:2.7.4
```

## Run

```bash
docker run -it --rm -p 80:8080 -p 1025:1025 -v /oviyam:/usr/local/tomcat/work oviyam:2.7.4
```

Or in order to run within the same docker network as DCM4CHEE

```bash
docker run -it  --network=dcm4chee_default --rm -p 80:8080 -p 1025:1025 -v /oviyam:/usr/local/tomcat/work oviyam:2.7.4
```

- **-p 80:8080** Maps host port 80 to port 8080 in the container
- **-p 1025:1025** Port for DICOM Listener
- **-v /oviyam:/usr/local/tomcat/work** Maps the directory _/oviyam_ on the host system to _/usr/local/tomcat/work_ to allow configurations to be retained if Docker instance is teardown

Navigate to http://localhost
