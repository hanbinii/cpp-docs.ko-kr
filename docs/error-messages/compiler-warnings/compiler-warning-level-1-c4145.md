---
title: "컴파일러 경고 (수준 1) C4145 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4145
dev_langs: C++
helpviewer_keywords: C4145
ms.assetid: 0440777a-cca2-4159-aff5-e67a254ad64a
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0e74e512512cd9eb97e4693aec71f33eee6002a5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4145"></a>컴파일러 경고(수준 1) C4145
'expression1': 관계식을 switch 식으로 사용했습니다. 'expression2'와 혼동할 수 있습니다.  
  
 `switch` 문은 관계식을 제어 식으로 사용하므로 **case** 문에 대해 부울 값이 생성됩니다. *expression2*를 사용하시겠어요?  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C4145를 생성합니다.  
  
```  
// C4145.cpp  
// compile with: /W1  
int main() {  
   int i = 0;  
   switch(i == 1) {   // C4145, use i instead of i == 1 to resolve  
      case 1:  
         break;  
      default:  
         break;  
   }  
}  
```