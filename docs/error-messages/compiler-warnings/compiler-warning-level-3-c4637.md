---
title: "컴파일러 경고 (수준 3) C4637 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4637
dev_langs: C++
helpviewer_keywords: C4637
ms.assetid: 5fd347c1-2de9-408f-9136-1bf1ff273622
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a183977d32594d63e0b5d8a8c65e32372940e1f4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-3-c4637"></a>컴파일러 경고(수준 3) C4637
XML 문서 주석 target: \<포함 > 태그가 삭제 되었습니다.  이유  
  
 구문은 [ \<포함 >](../../ide/include-visual-cpp.md) 태그가 잘못 되었습니다.  
  
 다음 샘플에서는 C4637을 생성합니다.  
  
```  
// C4637.cpp  
// compile with: /clr /doc /LD /W3  
using namespace System;  
  
/// Text for class MyClass.  
public ref class MyClass {   
public:  
   /// <include file="c:\davedata\jtest\xml_include.doc"/>  
   // Try the following line instead:  
   // /// <include file='xml_include.doc' path='MyDocs/MyMembers/*' />  
   void MyMethod() {  
   }  
};   // C4637  
```