# A demo app that uses Weather Company Data API for IBM Cloud
- - - - -
★Warning★
This sample app is only for Call for Code Challenge 2018 Users.
- - - - -

## Sysmtem Requrement
Any Web Browser

## Preparation
The application requires the following software to be installed locally.
1. Git - [Git](https://git-scm.com/downloads)
2. Node - [Node](https://nodejs.org/en/)
3. IBM Cloud Development Tool - [IBM Cloud CLI](https://console.bluemix.net/docs/cli/reference/ibmcloud/download_cli.html#install_use)
4. Code Editor.  For example [Visual Studio Code](https://code.visualstudio.com/).

# Step
## Clone Repository

1. Create IBM Cloud Account
Prepare IBM Cloud Account.  If you don't have account, access [**here**](https://ibm.biz/BdYzDx
) for **IBM Cloud for Call for Code** registration

2. Clone weather-company-data-demo-c4c repo to your local environment from your terminal using the following command:  
  ```
  git clone https://github.com/ayatokura/weather-company-data-demo-c4c.git
  ```

3. move to `cd weather-company-data-demo-c4c` directry.

## Install dependancy

4. Run **npm install** command.
  ```
  npm install
  ```

## Running the app locally

5. Edit the manifest.yml file and change the <name> and <host> to something unique.
  ```
applications:
- disk_quota: 1024M
  name: <name>
  host: <host>
  command: node app.js
  path: .
  domain: mybluemix.net
  instances: 1
  memory: 256M
  ```
 The host you use will determinate your application URL initially, for example, `<host>.mybluemix.net` 
 
 6. Access to [The Weather Company API Platform Site](https://callforcode.weather.com/) and sign up for The Weather Company API.  For more detail, [here](https://qiita.com/ayatokura/items/39fcdf140dc6567505bb) in Japanese.
 
 7. Add API Key into app.js file.
 ```
 var apiKey = "";
 ```
 
 8. In a terminal, run:
  ```
  node app
  ```
 
 9. You can access the UI by accessing the URL in the browser (For exapmple http://localhost:6001):
   ```
  server starting on http://localhost:6001
   ```
 ## Deploy Web Application to IBM Cloud
 
 10. Log in to IBM Cloud.
  ```
  $ ibmcloud login
  $ ibmcloud target --cf
  ```
 
 11. Deploy Web App to IBM Cloud.
   ```
  $ ibmcloud app push
  ```
  
 12. (Option) If you want to deploy without auto start, run the following command.
 ```
$ ibmcloud login
$ ibmcloud target --cf
$ ibmcloud cf push --no-start
$ ibmcloud cf start [host name]
```

## Access to Published Web Site
13. After deploying to IBM Cloud successfully, the web application will be published at the following URL.
`https://<host>.mybluemix.net`

# Web Application Image
<img src="https://8ingja.bn.files.1drv.com/y4molxlwvbLVOvjR5SLIGSY8tvPP1NHNYfvDoQf5QIHKpPPUAC-v85AYB60lANnbSkMh2VX2Z9KOeJqu8e9o8FX_q5QP3PWJXdQNWi9rj_fdv8q1-gxEV6CP6mqpvIJUc14SE3eaR3qo6knX-S7LtshIdYpi2NXfcuDhkhw9Qv_9zwVbABUkNEEsaB3xIYGUhcsmTv2sGNemMzvcI55RK3WDQ?width=1730&height=1368&cropmode=none" width="600">
