---
title: "컴파일러 오류 C3417 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3417
dev_langs:
- C++
helpviewer_keywords:
- C3417
ms.assetid: 3e7869ea-8948-42fb-ba30-6ccafe499c35
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: e25adc1b699998235c1cfa16edbb50c2b774f983
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3417"></a>컴파일러 오류 C3417
'member': 값 형식은 사용자 정의 특수 멤버 함수를 포함할 수 없습니다  
  
 값 형식은 기본 인스턴스 생성자, 소멸자 또는 복사 생성자와 같은 함수를 포함할 수 없습니다.  
  
 다음 샘플에서는 C3517 오류가 생성 됩니다.  
  
```  
// C3417.cpp  
// compile with: /clr /c  
value class VC {  
   VC(){}   // C3417  
  
   // OK  
   static VC(){}  
   VC(int i){}  
};  
```