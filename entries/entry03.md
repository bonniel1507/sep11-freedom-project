# Entry 3
##### 02/07/22

Up until now we have added some more codes to our project. We learned on how to let the users to sign in with their google account. We thought about letting the users create a total different account for this, but it kind of defeat the purpose since we help user remember their passwords and what if they forgets their password for this, so we go with google sign in.

We will first have to import what we need from Firebase first. For signing it, we want to when users click "sign-in with Google" to have a small window poping up, so we also imported `signInWithPopup`. We created 2 constants for later use.
```js
import { getAuth, signInWithPopup, GoogleAuthProvider } from "firebase/auth";

const provider = new GoogleAuthProvider();

const auth = getAuth();
```

The engineering design process I'm on right now is Plan the most promising solution and Create a prototype. Me and my partner had the first part where the user signs in planned and the code typed out. We will need to organize our code and test it out. We also have to make a plan for the next step of the project. The skills I developed in this process was Collaboration and Embracing failure. Me and my partner combined what we both learn together. Embracing failure is that we both had a hard time understanding the code and we still have to make it to work.


[Previous](entry02.md) | [Next](entry04.md)

[Home](../README.md)
