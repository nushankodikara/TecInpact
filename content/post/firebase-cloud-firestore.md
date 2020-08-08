---
title: "Firebase Cloud Firestore"
date: 2020-08-06T06:00:00+05:30
vDescription: "Complete Guide on Firebase Cloud Firestore Database"
Tags: ["Mobile Development","web Development","Firebase"]
Categories: []
DisableComments: false
---

## Introduction

Use our flexible, scalable NoSQL cloud database to store and sync data for client- and server-side development.

Cloud Firestore is a flexible, scalable database for mobile, web, and server development from Firebase and Google Cloud Platform, Like Firebase Realtime Database, it keeps your data in sync across client apps through realtime listeners and offers offline support for mobile and web so you can build responsive apps that work regardless of network latency or Internet connectivity, Cloud Firestore also offers seamless integration with other Firebase and Google Cloud Platform products, including Cloud Functions.

## Key capabilities

| capability          | Description                                                                                                                                                                                                                                                                                                                                                                          |
| :------------------ | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Flexibility         | The Cloud Firestore data model supports flexible, hierarchical data structures. Store your data in documents, organized into collections. Documents can contain complex nested objects in addition to subcollections.                                                                                                                                                                |
| Expressive querying | In Cloud Firestore, you can use queries to retrieve individual, specific documents or to retrieve all the documents in a collection that match your query parameters. Your queries can include multiple, chained filters and combine filtering and sorting. They're also indexed by default, so query performance is proportional to the size of your result set, not your data set. |
| Realtime updates    | Like Realtime Database, Cloud Firestore uses data synchronization to update data on any connected device. However, it's also designed to make simple, one-time fetch queries efficiently.                                                                                                                                                                                            |
| Offline support     | Cloud Firestore caches data that your app is actively using, so the app can write, read, listen to, and query data even if the device is offline. When the device comes back online, Cloud Firestore synchronizes any local changes back to Cloud Firestore.                                                                                                                         |
| Designed to scale   | Cloud Firestore brings you the best of Google Cloud Platform's powerful infrastructure: automatic multi-region data replication, strong consistency guarantees, atomic batch operations, and real transaction support. We've designed Cloud Firestore to handle the toughest database workloads from the world's biggest apps.                                                       |

## How does it work

Cloud Firestore is a cloud-hosted, NoSQL database that your iOS, Android, and web apps can access directly via native SDKs. Cloud Firestore is also available in native Node.js, Java, Python, Unity, C++ and Go SDKs, in addition to REST and RPC APIs.

Following Cloud Firestore's NoSQL data model, you store data in documents that contain fields mapping to values. These documents are stored in collections, which are containers for your documents that you can use to organize your data and build queries. Documents support many different data types, from simple strings and numbers, to complex, nested objects. You can also create subcollections within documents and build hierarchical data structures that scale as your database grows. The Cloud Firestore data model supports whatever data structure works best for your app.

Additionally, querying in Cloud Firestore is expressive, efficient, and flexible. Create shallow queries to retrieve data at the document level without needing to retrieve the entire collection, or any nested subcollections. Add sorting, filtering, and limits to your queries or cursors to paginate your results. To keep data in your apps current, without retrieving your entire database each time an update happens, add realtime listeners. Adding realtime listeners to your app notifies you with a data snapshot whenever the data your client apps are listening to changes, retrieving only the new changes.

Protect access to your data in Cloud Firestore with Firebase Authentication and Cloud Firestore Security Rules for Android, iOS, and JavaScript, or Identity and Access Management (IAM) for server-side languages.

## Get started with Cloud Firestore

This quickstart shows you how to set up Cloud Firestore, add data, then view the data you just added in the Firebase console.

## Create a Cloud Firestore database

1. If you haven't already, create a Firebase project: In the Firebase console, click Add project, then follow the on-screen instructions to create a Firebase project or to add Firebase services to an existing GCP project.

2. Navigate to the Database section of the Firebase console. You'll be prompted to select an existing Firebase project. Follow the database creation workflow.

3. Select a starting mode for your Cloud Firestore Security Rules:

### Test mode

Good for getting started with the mobile and web client libraries, but allows anyone to read and overwrite your data. After testing, make sure to review the Secure your data section.

To get started with the web, iOS, or Android SDK, select test mode.

### Locked mode

Denies all reads and writes from mobile and web clients. Your authenticated application servers (C#, Go, Java, Node.js, PHP, Python, or Ruby) can still access your database.

To get started with the C#, Go, Java, Node.js, PHP, Python, or Ruby server client library, select locked mode.

4. Select a location for your database.

* This location setting is your project's default Google Cloud Platform (GCP) resource location. Note that this location will be used for GCP services in your project that require a location setting, specifically, your default Cloud Storage bucket and your App Engine app (which is required if you use Cloud Scheduler).

* If you aren't able to select a location, then your project already has a default GCP resource location. It was set either during project creation or when setting up another service that requires a location setting.

5. Click Done.

I'm skipping the first step because we did it in the previous post. And continuing from there, It's not much harder just create a new project.

![Creating Database](/uploads/20200806_01.gif)

## Set up your development environment

Add the required dependencies and client libraries to your app. In this case, we need firestore library and the app initialization library.

1. Follow the instructions to add Firebase to your Web app.
2. Add the Firebase and Cloud Firestore libraries to your app:

```js
<script src="https://www.gstatic.com/firebasejs/7.17.1/firebase-app.js"></script>
<script src="https://www.gstatic.com/firebasejs/7.17.1/firebase-firestore.js"></script>
```

Now Let's Initialize the app with our database. To do this, You have to add the initialization code from your console.

![Initializing App](/uploads/20200806_02.gif)

## Add data

Cloud Firestore stores data in Documents, which are stored in Collections. Cloud Firestore creates collections and documents implicitly the first time you add data to the document. You do not need to explicitly create collections or documents.

Create a new collection and a document using the following example code.

```js
db.collection("users").add({
    first: "Ada",
    last: "Lovelace",
    born: 1815
})
.then(function(docRef) {
    console.log("Document written with ID: ", docRef.id);
})
.catch(function(error) {
    console.error("Error adding document: ", error);
});
```

Now add another document to the users collection. Notice that this document includes a key-value pair (middle name) that does not appear in the first document. Documents in a collection can contain different sets of information.

```js
// Add a second document with a generated ID.
db.collection("users").add({
    first: "Alan",
    middle: "Mathison",
    last: "Turing",
    born: 1912
})
.then(function(docRef) {
    console.log("Document written with ID: ", docRef.id);
})
.catch(function(error) {
    console.error("Error adding document: ", error);
});
```

## Read data

To quickly verify that you've added data to Cloud Firestore, use the data viewer in the Firebase console.

You can also use the "get" method to retrieve the entire collection.

```js
db.collection("users").get().then((querySnapshot) => {
    querySnapshot.forEach((doc) => {
        console.log(`${doc.id} => ${doc.data()}`);
    });
});
```

## Secure your data

If you're using the Web, Android, or iOS SDK, use Firebase Authentication and Cloud Firestore Security Rules to secure your data in Cloud Firestore.

Here are some basic rule sets you can use to get started. You can modify your security rules in the Rules tab of the console. (We're Discussing Security in detail on another day!)

```js
// Allow read/write access on all documents to any user signed in to the application
service cloud.firestore {
  match /databases/{database}/documents {
    match /{document=**} {
      allow read, write: if request.auth != null;
    }
  }
}
```

If you're using one of the server SDKs, use Identity and Access Management (IAM) to secure your data in Cloud Firestore.

Let's dive deeper into the above topics.

## Adding Data Explanation

There are several ways to write data to Cloud Firestore:

* Set the data of a document within a collection, explicitly specifying a document identifier.
* Add a new document to a collection. In this case, Cloud Firestore automatically generates the document identifier.
* Create an empty document with an automatically generated identifier, and assign data to it later.

This guide explains how to use the set, add, or update individual documents in Cloud Firestore. If you want to write data in bulk, see Transactions and Batched Writes.

## Set a document

To create or overwrite a single document, use the set() method:

```js
// Add a new document in collection "cities"
db.collection("cities").doc("LA").set({
    name: "Los Angeles",
    state: "CA",
    country: "USA"
})
.then(function() {
    console.log("Document successfully written!");
})
.catch(function(error) {
    console.error("Error writing document: ", error);
});
```

If the document does not exist, it will be created. If the document does exist, its contents will be overwritten with the newly provided data, unless you specify that the data should be merged into the existing document, as follows:

```js
var cityRef = db.collection('cities').doc('BJ');

var setWithMerge = cityRef.set({
    capital: true
}, { merge: true });
```

If you're not sure whether the document exists, pass the option to merge the new data with any existing document to avoid overwriting entire documents.

## Data types

Cloud Firestore lets you write a variety of data types inside a document, including strings, booleans, numbers, dates, null, and nested arrays and objects. Cloud Firestore always stores numbers as doubles, regardless of what type of number you use in your code.

```js
var docData = {
    stringExample: "Hello world!",
    booleanExample: true,
    numberExample: 3.14159265,
    dateExample: firebase.firestore.Timestamp.fromDate(new Date("December 10, 1815")),
    arrayExample: [5, true, "hello"],
    nullExample: null,
    objectExample: {
        a: 5,
        b: {
            nested: "foo"
        }
    }
};
db.collection("data").doc("one").set(docData).then(function() {
    console.log("Document successfully written!");
});
```

## Custom objects

Using Map or Dictionary objects to represent your documents is often not very convenient, so Cloud Firestore supports writing documents with custom classes. Cloud Firestore converts the objects to supported data types.

Using custom classes, you could rewrite the initial example as follows:

```js
class City {
    constructor (name, state, country ) {
        this.name = name;
        this.state = state;
        this.country = country;
    }
    toString() {
        return this.name + ', ' + this.state + ', ' + this.country;
    }
}

    // Firestore data converter
  cityConverter = {
      toFirestore: function(city) {
          return {
              name: city.name,
              state: city.state,
              country: city.country
              }
      },
      fromFirestore: function(snapshot, options){
          const data = snapshot.data(options);
          return new City(data.name, data.state, data.country)
      }
  }
```

```js
// Set with cityConverter
db.collection("cities").doc("LA")
  .withConverter(cityConverter)
  .set(new City("Los Angeles", "CA", "USA"));
```

## Add a document

When you use set() to create a document, you must specify an ID for the document to create. For example:

```js
db.collection("cities").doc("new-city-id").set(data);
```

But sometimes there isn't a meaningful ID for the document, and it's more convenient to let Cloud Firestore auto-generate an ID for you. You can do this by calling add():

```js
// Add a new document with a generated id.
db.collection("cities").add({
    name: "Tokyo",
    country: "Japan"
})
.then(function(docRef) {
    console.log("Document written with ID: ", docRef.id);
})
.catch(function(error) {
    console.error("Error adding document: ", error);
});
```

In some cases, it can be useful to create a document reference with an auto-generated ID, then use the reference later. For this use case, you can call doc():

```js
// Add a new document with a generated id.
var newCityRef = db.collection("cities").doc();

// later...
newCityRef.set(data);
```

Behind the scenes, .add(...) and .doc().set(...) are completely equivalent, so you can use whichever is more convenient.

## Update a document

To update some fields of a document without overwriting the entire document, use the update() method:

```js
var washingtonRef = db.collection("cities").doc("DC");

// Set the "capital" field of the city 'DC'
return washingtonRef.update({
    capital: true
})
.then(function() {
    console.log("Document successfully updated!");
})
.catch(function(error) {
    // The document probably doesn't exist.
    console.error("Error updating document: ", error);
});
```

## Server Timestamp

You can set a field in your document to a server timestamp which tracks when the server receives the update.

```js
var docRef = db.collection('objects').doc('some-id');

// Update the timestamp field with the value from the server
var updateTimestamp = docRef.update({
    timestamp: firebase.firestore.FieldValue.serverTimestamp()
});
```

## Update fields in nested objects

If your document contains nested objects, you can use "dot notation" to reference nested fields within the document when you call update():

```js
// Create an initial document to update.
var frankDocRef = db.collection("users").doc("frank");
frankDocRef.set({
    name: "Frank",
    favorites: { food: "Pizza", color: "Blue", subject: "recess" },
    age: 12
});

// To update age and favorite color:
db.collection("users").doc("frank").update({
    "age": 13,
    "favorites.color": "Red"
})
.then(function() {
    console.log("Document successfully updated!");
});
```

Dot notation allows you to update a single nested field without overwriting other nested field. If you update a nested field without dot notation, you will overwrite the entire map field, for example:

```js
// Create our initial doc
db.collection("users").doc("frank").set({
  name: "Frank",
  favorites: {
    food: "Pizza",
    color: "Blue",
    subject: "Recess"
  },
  age: 12
}).then(function() {
  console.log("Frank created");
});

// Update the doc without using dot notation.
// Notice the map value for favorites.
db.collection("users").doc("frank").update({
  favorites: {
    food: "Ice Cream"
  }
}).then(function() {
  console.log("Frank food updated");
});

/*
Ending State, favorite.color and favorite.subject are no longer present:
/users
    /frank
        {
            name: "Frank",
            favorites: {
                food: "Ice Cream",
            },
            age: 12
        }
 */
```

## Update elements in an array

If your document contains an array field, you can use arrayUnion() and arrayRemove() to add and remove elements. arrayUnion() adds elements to an array but only elements not already present. arrayRemove() removes all instances of each given element.

```js
var washingtonRef = db.collection("cities").doc("DC");

// Atomically add a new region to the "regions" array field.
washingtonRef.update({
    regions: firebase.firestore.FieldValue.arrayUnion("greater_virginia")
});

// Atomically remove a region from the "regions" array field.
washingtonRef.update({
    regions: firebase.firestore.FieldValue.arrayRemove("east_coast")
});
```

## Increment a numeric value

You can increment or decrement a numeric field value as shown in the following example. An increment operation increases or decreases the current value of a field by the given amount. If the field does not exist or if the current field value is not a numeric value, the operation sets the field to the given value.

```js
var washingtonRef = db.collection('cities').doc('DC');

// Atomically increment the population of the city by 50.
washingtonRef.update({
    population: firebase.firestore.FieldValue.increment(50)
});

```

Increment operations are useful for implementing counters, but keep in mind that you can update a single document only once per second.

## Delete data from Cloud Firestore

The following examples demonstrate how to delete documents, fields, and collections.

## Delete documents

To delete a document, use the delete() method:

```js
db.collection("cities").doc("DC").delete().then(function() {
    console.log("Document successfully deleted!");
}).catch(function(error) {
    console.error("Error removing document: ", error);
});
```

When you delete a document, Cloud Firestore does not automatically delete the documents within its subcollections. You can still access the subcollection documents by reference. For example, you can access the document at path /mycoll/mydoc/mysubcoll/mysubdoc even if you delete the ancestor document at /mycoll/mydoc.

Non-existent ancestor documents appear in the console, but they do not appear in query results and snapshots.

If you want to delete a document and all the documents within its subcollections, you must do so manually. For more information, see Delete Collections.

## Delete fields

To delete specific fields from a document, use the FieldValue.delete() method when you update a document:

```js
var cityRef = db.collection('cities').doc('BJ');

// Remove the 'capital' field from the document
var removeCapital = cityRef.update({
    capital: firebase.firestore.FieldValue.delete()
});
```

### Delete collections

To delete an entire collection or subcollection in Cloud Firestore, retrieve all the documents within the collection or subcollection and delete them. If you have larger collections, you may want to delete the documents in smaller batches to avoid out-of-memory errors. Repeat the process until you've deleted the entire collection or subcollection.

Deleting a collection requires coordinating an unbounded number of individual delete requests. If you need to delete entire collections, do so only from a trusted server environment. While it is possible to delete a collection from a mobile/web client, doing so has negative security and performance implications.

The snippets below are somewhat simplified and do not deal with error handling, security, deleting subcollections, or maximizing performance. To learn more about one recommended approach to deleting collections in production, see Deleting Collections and Subcollections.

```js
// Deleting collections from a Web client is not recommended.
```

## Get data with Cloud Firestore

There are two ways to retrieve data stored in Cloud Firestore. Either of these methods can be used with documents, collections of documents, or the results of queries:

* Call a method to get the data.
* Set a listener to receive data-change events.
  
When you set a listener, Cloud Firestore sends your listener an initial snapshot of the data, and then another snapshot each time the document changes.

## Example data

To get started, write some data about cities so we can look at different ways to read it back:

```js
var citiesRef = db.collection("cities");

citiesRef.doc("SF").set({
    name: "San Francisco", state: "CA", country: "USA",
    capital: false, population: 860000,
    regions: ["west_coast", "norcal"] });
citiesRef.doc("LA").set({
    name: "Los Angeles", state: "CA", country: "USA",
    capital: false, population: 3900000,
    regions: ["west_coast", "socal"] });
citiesRef.doc("DC").set({
    name: "Washington, D.C.", state: null, country: "USA",
    capital: true, population: 680000,
    regions: ["east_coast"] });
citiesRef.doc("TOK").set({
    name: "Tokyo", state: null, country: "Japan",
    capital: true, population: 9000000,
    regions: ["kanto", "honshu"] });
citiesRef.doc("BJ").set({
    name: "Beijing", state: null, country: "China",
    capital: true, population: 21500000,
    regions: ["jingjinji", "hebei"] });
```

## Get a document

The following example shows how to retrieve the contents of a single document using get():

```js
var docRef = db.collection("cities").doc("SF");

docRef.get().then(function(doc) {
    if (doc.exists) {
        console.log("Document data:", doc.data());
    } else {
        // doc.data() will be undefined in this case
        console.log("No such document!");
    }
}).catch(function(error) {
    console.log("Error getting document:", error);
});
```

## Source Options

For platforms with offline support, you can set the source option to control how a get call uses the offline cache.

By default, a get call will attempt to fetch the latest document snapshot from your database. On platforms with offline support, the client library will use the offline cache if the network is unavailable or if the request times out.

You can specify the source option in a get() call to change the default behavior. You can fetch from only the database and ignore the offline cache, or you can fetch from only the offline cache. For example:

```js
var docRef = db.collection("cities").doc("SF");

// Valid options for source are 'server', 'cache', or
// 'default'. See https://firebase.google.com/docs/reference/js/firebase.firestore.GetOptions
// for more information.
var getOptions = {
    source: 'cache'
};

// Get a document, forcing the SDK to fetch from the offline cache.
docRef.get(getOptions).then(function(doc) {
    // Document was found in the cache. If no cached document exists,
    // an error will be returned to the 'catch' block below.
    console.log("Cached document data:", doc.data());
}).catch(function(error) {
    console.log("Error getting cached document:", error);
});
```

## Custom  objects

The previous example retrieved the contents of the document as a map, but in some languages it's often more convenient to use a custom object type. In Add Data, you defined a City class that you used to define each city. You can turn your document back into a City object:

```js
class City {
    constructor (name, state, country ) {
        this.name = name;
        this.state = state;
        this.country = country;
    }
    toString() {
        return this.name + ', ' + this.state + ', ' + this.country;
    }
}

    // Firestore data converter
  cityConverter = {
      toFirestore: function(city) {
          return {
              name: city.name,
              state: city.state,
              country: city.country
              }
      },
      fromFirestore: function(snapshot, options){
          const data = snapshot.data(options);
          return new City(data.name, data.state, data.country)
      }
  }
```

```js
db.collection("cities").doc("LA")
  .withConverter(cityConverter)
  .get().then(function(doc) {
    if (doc.exists){
      // Convert to City object
      city = doc.data();
      // Use a City instance method
      console.log(city.toString());
    } else {
      console.log("No such document!")
    }}).catch(function(error) {
      console.log("Error getting document:", error)
    });
```

## Get multiple documents from a collection

You can also retrieve multiple documents with one request by querying documents in a collection. For example, you can use where() to query for all of the documents that meet a certain condition, then use get() to retrieve the results:

```js
db.collection("cities").where("capital", "==", true)
    .get()
    .then(function(querySnapshot) {
        querySnapshot.forEach(function(doc) {
            // doc.data() is never undefined for query doc snapshots
            console.log(doc.id, " => ", doc.data());
        });
    })
    .catch(function(error) {
        console.log("Error getting documents: ", error);
    });
```

By default, Cloud Firestore retrieves all documents that satisfy the query in ascending order by document ID, but you can order and limit the data returned.

## Get all documents in a collection

In addition, you can retrieve all documents in a collection by omitting the where() filter entirely:

```js
db.collection("cities").get().then(function(querySnapshot) {
    querySnapshot.forEach(function(doc) {
        // doc.data() is never undefined for query doc snapshots
        console.log(doc.id, " => ", doc.data());
    });
});
```

## Get multiple documents from a collection group

A collection group consists of all collections with the same ID. For example, if each document in your cities collection has a subcollection called landmarks, all of the landmarks subcollections belong to the same collection group. By default, queries retrieve results from a single collection in your database. Use a collection group query to retrieve results from a collection group instead of from a single collection.

## List subcollections of a document

The getCollections() method of the Cloud Firestore server client libraries lists all subcollections of a document reference.

Retrieving a list of collections is not possible with the mobile/web client libraries. You should only look up collection names as part of administrative tasks in trusted server environments. If you find that you need this capability in the mobile/web client libraries, consider restructuring your data so that subcollection names are predictable.

## Get realtime updates with Cloud Firestore

You can listen to a document with the onSnapshot() method. An initial call using the callback you provide creates a document snapshot immediately with the current contents of the single document. Then, each time the contents change, another call updates the document snapshot.

```js
db.collection("cities").doc("SF")
    .onSnapshot(function(doc) {
        console.log("Current data: ", doc.data());
    });
```

## Events for local changes

Local writes in your app will invoke snapshot listeners immediately. This is because of an important feature called "latency compensation." When you perform a write, your listeners will be notified with the new data before the data is sent to the backend.

Retrieved documents have a metadata.hasPendingWrites property that indicates whether the document has local changes that haven't been written to the backend yet. You can use this property to determine the source of events received by your snapshot listener:

```js
db.collection("cities").doc("SF")
    .onSnapshot(function(doc) {
        var source = doc.metadata.hasPendingWrites ? "Local" : "Server";
        console.log(source, " data: ", doc.data());
    });
```

## Events for metadata changes

When listening for changes to a document, collection, or query, you can pass options to control the granularity of events that your listener will receive.

By default, listeners are not notified of changes that only affect metadata. Consider what happens when your app writes a new document:

1. A change event is immediately fired with the new data. The document has not yet been written to the backend so the "pending writes" flag is true.
1. The document is written to the backend.
1. The backend notifies the client of the successful write. There is no change to the document data, but there is a metadata change because the "pending writes" flag is now false.

If you want to receive snapshot events when the document or query metadata changes, pass a listen options object when attaching your listener:

```js
db.collection("cities").doc("SF")
    .onSnapshot({
        // Listen for document metadata changes
        includeMetadataChanges: true
    }, function(doc) {
        // ...
    });
```

## Listen to multiple documents in a collection

As with documents, you can use onSnapshot() instead of get() to listen to the results of a query. This creates a query snapshot. For example, to listen to the documents with state CA:

```js
db.collection("cities").where("state", "==", "CA")
    .onSnapshot(function(querySnapshot) {
        var cities = [];
        querySnapshot.forEach(function(doc) {
            cities.push(doc.data().name);
        });
        console.log("Current cities in CA: ", cities.join(", "));
    });
```

The snapshot handler will receive a new query snapshot every time the query results change (that is, when a document is added, removed, or modified).

## View changes between snapshots

It is often useful to see the actual changes to query results between query snapshots, instead of simply using the entire query snapshot. For example, you may want to maintain a cache as individual documents are added, removed, and modified.

```js
db.collection("cities").where("state", "==", "CA")
    .onSnapshot(function(snapshot) {
        snapshot.docChanges().forEach(function(change) {
            if (change.type === "added") {
                console.log("New city: ", change.doc.data());
            }
            if (change.type === "modified") {
                console.log("Modified city: ", change.doc.data());
            }
            if (change.type === "removed") {
                console.log("Removed city: ", change.doc.data());
            }
        });
    });
```

The initial state can come from the server directly, or from a local cache. If there is state available in a local cache, the query snapshot will be initially populated with the cached data, then updated with the server's data when the client has caught up with the server's state.

## Detach a listener

When you are no longer interested in listening to your data, you must detach your listener so that your event callbacks stop getting called. This allows the client to stop using bandwidth to receive updates. For example:

```js
var unsubscribe = db.collection("cities")
    .onSnapshot(function (){
      // Respond to data
      // ...
    });

// Later ...

// Stop listening to changes
unsubscribe();
```

## Handle listen errors

A listen may occasionally fail — for example, due to security permissions, or if you tried to listen on an invalid query. (Learn more about valid and invalid queries.) To handle these failures, you can provide an error callback when you attach your snapshot listener. After an error, the listener will not receive any more events, and there is no need to detach your listener.

```js
db.collection("cities")
    .onSnapshot(function(snapshot) {
        //...
    }, function(error) {
        //...
    });
```

And That's what we need for the basics! We'll preform advanced quarries and so many things later!

## Conclusion

Here, we hav another great firebase solution from the firebase. This is not the full guide, because we need authentication for further details, I'm ending this basic guide here, After we discuss about the authentication in advanced, We can proceed with Firebase Firestore!