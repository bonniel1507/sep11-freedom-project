# Entry 5
##### 4/2/22

Now it was at like the end of the freedom project. This time me and my partner will have a website that can save usernames and password using Firebase.

Before the code to show the informations. We declared some constants for later use.
```js
const db = getFirestore()
const colRef = collection(db,'Websites')
```

We need the data to show before we can do anying to it. `onSnapshot` is a method in Firebase that allow us to view the documents/data we have saved. The indiviual documents(doc) will be push to the array and preview in the console.
```js
onSnapshot(colRef, (snapshot) => {
    let websites = []
    snapshot.docs.forEach((doc) => {
        websites.push({ ...doc.data(), id: doc.id })
    })
    console.log(websites)
})
```
But, because our data was stored in the firestore database instead of the realtime database, we can make it to show only in the console for now.

Now, we have the data shown, our goal was to be able to save informations, if there's new username and password, we need to be able to add more to it.

[Previous](entry04.md) | [Next](entry06.md)

[Home](../README.md)
