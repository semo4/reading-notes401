# Android Fundamentals


![images](https://res.cloudinary.com/jerrick/image/upload/fl_progressive,q_auto,w_1024/5f5b11b6a6b679001ce6c799.png)

## Application Fundamentals


- One APK file contains all the contents of an Android app and is the file that Android-powered devices use to install the app.

- By default, the system assigns each app a unique Linux user ID . The system sets permissions for all the files in an app so that only the user ID assigned to that app can access them. Each process has its own virtual machine , so an app's code runs in isolation from other apps. This creates a very secure environment in which an app cannot access parts of the system for which it is not given permission.

- To conserve system resources, apps with the same user ID can also arrange to run in the same Linux process and share the same VM. The apps must also be signed with the same certificate. The user has to explicitly grant these permissions. For more information, see Working with System Permissions.


## App components
- App components are the essential building blocks of an Android app. Each component is an entry point through which the system or a user can enter your app. Some components depend on others.

- There are four different types of app components:

1. Activities
2. Services
3. Broadcast receivers
4. Content providers

### Activities
- An activity is the entry point for interacting with the user. It represents a single screen with a user interface. For example, an email app might have one activity that shows a list of new emails, another activity to compose an email, and another activity for reading emails. As such, a different app can start any one of these activities if the email app allows it. For example, a camera app can start the activity in the email app that composes new mail to allow the user to share a picture. Knowing that previously used processes contain things the user may return to , and thus more highly prioritize keeping those processes around.
- Helping the app handle having its process killed so the user can return to activities with their previous state restored.

### Services


- A service is a general-purpose entry point for keeping an app running in the background for all kinds of reasons. It is a component that runs in the background to perform long-running operations or to perform work for remote processes. A service does not provide a user interface. For example, a service might play music in the background while the user is in a different app, or it might fetch data over the network without blocking user interaction with an activity.

- This could be to sync some data in the background or play music even after the user leaves the app. It may allow it to be killed if it needs RAM for things that are of more immediate concern to the user. Bound services run because some other app has said that it wants to make use of the service. Further, if process A is something the user cares about, then it also knows to treat process B as something the user also cares about.

- Because of their flexibility , services have turned out to be a really useful building block for all kinds of higher-level system concepts. Live wallpapers, notification listeners, screen savers, input methods, accessibility services, and many other core system features are all built as services that applications implement and the system binds to when they should be running.

### Broadcast receivers
- A broadcast receiver is a component that enables the system to deliver events to the app outside of a regular user flow, allowing the app to respond to system-wide broadcast announcements. Because broadcast receivers are another well-defined entry into the app, the system can deliver broadcasts even to apps that aren't currently running. So, for example, an app can schedule an alarm to post a notification to tell the user about an upcoming event... and by delivering that alarm to a BroadcastReceiver of the app, there is no need for the app to remain running until the alarm goes off. Although broadcast receivers don't display a user interface, they may create a status bar notification to alert the user when a broadcast event occurs.

### Content providers
- A content provider manages a shared set of app data that you can store in the file system, in a SQLite database, on the web, or on any other persistent storage location that your app can access. Through the content provider, other apps can query or modify the data if the content provider allows it. To the system, a content provider is an entry point into an app for publishing named data items, identified by a URI scheme. Thus an app can decide how it wants to map the data it contains to a URI namespace, handing out those URIs to other entities which can in turn use them to access the data.

- The system only needs to make sure that an owning app is still running when it has to retrieve the app's data from the corresponding URI. When a second app attempts to access that URI on the clipboard, the system can allow that app to access the data via a temporary URI permission grant so that it is allowed to access the data only behind that URI, but nothing else in the second app. Content providers are also useful for reading and writing data that is private to your app and not shared.


## Activating components
- An intent is created with an Intent object, which defines a message to activate either a specific component or a specific type of component . For activities and services, an intent defines the action to perform and may specify the URI of the data to act on, among other things that the component being started might need to know. For example, an intent might convey a request for an activity to show an image or to open a web page. In some cases, you can start an activity to receive a result, in which case the activity also returns the result in an Intent.

- For example, you can issue an intent to let the user pick a personal contact and have it returned to you. The return intent includes a URI pointing to the chosen contact. For broadcast receivers, the intent simply defines the announcement being broadcast.

- There are separate methods for activating each type of component

- You can start an activity or give it something new to do by passing an Intent to startActivity or startActivityForResult . You can bind to the service by passing an Intent to bindService. You can initiate a broadcast by passing an Intent to methods such as sendBroadcast, sendOrderedBroadcast, or sendStickyBroadcast. You can perform a query to a content provider by calling query on a ContentResolver.

### The manifest file

- Before the Android system can start an app component, the system must know that the component exists by reading the app's manifest file, AndroidManifest.

- Identifies any user permissions the app requires, such as Internet access or read-access to the user's contacts.
- Declares the minimum API Level required by the app, based on which APIs the app uses.

## App resources

- Using app resources makes it easy to update various characteristics of your app without modifying code. Providing sets of alternative resources enables you to optimize your app for a variety of device configurations, such as different languages and screen sizes. For every resource that you include in your Android project, the SDK build tools define a unique integer ID, which you can use to reference the resource from your app code or from other resources defined in XML. For example, if your app contains an image file named logo , the SDK tools generate a resource ID named R. This ID maps to an app-specific integer, which you can use to reference the image and insert it in your user interface.

- One of the most important aspects of providing resources separate from your source code is the ability to provide alternative resources for different device configurations. When the device screen is in portrait orientation , you might want a layout with buttons to be vertical, but when the screen is in landscape orientation , the buttons could be aligned horizontally. To change the layout depending on the orientation, you can define two different layouts and apply the appropriate qualifier to each layout's directory name. Then, the system automatically applies the appropriate layout depending on the current device orientation.

- For more about the different kinds of resources you can include in your application and how to create alternative resources for different device configurations, read Providing Resources.