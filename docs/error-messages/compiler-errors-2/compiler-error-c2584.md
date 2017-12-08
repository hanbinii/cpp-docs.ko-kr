---
title: "컴파일러 오류 C2584 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2584
dev_langs: C++
helpviewer_keywords: C2584
ms.assetid: 836e2c0a-86c0-4742-b432-beb0191ad20e
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1ff3567f3f4981ecb86926ad76b0d23627da1fb2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2584"></a>컴파일러 오류 C2584
'Class': 직접 기본 '2 '했습니다. 액세스할 수 있음 이미 'Base1'의 기본  
  
 `Class`직접 파생 이미 `Base1`합니다. `Base2`또한에서 파생 `Base1`합니다. `Class`파생 될 수 없습니다 `Base2` 에서 간접적으로 상속 이므로 `Base1` 다시, 이것은 잘못 때문에 `Base1` 이미 직접 기본 클래스입니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2584 오류가 발생 합니다.  
  
```  
// C2584.cpp  
// compile with: /c  
struct A1 {  
   virtual int MyFunction();  
};  
  
struct A2 {  
    virtual int MyFunction();  
};  
  
struct B1: public virtual A1, virtual A2 {  
    virtual int MyFunction();  
};  
  
struct B2: public virtual A2, virtual A1 {  
    virtual int MyFunction();  
};  
  
struct C: virtual B1, B2 {  
    virtual int MyFunction();  
};  
  
struct Z : virtual B2, virtual C {   // C2584  
// try the following line insted  
// struct Z : virtual C {  
    virtual int MyFunction();  
};  
```