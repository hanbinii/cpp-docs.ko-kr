---
title: "컴파일러 오류 C2486 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2486
dev_langs: C++
helpviewer_keywords: C2486
ms.assetid: 436da349-6461-4e32-bfca-4f3e620108e2
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b7f54417beefb9bd2c82763464d0e76ed81bf7ed
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2486"></a>컴파일러 오류 C2486
' __LOCAL_SIZE' 'naked' 특성이 있는 함수에만 사용할 수  
  
 인라인 어셈블리 함수 이름에서에서 `__LOCAL_SIZE` 으로 선언 된 함수의 예약 되는 [naked](../../cpp/naked-cpp.md) 특성입니다.  
  
 다음 샘플에서는 C2486 오류가 생성 됩니다.  
  
```  
// C2486.cpp  
// processor: x86  
void __declspec(naked) f1() {  
   __asm {  
      mov   eax,   __LOCAL_SIZE  
   }  
}  
void f2() {  
   __asm {  
      mov   eax,   __LOCAL_SIZE   // C2486  
   }  
}  
```