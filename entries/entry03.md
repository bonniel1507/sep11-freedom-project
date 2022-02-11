# Entry 3
##### 02/07/22

Up until now we have added some more codes to our project. We used this [website](https://firebase.google.com/docs/auth/web/google-signin) to help us with this part of the project. We learned on how to let the users to sign in with their google account. We thought about letting the users create a total different account for this, but it kind of defeat the purpose since we help user remember their passwords and what if they forgets their password for this, so we go with google sign in.

We will first have to import what we need from Firebase first. For signing it, we want to when users click "sign-in with Google" to have a small window poping up, so we also imported `signInWithPopup`. We created 2 constants for later use. `constant` is basically like `var`, but once you assign a value to it, it is set and you can make any changes to it.
```js
import { getAuth, signInWithPopup, GoogleAuthProvider } from "firebase/auth";

const provider = new GoogleAuthProvider();

const auth = getAuth();
```

This is when users start signing in. The first 2 constants gives you a Google Access Token to access the Google API. The last one is the signed-in user info.
```js
signInWithPopup(auth, provider)
  .then((result) => {
    const credential = GoogleAuthProvider.credentialFromResult(result);
    const token = credential.accessToken;
    const user = result.user;
  })
```

This was use to catch any errors. To be clear, the `.catch((error) => {` is actually on the same line with the `})` from the code above, it should look like this `}).catch((error) => {`. They will be handling the errors.
```js
.catch((error) => {
    const errorCode = error.code;
    const errorMessage = error.message;
    const email = error.email;
    const credential = GoogleAuthProvider.credentialFromError(error);
  });
```

The engineering design process I'm on right now is Plan the most promising solution and Create a prototype. Me and my partner had the first part where the user signs in planned and the code typed out. We will need to organize our code and test it out. We also have to make a plan for the next step of the project. The skills I developed in this process was Collaboration and Embracing failure. Me and my partner combined what we both learn together. Embracing failure is that we both had a hard time understanding the code and we still have to make it to work.


[Previous](entry02.md) | [Next](entry04.md)

[Home](../README.md)
