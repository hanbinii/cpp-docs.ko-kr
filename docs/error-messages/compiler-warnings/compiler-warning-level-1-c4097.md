---
title: "컴파일러 경고 (수준 1) C4097 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4097
dev_langs: C++
helpviewer_keywords: C4097
ms.assetid: 2525be51-fac2-43b2-b57c-3bbf1a2268f7
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3ca91f0a8df6a78b11baf77940b1c4b21e258d23
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4097"></a>컴파일러 경고 (수준 1) C4097
pragma 매개 변수는 'restore' 또는 'off'이어야 합니다.  
  
 Pragma에 잘못된 값이 전달되었습니다.  
  
 다음 샘플에서는 C4097을 생성합니다.  
  
```  
// C4097.cpp  
// compile with: /W1  
#pragma runtime_checks("",test)   // C4097  
// try the following line instead  
// #pragma runtime_checks("",off)  
  
int main() {  
}  
```