---
title: 링커 도구 경고 LNK4217
ms.date: 04/15/2019
f1_keywords:
- LNK4217
helpviewer_keywords:
- LNK4217
ms.assetid: 280dc03e-5933-4e8d-bb8c-891fbe788738
ms.openlocfilehash: f1ea3cd0a8770571ae5c55d29a901c134311550f
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/17/2019
ms.locfileid: "59674242"
---
# <a name="linker-tools-warning-lnk4217"></a>링커 도구 경고 LNK4217

> 기호 '*기호*'에 정의 된'*filename_1.obj*'에서 가져온'*filename_2.obj*'function' in에서*함수*'

[__declspec (dllimport)](../../cpp/dllexport-dllimport.md) 기호가 동일한 이미지에서 개체 파일에 정의 된 경우에 기호에 대해 지정 되었습니다. 제거 된 `__declspec(dllimport)` 이 경고를 해결 하려면 한정자입니다.

## <a name="remarks"></a>설명

*기호* 이미지 내에 정의 된 기호 이름입니다. *함수* 함수 기호를 가져오는입니다.

사용 하 여 컴파일하면이 경고가 나타나지 합니다 [/clr](../../build/reference/clr-common-language-runtime-compilation.md) 옵션입니다.

LNK4217 대신 두 번째 모듈의 첫 번째 모듈 가져오기 라이브러리를 사용 하 여 컴파일해야 하는 경우 두 모듈을 함께 연결 하려는 경우에 발생할 수 있습니다.

```cpp
// LNK4217.cpp
// compile with: /LD
#include "windows.h"
__declspec(dllexport) void func(unsigned short*) {}
```

그리고

```cpp
// LNK4217b.cpp
// compile with: /c
#include "windows.h"
__declspec(dllexport) void func(unsigned short*) {}
```

이러한 두 모듈을 연결할 LNK4217 발생 합니다. 해결 하려면 첫 번째 샘플의 가져오기 라이브러리를 사용 하 여 두 번째 예제를 컴파일하십시오.

## <a name="see-also"></a>참고자료

[링커 도구 경고 LNK4049](linker-tools-warning-lnk4049.md) \
[링커 도구 경고 LNK4286](linker-tools-warning-lnk4286.md) \
[dllexport, dllimport](../../cpp/dllexport-dllimport.md)