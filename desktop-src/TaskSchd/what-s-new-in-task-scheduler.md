---
title: What's New in Task Scheduler
description: List of new functionality introduced by different versions of Task Scheduler.
ms.assetid: 43fbbbd2-6e97-4ba5-9474-23c5e2b33612
keywords:
- Task Scheduler Task Scheduler , what's new
ms.topic: article
ms.date: 05/31/2018
---

# What's New in Task Scheduler

The following changes summarize what is new in different versions of Task Scheduler.

## Windows 10

The following Task Scheduler changes are introduced in Windows 10:

-   When battery saver is on, Windows Task Scheduler tasks are triggered only if the task is:

    -   Not set to **Start the task only if the computer is idle...** (task doesn't use [**IdleSettings**](/windows/desktop/api/taskschd/nf-taskschd-itasksettings-get_idlesettings))
    -   Not set to run during automatic maintenance (task doesn't use [**MaintenanceSettings**](/windows/desktop/api/Taskschd/nf-taskschd-itasksettings3-get_maintenancesettings))
    -   Is set to **Run only when user is logged on** (task [**LogonType**](/windows/desktop/api/taskschd/nf-taskschd-iprincipal-get_logontype) is **TASK\_LOGON\_INTERACTIVE\_TOKEN** or **TASK\_LOGON\_GROUP**)

    All other triggers are delayed until battery saver is off. For more information about accessing battery saver status in your application, see [**SYSTEM\_POWER\_STATUS**](https://docs.microsoft.com/windows/desktop/api/winbase/ns-winbase-system_power_status). For general information about battery saver, see [battery saver (in the hardware component guidelines)](https://docs.microsoft.com/windows-hardware/design/component-guidelines/battery-saver).

## Windows 8

The following Task Scheduler 2.0 changes are introduced in Windows 8:

-   Powershell support: users can manage (create, delete, modify, explicitly start, stop etc.) Windows Task Scheduler tasks using the ScheduledTasks powershell module.
-   Managed passwords: administrators can use the Active Directory managed password accounts as task principals. These tasks no longer require an enforced password reset policy.
-   API changes: Introduced two new task settings with the [**ITaskSettings3**](/windows/desktop/api/taskschd/nn-taskschd-itasksettings3) interface.
    -   [**MaintenanceSettings**](/windows/desktop/api/Taskschd/nf-taskschd-itasksettings3-get_maintenancesettings): tasks using these settings are treated as a new type of scheduled tasks that are invoked during OS automatic maintenance time, according to the specified periodicity and deadline.
    -   [**Volatile**](/windows/desktop/api/Taskschd/nf-taskschd-itasksettings3-get_volatile): tasks that are set to be volatile are always disabled on an OS boot and must be explicitly re-enabled back when required. Volatile tasks are utilized by the failover clusters to ensure only one task instance is scheduled on a cluster at a time.
-   The unified scheduling engine now supports the following features:
    -   S4U Logon type, through the [**LogonType**](taskschedulerschema-logontype-principaltype-element.md) element.
    -   XPath query values for event triggers, through the [**ValueQueries**](taskschedulerschema-valuequeries-eventtriggertype-element.md) element.
    -   Do not allow task hard terminate, through the [**AllowHardTerminate**](taskschedulerschema-allowhardterminate-settingstype-element.md) element.
-   Features deprecated in this release
    -   Action: [**sendEmail**](taskschedulerschema-sendemail-actiongroup-element.md) (you can use [**IExecAction**](/windows/desktop/api/taskschd/nn-taskschd-iexecaction) with the [Windows PowerShell](https://technet.microsoft.com/library/bb978526.aspx)[Send-MailMessage](https://technet.microsoft.com/library/hh849925.aspx) cmdlet as a workaround).
    -   Action: [**showMessage**](taskschedulerschema-showmessage-actiongroup-element.md).
    -   AT.exe cmdline utility

## Windows 7

The following Task Scheduler 2.0 changes are introduced in Windows 7:

-   Using the unified scheduling engine provided by the underlying operating system.
-   Ability to reject starting tasks in Remote Applications Integrated Locally (RAIL) sessions.
-   Task security hardening (for tasks running as "NETWORK SERVICE" or "LOCAL SERVICE" only):

    -   Ability to assign a process token security identifier (SID) type (for example, unrestricted or none) to a task.
    -   Allow task developers to request the exact set of privileges that their task requires.

-   API changes:

    -   Task security hardening support: new task security hardening feature is introduced with new IPrincipal2 interface.
    -   Introduced two new task settings with the new ITaskSettings2 interface.

        -   DisallowStartOnRemoteAppSession: The new DisallowStartOnRemoteAppSession setting can reject a task start if triggered in [Remote Applications Integrated Locally (RAIL)](https://go.microsoft.com/fwlink/p/?linkid=168157) sessions.
        -   UseUnifiedSchedulingEngine: Using the UseUnifiedSchedulingEngine setting provides a cohesive behavior for Windows Tasks and Services because it is being managed in a uniform manner by a common system-wide scheduling engine. Although using a unified engine is recommended, it does not support some of the Task Scheduler features. If the combination of properties will not allow running of the task under a unified engine, the registration of such will be rejected.
        -   The task features that are not supported by the unified scheduling engine include:

            -   Logon types:

                -   [TASK\_LOGON\_INTERACTIVE\_TOKEN\_OR\_PASSWORD](https://go.microsoft.com/fwlink/p/?linkid=168159)

            -   Multiple instance policy:

                -   [**TASK\_INSTANCES\_STOP\_EXISTING**](taskschedulerschema-multipleinstancespolicy-settingstype-element.md)

            -   Actions:

                -   [Send email](https://go.microsoft.com/fwlink/p/?linkid=168161)
                -   [Display message](https://go.microsoft.com/fwlink/p/?linkid=168164)

            -   Settings:

                -   [Task network settings](https://go.microsoft.com/fwlink/p/?linkid=168166)
                -   [Do not allow task hard terminate](https://go.microsoft.com/fwlink/p/?linkid=168167)

            -   Triggers:

                -   [Trigger execution time limit](https://go.microsoft.com/fwlink/p/?linkid=168168)
                -   [Repetition patterns for calendar triggers]( https://go.microsoft.com/fwlink/p/?linkid=168169)
                -   [XPath query values for event triggers]( https://go.microsoft.com/fwlink/p/?linkid=168170)
                -   [Monthly](https://go.microsoft.com/fwlink/p/?linkid=168171) and [Monthly day-of-week](https://go.microsoft.com/fwlink/p/?linkid=168173) trigger types

## Windows Vista

The Task Scheduler 2.0 API should be used in developing applications that use the Task Scheduler service on Windows Vista. For more information, see [Task Scheduler Reference](task-scheduler-reference.md) and [Using the Task Scheduler](using-the-task-scheduler.md).

## Windows 2000, Windows XP, and Windows Server 2003

The Task Scheduler 2.0 API is not available. Use Task Scheduler 1.0.

## Related topics

<dl> <dt>

[Task Scheduler](task-scheduler-start-page.md)
</dt> <dt>

[About The Task Scheduler](about-the-task-scheduler.md)
</dt> </dl>

 

 




