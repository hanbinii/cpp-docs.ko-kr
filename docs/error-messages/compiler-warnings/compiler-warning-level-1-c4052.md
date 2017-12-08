---
title: "컴파일러 경고 (수준 1) C4052 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4052
dev_langs: C++
helpviewer_keywords: C4052
ms.assetid: f9955421-16ab-46e5-8f9d-bf1639a519ef
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 24be11296f5a79569dd02bbabafc765527ce1a40
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4052"></a>컴파일러 경고(수준 1) C4052
함수 선언이 다릅니다. 한쪽에 가변 인수가 들어 있습니다.  
  
 하나의 함수 선언에 변수 인수가 없습니다. 무시됩니다.  
  
 다음 샘플에서는 C4052를 생성합니다.  
  
```  
// C4052.c  
// compile with: /W4 /c  
int f();  
int f(int i, ...);   // C4052  
```