---
title: 컴파일러 오류 C2264
ms.date: 11/04/2016
f1_keywords:
- C2264
helpviewer_keywords:
- C2264
ms.assetid: 158b72cc-cee9-4a08-bd79-b7a5955345a8
ms.openlocfilehash: 65f8dc1f6f1ad8514b2a6bda1bbd9645af5c251a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62243945"
---
# <a name="compiler-error-c2264"></a>컴파일러 오류 C2264

'function': 함수 정의 또는 선언;에 오류가 있습니다. 함수가 호출 되지 않습니다

잘못 된 정의 또는 선언으로 인해 함수를 호출할 수 없습니다.

다음 샘플에서는 C2264 오류가 생성 됩니다.

```
// C2264.cpp
struct C {
   // Delete the following line to resolve.
   operator int(int = 0){}   // incorrect declaration
};

struct D {
   operator int(){return 0;}   // OK
};

int main() {
   int i;

   C c;
   i = c;   // C2264

   D d;
   i = d;   // OK
}
```