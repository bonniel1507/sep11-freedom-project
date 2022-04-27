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

Now, we have the data shown, our goal was to be able to save informations, if there's new username and password, we need to be able to add more to it. `addWebsiteForm was assigned with the add button and it would be listening when the person clicks it. `e.preventDefault()` is to prevent the page from refreshing. `addDoc()` will grab what the person filled in the text box for website, username and password and save in the firebase. Then, the text boxes would reset.
```js
const addWebsiteForm = document.querySelector('.add')
addWebsiteForm.addEventListener('submit', (e) => {
    e.preventDefault()
    
    addDoc(colRef, {
        website: addWebsiteForm.website.value,
        username: addWebsiteForm.username.value,
        password: addWebsiteForm.password.value,
    })
    .then(() => {
        addWebsiteForm.reset()
    })
})
```

If there is a add function, there should be a delete function too. The delete function is basically the same as the add function above.

Later, we also added a update function, so users can directly make changes and not delete that than add a new one. It's similar the the add function, it will take what the user put in the text box of the form and reassign the new username and password to the data.
```js
updateDoc(docRef, {
    username: updateForm.username.value,
    password: updateForm.password.value,
})
.then(() => {
    updateForm.reset()
})
```

The engineering design process we are at was Test and evaluate the prototype and Improve as needed. We basically have the website simpily done and we were testing it to work and made little improvement to the front end of the website. Me and my parrtner can latter dicuss on our project and add more improvement in the future. The skills I developed were Time Management and communication. Because me and my partner are free different time, so we worked on it alternativily and with a little time overlapping, so while she's working on the js, I will go to work on the html. Also with communication skills that we have to show what we did before we switch and explain it so we can understand and be able to pick up from where she left.

[Previous](entry04.md) | [Next](entry06.md)

[Home](../README.md)
