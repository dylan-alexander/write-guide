---
Description: The RealTimeStylus object is designed to provide real-time access to the data stream from the tablet pen.
ms.assetid: 7217e2d5-ca62-4d65-bf22-9511b367c798
title: Plug-ins and the RealTimeStylus Class
ms.topic: article
ms.date: 05/31/2018
---

# Plug-ins and the RealTimeStylus Class

The [**RealTimeStylus**](realtimestylus-class.md) object is designed to provide real-time access to the data stream from the tablet pen. Plug-ins, objects that implement the [**IStylusSyncPlugin**](https://msdn.microsoft.com/en-us/library/ms704312(v=VS.85).aspx) or [**IStylusAsyncPlugin**](https://msdn.microsoft.com/en-us/library/ms702522(v=VS.85).aspx) interface, can be added to a **RealTimeStylus** object. Synchronous plug-ins are generally called directly by the **RealTimeStylus** object on a high-priority thread, while asynchronous plug-ins are generally called on the application's user interface (UI) thread. Create or use synchronous plug-ins for tasks that require real-time access to the data stream and are computationally undemanding, such as packet filtering. Create or use asynchronous plug-ins for tasks that do not require real-time access to the data stream, such as ink collection.

Certain tasks may be computationally demanding yet require real-time access to the data stream, such as multistroke gesture recognition. To address these needs, the StylusInput APIs provide a cascaded [**RealTimeStylus**](realtimestylus-class.md) model that allows you to use two **RealTimeStylus** objects, each running on its own thread. For more information about the cascaded **RealTimeStylus** model, see [The Cascaded RealTimeStylus Model](the-cascaded-realtimestylus-model.md).

Both the [**IStylusSyncPlugin**](https://msdn.microsoft.com/en-us/library/ms704312(v=VS.85).aspx) and [**IStylusAsyncPlugin**](https://msdn.microsoft.com/en-us/library/ms702522(v=VS.85).aspx) interfaces define the same methods. These methods allow the [**RealTimeStylus**](realtimestylus-class.md) object to pass the pen data to each plug-in, regardless of whether it is an asynchronous or synchronous plug-in. The [Microsoft.StylusInput.IStylusSyncPlugin.DataInterest](https://msdn.microsoft.com/library/ms824752(v=MSDN.10).aspx) and [Microsoft.StylusInput.IStylusAsyncPlugin.DataInterest](https://msdn.microsoft.com/library/ms824769(v=MSDN.10).aspx) properties allow each plug-in to subscribe to specific data in the tablet pen data stream. A plug-in should only subscribe to the data necessary to perform its task, minimizing performance demands. For more information about threading and the **RealTimeStylus** class, see [Threading Considerations for the StylusInput APIs](threading-considerations-for-the-stylusinput-apis.md).

The [**RealTimeStylus**](realtimestylus-class.md) object uses objects in the [Microsoft.StylusInput.PluginData](https://msdn.microsoft.com/library/ms823992(v=MSDN.10).aspx) namespace to pass the pen data to its plug-ins. The **RealTimeStylus** also catches exceptions thrown by plug-ins. When the **RealTimeStylus** catches exceptions, it notifies the plug-ins by calling the [IStylusSyncPlugin.Error](https://msdn.microsoft.com/library/ms824754(v=MSDN.10).aspx) or [IStylusAsyncPlugin.Error](https://msdn.microsoft.com/library/ms824771(v=MSDN.10).aspx) method. For more information about using plug-in data, see [Plug-in Data and the RealTimeStylus](plug-in-data-and-the-realtimestylus-class.md) Class. For more information about error handling, see [Error Handling Considerations for the StylusInput APIs](error-handling-considerations-for-the-stylusinput-apis.md) and the Error Data section of Plug-in Data and the RealTimeStylus Class.

> [!Note]  
> At least one plug-in must be attached to the [**RealTimeStylus**](realtimestylus-class.md) object before the **RealTimeStylus** object can be enabled.

 

The following topics describe some common categories of plug-ins.

-   [Ink-Collection Plug-ins](ink-collection-plug-ins.md)
-   [Dynamic-Renderer Plug-ins](dynamic-renderer-plug-ins.md)
-   [Recognizer Plug-ins](recognizer-plug-ins.md)

## Special Considerations

Because of the complex nature of the [**RealTimeStylus**](realtimestylus-class.md) object, you should take note of the following.

The [**RealTimeStylus**](realtimestylus-class.md) object throws an exception if a plug-in modifies the plug-in collection to which it is attached. This happens only when the plug-in does so while it is being called by the **RealTimeStylus** object as a member of that collection.

The following C\# example is code that causes the [**RealTimeStylus**](realtimestylus-class.md) object to throw an exception.


```C++
using Microsoft.Ink;
using Microsoft.StylusInput;
using Microsoft.StylusInput.PluginData;

// ...
public class thePlugin : Microsoft.StylusInput.IStylusAsyncPlugin
{
    // ...

    // Called when a system gesture occurs.
    public void SystemGesture(RealTimeStylus sender, SystemGestureData data)
    {
        // The following line will cause the realtime stylus that calls this method
        // to throw an exception.
        sender.Dispose();
    }
    
    // ...
}
```



The [**RealTimeStylus**](realtimestylus-class.md) object throws an exception if a plug-in calls the **RealTimeStylus** object's [Dispose](https://msdn.microsoft.com/library/ms825891(v=MSDN.10).aspx) method. This happens only when the plug-in does so while it is being called by the **RealTimeStylus** object.

The following C\# example is code that causes the [**RealTimeStylus**](realtimestylus-class.md) object to throw an exception.


```C++
using Microsoft.Ink;
using Microsoft.StylusInput;
using Microsoft.StylusInput.PluginData;

// ...
public class thePlugin : Microsoft.StylusInput.IStylusAsyncPlugin
{
    Microsoft.StylusInput.GestureRecognizer theGestureRecognizer;

    // ...

    // Called when a system gesture occurs.
    public void SystemGesture(RealTimeStylus sender, SystemGestureData data)
    {
        // The following line will cause the realtime stylus that calls this method
        // to throw an exception.
        sender.AsyncPluginCollection.Add(this.theGestureRecognizer);
    }
    
    // ...
}
```



Plug-in collections can be modified while the [**RealTimeStylus**](realtimestylus-class.md) object is enabled; however, this can make the behavior of your application harder to predict. When a plug-in is added while the **RealTimeStylus** object is enabled, the **RealTimeStylus** object calls the plug-in's [IStylusAsyncPlugin.RealTimeStylusEnabled](https://msdn.microsoft.com/library/ms824775(v=MSDN.10).aspx) or [IStylusSyncPlugin.RealTimeStylusEnabled](https://msdn.microsoft.com/library/ms824758(v=MSDN.10).aspx) method. When a plug-in is removed while the **RealTimeStylus** object is enabled, the **RealTimeStylus** object calls the plug-in's [IStylusAsyncPlugin.RealTimeStylusDisabled](https://msdn.microsoft.com/library/ms824774(v=MSDN.10).aspx) or [IStylusSyncPlugin.RealTimeStylusDisabled](https://msdn.microsoft.com/library/ms824757(v=MSDN.10).aspx) method. This allows the plug-in to maintain its proper state without having to check the [Enabled](https://msdn.microsoft.com/library/ms824832(v=MSDN.10).aspx) property of the **RealTimeStylus** object.

When a plug-in is added while the [**RealTimeStylus**](realtimestylus-class.md) object is enabled, the plug-in data that the plug-in receives may not contain enough information to adequately establish the context of the initial data. For example, the newly added plug-in could start receiving packet data from a pen that is mid-stroke. Similarly, when a plug-in removed while the **RealTimeStylus** object is enabled, the plug-in data that the plug-in has received may be insufficient to finish processing the data.

> [!Note]  
> For overall stability, reset a plug-in's internal state when either its [**RealTimeStylusEnabled**](/windows/desktop/api/RTSCom/nf-rtscom-istylusplugin-realtimestylusenabled) or [**RealTimeStylusDisabled**](/windows/desktop/api/RTSCom/nf-rtscom-istylusplugin-realtimestylusdisabled) method is called.

 

## Related topics

<dl> <dt>

[The Cascaded RealTimeStylus Model](the-cascaded-realtimestylus-model.md)
</dt> <dt>

[Error Handling Considerations for the StylusInput APIs](error-handling-considerations-for-the-stylusinput-apis.md)
</dt> <dt>

[Plug-in Data and the RealTimeStylus Class](plug-in-data-and-the-realtimestylus-class.md)
</dt> <dt>

[Threading Considerations for the StylusInput APIs](threading-considerations-for-the-stylusinput-apis.md)
</dt> </dl>

 

 



