---
title: "컴파일러 오류 C3622 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3622
dev_langs: C++
helpviewer_keywords: C3622
ms.assetid: 02836f78-0cf2-4947-b87e-710187d81014
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a5ebccc9fb6cc8c25a8a6b42ae3b99439b1f5d44
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3622"></a>컴파일러 오류 C3622
'class': 'keyword' 인스턴스화할 수 없습니다 클래스 선언  
  
로 표시 된 클래스를 인스턴스화하려고 했습니다 [추상](../../windows/abstract-cpp-component-extensions.md)합니다. 로 표시 된 클래스가 `abstract` 기본 클래스로 사용할 수 있지만 인스턴스화할 수 없습니다.  
  
## <a name="example"></a>예제  
다음 샘플에서는 C3622 오류가 발생 합니다.  
  
```  
// C3622.cpp  
// compile with: /clr  
ref class a abstract {};  
  
int main() {  
   a aa;   // C3622  
}  
```  