---
title: "컴파일러 오류 C2310 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2310
dev_langs: C++
helpviewer_keywords: C2310
ms.assetid: 1969c682-b97e-43fb-b9a9-f783e7ff1710
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 526ba25418a3d61764eb2ce1fa36c1e5faea00e3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2310"></a>컴파일러 오류 C2310
catch 처리기 유형임을 지정 해야 합니다.  
  
 Catch 처리기 형식이 없는 또는 여러 형식을 지정 합니다.  
  
 다음 샘플에서는 C2310 오류가 생성 됩니다.  
  
```  
// C2310.cpp  
// compile with: /EHsc  
#include <eh.h>  
int main() {  
   try {  
      throw "Out of memory!";  
   }  
   catch( int ,int) {}   // C2310 two types  
   // try the following line instead  
   // catch( int)  {}  
}  
```