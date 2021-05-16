# Understand Tasks and Back Stack
- A task is a collection of activities that users interact with when performing a certain job. When the user selects a message, a new activity opens to view that message. This new activity is added to the back stack. If the user presses the Back button, that new activity is finished and popped off the stack.

- When the user touches an icon in the app launcher , that app's task comes to the foreground. If no task exists for the app , then a new task is created and the «main» activity for that app opens as the root activity in the stack. When the current activity starts another, the new activity is pushed on the top of the stack and takes focus. The previous activity remains in the stack, but is stopped.

- When an activity stops, the system retains the current state of its user interface. When the user presses the Back button, the current activity is popped from the top of the stack and the previous activity resumes . Figure 1 visualizes this behavior with a timeline showing the progress between activities along with the current back stack at each point in time. A representation of how each new activity in a task adds an item to the back stack.

- When the user presses the Back button, the current activity is destroyed and the previous activity resumes. If the user continues to press Back, then each activity in the stack is popped off to reveal the previous one, until the user returns to the Home screen . When all activities are removed from the stack, the task no longer exists. The user presses the Home button, then starts a new app from the app launcher.

- When the new app starts, the system starts a task for that app with its own stack of activities. After interacting with that app, the user returns Home again and selects the app that originally started Task A. At this point, the user can also switch back to Task B by going Home and selecting the app icon that started that task .

- As such, one activity in your app might be instantiated multiple times , as shown in figure 3. As such, if the user navigates backward using the Back button, each instance of the activity is revealed in the order they were opened . However, you can modify this behavior if you do not want an activity to be instantiated more than once.

## Managing Tasks
- The way Android manages tasks and the back stack, as described above—by placing all activities started in succession in the same task and in a «last in, first out» stack—works great for most apps and you shouldn't have to worry about how your activities are associated with tasks or how they exist in the back stack.
- In this regard, the principal <activity> attributes you can use are:

1. taskAffinity
2. launchMode
3. allowTaskReparenting
4. clearTaskOnLaunch
5. alwaysRetainTaskState
6. finishOnTaskLaunch
- And the principal intent flags you can use are:

1. FLAG_ACTIVITY_NEW_TASK
2. FLAG_ACTIVITY_CLEAR_TOP
3. FLAG_ACTIVITY_SINGLE_TOP

## Defining launch modes
- Using the manifest file
    - When you declare an activity in your manifest file, you can specify how the activity should associate with tasks when it starts.

- Using Intent flags
    - When you call startActivity(), you can include a flag in the Intent that declares how (or whether) the new activity should associate with the current task.


## Clearing the back stack
- alwaysRetainTaskState
    - The task retains all activities in its stack even after a long period.

- clearTaskOnLaunch
    - If this attribute is set to «true» in the root activity of a task, the task is cleared down to the root activity whenever the user leaves the task and returns to it. The user always returns to the task in its initial state, even after leaving the task for only a moment.

- finishOnTaskLaunch
    - This attribute is like clearTaskOnLaunch, but it operates on a single activity, not an entire task. When it's set to «true», the activity remains part of the task only for the current session.


# SharedPreferences
- A SharedPreferences object points to a file containing key-value pairs and provides simple methods to read and write them. Each SharedPreferences file is managed by the framework and can be private or shared.

## Get a handle to shared preferences
- You can create a new shared preference file or access an existing one by calling one of these methods:

- getSharedPreferences() — Use this if you need multiple shared preference files identified by name, which you specify with the first parameter. You can call this from any Context in your app.
- getPreferences() — Use this from an Activity if you need to use only one shared preference file for the activity. Because this retrieves a default shared preference file that belongs to the activity, you don't need to supply a name.