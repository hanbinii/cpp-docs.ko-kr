---
title: "컴파일러 오류 c 2758 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2758
dev_langs: C++
helpviewer_keywords: C2758
ms.assetid: 1d273034-194c-4926-9869-142d1b219cbe
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f694df9f39edbc257b887bcfd9bd13a0ba31a1a0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2758"></a>컴파일러 오류 c 2758
'member': 참조 형식의 멤버를 초기화해야 합니다.  
  
 컴파일러 오류 C2758은 생성자가 이니셜라이저 목록에서 참조 형식의 멤버를 초기화하지 않는 경우 발생합니다. 컴파일러는 멤버를 정의되지 않은 상태로 유지합니다. 참조 멤버 함수는 생성자의 이니셜라이저 목록에서 값을 선언하거나 지정할 때 초기화되어야 합니다.  
  
 다음 샘플에서는 C2758을 생성합니다.  
  
```  
// C2758.cpp  
// Compile by using: cl /W3 /c C2758.cpp  
struct A {  
   const int i;  
  
   A(int n) { };   // C2758  
   // try the following line instead  
   // A(int n) : i{n} {};  
};  
```