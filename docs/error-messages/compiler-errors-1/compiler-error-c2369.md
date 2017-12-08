---
title: "컴파일러 오류 C2369 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2369
dev_langs: C++
helpviewer_keywords: C2369
ms.assetid: 2a3933f6-2313-40ff-800f-921b296fdbbf
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6c835d306a144d21d07285abfb23a8145ebcca16
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2369"></a>컴파일러 오류 C2369
'array': 재정의. 첨자가 다릅니다.  
  
 배열이 다른 아래 첨자로 이미 선언되었습니다.  
  
 다음 샘플에서는 C2369를 생성합니다.  
  
```  
// C2369.cpp  
// compile with: /c  
int a[10];  
int a[20];   // C2369  
int b[20];   // OK  
```