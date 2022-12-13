MIT xPro Week 26 - Firebase Cloud Functions

[Cloud functions](https://cloud.google.com/functions) allow you to write and group functions and deploy them for use across different applications. In this video, you’ll deploy a function via Firebase. You could then incorporate this function into another application, without worrying about maintaining it as you would if you had to manage a traditional server.

Note: While Firebase functions offer a free usage tier, Firebase requires that you upgrade your account billing to the “Blaze plan” which will require a payment method. It is unlikely that you will exceed the Firebase free usage tier. Moreover, this is an optional activity and you are not required to use cloud functions.

To use cloud functions, you can:

- Start by creating a directory in your terminal window and installing firebase tools. 

     - Note that, in the video, Dr. Sanchez uses the ```sudo npm install -g firebase-tools``` command. This command will only work for Mac users. If you use Windows or Linux, you can write ```npm install -g firebase-tools```.

- Log in (you will need to authenticate with a Google account).

```firebase login```

- Initialize Firebase.

```firebase init```

- Select functions.

```❯◯ Functions: Configure a Cloud Functions directory and its files```

- Use an existing project: in this case, firebase-practice.

```
=== Functions Setup
Let's create a new codebase for your functions.
A directory corresponding to the codebase will be created in your project
with sample code pre-configured.

See https://firebase.google.com/docs/functions/organize-functions for
more information on organizing your functions using codebases.

Functions can be deployed with firebase deploy.
```

- Select JavaScript and say "no" to linting.

- Install dependencies for cloud functions.

- Open your index.js file, uncomment the code, and save it.

```
const functions = require("firebase-functions");

// // Create and deploy your first functions
// // https://firebase.google.com/docs/functions/get-started

exports.helloWorld = functions.https.onRequest((request, response) => {
   functions.logger.info("Hello logs!", {structuredData: true});
   response.send("Hello from Firebase!");
});
```

- Deploy to the cloud.

```firebase deploy```