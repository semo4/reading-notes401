# Notification
- A notification is a message you can display to the user outside of your application's normal UI.

## Create and Send Notifications
- Step 1 - Create Notification Builder
    - ou will use Notification Builder to set various Notification properties like its small and large icons, title, priority etc.

- Step 2 - Setting Notification Properties
    -  you can set its Notification properties using Builder object
        - setSmallIcon(): It sets the icon of notification.
        - setContentTitle(): It is used to set the title of notification.
        - setContentText(): It is used to set the text message.
        - setAutoCancel(): It sets the cancelable property of notification.
        - setPriority(): It sets the priority of notification.

- Step 3 - Attach Actions
    - This is an optional part and required if you want to attach an action with the notification.
    - The action is defined by a PendingIntent containing an Intent that starts an Activity in your application
    - A PendingIntent object helps you to perform an action on your applications behalf

- Step 4 - Issue the notification
    - Finally, you pass the Notification object to the system by calling NotificationManager.notify() to send your notification



## Amazon SNS
- Amazon provide a system to send notification and messages called Simple Notification Service (SNS
- for more details and to getStarted with it you can visit 
[SNS: Getting Started](https://aws.amazon.com/sns/getting-started/)