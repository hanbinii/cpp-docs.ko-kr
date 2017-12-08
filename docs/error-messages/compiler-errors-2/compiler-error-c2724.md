---
title: "컴파일러 오류 C2724 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2724
dev_langs: C++
helpviewer_keywords: C2724
ms.assetid: 4e4664bc-8c96-4156-b79f-03436f532ea8
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 13c582f081d78e415b4c98bf300b18004fcc33bc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2724"></a>컴파일러 오류 C2724
'identifier': 'static' 사용할 수 없습니다 파일 범위에서 정의 된 멤버 함수에서  
  
 외부 링크가 있는 정적 멤버 함수를 선언 해야 합니다.  
  
 다음 샘플에서는 C2724 오류가 생성 됩니다.  
  
```  
// C2724.cpp  
class C {  
   static void func();  
};  
  
static void C::func(){};   // C2724  
// try the following line instead  
// void C::func(){};  
```