# Intent Filters
## Allowing Other Apps to Start Your Activity
- intent filter is useful for your app if you need it to request for specific action.
- for use it you need to add an `<intent-filter>` element in your manifest file for the corresponding `<activity>` element.

## Add an Intent Filter
- each intent filter we add should be as specific as possible in terms of the type of action and data the activity accept
- intent filter fulfills the following criteria of the Intent object:
    - Action : A string naming the action to perform. 
    - Data : A description of the data associated with the intent.
    - Category : Provides an additional way to characterize the activity handling the intent

- Each incoming intent specifies only one action and one data type

## Handle the Intent in Your Activity
- As your activity starts, call getIntent() to retrieve the Intent that started the activity

## Return a Result
- If you want to return a result to the activity that invoked yours

- for more data you can visit [Intent Filters](https://developer.android.com/training/basics/intents/filters)