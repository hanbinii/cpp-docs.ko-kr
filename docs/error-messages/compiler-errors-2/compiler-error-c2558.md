---
title: "컴파일러 오류 C2558 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2558
dev_langs:
- C++
helpviewer_keywords:
- C2558
ms.assetid: 822b701e-dcae-423a-b21f-47f36aff9c90
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: b11827ed70609a83be9e63de2af3d3b8f12d2310
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2558"></a>컴파일러 오류 C2558
'identifier' : 복사 생성자를 사용할 수 없거나 복사 생성자가 'explicit'으로 선언되었습니다.  
  
 복사 생성자는 형식이 같은 다른 개체로부터 개체를 초기화하며 개체의 복사본을 만듭니다. 생성자를 정의하지 않은 경우에 컴파일러는 기본 복사 생성자를 생성합니다.  
  
### <a name="to-fix-this-error"></a>이 오류를 해결하려면  
  
1.  복사 생성자가 `private`인 클래스를 복사하려고 하면 문제가 발생할 수 있습니다. 대부분의 경우 `private` 복사 생성자를 포함하는 클래스는 복사해서는 안 됩니다. 일반적인 프로그래밍 기술에서는 `private` 복사 생성자를 선언하여 클래스를 직접 사용하지 못하도록 합니다. 이 클래스 자체만으로는 사용될 수 없습니다. 제대로 작동하려면 또 다른 클래스가 필요합니다.  
  
     `private` 복사 생성자를 포함하는 클래스를 사용해도 안전하다고 판단되는 경우 `private` 생성자가 있는 클래스에서 새 클래스를 파생시킨 다음 새 클래스에서 사용할 수 있는 `public` 또는 `protected` 복사 생성자를 만듭니다. 원본 클래스 대신 파생 클래스를 사용하십시오.  
  
2.  복사 생성자가 명시적인 클래스를 복사하려고 하면 문제가 발생할 수 있습니다. 복사 생성자를 `explicit`으로 선언하면 클래스 개체를 함수에 전달하거나 함수로부터 반환할 수 없습니다. 명시적 생성자에 대 한 자세한 내용은 참조 [사용자 정의 형식 변환](../../cpp/user-defined-type-conversions-cpp.md)합니다.  
  
3.  `const` 참조 매개 변수를 사용하지 않는 복사 생성자를 사용하여 `const`로 선언된 클래스 인스턴스를 복사하려고 하면 문제가 발생할 수 있습니다. non-const 형식 참조 대신에 `const` 형식 참조를 사용하여 복사 생성자를 선언합니다.