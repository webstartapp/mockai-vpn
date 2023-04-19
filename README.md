# mockai-vpn
MockAI-VPN is standalone nodeJS application, that creates bridge between the mockatee.com application and service behind closed network. 

## Content
MockAI-VPN has only two files. The main application file named **mockai-vpn.js** and configuration file **mockai-config.json** .

### mockai-vpn.js
Main application file is build on nodeJS and compatible with version 14 and higher, but it has no other dependencies. 

You can run it from windows, mac or linux terminal with just calling "***node mockai-vpn.js***" 

### mockai-config.json
**mockai-config.json** is an configuration file holding four fields: 

    "brandEndpoint": "https://ipc.mockatee.com"
    "localEndpoint": "http://localhost:9999"
    "accessToken": "iyymwgdpmclvbehmainxelvazlwogk"
    "port": "3001"

***brandEndpoint***: Field is required should direct to the mockatee api to the subdomain of connected project.
***localEndpoint***: Is the local application endpoint, that isn't accesible from the internet, but only from internal network. The local endpoint can differ from the one you have saved as project domain in dashboard https://mockatee.com/brand , as ***localEndpoint** values overrides it. 
***accessToken*** is the security measure defined by the project dashboard. 
***port*** het you chose what port should the **mockai-vpn.js** application connect and listen.

## Example of use
The current setting in **mockai-config.json** gives readOnly access to demo account https://mockatee.com/project/ipc . 

Usualy will mockAI try to reach the endpoint "localEndpoint". as long as this port will be unreachable, the Mockai will serve mock data as stated in **ipc** exapmple. 

Access token is ment to secure your application but it can be also used to define with what version of project you wanna work. 
so if the project doesn't require access token you can ommit the "**accessToken***" field, but that way it will serve only the current version.
