# UNITY 
![](https://unity.com/logo-unity-web.png)


Unity is a cross-platform game engine developed by Unity Technologies, first announced and released in June 2005 at Apple Inc.'s Worldwide Developers Conference as a Mac OS X-exclusive game engine. 
As of 2018, the engine had been extended to support more than 25 platforms.



## About AR Foundation

AR Foundation allows you to work with augmented reality platforms in a multi-platform way within Unity.

AR Foundation is a set of MonoBehaviours and APIs for dealing with devices that support following concepts:

    World tracking: track the device's position and orientation in physical space.
    Plane detection: detect horizontal and vertical surfaces.
    Point clouds, also known as feature points.
    Reference points: an arbitrary position and orientation that the device tracks.
    Light estimation: estimates for average color temperature and brightness in physical space.
    Environment probes: a means for generating a cube map to represent a particular area of the physical environment.
    Face tracking: detect and track human faces.
    Image tracking: detect and track 2D images.
    Object tracking: detect 3D objects.

If you are migrating from AR Foundation 1.0, see the Migration Guide.
Subsystems

AR Foundation is built on subsystems. A "subsystem" is a platform-agnostic interface for surfacing different types of information. The AR-related subsystems are defined in the AR Subsystems package and use the namespace UnityEngine.XR.ARSubsystems. You will occasionally need to interact with the types in the AR Subsystems package.

Each subsystem handles some specific functionality. For example, the plane detection interface is provided by the XRPlaneSubsystem.
Providers

A "provider" is a concrete implementation of a subsystem. For example, the ARCore XR Plugin package contains the ARCore implementation for many of the AR subsystems.

Because different providers have varying support for specific features, each subsystem also has a descriptor that indicates which specific subsystem features it supports. For example, the XRPlaneSubsystemDescriptor contains properties indicating whether horizontal or vertical plane detection is supported.

While it is up to the providers to determine how they will implement each subsystem, in general they are wrapping that platform's native SDK (e.g., ARKit on iOS and ARCore on Android).
Installing AR Foundation

To install this package, follow the instructions in the Package Manager documentation.

Subsystems are implemented in other packages, so to use AR Foundation, you will also need to install at least one platform-specific AR package (Window > Package Manager):

    ARKit XR Plugin
    ARCore XR Plugin

## Glossary
Term 	Meaning
Tracking 	The ability of the AR device to determine its relative position and orientation in the world. If the environment is too dark, for example, the device may "lose tracking", which means it can no longer accurately report its position.
Trackable 	A real-world feature detected and/or tracked by the AR device, e.g., a planar surface.
Feature Point 	A specific point in a point cloud. AR devices use a camera and image analysis to track specific points in the world which are used to build a map of its environment. These are usually high frequency elements, such as a knot in a wood-grain surface.
Session 	Refers to an AR instance.
Session Space 	The coordinate system relative to the beginning of the AR session. For example, session space (0, 0, 0) refers to the position at which the AR session was created. An AR device typically reports trackables and tracking information relative to its session origin.
