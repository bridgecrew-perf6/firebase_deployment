# firebase_deployment

1: Create new repo on github

2: git clone repo HTTPS_link
Clone it on the system

3: ng new App_name
Create new angular 13 app

4: Create firebase account -> create a project
-project name: firebaseApp
-unique name: fir-app-a8f9f
unique name is created by firebase automatically so we can target your project from cli
-disable Google Analytics for this project: because this is just for practice.

5: npm i -g firebase-tools
6: firebase login --interactive

7: firebase init
Command
? Are you ready to proceed? **Yes**
Command
? Which Firebase features do you want to set up for this directory? Press Space to select features, then Enter to confirm your choices. Hosting: Configure files for Fir
ebase Hosting and (optionally) **set up GitHub Action deploys**
Command
? Please select an option: **Use an existing project**
Command
? Select a default Firebase project for this directory: fir-app-a8f9f **(firebaseApp)**
i Using project fir-app-a8f9f (firebaseApp)
Command
? What do you want to use as your public directory? **public**
Command
? Configure as a single-page app (rewrite all urls to /index.html)? **No**
Command
? Set up automatic builds and deploys with GitHub? **Yes**
Command
? For which GitHub repository would you like to set up a GitHub workflow? (format: user/repository) **fawad4bros/firebase_deployment**
Command
? Set up the workflow to run a build script before every deploy? **Yes**
Command
? What script should be run before every deploy? (npm ci && npm run build)**press Enter**
? What script should be run before every deploy? npm ci && npm run build
Command
? Set up automatic deployment to your site's live channel when a PR is merged? **Yes**
Command
? What is the name of the GitHub branch associated with your site's live channel? **main**
8 Changes in code
8.1 Delete index.html file from public folder
8.2 Edit firebase.json file
{
"hosting": {
"public": "docs",
"ignore": ["firebase.json", "**/.*", "**/node_modules/**"],
"rewrites": [{
"source": "\*\*",
"destination": "/index.html"
}]}}
8.3 outputPath value in the angular.json should be docs and public value in the firebase.json should be docs
9: ng build
10: firebase deploy
