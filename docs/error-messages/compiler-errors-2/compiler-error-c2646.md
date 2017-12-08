---
title: "컴파일러 오류 C2646 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2646
dev_langs: C++
helpviewer_keywords: C2646
ms.assetid: 92ff1f02-5eaf-40a5-8b7a-a682f149e967
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 353f65b4d9702ed82ff92eae63fcedaa6adba227
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2646"></a>컴파일러 오류 C2646
전역 또는 네임스페이스 범위의 익명 구조체 또는 공용 구조체는 static으로 선언해야 합니다.  
  
 익명 구조체 또는 공용 구조체가 전역 또는 네임스페이스 범위를 가지지만 `static`으로 선언되지 않았습니다.  
  
 다음 샘플에서는 C2646 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.  
  
```  
// C2646.cpp  
// compile with: /c  
union { int i; };   // C2646 not static  
  
// OK  
static union { int j; };  
union U { int i; };  
```