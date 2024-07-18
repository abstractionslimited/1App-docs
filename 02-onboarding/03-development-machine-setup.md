# Development Environment

All developers should have [tools](./01-tools) mentioned here installed on their machine.

## Git command-line configuration

Make sure you have configured your user with Git. This information will be used by Git.

```
git config --global user.name "Your Fullname"
git config --global user.email "Your Xebia Email"
```

Windows users should use Git bash for better command-line experience.

If you are not well-versed with Git then you can read the [tutorial](https://github.com/shekhargulati/git-the-missing-tutorial).

## Connecting to Github using SSH

Refer to this [link](https://docs.github.com/en/free-pro-team@latest/github/authenticating-to-github/connecting-to-github-with-ssh) to setup SSH for your Github account.

## Clone the application

Clone the application using the following command.


- Clone the application using **SSH** or **HTTPS**

```
git clone git@gitlab.com:vodacomsa/digital-engineering/digital-channels/vodacom-cloud-app/my-vodacom-mono.git
```

```
git clone https://gitlab.com/vodacomsa/digital-engineering/digital-channels/vodacom-cloud-app/my-vodacom-mono.git
```


## Setup environments

1. Navigate to `my-vodacom-app/vite.config.ts` and replace `/oath2` object with the following:
   

```json
  '/oauth2': {
        target: 'https://appqa.vodacom.co.za',
        changeOrigin: true,
        secure: false
      }
```



2. Navigate to `apps/my-vodacom-widget/src/environments.js` and update the following under `Local` environment

   
   -  update `vpayParentOrigin`  to: `vpayParentOrigin: 'http://vodapay-m.test4.vfs.africa'`
  
     
3. Navigate to `apps/my-vodacom-app/src/environments.js` and uncomment the code below, this is useful for testing MVA container using the browser:


  ```
   useBrowser: {
      msisdn: '27721506801',
      password: 'Testing1'
    }
```
## Running the application

To run the application please run the following command.

```
cd my-vodacom-mono
```

```
npm install
```

```
npm run build
```

```
npm run dev
```


The main container will listen on port 4000 and the widget will listen on port 3000. Once you reach this point, you have successfully cloned and set up the project for development.

## Configs

- From my understanding when you run the stable TC build for x-config, it will overwrite the master build as well, so just need to run the build again afterward

[Team City](https://teamcity.orbit.prod.vodacom.co.za/project/VodacomMobileBuilds_MyVodacomXConfig?mode=builds)

### AWS 


https://us-east-1.console.aws.amazon.com/cloudfront/v4/home?region=us-east-1#/distributions/E1OZMRPJ97D006
 
[14:58] Bitzer Havenga, Vodacom (External)
mva-static.nonprod.vodacom.co.za
 
[15:00] Bitzer Havenga, Vodacom (External)
Then from there, you can click on Invalidations tab, click on last Invalidations, copy to new, and then just edit object paths as needed
 

Follow the steps mentioned below to run the application in Docker.
