---
Description: The following example creates a timer routine that will be executed by a thread from a timer queue after a 10 second delay.
ms.assetid: 779156fe-f825-452b-acbe-e2cb189e24d2
title: Using Timer Queues
ms.topic: article
ms.date: 05/31/2018
---

# Using Timer Queues

The following example creates a timer routine that will be executed by a thread from a [timer queue](timer-queues.md) after a 10 second delay. First, the code uses the [**CreateEvent**](https://msdn.microsoft.com/en-us/library/ms682396(v=VS.85).aspx) function to create an event object that is signaled when the timer-queue thread completes. Then it creates a timer queue and a timer-queue timer, using the [**CreateTimerQueue**](https://msdn.microsoft.com/en-us/library/ms682483(v=VS.85).aspx) and [**CreateTimerQueueTimer**](https://msdn.microsoft.com/en-us/library/ms682485(v=VS.85).aspx) functions, respectively. The code uses the [**WaitForSingleObject**](https://msdn.microsoft.com/en-us/library/ms685061(v=VS.85).aspx) function to determine when the timer routine has completed. Finally, the code calls [**DeleteTimerQueue**](/windows/desktop/api/WinBase/nf-winbase-deletetimerqueue) to clean up.

For more information on the timer routine, see [**WaitOrTimerCallback**](https://msdn.microsoft.com/en-us/library/ms687066(v=VS.85).aspx).


```C++
#include <windows.h>
#include <stdio.h>

HANDLE gDoneEvent;

VOID CALLBACK TimerRoutine(PVOID lpParam, BOOLEAN TimerOrWaitFired)
{
    if (lpParam == NULL)
    {
        printf("TimerRoutine lpParam is NULL\n");
    }
    else
    {
        // lpParam points to the argument; in this case it is an int

        printf("Timer routine called. Parameter is %d.\n", 
                *(int*)lpParam);
        if(TimerOrWaitFired)
        {
            printf("The wait timed out.\n");
        }
        else
        {
            printf("The wait event was signaled.\n");
        }
    }

    SetEvent(gDoneEvent);
}

int main()
{
    HANDLE hTimer = NULL;
    HANDLE hTimerQueue = NULL;
    int arg = 123;

    // Use an event object to track the TimerRoutine execution
    gDoneEvent = CreateEvent(NULL, TRUE, FALSE, NULL);
    if (NULL == gDoneEvent)
    {
        printf("CreateEvent failed (%d)\n", GetLastError());
        return 1;
    }

    // Create the timer queue.
    hTimerQueue = CreateTimerQueue();
    if (NULL == hTimerQueue)
    {
        printf("CreateTimerQueue failed (%d)\n", GetLastError());
        return 2;
    }

    // Set a timer to call the timer routine in 10 seconds.
    if (!CreateTimerQueueTimer( &hTimer, hTimerQueue, 
            (WAITORTIMERCALLBACK)TimerRoutine, &arg , 10000, 0, 0))
    {
        printf("CreateTimerQueueTimer failed (%d)\n", GetLastError());
        return 3;
    }

    // TODO: Do other useful work here 

    printf("Call timer routine in 10 seconds...\n");

    // Wait for the timer-queue thread to complete using an event 
    // object. The thread will signal the event at that time.

    if (WaitForSingleObject(gDoneEvent, INFINITE) != WAIT_OBJECT_0)
        printf("WaitForSingleObject failed (%d)\n", GetLastError());

    CloseHandle(gDoneEvent);

    // Delete all timers in the timer queue.
    if (!DeleteTimerQueue(hTimerQueue))
        printf("DeleteTimerQueue failed (%d)\n", GetLastError());

    return 0;
}
```



 

 



