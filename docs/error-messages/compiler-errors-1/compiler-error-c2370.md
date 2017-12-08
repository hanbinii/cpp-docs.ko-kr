---
title: "컴파일러 오류 C2370 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2370
dev_langs: C++
helpviewer_keywords: C2370
ms.assetid: 03403e8f-f393-47c4-bd25-5c1c7ea7d5cd
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 99059e2032ac3f58676172b171f234e48baf78cf
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2370"></a>컴파일러 오류 C2370
'identifier': 재정의. 저장소 클래스가 다릅니다.  
  
 식별자를 다른 저장소 클래스로 이미 선언했습니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2370을 생성합니다.  
  
```  
// C2370.cpp  
// compile with: /Za /c  
extern int i;  
static int i;   // C2370  
int i;   // OK  
```  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2370을 생성합니다.  
  
```  
// C2370b.cpp  
#define Thread __declspec( thread )  
extern int tls_i;  
int Thread tls_i;   // C2370 declaration and the definition differ  
int tls_i;   // OK  
```