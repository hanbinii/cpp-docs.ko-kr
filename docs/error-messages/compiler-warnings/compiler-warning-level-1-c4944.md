---
title: 컴파일러 경고(수준 1) C4944
ms.date: 11/04/2016
f1_keywords:
- C4944
helpviewer_keywords:
- C4944
ms.assetid: e2905eb1-2e3b-4fab-a48b-c0cae0fd997f
ms.openlocfilehash: 0c58a438f4e2c1437e1038b6087d57f47db30775
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50585525"
---
# <a name="compiler-warning-level-1-c4944"></a>컴파일러 경고(수준 1) C4944

'symbol': 'assembly1'에서 기호를 가져올 수 없습니다. 'symbol'이 현재 범위에 이미 있습니다.

기호가 소스 코드 파일에서 정의된 다음 참조된 #using 문 및 기호를 정의한 어셈블리에서도 정의되었습니다. 어셈블리의 기호는 무시됩니다.

## <a name="example"></a>예제

다음 샘플에서는 ClassA라는 형식으로 구성 요소를 만듭니다.

```
// C4944.cs
// compile with: /target:library
// C# source code to create a dll
public class ClassA {
   public int i;
}
```

## <a name="example"></a>예제

다음 샘플에서는 C4944를 생성합니다.

```
// C4944b.cpp
// compile with: /clr /W1
class ClassA {
public:
   int u;
};

#using "C4944.dll"   // C4944 ClassA also defined C4944.dll

int main() {
   ClassA * x = new ClassA();
   x->u = 9;
   System::Console::WriteLine(x->u);
}
```