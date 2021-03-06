---
title: novtable
ms.date: 11/04/2016
f1_keywords:
- novtable_cpp
helpviewer_keywords:
- novtable __declspec keyword
- __declspec keyword [C++], novtable
ms.assetid: cfef09c5-8c1e-4b14-8a72-7d726ded4484
ms.openlocfilehash: 9dcca6ec07a19d53da238020805299b652cbf919
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50630245"
---
# <a name="novtable"></a>novtable

## <a name="microsoft-specific"></a>Microsoft 전용

`__declspec` 확장 특성입니다.  

이 형태의 `__declspec`는 모든 클래스 선언에 적용할 수 있지만, 자체적으로 인스턴스화되지 않을 클래스인 순수 인터페이스 클래스에만 적용해야 합니다. `__declspec`는 컴파일러가 클래스의 생성자와 소멸자에서 vfptr을 초기화하는 코드를 생성하지 않도록 합니다. 대부분의 경우 이렇게 하면 클래스와 연결된 vtable에 대한 참조만 제거되므로 링커가 이를 제거합니다. 이 형태의 `__declspec`를 사용하면 코드 크기를 상당히 줄일 수 있습니다. 

`novtable`로 표시된 클래스를 인스턴스화한 다음 클래스 멤버에 액세스하려고 하면 AV(액세스 위반)가 발생합니다.  

## <a name="example"></a>예제

```cpp
// novtable.cpp
#include <stdio.h>

struct __declspec(novtable) X {
   virtual void mf();
};

struct Y : public X {
   void mf() {
      printf_s("In Y\n");
   }
};

int main() {
   // X *pX = new X();
   // pX->mf();   // Causes a runtime access violation.

   Y *pY = new Y();
   pY->mf();
}
```

```Output
In Y
```

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[__declspec](../cpp/declspec.md)<br/>
[키워드](../cpp/keywords-cpp.md)
