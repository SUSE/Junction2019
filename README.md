# Open Open City at Junction 2019

__Welcome to Junction 2019!__

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

## Download

Please use and utilize as much SUSE software as possible. Our  releases can be 
downloaded -after a registration- at: https://www.suse.com/download-linux/

We will upgrade your license to a 1 year license. The only requirement for that
is that you specify __Junction2019__ as the company in the registration form.

![download reg form](/static/SUSE_reg_form.png)

## Developer Platforms

You may use any ways to develop and deploy your solution, so that our judges can
evaluate your work on Sunday. However we do offer some options, if you feel like
trying them out:

* OpenFaaS Cloud for "serverless" solutions
* OpenFaaS - for extending uMEC platform capabilities
* SUSE CAP - for cloud native development (subject to availability)

We will walk you through and provide information on how to get access to the 
above mentioned systems shortly after Junction's kick-off. 

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

The API allows to read [RuuviTags](https://ruuvi.com/ruuvitag-specs) and get 
temperature, air pressure and humidity information from various points of the city. 

__API endpoint: http://micromec.org:32001__

Sources: https://github.com/rulex/ruuvimec

### uMEC Detection API

The API allows object detections in images using a Tensorflow model.

__API endpoint: http://micromec.org:32002__

Usage: uMEC Detection API How-to published shortly

Sample codes at GitHub:
* [Selfie app in Node.js](https://github.com/feri/selfie)
* [Selfie app in HTML / JS](https://github.com/feri/selfie2)

### uMEC Lights API

Allows to turn lights ON and OFF in the Open Open City.

__API endpoint and usage info: http://micromec.org:32003__

Sources: https://github.com/agrasagar/ledpi4

### uMEC Camera API

Allows to take snapshots from the cameras deployed in the Open Open City.

__API endpoint and usage info: http://micromec.org:32004__

Sources: https://github.com/agrasagar/campi4

## Contact Us

Please do reach out to us, if you have questions, doubts, or even cool new ideas.
We will be at your disposal throughout the hackathon. You can find us at the 
SUSE stand or just ping us online via Discord: 

[challenge-suse channel](https://discordapp.com/channels/622013195867127828/633980829923672064) 

### Have a lot of fun... Happy Hacking!


