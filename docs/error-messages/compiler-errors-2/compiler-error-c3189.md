---
title: 컴파일러 오류 C3189
ms.date: 11/04/2016
f1_keywords:
- C3189
helpviewer_keywords:
- C3189
ms.assetid: b254de79-931e-4a59-a9f4-1c690d90ca5e
ms.openlocfilehash: b2de290178657ae427b5ad7999c511ae7ff9f1eb
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59778607"
---
# <a name="compiler-error-c3189"></a>컴파일러 오류 C3189

' typeid\<추상 선언 자 입력 >':이 구문은 지원 되지 않는, 사용:: typeid 대신

사용 되지 않는 형태로 [typeid](../../extensions/typeid-cpp-component-extensions.md) 된 새 형식을 사용 하 여 사용 합니다.

다음 샘플에서는 C3189 오류가 생성 됩니다.

```
// C3189.cpp
// compile with: /clr
int main() {
   System::Type^ t  = typeid<System::Object>;   // C3189
   System::Type^ t2  = System::Object::typeid;   // OK
}
```