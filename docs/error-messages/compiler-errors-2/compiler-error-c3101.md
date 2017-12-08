---
title: "컴파일러 오류 C3101 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3101
dev_langs:
- C++
helpviewer_keywords:
- C3101
ms.assetid: 4f673766-d4f7-4632-94a5-d36a83f7f4b5
caps.latest.revision: 3
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: f08cfe2c201981183305f6ac04d1bf24b6378d48
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3101"></a>컴파일러 오류 C3101
명명 된 특성 인수 'field'에 대 한 잘못 된 식  
  
 명명된 된 특성 인수를 초기화할 때 값은 컴파일 타임 상수 여야 합니다.  
  
 특성에 대 한 자세한 내용은 참조 하십시오. [사용자 정의 특성](../../windows/user-defined-attributes-cpp-component-extensions.md)합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3101 오류가 발생 합니다.  
  
```  
// C3101.cpp  
// compile with: /clr /c  
ref class AAttribute : System::Attribute {  
public:  
   int Field;  
};  
  
extern int i;  
  
[assembly:A(Field = i)];   // C3101  
[assembly:A(Field = 0)];   // OK  
```