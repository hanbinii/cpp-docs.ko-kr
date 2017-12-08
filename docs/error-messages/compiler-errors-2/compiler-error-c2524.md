---
title: "컴파일러 오류 C2524 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2524
dev_langs: C++
helpviewer_keywords: C2524
ms.assetid: e71d17f5-2fc2-416b-8dbd-e9bed85eb33a
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f0b80ac9029f530b68afdc379d7660bba1ff76cb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2524"></a>컴파일러 오류 C2524
'소멸자': 소멸자/종료자에는 'void' 매개 변수 목록이 있어야 합니다.  
  
 소멸자 또는 종료자에 없는 매개 변수 목록이 [void](../../cpp/void-cpp.md)합니다. 다른 매개 변수 형식은 허용 되지 않습니다.  
  
## <a name="example"></a>예제  
 다음 코드는 C2524 재현 합니다.  
  
```  
// C2524.cpp  
// compile with: /c  
class A {  
   A() {}  
   ~A(int i) {}    // C2524  
   // try the following line instead  
   // ~A() {}  
};  
```  
  
## <a name="example"></a>예제  
 다음 코드는 C2524 재현 합니다.  
  
```  
// C2524_b.cpp  
// compile with: /clr /c  
ref struct I1 {  
protected:  
   !I1(int i);   // C2524  
   // try the following line instead  
   // !I1();  
};  
```