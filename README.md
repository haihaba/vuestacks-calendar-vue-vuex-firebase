# vuestacks-calendar-vue-vuex-firebase

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Run your tests
```
npm run test
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).

### Check out https://jsfanatik.github.io to learn more about the VueStacks initiative!

![alt text](https://raw.githubusercontent.com/jsfanatik/jsfanatik.github.io/master/assets/cal-screen3.jpg)

![alt text](https://raw.githubusercontent.com/jsfanatik/jsfanatik.github.io/master/assets/cal-screen4.JPG)

### Technical Overview

The VueStacks calendar demo utilizes general Vue.js + Firebase CRUD functions to enable creating, updating, and deleting of events in a modified Vuetify calendar component (see the following to learn more about Vuetify calendars: https://vuetifyjs.com/en/components/calendars). The user can create a new calendar event by clicking “new event” and adding event name, details, start/end times, and event colors. The user can then edit the event detail by clicking “edit” and then update the event by clicking save. The user can delete the event by clicking the trash icon.

```addEvent ()``` adds the inputted event to the database collection in firebase.

```deleteEvent ()``` removes the targeted event in the database.

```editEvent ()``` enables updating for the targeted event.

```updateEvent ()``` triggers the update of the event. 

```getEvent ()``` is a callback function that dispatches an action in store.js (Vuex store). The action retrieves the inputted event from the database then commits a mutation. State is then updated with the retrieved event. A ```getter ()``` method returns the state to the component (see: ```:events="this.$store.getters.getEvents"``` in Calendar.vue). 

### Addition Dependencies

This demo uses ```vue-textarea-autosize``` as a dependency. See the following for installation instructions: https://www.npmjs.com/package/vue-textarea-autosize

### Setting Up Firebase

1. Set up a new project in Firebase with Database enabled.
2. Implement the following Firebase SDK scripts in main.js:

```
import firebase from "firebase";
firebase.initializeApp({
  apiKey: "",
  authDomain: "",
  databaseURL: "",
  projectId: "",
  storageBucket: "",
  messagingSenderId: "",
  appId: ""
});

export const db = firebase.firestore();
```
Enjoy the demo! Submit an issue if you see anything that could be improved!
