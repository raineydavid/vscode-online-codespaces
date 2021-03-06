---
author: nikmd23
ms.author: nimolnar
ms.service: visual-studio-online
title: Visual Studio Codespaces Frequently Asked Questions
ms.topic: overview
ms.date: 05/29/2020
---

# FAQ

## General questions

### What is Visual Studio Codespaces?

Visual Studio Codespaces provides managed, on-demand development environments that can be used for long-term development projects or short-term tasks like pull requests. You can work with environments using Visual Studio Code, Visual Studio 2019 ([sign up for the Private Preview](https://aka.ms/vsfutures-signup)), or the included browser-based editor.

### How does Visual Studio Codespaces relate to Visual Studio Code Remote Development?

Visual Studio Codespaces conceptually and technically extends the [Visual Studio Code Remote Development extensions](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack). You can think of Codespaces's cloud-hosted environments as "Remote Containers as a Service" and it's self-hosted environments as "Remote SSH as a Service".

Visual Studio Codespaces optimizes for productivity by streamlining setup with default configurations. If you're interested in managing your own machines and configuration, see [Visual Studio Code's Remote Development](https://code.visualstudio.com/docs/remote/remote-overview).

### What is running on self-hosted machines to make them accessible?

The Visual Studio Live Share agent runs on self-hosted machines and listens for connections.

### How do I try Visual Studio Codespaces with Visual Studio 2019?

Connecting to a Codespace from Visual Studio 2019 is available through a Private Preview while we scale up the service. You can sign up for the Private Preview by going to the [Visual Studio Codespaces for Visual Studio 2019 signup](https://aka.ms/vsfutures-signup). For more information about Visual Studion 2019 support, see the [Visual Studio Blog](https://aka.ms/vs2019-codespaces-blog).

### Can any Visual Studio client access any Codespace?

We are actively expanding support for more features and workloads across the Visual Studio clients. Not all clients have been upgraded to support all Codespaces. Here is a summary of the Visual Studio clients and the Codespaces they can support.

|                       | Codespace (Windows) | Codespace (Linux) |
|-----------------------|:-------------------:|:-----------------:|
| Visual Studio code    |         ✔         |        ✔         |
| Browser based editor  |         ✔         |        ✔         |
| Visual Studio 2019    |         ✔         |        ❌         |
| Visual Studio for Mac |         ❌         |        ❌         |

### I'm building a service for developers. Can I integrate Visual Studio Codespaces into my own product's experience?

If you're an organization building a service and you want to integrate Visual Studio Codespaces into your experience, we'd like to hear from you. We have an embedded offering in private preview that enables you to use your service's own independent authentication, authorization, and billing systems, while integrating Visual Studio Codespaces directly into your product experience. 

If you're interested, and would like to find out more, please [send us an inquiry](mailto:vscs-inquiry@microsoft.com).

## Security questions

### What do you mean by "repositories you trust"?

Visual Studio Codespaces will clone and utilize the user-provided source and/or dotfile repositories to create and configure your cloud-hosted environment. To avoid unknowingly creating and connecting to an environment with malicious extensions or processes, be sure you understand and trust all repositories referenced during environment creation.

### Where can security issues or concerns be reported?

Visual Studio Codespaces is eligible under the Microsoft Azure Bounty Program. For information, visit <https://www.microsoft.com/msrc/bounty-microsoft-azure>.

## Billing questions

### What is an environment unit? 

Environment units bundle compute, network, snapshot and disk costs together. A Codespaces environment instance is billed on an hourly basis according to a base set of environment units which depend on the environment instance size.  A standard Codespaces environment has a different base rate of environment units than a premium Codespaces environment due to the difference of compute, network, snapshot and disk costs together. While environment pricing is listed in units per hour, usage is calculated per-second (including fractional units), so you only pay for exactly what you use. Find out more at our [pricing page](https://aka.ms/vso-pricing).

### What happens when I'm not using an environment? 

Once created, you can connect to a cloud-hosted environment by opening it in the browser or connecting to it from a client like Visual Studio Code. While connected, the environment is "active". If you disconnect, the environment can automatically move into a "suspended" state until you either connect to it again or delete it. The auto-suspend delay is configurable, or you can disable it if you want more control.

### If I create an environment, use it for 6 minutes, 45 seconds, then delete it, how much do I get billed? 

Time is measured in seconds, so you will be billed for 6 minutes and 45 seconds of active time in environment units. 

### Will I be billed for cloud-hosted environments while I'm not using them? 

Yes, once created, an cloud-hosted environment bills at a nominal base rate until you delete it. Find out more at our [pricing page](https://aka.ms/vso-pricing).

### What are self-hosted environments?  

By default, Codespaces provisions fully managed environments that run in Azure. These environments are backed by the full power of Azure (always available, quick to create, scalable, etc). However, you may also register your own physical or virtualized environment to your Codespaces Plan. This allows you to have some of the benefits of Codespaces (e.g. use of the browser-based editor) while leveraging your existing, potentially specialized, infrastructure.

### What is a Visual Studio Codespaces plan?

All Codespaces environments are created within the confines of a plan. A plan is a simple grouping mechanism, and is also the level of reporting for billing purposes. For example, if you create three environments within a plan named "Foo", your Azure bill will have one Codespaces line item for the plan named "Foo", which would aggregate the costs for all three of its environments. A subscription can have more than one Codespaces plan, up to the default quota.

### What are Visual Studio Codespaces's quotas?

Codespaces, by default, allows users to create 3 environments per plan, and 2 plans per subscription.

### Where can I report an issue with my billing?

Billing support is available online at [https://aka.ms/vso-billing-issues](https://aka.ms/vso-billing-issues).

## Visual Studio questions

### What kinds of apps and projects are supported in Visual Studio and Visual Studio Codespace?

Visual Studio currently supports building .NET Core and C++ applications while connected to a Codespace. In .NET Core you an create Console, Library, and ASP.NET applications. For C++ both CMake and .VCXProj based projects are supported for build Console apps and libraries. We are adding support for many more projects so check back again soon.

> [!NOTE]
> If .NET Core projects fail to load, check whether you have the appropriate .NET Core SDK version installed.
