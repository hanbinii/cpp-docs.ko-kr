---
title: "컴파일러 경고 (수준 2) C4094 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4094
dev_langs: C++
helpviewer_keywords: C4094
ms.assetid: e68929fb-3a1c-4be7-920b-d5f79f534f99
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 01b52b13876e30528632dec13dbaee60acf886fc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-2-c4094"></a>컴파일러 경고 (수준 2) C4094
태그가 지정 되지 않은 ' token' 기호가 없는 선언  
  
 컴파일러는 태그가 지정 되지 않은 구조체, 공용 구조체 또는 클래스를 사용 하 여 빈 선언을 발견 했습니다. 선언이 무시 됩니다.  
  
## <a name="example"></a>예제  
  
```  
// C4094.cpp  
// compile with: /W2  
struct  
{  
};   // C4094  
  
int main()  
{  
}  
```  
  
 이 조건은 ANSI 규격 오류를 발생 시킵니다 ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).