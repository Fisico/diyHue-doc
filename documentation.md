# diyHue - A Hue Bridge Emulator
[![Discourse](https://img.shields.io/discourse/users?server=https%3A%2F%2Fdiyhue.discourse.group)](https://diyhue.discourse.group) [![JoinSlack](https://img.shields.io/badge/Join%20us-on%20Slack-green.svg)](https://join.slack.com/t/diyhue/shared_invite/enQtNzAwNDE1NDY2MzQxLTljNGMwZmE0OWRhNDIwM2FjOGM1ZTcxNjNmYjc5ZmE3MjZlNmNjMmUzYmRkZjhhOGNjOTc4NzA0MGVkYzE2NWM)  [![Build Status](https://github.com/diyhue/diyHue/workflows/diyHue%20CI%20Build/badge.svg)](https://github.com/diyhue/diyHue/actions)
[![DockerPulls](https://img.shields.io/docker/pulls/diyhue/core.svg)](https://hub.docker.com/r/diyhue/core/)
[![CommitActivity](https://img.shields.io/github/commit-activity/y/diyhue/diyhue.svg)](https://github.com/diyhue/diyHue/commits/master)


<br></br>
![diyHueLogo](https://diyhue.org/cdn/img/diyHue-Logo.png)

<br></br>


diyHue provides a Ecosystem for several smart home solutions, eliminating the need for vendor specific bridges and hardware.
It is Open Source and written in Python, you are now able to import and control all your lights and sensors into one system.

Lightweight and resource friendly, to run on small devices like the RPi .... 24/7

The best part? No cloud connection by design!

Enjoy your diyHue enlighted home.


![diyHue ecosystem](https://raw.githubusercontent.com/diyhue/diyhue.github.io/master/assets/images/hue-map.png)




## Requirements

- A system that can run Docker images 24/7 (Raspberry Pi for example)
- Python 3
- Python modules: ws4py, requests, astral, paho-mqtt [see requirements.txt](./requirements.txt)

[Recommendation - minimal setup](./recommendation.md)

[Working diyHue features](./Workingfeatures.md)

# Installation

2021 Phillips released a huge update that required a reverse engineering of the Phillips Hue Bridge and a complete rewrite of the diyHue Bridge. In order to use DiyHue with the latest Hue App and products, you have to upgrade to the newest diyHue Version. Old configs are not upgradeable.


- Connect to 
- Raspberry Pi setup:
  - ```apt-get update```
  - ```apt-get upgrade```
  - Download Docker installation script ```curl -fsSL https://get.docker.com -o get-docker.sh```
  - Install Docker ```sudo sh get-docker.sh```
  - Install Python 3 pip ```sudo apt install python3-pip```
  - Install Docker compose ```sudo pip3 install docker-compose```
    Create DiyHue config directory```mkdir /opt/hue-emulator/config```
  - Navigate to Docker folder ```cd /etc/docker/```
  - Create Docker compose file ```sudo nano docker-compose.yml```
  - Paste Docker-compose.yaml [template](template.md)
  - Save Docker-compose.yml with ```control + o``` -> ```enter``` ->  ```control + x```
  - Start Docker container ```sudo docker-compose up -d```
  - Open a browser and type the IP-Address of your Raspberry and login with ```admin@diyhue.org``` and ```changeme```
  - Add lights via webinterface or app
  - Have fun with diyHue


## Updating DiyHue 
Steps to update to the latest version of diyHue, the config keeps unchanged:
- Stop Docker container ```sudo docker stop "diyhue"```
- Remove Docker container ```sudo docker rm -f diyhue```
- ```sudo docker system prune -af```
- Navigate to docker directory ```cd /etc/docker/```
- Start new container ```sudo docker-compose up -d```

## Start, Stop, Restart
- ```sudo docker start "diyhue"```
- ```sudo docker stop "diyhue"```
- ```sudo docker restart "diyhue"```



<br></br>
# Get Help  
If you need help with diyHue you can get support from other users, aswell as the maintainer.

## Logs
Before opening an issue please locate the errorlog with ```sudo docker logs --tail 50 -f diyhue``` and paste a pastebin.com link into the issue.

## Slack [![JoinSlack](https://img.shields.io/badge/Join%20us-on%20Slack-green.svg)](https://join.slack.com/t/diyhue/shared_invite/enQtNzAwNDE1NDY2MzQxLTljNGMwZmE0OWRhNDIwM2FjOGM1ZTcxNjNmYjc5ZmE3MjZlNmNjMmUzYmRkZjhhOGNjOTc4NzA0MGVkYzE2NWM) [![SlackStatus](https://slackinvite.squishedmooo.com/badge.svg?colorB=8ebc06)](https://slackinvite.squishedmooo.com/)
Use Slack for a general chat or fast live support. 

However: Since Slack is faster at providing live support but not as good when it comes to save and show known issues, we kindly ask you to open a topic at our discourse group. This will provide help for others in the future.

## Discourse [![Discourse](https://img.shields.io/discourse/users?server=https%3A%2F%2Fdiyhue.discourse.group)](https://diyhue.discourse.group)

Our board might already have your fix and answer ready. Have a look!


> General note:
> Please provide some logs to make it easier for all of us. Enable Debug by manually starting diyHue with additional `--debug true` argument.


  
Please post on our [Slack team](https://slackinvite.squishedmooo.com/) any other device/application that you find to work with this emulator.
  

## Documentation

All documentation and instructions can be found over at [diyhue.readthedocs.io](https://diyhue.readthedocs.io/)


## Support us

diyHue is open source and maintained by volunteers in their free time. You are welcome to contribute and become a recognised member of the diyHue community.
Feel free to add pullrequests and commits to our beta branch.
If you are experienced in 
- Webdesign
- Python
- Arduino/C++
- Coding in general

We highly appreciate your support, making diyHue even better!
<br></br>
## Coffee

diyHue is and will be free to use. However it does take a lot of time to maintain the code etc etc.

Long story short.... you can support us at Ko-Fi

[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/R6R54Y1LF)

Thank you very much!

## Credits

- Ben ([@cheesemarathon](https://github.com/cheesemarathon)) All fancy github integrations
- [Stephan van Rooij](https://github.com/svrooij) - zigbee2mqtt integration
- [@avinashraja98](https://github.com/avinashraja98) - Hue Entertainment server
- Federico Zivolo ([@FezVrasta](https://github.com/FezVrasta)) Internal WebGUI
- [@J3n50m4t](https://github.com/J3n50m4t) - Yeelight integration
- Martin Černý ([@mcer12](https://github.com/mcer12)) - Yeelight color bulb
- probonopd https://github.com/probonopd/ESP8266HueEmulator
- sidoh https://github.com/sidoh/esp8266_milight_hub
- StefanBruens https://github.com/StefanBruens/ESP8266_new_pwm
- Cédric @ticed35 for linkbutton implementation
- [@cheesemarathon](https://github.com/cheesemarathon) - Help with Docker images
- [@Mevel](https://github.com/Mevel) - 433Mhz devices
- [@Nikfinn99](https://github.com/Nikfinn99) - PCB designs
- [@crankyoldgit](https://github.com/crankyoldgit) - IR Remote library


## Additional Projects and Ideas

Hue living color light project for 3D printing: [Thingiverse 2773413](https://www.thingiverse.com/thing:2773413)


## License

[![license](https://img.shields.io/badge/license-GPLv3%2FApache%202.0%2FCC%20BY--SA%204.0-blue.svg)](https://github.com/diyhue/diyHue/blob/master/LICENSE.md)
