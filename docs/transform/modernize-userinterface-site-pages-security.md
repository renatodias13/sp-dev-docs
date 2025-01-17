---
title: Security requirements for using page transformation
description: Explains the required permission levels for page transformation
ms.date: 02/11/2021
ms.prod: sharepoint
ms.localizationpriority: high
---

# Security requirements for using page transformation

> [!IMPORTANT]
> SharePoint PnP Modernization is part of the [PnP Framework](https://github.com/pnp/pnpframework) and is continuously evolving, checkout [the release notes](https://github.com/pnp/pnpframework/blob/dev/src/lib/CHANGELOG.md) to stay up to date on the latest changes. If you encounter problems please file an issue in the [PnP Framework GitHub issue list](https://github.com/pnp/pnpframework/issues).

Before an existing wiki or web part page can be transformed to a modern page you do need to have the needed SharePoint permissions. This short article explains what permissions are required.

## General security requirements

These requirements apply always, regardless whether you're using page transformation from PowerShell or .Net.

Page Transformation feature | SharePoint Permission | Included in default permission levels
----------------------------|-----------------------|--------------------------------------
Create a modern version of the wiki or web part page | Edit Items | Contribute, Edit, Full Control
Copy the page metadata (except page editor/author/created/modified settings) | Edit Items | Contribute, Edit, Full Control
Copy the item level permissions (if any) | Manage Permissions | Full Control
Copy the page editor/author/created/modified settings | Manage Permissions | Full Control

Above chart shows that with the default `Edit` or `Contribute` permission level you can use page transformation but if there's item level permissions on the source page these are not copied over. Using the `Full Control` permission level does enable the copy of item level permissions as that one by default includes the `Manage Permissions` permission.