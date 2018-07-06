# Radar Ionic Plugin

[Radar](https://radar.io/) is a location platform for mobile apps.

## Available Radar Functions

- Tracking
- Stop Tracking
- Set UserID
- Get Permission
- Check Permissions

## Installation

------



## Usage

------

#### Setting up Radar Keys

For Android, under `src -> android -> com -> Radar` in `Radar.java`, add your Radar Key in the initialize method

```java
public void initialize(CordovaInterface cordova, CordovaWebView webView) {
    super.initialize(cordova, webView);
    Context context = this.cordova.getActivity().getApplicationContext();
    Radar.initialize(context, "your_radar_key");
    Log.d(TAG, "Initializing Radar Plugin");
  }
```

For iOS, under `ios` in `RadarWrapper.swift`, add your Radar Key in the pluginInitialize function

```swift
override func pluginInitialize() {
      Radar.initialize(publishableKey: "your_radar_key");
}
```

------

#### Declaring Cordova

On whichever page you want to use the Radar plugin, you can declare `cordova` just below your exports, as follows:

```typescript
declare var cordova: any;
```

------

#### Start Tracking

When you want to begin tracking the user's location in the background, simply call the start tracking method:

```typescript
cordova.plugins.RadarPlugin.startTracking(value => {
});
```

------

#### Stop Tracking

To stop background location tracking, run:

```typescript
cordova.plugins.RadarPlugin.stopTracking(value => {
});
```

------

#### Set User ID

If you want to give users a customized user ID rather than the one generated by Radar, you can do it by running the following:

```typescript
cordova.plugins.RadarPlugin.stopTracking(userID, value => {
});
```

------

#### Check Permission

Check if the app has location permission:

```typescript
cordova.plugins.RadarPlugin.checkPermissions();
```

------

#### Get Permission

Ask the user for location permission:

```typescript
cordova.plugins.RadarPlugin.checkPermissions();
```
