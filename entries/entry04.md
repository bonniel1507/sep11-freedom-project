# Entry 4
##### 3/14/22

We continued on our project with the google sign-in part. We did a very quick web page for sign-in button. It was just a testing right now, we will do the css later. 
```html
<div id ="LoginScreen">
  <button id = "login">Login with Google</button>
</div>
<div id ="dashboard">
  <button id="signOut">Log Out</button>
</div>
```

Import some functions from firebase first. The pop up when the user clicks login and the sign out when user logs out.
```js
import { getAuth, GoogleAuthProvider, signInWithPopup, signOut } from "https://www.gstatic.com/firebasejs/9.6.6/firebase-auth.js";
```

In the ide, we would need to listen for when the login button was clicked. We added an `.ddEventListener` for the login button. The `(e)` was the same thing as the event.
```js
login.addEventListener('click',(e) => {
```

[irl](https://firebase.google.com/docs/auth/web/google-signin)

[Previous](entry03.md) | [Next](entry05.md)

[Home](../README.md)
