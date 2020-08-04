---
title: "Firebase Realtime Database"
date: 2020-08-05T06:00:00+05:30
Description: "Complete Guide on Firebase Realtime Database"
Tags: ["Mobile Development","web Development"]
Categories: []
DisableComments: false
---

## Introduction

Okay, Let's do some database actions, But without SQL or any of those table based old style databases, We're learning how to use Firebase Realtime database with a web application, but also the codes are the same for mobile applications, so it won't make much difference at all, And in the end of this series, After we covered Authentication, We're creating a fully fledged Chat application and maybe a social media application to test our knowledge.

## Environmental Setup

First you need to have a firebase project settled up, We're starting the firebase database section without any security rules at first, then we're doing it with rules. First, let's explore the possibilities of Firebase Database

Key capabilities

| Capability                      | Description                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| :------------------------------ | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Realtime                        | Instead of typical HTTP requests, the Firebase Realtime Database uses data synchronization—every time data changes, any connected device receives that update within milliseconds. Provide collaborative and immersive experiences without thinking about networking code.                                                                                                                                                                           |
| Offline                         | Firebase apps remain responsive even when offline because the Firebase Realtime Database SDK persists your data to disk. Once connectivity is reestablished, the client device receives any changes it missed, synchronizing it with the current server state.                                                                                                                                                                                       |
| Accessible from Client Devices  | The Firebase Realtime Database can be accessed directly from a mobile device or web browser; there’s no need for an application server. Security and data validation are available through the Firebase Realtime Database Security Rules, expression-based rules that are executed when data is read or written.                                                                                                                                     |
| Scale across multiple databases | With Firebase Realtime Database on the Blaze pricing plan, you can support your app's data needs at scale by splitting your data across multiple database instances in the same Firebase project. Streamline authentication with Firebase Authentication on your project and authenticate users across your database instances. Control access to the data in each database with custom Firebase Realtime Database Rules for each database instance. |

## How does it work

The Firebase Realtime Database lets you build rich, collaborative applications by allowing secure access to the database directly from client-side code. Data is persisted locally, and even while offline, realtime events continue to fire, giving the end user a responsive experience. When the device regains connection, the Realtime Database synchronizes the local data changes with the remote updates that occurred while the client was offline, merging any conflicts automatically.

The Realtime Database provides a flexible, expression-based rules language, called Firebase Realtime Database Security Rules, to define how your data should be structured and when data can be read from or written to. When integrated with Firebase Authentication, developers can define who has access to what data, and how they can access it.

The Realtime Database is a NoSQL database and as such has different optimizations and functionality compared to a relational database. The Realtime Database API is designed to only allow operations that can be executed quickly. This enables you to build a great realtime experience that can serve millions of users without compromising on responsiveness. Because of this, it is important to think about how users need to access your data and then structure it accordingly.

## Choose a Database: Cloud Firestore or Realtime Database

Firebase offers two cloud-based, client-accessible database solutions that support realtime data syncing:

* **Cloud Firestore** is Firebase's newest database for app development. It builds on the successes of the Realtime Database with a new, more intuitive data model. Cloud Firestore also features richer, faster queries and scales further than the Realtime Database.

* **Realtime Database** is Firebase's original database. It's an efficient, low-latency solution for apps that require synced states across clients in realtime.

We're looking into the Realtime Database solution Today. It's a key:value paired database solution with directories and easy operations. We need a clear data modal before starting a project of two reasons.

1. Firebase Realtime database doesn't have a pre-defined Data structure
2. Security Purposes (We'll Discuss later)

Also Realtime database Stores data as one large JSON tree.

* Simple data is very easy to store.
* Complex, hierarchical data is harder to organize at scale.

Otherhand in Cloud Firestore
Stores data as collections of documents.

* Simple data is easy to store in documents, which are very similar to JSON.
* Complex, hierarchical data is easier to organize at scale, using subcollections within documents.
* Requires less denormalization and data flattening.

Keep that in mind for a bit. And again, We're using the web SDK for this project with Javascript because we're doing JAMStack development from here on. It's the same for all of the SDKs so don't get panicked.

## Installation & Setup in JavaScript

I'm creating a simple html document with HTML, CSS and JS also linking them all, as always you can download the project [HERE](/zip/FirebaseAssestPack1.zip). Also if you're using Visual Studio code as I do, Go ahead and install [Firebase Explorer Extension](https://marketplace.visualstudio.com/items?itemName=jsayol.firebase-explorer) To view your project right in VSCode (It Helps Allot!).

The Firebase Realtime Database is a cloud-hosted database. Data is stored as JSON and synchronized in realtime to every connected client. When you build cross-platform apps with our Android, iOS, and JavaScript SDKs, all of your clients share one Realtime Database instance and automatically receive updates with the newest data.

### Prerequisites

Let's add firebase to our project. in order to do this, you have to implement links to these files in your HTML page. These versions could be changed so go to this site <https://firebase.google.com/docs/web/setup> to get the latest

```html
<!-- This is the main JS file to implement Firebase -->
<script src="/__/firebase/7.17.1/firebase-app.js"></script>
<!-- Now you can add any modular firebase services in this case Realtime Database -->
<script src="https://www.gstatic.com/firebasejs/7.17.1/firebase-database.js"></script>
```

It's simple as that!. And now that out to the way, we have to initialize your Firebase project. To do this you have to goto <https://console.firebase.google.com/> And create a new project.

![Creating a firebase project](/uploads/20200805_01.gif)

Now you have to add the initialization code from the project. Doing this is simple, go to your project and copy the web SDK code And put in right below the Firebase implementation service. This code is okay to be exposed and you can add security rules to make sure no one's going to peek into your database in unwanted ways.

![Creating a firebase project](/uploads/20200805_02.gif)
![Creating a firebase project](/uploads/20200805_03.gif)

If you're using the firebase explorer plugin, now you can see the database in the left hand corner of your VSCode editor. This is a nice addition for quick exploration.

![Creating a firebase project](/uploads/20200805_04.gif)

Alright Now Let's make a demo application and Start working out! I'm creating a quick HTML document and adding a text input bar to it along with a button, so I can get data from the element and write it to the database! Before that, Let's explore how the data stored in this database type.

## Structure Your Database

This guide covers some of the key concepts in data architecture and best practices for structuring the JSON data in your Firebase Realtime Database.

Building a properly structured database requires quite a bit of forethought. Most importantly, you need to plan for how data is going to be saved and later retrieved to make that process as easy as possible.

### How data is structured: it's a JSON tree

All Firebase Realtime Database data is stored as JSON objects. You can think of the database as a cloud-hosted JSON tree. Unlike a SQL database, there are no tables or records. When you add data to the JSON tree, it becomes a node in the existing JSON structure with an associated key. You can provide your own keys, such as user IDs or semantic names, or they can be provided for you using `push()`.

For example, consider a chat application that allows users to store a basic profile and contact list. A typical user profile is located at a path, such as /users/$uid. The user alovelace might have a database entry that looks something like this:

```json
{
  "users": {
    "alovelace": {
      "name": "Ada Lovelace",
      "contacts": { "ghopper": true },
    },
    "ghopper": { ... },
    "eclarke": { ... }
  }
}
```

Although the database uses a JSON tree, data stored in the database can be represented as certain native types that correspond to available JSON types to help you write more maintainable code.

## Read and Write Data on the Web

Alright Before starting, Let's go to the firebase and remove security from security rules. In order to do this, we have to set read and write permission to true. So anyone can read and write from the database.

![Creating a firebase project](/uploads/20200805_05.gif)

## Get a database reference

To read or write data from the database, you need an instance of firebase.database.Reference, in order to do this we use the following code in our main JS file, I like to make this into a constant variable,

```js
const database = firebase.database();
```

Now we can use this database variable to do anything with our Database, Let's start with basic operations.

## Basic Writing Operation

For basic write operations, you can use `set()` to save data to a specified reference, replacing any existing data at that path. For example a social blogging application might add a user with `set()` as follows:

```js
writeUserData = (userId, name, email, imageUrl) => {
  firebase.database().ref('users/' + userId).set({
    username: name,
    email: email,
    profile_picture : imageUrl
  });
}
```

This function passes 4 variables, userID, name, email and imageUrl to the firebase database reference set function, and from there it's writing to `users/*UserID` directory where the UserID is the user's unique ID, and setting username variable to padded name, email variable to passed email and profile picture to the passed URL. you can use `database` variable instead of `firebase.database()`, however I like to set the whole reference point into a constant variable so I just have to use the set function on it.

But with this set function, if there are data in that specific location it would be overwritten.

## Listen for value events (Basic Read Operations)

To read data at a path and listen for changes, use the `on()` or `once()` methods of `firebase.database.Reference` to observe events. As is says, `once()` is for reading data only once, and `on()` is to listen for data in realtime.

now let's see how we can listen to data in realtime

```js
let starCountRef = firebase.database().ref('posts/' + postId + '/starCount');
starCountRef.on('value', function(snapshot) {
  updateStarCount(postElement, snapshot.val());
});
```

Now with his piece of code, It's listening to the `post/*postID/starCount` in realtime, and the postID is dynamic as you can see. From this code the SDK is always listening to the starCount of the specific post and once it's been updated, Fires the updateStarCount() function every time with the updated value of the `post/*postID/starCount` directory. It's that simple to use. ah also the value can be retrieved using `snapshot.val()` function. Data would be returned as a string.

now let's read the data once. It's the same as the above function, But it's only firing the function, when we define the variable, or you can use it to manually fetch data from the database.

```js
let userId = firebase.auth().currentUser.uid;
return firebase.database().ref('/users/' + userId).once('value').then(function(snapshot) {
  let username = (snapshot.val() && snapshot.val().username) || 'Anonymous';
  // ...
});
```

Consider this piece of code as a snippet from a function to get the username from a user. here, first we set the authentication reference to userID variable. then using `once()` function, we're retrieving data from `/users/*userID/` path, then what is that on the returning section you may ask, it's checking for is there any has been returned, this is false if you're using Anonymous authentication, and we're discussing about authentication in a while so be patient. And if the function returns a value, we're using it as the username, otherwise we're putting Anonymous as the username.

## Updating or deleting data

### Update specific fields

To simultaneously write to specific children of a node without overwriting other child nodes, use the `update()` method.

When calling `update()`, you can update lower-level child values by specifying a path for the key. If data is stored in multiple locations to scale better, you can update all instances of that data using data fan-out.

For example, a social blogging app might create a post and simultaneously update it to the recent activity feed and the posting user's activity feed using code like this:

```js
writeNewPost = (uid, username, picture, title, body) => {
  // A post entry.
  let postData = {
    author: username,
    uid: uid,
    body: body,
    title: title,
    starCount: 0,
    authorPic: picture
  };

  // Get a key for a new Post.
  let newPostKey = firebase.database().ref().child('posts').push().key;

  // Write the new post's data simultaneously in the posts list and the user's post list.
  let updates = {};
  updates['/posts/' + newPostKey] = postData;
  updates['/user-posts/' + uid + '/' + newPostKey] = postData;

  return firebase.database().ref().update(updates);
}
```

Let me explain what this does. we have the `writeNewPost()` function passing uid, username, picture, title and body variables and assigning them to an array in postData. you can get a unique key for a data set using the `push()` function and we're going to update two directories simultaneously. You can see the update array has two directories with the same dataset, `/post/*newPostKey` and `/user-posts/uid/newpostkey/` are getting updated the same time, This can be an example of think like facebook or instagram managing a bigger feed and personal feed with same post data. (There are more efficent ways to do this)

Using these paths, you can perform simultaneous updates to multiple locations in the JSON tree with a single call to update(), such as how this example creates the new post in both locations. Simultaneous updates made this way are atomic: either all updates succeed or all updates fail.

## Add a Completion Callback

If you want to know when your data has been committed, you can add a completion callback. Both set() and update() take an optional completion callback that is called when the write has been committed to the database. If the call was unsuccessful, the callback is passed an error object indicating why the failure occurred.

```js
firebase.database().ref('users/' + userId).set({
    username: name,
    email: email,
    profile_picture : imageUrl
}, function(error) {
    if (error) {
      // The write failed...
    } else {
      // Data saved successfully!
    }
  });
}
```

## Delete data

The simplest way to delete data is to call remove() on a reference to the location of that data.

You can also delete by specifying null as the value for another write operation such as set() or update(). You can use this technique with update() to delete multiple children in a single API call.

## Receive a Promise

To know when your data is committed to the Firebase Realtime Database server, you can use a Promise. Both set() and update() can return a Promise you can use to know when the write is committed to the database.

## Detach listeners

Callbacks are removed by calling the off() method on your Firebase database reference.

```js
firebase.database().ref('users/' + userId).off()
```

You can remove a single listener by passing it as a parameter to off(). Calling off() on the location with no arguments removes all listeners at that location.

Calling off() on a parent listener does not automatically remove listeners registered on its child nodes; off() must also be called on any child listeners to remove the callback.

## Save data as transactions

When working with data that could be corrupted by concurrent modifications, such as incremental counters, you can use a transaction operation. You can give this operation an update function and an optional completion callback. The update function takes the current state of the data as an argument and returns the new desired state you would like to write. If another client writes to the location before your new value is successfully written, your update function is called again with the new current value, and the write is retried.

For instance, in the example social blogging app, you could allow users to star and unstar posts and keep track of how many stars a post has received as follows:

function toggleStar(postRef, uid) {
  postRef.transaction(function(post) {
    if (post) {
      if (post.stars && post.stars[uid]) {
        post.starCount--;
        post.stars[uid] = null;
      } else {
        post.starCount++;
        if (!post.stars) {
          post.stars = {};
        }
        post.stars[uid] = true;
      }
    }
    return post;
  });
}

Using a transaction prevents star counts from being incorrect if multiple users star the same post at the same time or the client had stale data. If the transaction is rejected, the server returns the current value to the client, which runs the transaction again with the updated value. This repeats until the transaction is accepted or you abort the transaction.

## Write data offline

If a client loses its network connection, your app will continue functioning correctly.

Every client connected to a Firebase database maintains its own internal version of any active data. When data is written, it's written to this local version first. The Firebase client then synchronizes that data with the remote database servers and with other clients on a "best-effort" basis.

As a result, all writes to the database trigger local events immediately, before any data is written to the server. This means your app remains responsive regardless of network latency or connectivity.

Once connectivity is reestablished, your app receives the appropriate set of events so that the client syncs with the current server state, without having to write any custom code.

## Work with Lists of Data on the Web

Here we're discussing about how to manage data lists, for an instance, imagine of a chat in a chat application, it's a list of messages, of facebook's post data, it's a list of posts etc etc...

### Get a reference of the database

To read or write data from the database, you need an instance of firebase.database.Reference:

```js
// Get a reference to the database service
let database = firebase.database();
```

### Reading and writing lists

#### Append to a list of data

Use the `push()` method to append data to a list in multiuser applications. The push() method generates a unique key every time a new child is added to the specified Firebase reference. By using these auto-generated keys for each new element in the list, several clients can add children to the same location at the same time without write conflicts. The unique key generated by push() is based on a timestamp, so list items are automatically ordered chronologically.

You can use the reference to the new data returned by the push() method to get the value of the child's auto-generated key or set data for the child. The .key property of a push() reference contains the auto-generated key.

You can use these auto-generated keys to simplify flattening your data structure. For more information, see the data fan-out example.

For example, push() could be used to add a new post to a list of posts in a social application:

```js
// Create a new post reference with an auto-generated id
let newPostRef = postListRef.push();
newPostRef.set({
    // ...
});
```

### Listen for child events

Child events are triggered in response to specific operations that happen to the children of a node from an operation such as a new child added through the push() method or a child being updated through the update() method.

| Event         | Typical usage                                                                                                                                                                                                                                                     |
| :------------ | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| child_added   | Retrieve lists of items or listen for additions to a list of items. This event is triggered once for each existing child and then again every time a new child is added to the specified path. The listener is passed a snapshot containing the new child's data. |
| child_changed | Listen for changes to the items in a list. This event is triggered any time a child node is modified. This includes any modifications to descendants of the child node. The snapshot passed to the event listener contains the updated data for the child.        |
| child_removed | Listen for items being removed from a list. This event is triggered when an immediate child is removed.The snapshot passed to the callback block contains the data for the removed child.                                                                         |
| child_moved   | Listen for changes to the order of items in an ordered list. child_moved events always follow the child_changed event that caused the item's order to change (based on your current order-by method).                                                             |

Each of these together can be useful for listening to changes to a specific node in a database. For example, a social blogging app might use these methods together to monitor activity in the comments of a post, as shown below:

```js
let commentsRef = firebase.database().ref('post-comments/' + postId);
commentsRef.on('child_added', function(data) {
  addCommentElement(postElement, data.key, data.val().text, data.val().author);
});

commentsRef.on('child_changed', function(data) {
  setCommentValues(postElement, data.key, data.val().text, data.val().author);
});

commentsRef.on('child_removed', function(data) {
  deleteComment(postElement, data.key);
});
```

### Listen for value events

While listening for child events is the recommended way to read lists of data, there are situations listening for value events on a list reference is useful.

Attaching a value observer to a list of data will return the entire list of data as a single snapshot which you can then loop over to access individual children.

Even when there is only a single match for the query, the snapshot is still a list; it just contains a single item. To access the item, you need to loop over the result:

```js
ref.once('value', function(snapshot) {
  snapshot.forEach(function(childSnapshot) {
    var childKey = childSnapshot.key;
    var childData = childSnapshot.val();
    // ...
  });
});
```

This pattern can be useful when you want to fetch all children of a list in a single operation, rather than listening for additional child added events.

### Sorting and filtering data

You can use the Realtime Database Query class to retrieve data sorted by key, by value, or by value of a child. You can also filter the sorted result to a specific number of results or a range of keys or values.

### Sort data

To retrieve sorted data, start by specifying one of the order-by methods to determine how results are ordered:

| Method         | Usage                                                                     |
| :------------- | :------------------------------------------------------------------------ |
| orderByChild() | Order results by the value of a specified child key or nested child path. |
| orderByKey()   | Order results by child keys.                                              |
| orderByValue() | Order results by child values.                                            |

You can only use one order-by method at a time. Calling an order-by method multiple times in the same query throws an error.

The following example demonstrates how you could retrieve a list of a user's top posts sorted by their star count:

```js
let myUserId = firebase.auth().currentUser.uid;
let topUserPostsRef = firebase.database().ref('user-posts/' + myUserId).orderByChild('starCount');
```

This defines a query that when combined with a child listener synchronizes the client with the user's posts from the path in the database based on their user ID, ordered by the number of stars each post has received. This technique of using IDs as index keys is called data fan out, you can read more about it in Structure Your Database.

The call to the `orderByChild()` method specifies the child key to order the results by. In this case, posts are sorted by the value of their respective "starCount" child. Queries can also be ordered by nested children, in case you have data that looks like this:

```js
"posts": {
  "ts-functions": {
    "metrics": {
      "views" : 1200000,
      "likes" : 251000,
      "shares": 1200,
    },
    "title" : "Why you should use TypeScript for writing Cloud Functions",
    "author": "Doug",
  },
  "android-arch-3": {
    "metrics": {
      "views" : 900000,
      "likes" : 117000,
      "shares": 144,
    },
    "title" : "Using Android Architecture Components with Firebase Realtime Database (Part 3)",
    "author": "Doug",
  }
}
```

In this case, we can order our list elements by values nested under the metrics key by specifying the relative path to the nested child in our orderByChild() call.

```js
var mostViewedPosts = firebase.database().ref('posts').orderByChild('metrics/views');
```

For more information on how other data types are ordered, see How query data is ordered.

### Filtering data

To filter data, you can combine any of the limit or range methods with an order-by method when constructing a query.

| Method         | Usage                                                                                                      |
| :------------- | :--------------------------------------------------------------------------------------------------------- |
| limitToFirst() | Sets the maximum number of items to return from the beginning of the ordered list of results.              |
| limitToLast()  | Sets the maximum number of items to return from the end of the ordered list of results.                    |
| startAt()      | Return items greater than or equal to the specified key or value, depending on the order-by method chosen. |
| endAt()        | Return items less than or equal to the specified key or value, depending on the order-by method chosen.    |
| equalTo()      | Return items equal to the specified key or value, depending on the order-by method chosen.                 |

Unlike the order-by methods, you can combine multiple limit or range functions. For example, you can combine the startAt() and endAt() methods to limit the results to a specified range of values.

### Limit the number of results

You can use the limitToFirst() and limitToLast() methods to set a maximum number of children to be synced for a given event. For example, if you use limitToFirst() to set a limit of 100, you initially only receive up to 100 child_added events. If you have fewer than 100 items stored in your Firebase database, a child_added event fires for each item.

As items change, you receive child_added events for items that enter the query and child_removed events for items that drop out of it so that the total number stays at 100.

The following example demonstrates how example blogging app defines a query to retrieve a list of the 100 most recent posts by all users:

```js
let recentPostsRef = firebase.database().ref('posts').limitToLast(100);
```

This example only defines a query, to actually synchronize data it needs to have an attached listener.

### Filter by key or value

You can use startAt(), endAt(), and equalTo() to choose arbitrary starting, ending, and equivalence points for queries. This can be useful for paginating data or finding items with children that have a specific value.

### How query data is ordered

This section explains how data is sorted by each of the order-by methods in the Query class.

#### orderByChild

When using orderByChild(), data that contains the specified child key is ordered as follows:

1. Children with a null value for the specified child key come first.
1. Children with a value of false for the specified child key come next. If multiple children have a value of false, they are sorted lexicographically by key.
1. Children with a value of true for the specified child key come next. If multiple children have a value of true, they are sorted lexicographically by key.
1. Children with a numeric value come next, sorted in ascending order. If multiple children have the same numerical value for the specified child node, they are sorted by key.
1. Strings come after numbers and are sorted lexicographically in ascending order. If multiple children have the same value for the specified child node, they are ordered lexicographically by key.
1. Objects come last and are sorted lexicographically by key in ascending order.

#### orderByKey

When using orderByKey() to sort your data, data is returned in ascending order by key.

1. Children with a key that can be parsed as a 32-bit integer come first, sorted in ascending order.
1. Children with a string value as their key come next, sorted lexicographically in ascending order.

#### orderByValue

When using orderByValue(), children are ordered by their value. The ordering criteria are the same as in orderByChild(), except the value of the node is used instead of the value of a specified child key.

#### Detach listeners for lists

Callbacks are removed by calling the off() method on your Firebase database reference.

You can remove a single listener by passing it as a parameter to off(). Calling off() on the location with no arguments removes all listeners at that location.

Calling off() on a parent listener does not automatically remove listeners registered on its child nodes; off() must also be called on any child listeners to remove the callback.

## So let's put our knowledge to the test

We can create a simple application of a public grocery list. to demonstrate the usage of firebase realtime database. This is the simplest as it can gets with all the functionalities. So let's see how I did it

![Grocery list](/uploads/20200805_06.gif)

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="style.css">
    <title>Firebase Demo - Realtime Database</title>
</head>

<body>
    <!-- Nothing Advanced But I Always Use a Content Section for Content -->
    <div class="content">
        <h1>-------------------------------------</h1>
        <h2>Simple Grocery List</h2>
        <h1>-------------------------------------</h1>
        <!-- A Simple Form to add items-->
        <form>
            <h4>Items</h4>
            <input type="text" id="Grocery" name="Grocery" placeholder="Item" />
            <h4>Quantity</h4>
            <input type="number" id="QTY" name="QTY" />
            <button onclick="postData();return false">Add item</button>
        </form>
        <h1>-------------------------------------</h1>
        <h2>
            Grocery List
        </h2>
        <!-- This would hold our Data and data would be added Programmatically-->
        <table id="table">

        </table>
        <h1>-------------------------------------</h1>
        <h2>
            Completed List
        </h2>
        <!-- This would hold our Data and data would be added Programmatically-->
        <table id="table2">

        </table>
    </div>

    <!-- This is the main JS file to implement Firebase -->
    <script src="https://www.gstatic.com/firebasejs/7.17.1/firebase-app.js"></script>
    <!-- Now you can add any modular firebase services in this case Realtime Database -->
    <script src="https://www.gstatic.com/firebasejs/7.17.1/firebase-database.js"></script>

    <!-- TODO: Add SDKs for Firebase products that you want to use
     https://firebase.google.com/docs/web/setup#available-libraries -->
    <script src="https://www.gstatic.com/firebasejs/7.17.1/firebase-analytics.js"></script>

    <script>
        // Your web app's Firebase configuration Should Be added Here
        var firebaseConfig = {
            apiKey: "AIzaSyDOMUpm4WNldKOVuQCeizCTZAUdSRLqAeU",
            authDomain: "tecinpact-demo.firebaseapp.com",
            databaseURL: "https://tecinpact-demo.firebaseio.com",
            projectId: "tecinpact-demo",
            storageBucket: "tecinpact-demo.appspot.com",
            messagingSenderId: "977048224763",
            appId: "1:977048224763:web:4891159dda17b97eb8c15e",
            measurementId: "G-RZPCV71CCZ"
        };
        // Initialize Firebase
        firebase.initializeApp(firebaseConfig);
        firebase.analytics();
    </script>
    <script src="app.js"></script>
</body>

</html>
```

I Added comments Explaining the HTML code and it's self explainatory.

```scss
* {
    font-family: monospace;
}

.content {
    display: grid;
    place-items: center;

    form {
        @extend .content;

        input {
            padding: 10px 35px;
            margin: 5px;
        }
    }

    table {
        width: 100%;
        max-width: 350px;
        text-align: left;
    }
}
```

```js
/* A Simple Function to push new data */
postData = () => {
    let gitem = document.getElementById("Grocery").value
    let gqty = document.getElementById("QTY").value
    /* Resetting Input Boxes after submission */
    document.getElementById("Grocery").value = ""
    document.getElementById("QTY").value = 0
    /* Pushing data to the Database's GroceryList Directory */
    let newItem = firebase.database().ref('/GroceryList/').push();
    newItem.set({
        item: gitem,
        qty: gqty
    });
}

/* Listner to get data from the Database As soon as it's added */
let items = firebase.database().ref('GroceryList/');
items.on('value', function (recivedItems) {
    /* Appends data to an array and then we can set the whole array to the table */
    let htmlArray = [`<tr><th>Items</th><th>QTY</th><th>Got It?</th></tr>`]
    recivedItems.forEach(item => {
        /* Formatting Received Data */
        htmlArray.push(`<tr><td>${item.val()["item"]}</td><td>${item.val()["qty"]}</td><td><button onclick="removedList('${item.key}')">✔️</button></td></tr>`)
    });
    /* Setting Data to table */
    document.getElementById('table').innerHTML = htmlArray.join('')
});

/* Adding data to another list when completed */
removedList = (id) => {
    let item = firebase.database().ref(`GroceryList/${id}`)
    item.on('value', function (snapshot) {
        /* Getting data and submitting it to Removed List */
        let newCompletedItem = firebase.database().ref('/GroceryRemovedList/').push();
        newCompletedItem.set(snapshot.val());
    });
    /* Removing from the first list */
    removeEntity("GroceryList", `${id}`)
}

/* Listner for the completed List */
let ritems = firebase.database().ref('GroceryRemovedList/');
ritems.on('value', function (recivedItems) {
    let htmlArray = [`<tr><th>Items</th><th>QTY</th><th>Remove It?</th></tr>`]
    recivedItems.forEach(item => {
        htmlArray.push(`<tr><td style="text-decoration: line-through;">${item.val()["item"]}</td><td>${item.val()["qty"]}</td><td><button onclick="removeEntity('GroceryRemovedList','${item.key}')">❌</button></td></tr>`)
    });
    document.getElementById('table2').innerHTML = htmlArray.join('')
});

/* This can delete items from the database */
removeEntity = (list, id) => {
    firebase.database().ref(`${list}/${id}`).remove()
}
```

## Conclusion

Well well well, Here we are at the end of another guide, Firebase realtime database is suitable for many applications, after most of these guides have been overed, We're going to make some sample applications to demonstrate the usages of the applications. So stay tuned and don't be shy to ask anything you get doubts on, You are here to learn, so take the advantage.
