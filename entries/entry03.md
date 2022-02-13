# Entry 3
##### 02/07/22

Up until now we have added some more codes to our project. We used this [website](https://firebase.google.com/docs/auth/web/google-signin) to help us with this part of the project. We learned how to let the users sign in with their google account. We thought about letting the users create a totally different account for this, but it kind of defeats the purpose since we help users remember their passwords and what if they forgets their password for this, so we go with google sign in.

We will first have to import what we need from Firebase first. For signing it, we want when users click "sign-in with Google" to have a small window popping up, so we also imported `signInWithPopup`. We created 2 constants for later use. `constant` is basically like `var`, but once you assign a value to it, it is set and you can make any changes to it.
```js
import { getAuth, signInWithPopup, GoogleAuthProvider } from "firebase/auth";

const provider = new GoogleAuthProvider();

const auth = getAuth();
```

This is when users start signing in. The first 2 constants give you a Google Access Token to access the Google API. The last one is the signed-in user info.
```js
signInWithPopup(auth, provider)
  .then((result) => {
    const credential = GoogleAuthProvider.credentialFromResult(result);
    const token = credential.accessToken;
    const user = result.user;
  })
```

This was used to catch any errors. To be clear, the `.catch((error) => {` is actually on the same line with the `})` from the code above, it should look like this `}).catch((error) => {`. They will be handling the errors.
```js
.catch((error) => {
  const errorCode = error.code;
  const errorMessage = error.message;
  const email = error.email;
  const credential = GoogleAuthProvider.credentialFromError(error);
});
```

We later found this [video](https://youtu.be/Dbq6yr9XKX8) to help enable the google sign in option for the project. They gave us some code and we have to copy and paste it into our project. This is the default Javascript sdk for Firebase. We were only a little into the video.
```js
<script type="module">
  import { initializeApp } from "https://www.gstatic.com/firebasejs/9.6.6/firebase-app.js";
  import { getAnalytics } from "https://www.gstatic.com/firebasejs/9.6.6/firebase-analytics.js";

  const firebaseConfig = {
    apiKey: "AIzaSyDwtt9nU5At77_2gIXsyPeYgV4AYibkvYo",
    authDomain: "password-saver-33a01.firebaseapp.com",
    databaseURL: "https://password-saver-33a01-default-rtdb.firebaseio.com",
    projectId: "password-saver-33a01",
    storageBucket: "password-saver-33a01.appspot.com",
    messagingSenderId: "730030078547",
    appId: "1:730030078547:web:396226808985562ab7e4a6",
    measurementId: "G-LLVNVDFB8Q"
  };

  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
</script>
```
Some challenges we are facing are we are using different tutorials for each step and we end up not knowing how to link all the different codes together and not sure how to organize them. I also realized some codes repeat and don't know if we need the repeated ones or not.

The engineering design process I'm on right now is Plan the most promising solution and Create a prototype. Me and my partner had the first part where the user signs in planned and the code typed out. We will need to organize our code and test it out. We also have to make a plan for the next step of making the front end, like the visual of the website because we have to test out the login function, adding buttons and stuff. The skills I developed in this process were Collaboration and Embracing failure. My partner and I combined what we both learned together. Embracing failure is that we both had a hard time understanding the code and we still have to make it to work.


[Previous](entry02.md) | [Next](entry04.md)

[Home](../README.md)
