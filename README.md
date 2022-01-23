## A-Frame Marker-Less AR App

This simple web application is to built based on A-Frame API to perform marker less tracking. The user is able to place a box on the targeted surface and change its color by clikcing on it. This app may be generalized to other simple user interactions and effects.

Web page: https://wlicb.github.io/WebXR-app/, it has to run on mobile devices that supports ARCore and browser with molliza core. The testing browser is "XRViewer" downloaded from App Store which supports the viewing of WebXR on iPhone.

Some notes on A-Frame based WebXR:

1. Hit test has to be performed to place virtual objects on real world planes. The API provides `xrHitTestSource` to compute hit tests for each XR frame and `getHitTestResults` method to retrive the hit test result. This app uses the hit test result to check whether a plane is detected. If so, a ring will be set to hit position to prompt the user to place the box on desired position and emit a `hit` event at the same time for other objects to check whether a plane is detected. 
2. To define any behaviours on the objects, the method `AFRAME.registerComponent` is used to define attributes to the objects. The behaviour can be implemented inside the method and the behaviour can be added or removed by adding or removing attributes on the object. In this app, attributes `ar-hit-test` is defined to perform hit test, `hide-in-ar-mode` is defined to hide objects that should not be visible in AR mode, `choose` is defined to enable the user to change the color of the box when clicking on it. 
3. The interactions that can be performed based on A-Frame can achieve simple effects such as change of properties of the objects. Same outcome may be achieved with some other tools such as Adobe Aero or Reality Composer without much coding. 

