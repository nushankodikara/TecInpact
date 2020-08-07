---
title: "Firebase Authentication"
date: 2020-08-07T06:00:00+05:30
Description: "Let's Use Firebase For User Authentication."
Tags: ["Mobile Development","web Development"]
Categories: []
DisableComments: false
---

## Introduction

Let's use firebase for user authentication, you don't need to setup custom authentications, app apis and other stupid things anymore, we have firebase on our back and few lines of codes can make the programs more efficient and more secure! today I'm only focusing Email, Google and Anonymous authentications mainly. you can browse firebase docs for more information on how to setup other authentications in advanced.

## Firebase Authentication

Most apps need to know the identity of a user. Knowing a user's identity allows an app to securely save user data in the cloud and provide the same personalized experience across all of the user's devices.
Firebase Authentication provides backend services, easy-to-use SDKs, and ready-made UI libraries to authenticate users to your app. It supports authentication using passwords, phone numbers, popular federated identity providers like Google, Facebook and Twitter, and more.

Firebase Authentication integrates tightly with other Firebase services, and it leverages industry standards like OAuth 2.0 and OpenID Connect, so it can be easily integrated with your custom backend.

## Users in Firebase Projects

The Firebase user object represents a user account that has signed up for an app in your project. Apps usually have many registered users, and every app in a project shares a user database.

User instances are independent from Firebase Authentication instances, so you can have several references to different users within the same context and still call any of their methods.

## User properties

Firebase users have a fixed set of basic properties—a unique ID, a primary email address, a name and a photo URL—stored in the project's user database, that can be updated by the user (iOS, Android, web). You cannot add other properties to the user object directly; instead, you can store the additional properties in any other storage services, like Google Cloud Firestore.

The first time a user signs up to your app, the user's profile data is populated using the available information:

* If the user signed up with an email address and password, only the primary email address property is populated
* If the user signed up with a federated identity provider, such as Google or Facebook, the account information made available by the provider is used to populate the user's profile
* If the user signed up with your custom auth system, you must explicitly add the information you want to the user's profile

Once a user account has been created, you can reload the user's information to incorporate any changes the user might have made on another device.

## Sign-in providers

You can sign in users to your apps using several methods: email address and password, federated identity providers, and your custom auth system. You can associate more than one sign-in method with a user: for example, a user can sign in to the same account using an email address and a password, or using Google Sign-In.

User instances keeps track of every provider linked to the user. This allows you to update empty profile's properties using the information given by a provider. See Managing Users (iOS, Android, web).

## The current user

When a user signs up or signs in, that user becomes the current user of the Auth instance. The instance persists the user's state, so that refreshing the page (in a browser) or restarting the application doesn't lose the user's information.

When the user signs out, the Auth instance stops keeping a reference to the user object and no longer persists its state; there is no current user. However, the user instance continues to be completely functional: if you keep a reference to it, you can still access and update the user's data.

## The user lifecycle

The recommended way to track the current state of the Auth instance is by using listeners (also called "observers" in JavaScript). An Auth listener gets notified any time something relevant happens to the Auth object. See Managing Users (iOS, Android, web).

An Auth listener gets notified in the following situations:

The Auth object finishes initializing and a user was already signed in from a previous session, or has been redirected from an identity provider's sign-in flow

* A user signs in (the current user is set)
* A user signs out (the current user becomes null)
* The current user's access token is refreshed. This case can happen in the following conditions:
* The access token expires: this is a common situation. The refresh token is used to get a new valid set of tokens.
* The user changes their password: Firebase issues new access and refresh tokens and renders the old tokens expired. This automatically expires the user's token and/or signs out the user on every device, for security reasons.
* The user re-authenticates: some actions require that the user's credentials are recently issued; such actions include deleting an account, setting a primary email address, and changing a password. Instead of signing out the user and then signing in the user again, get new credentials from the user, and pass the new credentials to the re-authenticate method of the user object.

## Easily add sign-in to your Web app with FirebaseUI

FirebaseUI is a library built on top of the Firebase Authentication SDK that provides drop-in UI flows for use in your app. FirebaseUI provides the following benefits:

* Multiple Providers - sign-in flows for email/password, email link, phone authentication, Google, Facebook, Twitter and GitHub sign-in.
* Account Linking - flows to safely link user accounts across identity providers.
* Customization - override CSS styles of FirebaseUI to match your app requirements. Also, because FirebaseUI is open source, you can fork the project and customize it exactly to your needs.
* Localized UI - internationalization for over 40 languages.
* Upgrading anonymous users - ability to upgrade anonymous users through sign-in/sign-up. For more information, visit the Upgrading anonymous users section.

## Before you begin

Add Firebase Authentication to your web application.

Include the following script and CSS file in the `<head>` tag of your page, below the initialization snippet from the Firebase Console:

```js
<script src="https://cdn.firebase.com/libs/firebaseui/3.5.2/firebaseui.js"></script>
<link type="text/css" rel="stylesheet" href="https://cdn.firebase.com/libs/firebaseui/3.5.2/firebaseui.css" />
```

## Initialize FirebaseUI

After importing the SDK, initialize the Auth UI.

```js
// Initialize the FirebaseUI Widget using Firebase.
var ui = new firebaseui.auth.AuthUI(firebase.auth());
```

## Set up sign-in methods

Before you can use Firebase to sign in users, you must enable and configure the sign-in methods you want to support.

## Email address and password

1. In the Firebase console, open the Authentication section and enable email and password authentication.

2. Add the email provider ID to the list of FirebaseUI signInOptions.

```js
ui.start('#firebaseui-auth-container', {
  signInOptions: [
    firebase.auth.EmailAuthProvider.PROVIDER_ID
  ],
  // Other config options...
});
```

3. Optional: The EmailAuthProvider can be configured to require the user to enter a display name (defaults to true).

```js
ui.start('#firebaseui-auth-container', {
  signInOptions: [
    {
      provider: firebase.auth.EmailAuthProvider.PROVIDER_ID,
      requireDisplayName: false
    }
  ]
});
```

## Authenticate with Firebase Anonymously Using JavaScript

You can use Firebase Authentication to create and use temporary anonymous accounts to authenticate with Firebase. These temporary anonymous accounts can be used to allow users who haven't yet signed up to your app to work with data protected by security rules. If an anonymous user decides to sign up to your app, you can link their sign-in credentials to the anonymous account so that they can continue to work with their protected data in future sessions.

## Before you  begin

1. Add Firebase to your JavaScript project.
1. If you haven't yet connected your app to your Firebase project, do so from the Firebase console.
1. Enable anonymous auth:

* In the Firebase console, open the Auth section.
* On the Sign-in Methods page, enable the Anonymous sign-in method.

## Authenticate with Firebase anonymously

When a signed-out user uses an app feature that requires authentication with Firebase, sign in the user anonymously by completing the following steps:

1. Call the signInAnonymously method:

```js
firebase.auth().signInAnonymously().catch(function(error) {
  // Handle Errors here.
  var errorCode = error.code;
  var errorMessage = error.message;
  // ...
});
```

This is also where you can catch and handle errors. For a list of error codes have a look at the Auth Reference Docs.

2. If the signInAnonymously method completes without error, the observer registered in the onAuthStateChanged will trigger and you can get the anonymous user's account data from the User object:

```js
firebase.auth().onAuthStateChanged(function(user) {
  if (user) {
    // User is signed in.
    var isAnonymous = user.isAnonymous;
    var uid = user.uid;
    // ...
  } else {
    // User is signed out.
    // ...
  }
  // ...
});
```

## Convert an anonymous account to a permanent account

When an anonymous user signs up to your app, you might want to allow them to continue their work with their new account—for example, you might want to make the items the user added to their shopping cart before they signed up available in their new account's shopping cart. To do so, complete the following steps:

1. When the user signs up, complete the sign-in flow for the user's authentication provider up to, but not including, calling one of the Auth.signInWith methods. For example, get the user's Google ID token, Facebook access token, or email address and password.

2. Get an AuthCredential for the new authentication provider:

Google Sign-In

```js
var credential = firebase.auth.GoogleAuthProvider.credential(
    googleUser.getAuthResponse().id_token);
```

Email-password sign-in

```js
var credential = firebase.auth.EmailAuthProvider.credential(email, password);
```

3. Pass the AuthCredential object to the sign-in user's link method:

```js
auth.currentUser.linkWithCredential(credential)
  .then(function(usercred) {
    var user = usercred.user;
    console.log("Anonymous account successfully upgraded", user);
  }).catch(function(error) {
    console.log("Error upgrading anonymous account", error);
  });
```

If the call to link succeeds, the user's new account can access the anonymous account's Firebase data.

## Authenticate Using Google Sign-In with JavaScript

You can let your users authenticate with Firebase using their Google Accounts by integrating Google Sign-In into your app. You can integrate Google Sign-In either by using the Firebase SDK to carry out the sign-in flow, or by carrying out the Google Sign-In flow manually and passing the resulting ID token to Firebase.

## Before you   begin

1. Add Firebase to your JavaScript project.
2. Enable Google Sign-In in the Firebase console:

* In the Firebase console, open the Auth section.
* On the Sign in method tab, enable the Google sign-in method and click Save.

## Handle the sign-in flow with the Firebase SDK

If you are building a web app, the easiest way to authenticate your users with Firebase using their Google Accounts is to handle the sign-in flow with the Firebase JavaScript SDK. (If you want to authenticate a user in Node.js or other non-browser environment, you must handle the sign-in flow manually.)

To handle the sign-in flow with the Firebase JavaScript SDK, follow these steps:

1. Create an instance of the Google provider object:

```js
var provider = new firebase.auth.GoogleAuthProvider();
```

2. Optional: Specify additional OAuth 2.0 scopes that you want to request from the authentication provider. To add a scope, call addScope. For example:

```js
provider.addScope('https://www.googleapis.com/auth/contacts.readonly');
```

3. See the authentication provider documentation.
Optional: To localize the provider's OAuth flow to the user's preferred language without explicitly passing the relevant custom OAuth parameters, update the language code on the Auth instance before starting the OAuth flow. For example:

```js
firebase.auth().languageCode = 'pt';
// To apply the default browser preference instead of explicitly setting it.
// firebase.auth().useDeviceLanguage();
```

4. Optional: Specify additional custom OAuth provider parameters that you want to send with the OAuth request. To add a custom parameter, call setCustomParameters on the initialized provider with an object containing the key as specified by the OAuth provider documentation and the corresponding value. For example:

```js
provider.setCustomParameters({
  'login_hint': 'user@example.com'
});
```

Reserved required OAuth parameters are not allowed and will be ignored. See the authentication provider reference for more details.

5. Authenticate with Firebase using the Google provider object. You can prompt your users to sign in with their Google Accounts either by opening a pop-up window or by redirecting to the sign-in page. The redirect method is preferred on mobile devices.
To sign in with a pop-up window, call signInWithPopup:

```js
firebase.auth().signInWithPopup(provider).then(function(result) {
  // This gives you a Google Access Token. You can use it to access the Google API.
  var token = result.credential.accessToken;
  // The signed-in user info.
  var user = result.user;
  // ...
}).catch(function(error) {
  // Handle Errors here.
  var errorCode = error.code;
  var errorMessage = error.message;
  // The email of the user's account used.
  var email = error.email;
  // The firebase.auth.AuthCredential type that was used.
  var credential = error.credential;
  // ...
});
```

Also notice that you can retrieve the Google provider's OAuth token which can be used to fetch additional data using the Google APIs.
This is also where you can catch and handle errors. For a list of error codes have a look at the Auth Reference Docs.

* To sign in by redirecting to the sign-in page, call signInWithRedirect:

```js
firebase.auth().signInWithRedirect(provider);
```

Then, you can also retrieve the Google provider's OAuth token by calling getRedirectResult when your page loads:

```js
firebase.auth().getRedirectResult().then(function(result) {
  if (result.credential) {
    // This gives you a Google Access Token. You can use it to access the Google API.
    var token = result.credential.accessToken;
    // ...
  }
  // The signed-in user info.
  var user = result.user;
}).catch(function(error) {
  // Handle Errors here.
  var errorCode = error.code;
  var errorMessage = error.message;
  // The email of the user's account used.
  var email = error.email;
  // The firebase.auth.AuthCredential type that was used.
  var credential = error.credential;
  // ...
});
```

This is also where you can catch and handle errors. For a list of error codes have a look at the Auth Reference Docs. You can find all of the providers here.

![Authentication Providers](/uploads/20200807_01.gif)

Alright! Now we know how we can authenticate with firebase, Now, Let's explore how we can secure our Firestore and Realtime databases.

## Understand Firebase Realtime Database Rules

Firebase Realtime Database Rules determine who has read and write access to your database, how your data is structured, and what indexes exist. These rules live on the Firebase servers and are enforced automatically at all times. Every read and write request will only be completed if your rules allow it. By default, your rules do not allow anyone access to your database. This is to protect your database from abuse until you have time to customize your rules or set up authentication.

Realtime Database Rules have a JavaScript-like syntax and come in four types:

| Rule      | Types                                                                                                        |
| :-------- | :----------------------------------------------------------------------------------------------------------- |
| .read     | Describes if and when data is allowed to be read by users.                                                   |
| .write    | Describes if and when data is allowed to be written.                                                         |
| .validate | Defines what a correctly formatted value will look like, whether it has child attributes, and the data type. |
| .indexOn  | Specifies a child to index to support ordering and querying.                                                 |

## Realtime Database security overview

The Firebase Realtime Database provides a full set of tools for managing the security of your app. These tools make it easy to authenticate your users, enforce user permissions, and validate inputs.

Firebase-powered apps run more client-side code than those with many other technology stacks. Therefore, the way we approach security may be a bit different than you're used to.

## Authentication

A common first step in securing your app is identifying your users. This process is called authentication. You can use Firebase Authentication to have users to sign in to your app. Firebase Authentication includes drop-in support for common authentication methods like Google and Facebook, as well as email and password login, anonymous login, and more.

User identity is an important security concept. Different users have different data, and sometimes they have different capabilities. For example, in a chat application, each message is associated with the user that created it. Users may also be able to delete their own messages, but not messages posted by other users.

## Authorization

Identifying your user is only part of security. Once you know who they are, you need a way to control their access to data in your database. Realtime Database Rules allow you to control access for each user. For example, here's a set of security rules that allows anyone to read the path /foo/, but no one to write to it:

```js
{
  "rules": {
    "foo": {
      ".read": true,
      ".write": false
    }
  }
}
```

.read and .write rules cascade, so this ruleset grants read access to any data at path /foo/ as well as any deeper paths such as /foo/bar/baz. Note that .read and .write rules shallower in the database override deeper rules, so read access to /foo/bar/baz would still be granted in this example even if a rule at the path /foo/bar/baz evaluated to false.

The Realtime Database Rules include built-in variables and functions that allow you to refer to other paths, server-side timestamps, authentication information, and more. Here's an example of a rule that grants write access for authenticated users to `/users/<uid>/`, where `<uid>` is the ID of the user obtained through Firebase Authentication.

```js
{
  "rules": {
    "users": {
      "$uid": {
        ".write": "$uid === auth.uid"
      }
    }
  }
}
```

## Data validation

The Firebase Realtime Database is schemaless. This makes it easy to change things as you develop, but once your app is ready to distribute, it's important for data to stay consistent. The rules language includes a .validate rule which allows you to apply validation logic using the same expressions used for .read and .write rules. The only difference is that validation rules do not cascade, so all relevant validation rules must evaluate to true in order for the write to be allowed.

These rule enforce that data written to /foo/ must be a string less than 100 characters:

```js
{
  "rules": {
    "foo": {
      ".validate": "newData.isString() && newData.val().length < 100"
    }
  }
}
```

Validation rules have access to all of the same built-in functions and variables as .read and .write rules. You can use these to create validation rules that are aware of data elsewhere in your database, your user's identity, server time, and much more.

## Defining database indexes

The Firebase Realtime Database allows ordering and querying data. For small data sizes, the database supports ad hoc querying, so indexes are generally not required during development. Before launching your app though, it is important to specify indexes for any queries you have to ensure they continue to work as your app grows.

Indexes are specified using the .indexOn rule. Here is an example index declaration that would index the height and length fields for a list of dinosaurs:

```js
{
  "rules": {
    "dinosaurs": {
      ".indexOn": ["height", "length"]
    }
  }
}
```

## Get started with Cloud Firestore Security Rules

With Cloud Firestore Security Rules, you can focus on building a great user experience without having to manage infrastructure or write server-side authentication and authorization code.

Security rules provide access control and data validation in a simple yet expressive format. To build user-based and role-based access systems that keep your users' data safe, you need to use Firebase Authentication with Cloud Firestore Security Rules.

## Security rules version 2

As of May 2019, version 2 of the Cloud Firestore security rules is now available. Version 2 of the rules changes the behavior of recursive wildcards {name=**}. You must use version 2 if you plan to use collection group queries. You must opt-in to version 2 by making rules_version = '2'; the first line in your security rules:

```js
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
```

## Writing rules

All Cloud Firestore Security Rules consist of match statements, which identify documents in your database, and allow expressions, which control access to those documents:

```js
service cloud.firestore {
  match /databases/{database}/documents {
    match /<some_path>/ {
      allow read, write: if <some_condition>;
    }
  }
}
```

Every database request from a Cloud Firestore mobile/web client library is evaluated against your security rules before reading or writing any data. If the rules deny access to any of the specified document paths, the entire request fails.

Below are some examples of basic rule sets. While these rules are valid, they are not recommended for production applications:

### Auth Required

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

### Deny all

```js
// Deny read/write access to all users under any conditions
service cloud.firestore {
  match /databases/{database}/documents {
    match /{document=**} {
      allow read, write: if false;
    }
  }
}
```

### Allow All

```js
// Allow read/write access to all users under any conditions
// Warning: **NEVER** use this rule set in production; it allows
// anyone to overwrite your entire database.
service cloud.firestore {
  match /databases/{database}/documents {
    match /{document=**} {
      allow read, write: if true;
    }
  }
}
```

The {document=**} path used in the examples above matches any document in the entire database. Continue on to the guide for structuring security rules to learn how to match specific data paths and work with hierarchical data.

## Testing rules

Cloud Firestore provides a rules simulator that you can use to test your ruleset. You can access the simulator from the Rules tab in the Cloud Firestore section of the Firebase console.

The rules simulator lets you simulate authenticated and unauthenticated reads, writes, and deletes. When you simulate an authenticated request, you can build and preview authentication tokens from various providers. Simulated requests run against the ruleset in your editor, not your currently deployed ruleset.

## Deploying rules

Before you can start using Cloud Firestore from your mobile app, you will need to deploy security rules. You can deploy rules in the Firebase console or using the Firebase CLI.

Updates to Cloud Firestore Security Rules can take up to a minute to affect new queries and listeners. However, it can take up to 10 minutes to fully propagate the changes and affect any active listeners.

## Use the Firebase console

To set up and deploy your first set of rules, open the Rules tab in the Cloud Firestore section of the Firebase console.

Write your rules in the online editor, then click Publish.

And That's what we need to know about! Use these wisely and you'll end-up with a super cool project overall!

## Conclusion

Firebase is a complete BaaS Solution for modern web developers. It also supports so many platforms but we're considering web SDKs for now.
