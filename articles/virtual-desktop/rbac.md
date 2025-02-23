---
title: Built-in Azure RBAC roles Azure Virtual Desktop
description: An overview of built-in Azure RBAC roles for Azure Virtual Desktop available.
services: virtual-desktop
author: Heidilohr
ms.service: virtual-desktop
ms.topic: conceptual
ms.date: 03/22/2022
ms.author: helohr
manager: femila
---
# Built-in Azure RBAC roles for Azure Virtual Desktop

Azure Virtual Desktop uses Azure role-based access control (RBAC) to control access to resources. There are a number of built-in roles for use with Azure Virtual Desktop  which is a collection of permissions. You assign roles to users and admins and these roles give permission to carry out certain tasks. To learn more about Azure RBAC, see [What is Azure RBAC?](../role-based-access-control/overview.md).

The standard built-in roles for Azure are Owner, Contributor, and Reader. However, Azure Virtual Desktop has additional roles that let you separate management roles for host pools, application groups, and workspaces. This separation lets you have more granular control over administrative tasks. These roles are named in compliance with Azure's standard roles and least-privilege methodology.

Azure Virtual Desktop doesn't have a specific Owner role. However, you can use the general Owner role for the service objects.

The built-in roles for Azure Virtual Desktop and the permissions for each one are detailed below. The assignable scope for all built-in roles are set to the root scope ("/"). The root scope indicates that the role is available for assignment in all scopes, for example management groups, subscriptions, or resource groups. For more information, see [Understand Azure role definitions](../role-based-access-control/role-definitions.md).

## Desktop Virtualization Contributor

The Desktop Virtualization Contributor role allows users to manage all aspects of the deployment. However, it doesn't grant users access to compute resources. You'll also need the *User Access Administrator* role to publish application groups to users or user groups.

| Action type | Permissions |
|--|--|
| actions | <ul><li>Microsoft.DesktopVirtualization/\*</li><li>Microsoft.Resources/subscriptions/resourceGroups/read</li><li>Microsoft.Resources/deployments/\*</li><li>Microsoft.Authorization/\*/read</li><li>Microsoft.Insights/alertRules/\*</li><li>Microsoft.Support/\*</li></ul> |
| notActions | None |
| dataActions | None |
| notDataActions | None |

## Desktop Virtualization Reader

The Desktop Virtualization Reader role allows users to view everything in the deployment, but doesn't let them make any changes.

| Action type | Permissions |
|--|--|
| actions | <ul><li>Microsoft.DesktopVirtualization/\*/read</li><li>Microsoft.Resources/subscriptions/resourceGroups/read</li><li>Microsoft.Resources/deployments/read</li><li>Microsoft.Authorization/\*/read</li><li>Microsoft.Insights/alertRules/read</li><li>Microsoft.Support/\*</li></ul> |
| notActions | None |
| dataActions | None |
| notDataActions | None |

## Desktop Virtualization User

The Desktop Virtualization User role allows users to use the applications in an application group.

| Action type | Permissions |
|--|--|
| actions | None |
| notActions | None |
| dataActions | <ul><li>Microsoft.DesktopVirtualization/applicationGroups/useApplications/action</li></ul> |
| notDataActions | None |

## Desktop Virtualization Host Pool Contributor

The Desktop Virtualization Host Pool Contributor role allows users to manage all aspects of host pools, including access to resources. You'll also need the *Virtual Machine Contributor* role to create virtual machines. You will need *Desktop Virtualization Application Group Contributor* and *Desktop Virtualization Workspace Contributor* roles to create host pools using the portal, or you can use the *Desktop Virtualization Contributor* role.

| Action type | Permissions |
|--|--|
| actions | <ul><li>Microsoft.DesktopVirtualization/hostpools/\*</li><li>Microsoft.Resources/subscriptions/resourceGroups/read</li><li>Microsoft.Resources/deployments/\*</li><li>Microsoft.Authorization/\*/read</li><li>Microsoft.Insights/alertRules/\*</li><li>Microsoft.Support/\*</li></ul> |
| notActions | None |
| dataActions | None |
| notDataActions | None |

## Desktop Virtualization Host Pool Reader

The Desktop Virtualization Host Pool Reader role allows users to view everything in the host pool, but won't allow them to make any changes.

| Action type | Permissions |
|--|--|
| actions | <ul><li>Microsoft.DesktopVirtualization/hostpools/\*/read</li><li>Microsoft.DesktopVirtualization/hostpools/read</li><li>Microsoft.Resources/subscriptions/resourceGroups/read</li><li>Microsoft.Resources/deployments/read</li><li>Microsoft.Authorization/\*/read</li><li>Microsoft.Insights/alertRules/read</li><li>Microsoft.Support/\*</li></ul> |
| notActions | None |
| dataActions | None |
| notDataActions | None |

## Desktop Virtualization Application Group Contributor

The Desktop Virtualization Application Group Contributor role allows users to manage all aspects of application groups. If you want users to publish application groups to users or user groups, they'll also need the *User Access Administrator* role.

| Action type | Permissions |
|--|--|
| actions | <ul><li>Microsoft.DesktopVirtualization/applicationgroups/\*</li><li>Microsoft.DesktopVirtualization/hostpools/read</li><li>Microsoft.DesktopVirtualization/hostpools/sessionhosts/read</li><li>Microsoft.Resources/subscriptions/resourceGroups/read</li><li>Microsoft.Resources/deployments/\*</li><li>Microsoft.Authorization/\*/read</li><li>Microsoft.Insights/alertRules/\*</li><li>Microsoft.Support/\*</ul></li> |
| notActions | None |
| dataActions | None |
| notDataActions | None |

## Desktop Virtualization Application Group Reader

The Desktop Virtualization Application Group Reader role allows users to view everything in the application group and will not allow them to make any changes.

| Action type | Permissions |
|--|--|
| actions | <ul><li>Microsoft.DesktopVirtualization/applicationgroups/\*/read</li><li>Microsoft.DesktopVirtualization/applicationgroups/read</li><li>Microsoft.DesktopVirtualization/hostpools/read</li><li>Microsoft.DesktopVirtualization/hostpools/sessionhosts/read</li><li>Microsoft.Resources/subscriptions/resourceGroups/read</li><li>Microsoft.Resources/deployments/read</li><li>Microsoft.Authorization/\*/read</li><li>Microsoft.Insights/alertRules/read</li><li>Microsoft.Support/\*</li></ul> |
| notActions | None |
| dataActions | None |
| notDataActions | None |

## Desktop Virtualization Workspace Contributor

The Desktop Virtualization Workspace Contributor role allows users to manage all aspects of workspaces. To get information on applications added to the application groups, they'll also need the *Application Group Reader* role.

| Action type | Permissions |
|--|--|
| actions | <ul><li>Microsoft.DesktopVirtualization/workspaces/\*</li><li>Microsoft.DesktopVirtualization/applicationgroups/read</li><li>Microsoft.Resources/subscriptions/resourceGroups/read</li><li>Microsoft.Resources/deployments/\*</li><li>Microsoft.Authorization/\*/read</li><li>Microsoft.Insights/alertRules/\*</li><li>Microsoft.Support/\*</li></ul> |
| notActions | None |
| dataActions | None |
| notDataActions | None |

## Desktop Virtualization Workspace Reader

The Desktop Virtualization Workspace Reader role allows users to view everything in the workspace, but won't allow them to make any changes.

| Action type | Permissions |
|--|--|
| actions | <ul><li>Microsoft.DesktopVirtualization/workspaces/read</li><li>Microsoft.DesktopVirtualization/applicationgroups/read</li><li>Microsoft.Resources/subscriptions/resourceGroups/read</li><li>Microsoft.Resources/deployments/read</li><li>Microsoft.Authorization/\*/read</li><li>Microsoft.Insights/alertRules/read</li><li>Microsoft.Support/\*</li></ul> |
| notActions | None |
| dataActions | None |
| notDataActions | None |

## Desktop Virtualization User Session Operator

The Desktop Virtualization User Session Operator role allows users to send messages, disconnect sessions, and use the "logoff" function to sign sessions out of the session host. However, this role doesn't let users perform session host management like removing session host, changing drain mode, and so on. This role can see assignments, but can't modify admins. We recommend you assign this role to specific host pools. If you give this permission at a resource group level, the admin will have read permission on all host pools under a resource group.

| Action type | Permissions |
|--|--|
| actions | <ul><li>Microsoft.DesktopVirtualization/hostpools/read</li><li>Microsoft.DesktopVirtualization/hostpools/sessionhosts/read</li><li>Microsoft.DesktopVirtualization/hostpools/sessionhosts/usersessions/\*</li><li>Microsoft.Resources/subscriptions/resourceGroups/read</li><li>Microsoft.Resources/deployments/\*</li><li>Microsoft.Authorization/\*/read</li><li>Microsoft.Insights/alertRules/\*</li><li>Microsoft.Support/\*</li></ul> |
| notActions | None |
| dataActions | None |
| notDataActions | None |

## Desktop Virtualization Session Host Operator

The Desktop Virtualization Session Host Operator role allows users to view and remove session hosts, as well as change drain mode. Users can't add session hosts using the Azure portal because they don't have write permission for host pool objects. If the registration token is valid (generated and not expired), users assigned this role can add session hosts to the host pool outside of the Azure portal if they also have the *Virtual Machine Contributor* role.

| Action type | Permissions |
|--|--|
| actions | <ul><li>Microsoft.DesktopVirtualization/hostpools/read</li><li>Microsoft.DesktopVirtualization/hostpools/sessionhosts/\*</li><li>Microsoft.Resources/subscriptions/resourceGroups/read</li><li>Microsoft.Resources/deployments/\*</li><li>Microsoft.Authorization/\*/read</li><li>Microsoft.Insights/alertRules/\*</li><li>Microsoft.Support/\*</li></ul> |
| notActions | None |
| dataActions | None |
| notDataActions | None |
