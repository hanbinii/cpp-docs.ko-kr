---
title: "컴파일러 경고 (수준 1) C4190 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4190
dev_langs: C++
helpviewer_keywords: C4190
ms.assetid: a4d0ad93-a19a-4063-addd-36d605831567
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1f01997ecd685942123b9e5c07db1a2dd59b6618
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4190"></a>컴파일러 경고 (수준 1) C4190
'identifier1'에 C 링크를 지정 하지만 UDT C와 호환 되지 않는 ' identifier2'를 반환 합니다.  
  
 반환 형식으로 함수 또는 함수 포인터에 UDT (사용자 정의 형식, 클래스, 구조체, 열거형 또는 공용 구조체는) 및 `extern` "C" 링크 합니다. 이것은 올바른 경우:  
  
-   이 함수에 대 한 모든 호출이 c + +에서 발생 합니다.  
  
-   C + +에서 함수 정의.  
  
## <a name="example"></a>예제  
  
```cpp  
// C4190.cpp  
// compile with: /W1 /LD  
struct X  
{  
   int i;  
   X ();  
   virtual ~X ();  
};  
  
extern "C" X func ();   // C4190  
```