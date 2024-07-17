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

```
git clone git@gitlab.com:vodacomsa/digital-engineering/digital-channels/vodacom-cloud-app/my-vodacom-mono.git
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
   -  Update

## Running the application

To run the application please run the following command.

```
git clone https://bitbucket.orbit.prod.vodacom.co.za/scm/vca/my-vodacom-mono.git

cd my-vodacom-mono

npm install

npm run build

npm run dev

```



The main container will listen on port 4000 and the widget will listen on port 3000. Once you reach this point, you have successfully cloned and set up the project for development.

##

Follow the steps mentioned below to run the application in Docker.
