---
title: 컴파일러 경고(수준 1) C4080
ms.date: 11/04/2016
f1_keywords:
- C4080
helpviewer_keywords:
- C4080
ms.assetid: 964fb3f4-b9fd-450b-aa23-35cece126172
ms.openlocfilehash: a91963d524300c8768768a8a4615b1ab27e033e2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50599799"
---
# <a name="compiler-warning-level-1-c4080"></a>컴파일러 경고(수준 1) C4080

세그먼트 이름에 대한 식별자가 있어야 하는데 'symbol'이 있습니다.

[#pragma alloc_text](../../preprocessor/alloc-text.md) 의 세그먼트 이름은 문자열 또는 식별자여야 합니다. 유효한 식별자가 없으면 컴파일러가 pragma를 무시합니다.

다음 샘플에서는 C4080을 생성합니다.

```
// C4080.cpp
// compile with: /W1
extern "C" void func(void);

#pragma alloc_text()   // C4080

// try this line to resolve the warning
// #pragma alloc_text("mysection", func)

int main() {
}

void func(void) {
}
```