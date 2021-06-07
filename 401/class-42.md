# Location
- to use location in our app we need google service 
- Specifically, we need the fused location provider to retrieve the device's last known location.
- is one of the location APIs in Google Play services

## Set up Google Play services
- we must include Google Play services
- Download and install the Google Play services component via the SDK Manager and add the library to your project
- see the guide to [Setting Up Google Play Services](https://developers.google.com/android/guides/setup)

## Specify app permissions
- also we had to add permissions in our manifest file 
- ` <uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />`

## Create location services client
- in MainActivity  create an instance of the Fused Location Provider Client
- `fusedLocationClient = LocationServices.getFusedLocationProviderClient(this);`


## Get the last known location
- after we create Location Services we can get the last known location of a user's device by using ` getLastLocation()` method to retrieve the device location

## Maintain a current best estimate
- To validate the accuracy of a location that's returned from getLastLocation(), complete steps that include the following:

    - Check whether the location retrieved is significantly newer than the previously fetched location.
    - Check whether the accuracy claimed by the location is better or worse than that of the previous estimate.
    - Check the provider that's associated with the new location. Decide whether you trust this provider more than the one used in your app's cached location.