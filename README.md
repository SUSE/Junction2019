# Open Open City at Junction 2019

Welcome to Junction 2019! 

On this page (and in this repository) we would like to provide useful info
for SUSE's [Open Open City challenge](https://2019.hackjunction.com/challenges/open-open-city).

## Overview

We are offering a set of uMEC APIs to "interact" with parts of our imaginary city. 

![city picture](/static/city01.jpg)

In this city we have an infrastrcuture that let's 3rd party apps
to access data and even extend the circle of services. All these services are 
meant to help and improve the quality of life of the citizens in the city.

We have deployed uMEC gateways in the city. These gateways are represented by
Raspberry Pis that are connected into a cluster. We use k3s for clustering and 
orchestrating all the containerized apps that provide our open APIs.

## uMEC APIs

uMEC is meant to enable new functionalities and business models on the network 
edge. Running applications on the network edge mean: 
 
* lower latency for end users
* less load on the network itself 
* improved security and privacy since data will not be moved to a data centre.
 
The APIs we provide today are in __early stage__ and not yet compliant with 
the specifications of [ETSI MEC](https://www.etsi.org/technologies/multi-access-edge-computing).

### uMEC MEC011 Application Enablement API

The implementation follows the [MEC011 specifications](https://forge.etsi.org/swagger/ui/?url=https://forge.etsi.org/gitlab/mec/gs011-app-enablement-api/raw/master/Mp1.yaml),
however as stated above, we may not be fully compliant yet.

__API endpoint: http://micromec.org:32000__

Sources: https://gerrit.akraino.org/r/gitweb?p=umec.git;a=tree;f=mec11;hb=HEAD

### uMEC Sensors API

The API allows to read [RuuviTags](https://ruuvi.com/ruuvitag-specs) and get temperature, air pressure and humidity information from various points of the city. 

__API endpoint: http://micromec.org:32001__

Sources: https://github.com/rulex/ruuvimec

### uMEC Detection API

The API allows object detections in images using a Tensorflow model.

__API endpoint: http://micromec.org:32002__

Usage: <todo> uMEC Detection API How-to

### uMEC Lights API

Allows to turn lights ON and OFF in the Open Open City.

__API endpoint and usage info: http://micromec.org:32003__

Sources: https://github.com/agrasagar/ledpi4

### uMEC Camera API

Allows to take snapshots from the cameras deployed in the Open Open City.

__API endpoint and usage info: http://micromec.org:32004__

Sources: https://github.com/agrasagar/campi4
