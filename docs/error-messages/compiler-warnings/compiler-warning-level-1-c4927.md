---
title: 컴파일러 경고(수준 1) C4927
ms.date: 11/04/2016
f1_keywords:
- C4927
helpviewer_keywords:
- C4927
ms.assetid: 7009e740-a2ef-4130-96ba-482e092f717a
ms.openlocfilehash: 59a39e4e695fdd161135cd70a74e1f3f6518e361
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50542212"
---
# <a name="compiler-warning-level-1-c4927"></a>컴파일러 경고(수준 1) C4927

변환이 잘못 되었습니다. 둘 이상의 사용자 정의 변환이 암시적으로 적용 된

둘 이상의 사용자 정의 변환이 암시적으로 단일 값-에 적용 되었습니다. 컴파일러 변환 하는 명시적 변환을 찾을 수 없습니다 하지만 해당 하는 변환의 찾을.

다음 샘플에서는 C4927 오류가 생성 됩니다.

```
// C4927.cpp
// compile with: /W1
struct B
{
   operator int ()
   {
      return 0;
   }
};

struct A
{
   A(int i)
   {
   }

   /*
   // uncomment this constructor to resolve
   A(B b)
   {
   }
   */
};

A f1( B& b)
{
   return A(b);
}

B& f2( B& b)
{
   return b;
}

A f()
{
   B b;
   return A(b);   // ok
   return f1(b);  // ok
   return b;      // C4927
   return B(b);   // C4927
   return f2(b);  // C4927
}

int main()
{
   B b;
   A a = b;
   A a2(b);
}
```