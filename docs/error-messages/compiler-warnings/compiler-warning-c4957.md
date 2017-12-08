---
title: "컴파일러 경고 C4957 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4957
dev_langs:
- C++
helpviewer_keywords:
- C4957
ms.assetid: a18c52d4-23e2-44f1-b4b5-f7fa5a7f3987
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c43ddf0e336d9964d08939bb7c1dd145caf6c848
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-warning-c4957"></a>컴파일러 경고 C4957
'cast': 'cast_from'에서 'cast_to'로의 명시적 캐스트는 확인할 수 없습니다.  
  
 캐스트로 인해 확인할 수 없는 이미지가 발생합니다.  
  
 일부 캐스트는 안전합니다(예: 사용자 정의 변환을 트리거하는 `static_cast` 및 `const_cast`). [safe_cast](../../windows/safe-cast-cpp-component-extensions.md) 는 확인할 수 있는 코드를 생성합니다.  
  
 자세한 내용은 참조 [순수형 및 안정형 코드 (C + + /cli CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md)합니다.  
  
 이 경고는 오류로 발생하며 [warning](../../preprocessor/warning.md) pragma 또는 [/wd](../../build/reference/compiler-option-warning-level.md) 컴파일러 옵션과 함께 사용하지 않도록 설정할 수 있습니다.  
  
 다음 샘플에서는 C4957을 생성합니다.  
  
```  
// C4957.cpp  
// compile with: /clr:safe  
// #pragma warning( disable : 4957 )  
using namespace System;  
int main() {  
   Object ^ o = "Hello, World!";  
   String ^ s = static_cast<String^>(o);   // C4957  
   String ^ s2 = safe_cast<String^>(o);   // OK  
}  
```