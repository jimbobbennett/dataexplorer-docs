---
title: .show cluster databases - Azure Data Explorer
description: This article describes .show cluster databases in Azure Data Explorer.
ms.reviewer: orspodek
ms.topic: reference
ms.date: 02/13/2020
---
# .show cluster databases

Returns a table showing all the databases attached to the cluster and to which the user invoking the command has access. If specific database names are used, only those databases would
be included.

**Syntax**

`.show` `cluster` `databases` [`details` | `identity` | `policies` | `datastats`]

`.show` `cluster` `databases` `(`database1`,` database2`,` ... databaseN`)`

**Output**
 
|Output parameter |Type |Description 
|---|---|---
|DatabaseName  |String |Database name. Database names are case-sensitive. 
|PersistentStorage  |String |The persistent storage URI in which the database is stored. (This field is empty for ephemeral databases.) 
|Version  |String |Database version number. This number is updated for each change operation in the database (such as adding data and changing the schema). 
|IsCurrent  |Boolean |True if the database is the one that the current connection points to. 
|DatabaseAccessMode  |String |How the cluster is attached to the database. For example, if the database is attached in ReadOnly mode, the cluster will fail all requests to modify the database in any way. 
|PrettyName |String |The database pretty name.
|CurrentUserIsUnrestrictedViewer |Boolean | Specifies if the current user is an unrestricted viewer on the database.
|DatabaseId |Guid |The database's unique ID.