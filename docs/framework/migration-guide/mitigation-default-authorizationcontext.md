---
title: "缓解：默认 AuthorizationContext | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6cfeee63-b148-429a-a7e6-6fe9b0cb7610
caps.latest.revision: 3
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d2cffc531efc0f0be841956d3a09e1ab253d8fbd
ms.lasthandoff: 04/18/2017

---
# <a name="mitigation-default-authorizationcontext"></a>缓解：默认 AuthorizationContext
调用具有 `null``authorizationPolicies` 自变量的 <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext%28System.Collections.Generic.IList%7BSystem.IdentityModel.Policy.IAuthorizationPolicy%7D%29> 所返回的 <xref:System.IdentityModel.Policy.AuthorizationContext> 实现更改了其在 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] 中的实现。  
  
## <a name="impact"></a>影响  
 在极少数情况下，使用自定义身份验证的 WCF 应用可能会看到行为差异。  
  
## <a name="mitigation"></a>缓解操作  
 你可以采用两种方式之一还原以前的行为：  
  
-   重新编译你的应用以面向早于 4.6 的 .NET Framework 版本。 对于 IIS 承载的服务，请使用 `<httpRuntime targetFramework="x.x" />` 元素以面向早期版本的 .NET Framework。  
  
-   将下面的行添加到 app.config 文件的 `<appSettings>` 部分：  
  
    ```  
    <add key="appContext.SetSwitch:Switch.System.IdentityModel.EnableCachedEmptyDefaultAuthorizationContext" value="true" />  
    ```  
  
## <a name="see-also"></a>另请参阅  
 [重定目标更改](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)
