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

``` shell
git clone git@gitlab.com:vodacomsa/digital-engineering/digital-channels/vodacom-cloud-app/my-vodacom-mono.git
```

```shell
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

## Setting Up an Android Emulator for Local Testing

Follow these steps to set up an Android emulator on your machine for testing purposes:

1. **Download and Install Android Studio**

   Download and install [Android Studio](https://developer.android.com/studio).

2. **Verify Virtual Device Manager Capabilities**

   Ensure that Android Studio has Virtual Device Manager capabilities.

3. **Launch Android Studio and Open Virtual Device Manager**

   - Open Android Studio.
   - Navigate to **Virtual Device Manager**.

   ![Virtual Device Manager](https://github.com/user-attachments/assets/988273e4-854e-4b1d-a431-aff8caa14339)

4. **Create a Virtual Device**

   - Click on **Create New Virtual Device**.
   - Follow the prompts to configure your virtual device.

5. **Install VodaPay Test APK Packages**

   - Download the VodaPay test APK packages.
   - Install the APK packages on your virtual device for testing.

6. **Use Test Data for Authentication**

   Use the provided test data for authentication on the authentication screen.

   ![image](https://github.com/user-attachments/assets/286c3a5b-537a-4625-bfa7-097eca4d9cb7)


8. **Find the Test Widget Component**

   - In the VodaPay Test App, locate the Test Widget component at the bottom.
   - Use the following values as your inputs:
     - **src**: `http://localhost:3000/mvwidget`
     - **height**: `320`
   - Ensure your project is running from step 1.

9. **Click Submit and Test Your Widget Locally**

   Click **Submit** and verify that your widget is functioning correctly on the emulator.

## Additional Instructions for iOS Testing

Don’t bother yourself with trying to debug with your iOS device. It doesn’t work; it’s proven: Don’t try to be a hero. For more details, refer to the [VodaPay Container Testing Guide](https://vodacom.atlassian.net/wiki/spaces/PV/pages/315622675/PRD+162+MVA+VodaPay+Container#Testing-Widget).

1. **Install Xcode**

   Download and install [Xcode](https://developer.apple.com/xcode/) from the Mac App Store.

2. **Open Simulator**

   - Once Xcode is open, navigate to the Xcode menu in the menu bar.
   - Select **Open Developer Tool > Simulator**.
   - Alternatively, you can search for Simulator using Spotlight.

3. **Select iOS Device**

   - In the Simulator window, you’ll see a list of available iOS devices.
   - Choose the device you want to simulate by clicking on it.
   - You can simulate various iPhone and iPad models with different iOS versions.

4. **Launch Your App**

   - Perform steps 7 and 8 above to test your widget on the iOS Simulator.

