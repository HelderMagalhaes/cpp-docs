---
title: "Compiler Error C3467 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: ["cpp-tools"]
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: ["C3467"]
dev_langs: ["C++"]
helpviewer_keywords: ["C3467"]
ms.assetid: e2b844d0-4920-412f-99fd-cd8051c4aa41
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
ms.workload: ["cplusplus"]
---
# Compiler Error C3467
'type' : this type has already been forwarded  
  
 The compiler found more than one forward type declaration for the same type. Only one declaration per type is allowed.  
  
 For more information, see [Type Forwarding (C++/CLI)](../../windows/type-forwarding-cpp-cli.md).  
  
## Example  
 The following sample creates a component.  
  
```  
// C3467.cpp  
// compile with: /LD /clr  
public ref class R {};  
```  
  
## Example  
 The following sample generates C3467.  
  
```  
// C3467_b.cpp  
// compile with: /clr /c  
#using "C3467.dll"  
[ assembly:TypeForwardedTo(R::typeid) ];  
[ assembly:TypeForwardedTo(R::typeid) ];   // C3467  
```