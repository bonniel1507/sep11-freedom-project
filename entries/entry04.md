# Entry 4
##### 3/14/22

We continued on our project with the google sign-in part. While watching the video for last time, I realized that the video was out of dated, there's code that I can't find on the firebase website anymore. So, I went to find another [video](https://firebase.google.com/docs/auth/web/google-signin) for the project.


We did a very quick web page for sign-in button. It was just a testing right now, we will do the css later. 
```html
<div id ="LoginScreen">
  <button id = "login">Login with Google</button>
</div>
<div id ="dashboard">
  <button id="signOut">Log Out</button>
</div>
```

Import some functions from firebase first. The pop up when the user clicks login and the sign out when user logs out. Also, create some var/const for later use.
```js
import { getAuth, GoogleAuthProvider, signInWithPopup, signOut } from "https://www.gstatic.com/firebasejs/9.6.6/firebase-auth.js";

const auth = getAuth(app)
const provider = new GoogleAuthProvider(app);
```

In the ide, we would need to listen for when the login button was clicked. We added an `.ddEventListener` for the login button. The `(e)` was the same thing as the event.
```js
login.addEventListener('click',(e) => {
```

The following code was given in this [website](https://firebase.google.com/docs/auth/web/google-signin). The use of these codes was to when the login button was clicked, a pop up of Gmail will show and the user can choose which one they would like to sign in with.

The engineering design process we are at was Plan the most promising solution and Create a prototype. We were creating the we page not with the Google sign in. We also planned a head with the inner page when the user finishes login, what would they see. Also with the login page, it need some designs. The skills I developed during the process was Embracing failure and Problem decomposition. We encountered some problems, like it works, but not all the way. We would break down our code and try to find what the problem is and fix it. There's also like silly mistakes that there's a typo and that's why it was acting weird.

[Previous](entry03.md) | [Next](entry05.md)

[Home](../README.md)
