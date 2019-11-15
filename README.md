#  SUSE Hackerpack for Junction 2019

Fancy hacking on an imaginery city and it's open APIs? Want to extend and offer
some more services? Come and talk to us! We would like to welcome you with our 
friends from Nokia at the Open Open City challenge.

## Downloads, Tools

Start with the essentials: https://www.suse.com/download-linux/

Grab your favorite SUSE product and enjoy enterprise grade open source software.
Upon registration you will be able to download and use our products. The 
evaluation license of SUSE Linux Enterprise Server and Containers as A Service 
Platform can be upgraded to a 1 year developer license. 

Just specify __Junction2019__ as the company in the registration form.

![download reg form](/static/SUSE_reg_form.png)

### Dev Platforms

You may use develop and deploy your solution in any way you like.  However we do
offer some options, if you feel like trying them out:

* OpenFaaS Cloud for "serverless" solutions
* OpenFaaS - for extending uMEC platform capabilities
* SUSE CAP - for cloud native development (subject to availability)

We will walk you through and provide information on how to get access to the 
above mentioned systems shortly after Junction's kick-off. 

## Overview

We are offering a set of uMEC APIs to "interact" with parts of our imaginary city. 

![city picture](/static/city01.jpg)

In this city we have an infrastructure that let's 3rd party apps
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

__API endpoint: https://micromec.org:32000__

Sources: https://gerrit.akraino.org/r/gitweb?p=umec.git;a=tree;f=mec11;hb=HEAD

### uMEC Sensors API

The API allows to read [RuuviTags](https://ruuvi.com/ruuvitag-specs) and get 
temperature, air pressure and humidity information from various points of the city. 

__API endpoint: https://micromec.org:32001__

Sources: https://github.com/rulex/ruuvimec

### uMEC Detection API

The API allows object detections in images using a Tensorflow model.

__API endpoint: https://micromec.org:32002__

Sample codes at GitHub:
* [Selfie app in Node.js](https://github.com/feri/selfie)
* [Selfie app in HTML / JS](https://github.com/feri/selfie2)

Demo app in action: 
* https://micromec.org/hack/feri_selfie2

### uMEC Lights API

Allows to turn lights ON and OFF in the Open Open City.

__API endpoint and usage info: https://micromec.org:32003__

Sources: https://github.com/agrasagar/ledpi4

### uMEC Camera API

Allows to take snapshots from the cameras deployed in the Open Open City.

__API endpoint and usage info: https://micromec.org:32004__

Sources: https://github.com/agrasagar/campi4

## Contact Us

Please do reach out to us, if you have questions, doubts, or even cool new ideas.
We will be at your disposal throughout the hackathon. You can find us at the 
SUSE stand or just ping us online via Discord: 

[challenge-suse channel](https://discordapp.com/channels/622013195867127828/633980829923672064) 

### Have a lot of fun... Happy Hacking!


