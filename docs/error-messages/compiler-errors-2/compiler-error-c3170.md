---
title: "컴파일러 오류 C3170 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3170
dev_langs:
- C++
helpviewer_keywords:
- C3170
ms.assetid: ca9a59d6-7df3-42f0-b028-c09d0af3ac2a
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: aa11ac93ab7e5637153a063a892d99e127b80f54
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3170"></a>컴파일러 오류 C3170
프로젝트에서 다른 모듈 식별자를 사용할 수 없습니다.  
  
 [모듈](../../windows/module-cpp.md) 의 두 컴파일에 파일에서 서로 다른 이름 가진 특성이 발견 되었습니다. 고유한 하나만 `module` 컴파일마다 특성을 지정할 수 있습니다.  
  
 동일한 `module` 둘 이상의 소스 코드 파일에서 특성을 지정할 수 있습니다.  
  
 예를 들어, 다음 모듈 특성이 발견 되었습니다.  
  
```  
// C3170.cpp  
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f") ];  
int main() {}  
```  
  
 그리고  
  
```  
// C3170b.cpp  
// compile with: C3170.cpp  
// C3170 expected  
[ module(name="MyModule1", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f") ];  
```  
  
 다르다는 C3170 (다른 이름 참고).