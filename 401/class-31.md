# Espresso
![images](https://i.ytimg.com/vi/7kMvjeNkz2g/maxresdefault.jpg)

- Espresso is a testing framework for Android to make it easy to write reliable user interface test

- Espresso has basically three components:

    1. ViewMatchers - allows to find view in the current view hierarchy

    2. ViewActions - allows to perform actions on the views

    3. ViewAssertions - allows to assert state of a view

- you can only perform black box testing, as you cannot access the classes outside of your application

### Features of Espresso
1. Very simple API and so, easy to learn.
2. Highly scalable and flexible.
3. Provides separate module to test Android WebView component.
4. Provides separate module to validate as well as mock Android Intents.
5. Provides automatic synchronization between your application and tests.

### Advantages of Espresso
1. Backward compatibility
2. Easy to setup.
3. Highly stable test cycle.
4. Supports testing activities outside application as well.
5. Supports JUnit4
6. UI automation suitable for writing black box tests.

# Create UI tests with Espresso Test Recorder
- Android studio provides a feature to record and generate espresso test cases. Record Espresso Test is available under the Run menu.
- so you can record your interactions with a device by using  The Espresso Test Recorder.

- to record a simple test case using Espresso Test Recorder
    1. Click Run > Record Espresso Test.
    2. In the Select Deployment Target window, choose the device on which you want to record the test
    3.  The Record Your Test window appears after the app launches.

- Save a recording
    1. Click Complete Recording. The Pick a test class name for your test window appears.
    2. unique name for each test case based on activity name.
    3. The file automatically opens after Espresso Test Recorder generates it


