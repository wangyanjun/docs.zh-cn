---
title: "global.json 引用 |Microsoft 文档"
description: "global.json 引用"
keywords: .NET, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/06/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 96102f96-d403-4385-8ef6-5d80e406eb0c
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: 253b8642ae6fc5308d47552e9addfdbed6813ff1
ms.lasthandoff: 03/07/2017

---

# <a name="globaljson-reference"></a>global.json 引用

global.json 文件允许通过 `sdk` 属性选择所使用的 .NET Core 工具版本。 

## <a name="sdk"></a>SDK
类型：Object

指定 SDK 相关信息。

### <a name="version"></a>版本
类型：String

要使用的 SDK 版本。

例如：

```json
{
    "sdk": {
        "version": "1.0.0-preview2-003121"
    }
}
```
