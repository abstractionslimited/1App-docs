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


- Clone the application using:
    -  **SSH**

```
git clone git@gitlab.com:vodacomsa/digital-engineering/digital-channels/vodacom-cloud-app/my-vodacom-mono.git
```
      -  or **HTTPS**
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


The main container will listen on port `4000` and the widget will listen on port `3000`. Once you reach this point, you have successfully cloned and set up the project for development.

### Successful launch

![image](https://github.com/user-attachments/assets/332fb862-5abf-44eb-bd84-c07829987954)


## Setting up your browser for port-forwarding

Follow these steps to set up port-forwarding in your browser.

1. Access inspect tools in your browser.
2. When using Chrome browser, you can use the following link: [chrome://inspect/#devices](chrome://inspect/#devices)

    - You will see the following:

        ![image](https://github.com/user-attachments/assets/cb503c78-128e-43bd-915a-1a1393c32395)
      
3. Click on port forwarding, and set the following ports:
**Enable port forwarding** as well

   ![image](https://github.com/user-attachments/assets/331b5510-7f4b-491f-bea9-8149ed82d496)

4. After setting up the above, click done and set up your emulator.

