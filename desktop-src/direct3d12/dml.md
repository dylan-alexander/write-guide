﻿---
title: Direct Machine Learning (DirectML)
description: Direct Machine Learning (DirectML) is a low-level API for machine learning. It has a familiar (native C++, nano-COM) programming interface and workflow in the style of DirectX 12.
ms.custom: Windows 10 May 2019 Update
ms.localizationpriority: high
ms.topic: article
ms.date: 04/19/2019
---

# Direct Machine Learning (DirectML)

Direct Machine Learning (DirectML) is a low-level API for machine learning. It has a familiar (native C++, nano-COM) programming interface and workflow in the style of DirectX 12. You can integrate machine learning inferencing workloads into your game, engine, middleware, backend, or other application. DirectML is supported by all DirectX 12-compatible hardware.

DirectML is introduced in Windows 10, version 1903, and in the corresponding version of the Windows SDK.

## In this section

| Topic | Description |
|-|-|
| [Introduction to DirectML](dml-intro.md) | Direct Machine Learning (DirectML) is a low-level API for machine learning (ML). |
| [Binding in DirectML](dml-binding.md) | In DirectML, *binding* refers to the attachment of resources to the pipeline for the GPU to use during the initialization and execution of your machine learning operators. These resources can be input and output tensors, for example, as well as any temporary or persistent resources that the operator needs. |
| [UAV barriers and resource state barriers in DirectML](dml-barriers.md) | Describes the correctness benefits of barriers, and how you can work with them in DirectML. |
| [Using strides to express padding and memory layout](dml-strides.md) | DirectML tensors are described by properties known as the *sizes* and the *strides* of the tensor. |
| [Resource lifetime and synchronization](dml-resource-lifetime.md) | In order to avoid undefined behavior, your DirectML application must correctly manage object lifetimes and synchronization between the CPU and the GPU. |
| [Using the DirectML debug layer](dml-debug-layer.md) | The DirectML debug layer is an optional development-time component that helps you in debugging your DirectML code. |
| [Handling errors and device-removal](dml-errors.md) | This topic discusses how to debug DirectML device-removal, and other error conditions. |
| [DirectML helper functions](dml-helper-functions.md) | Code listings of essential DirectML helper functions. |
| [DirectML sample applications](dml-min-app.md) | Links to DirectML sample applications, including a sample of a minimal DirectML application. |

## Related topics

* [Direct3D 12 programming guide](directx-12-programming-guide.md)
