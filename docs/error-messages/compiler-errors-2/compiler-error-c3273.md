---
title: "컴파일러 오류 C3273 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3273
dev_langs: C++
helpviewer_keywords: C3273
ms.assetid: 1d2ce9d9-222b-4cab-94e2-d2c1a9f5ebe0
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e67fa388853a301743c80ff9a2cd508f815cbba7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3273"></a>컴파일러 오류 C3273
__finally는 비관리 코드의 예외 블록에서 사용할 수 없습니다.  
  
 다음 샘플에서는 C3273을 생성합니다.  
  
```  
// C3273.cpp  
// compile with: /GX  
int main()  
{     
   try  
   {  
   }  
   catch (int)  
   {  
   }  
   __finally   // C3273, remove __finally clause  
   {  
   }  
}  
```