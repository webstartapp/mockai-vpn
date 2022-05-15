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
The current setting in **mockai-config.json** gives readOnly access to demo account https://mockatee.com/brand/ipc . 
the localEndpoint is not running exapmple, as with the demo account there is no allowed connection outside. The real application should set here a real - active endpoint so the local MockAI apllication can work properly. 

If your project doesn't require access token you can ommit the "**accessToken***". adding there anything different from access token will result in falure, as the MockAI will try to link the access token to proper version.
