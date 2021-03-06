---
title: _local_unwind2
ms.date: 11/04/2016
apiname:
- _local_unwind2
apilocation:
- msvcr110_clr0400.dll
- msvcrt.dll
- msvcr100.dll
- msvcr110.dll
- msvcr80.dll
- msvcr90.dll
- msvcr120.dll
apitype: DLLExport
f1_keywords:
- _local_unwind2
- local_unwind2
helpviewer_keywords:
- _local_unwind2 function
- local_unwind2 function
ms.assetid: 44f1fa82-e01e-490f-a6e6-18fc6811c28c
ms.openlocfilehash: c62763ecbdd2c05e8cd7b6733ec1df4254362527
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57744002"
---
# <a name="localunwind2"></a>_local_unwind2

내부 CRT 함수입니다. 지정된 범위 테이블에 나열된 모든 종료 처리기를 실행합니다.

## <a name="syntax"></a>구문

```
void _local_unwind2(
   PEXCEPTION_REGISTRATION xr,
   int stop
);
```

#### <a name="parameters"></a>매개 변수

*xr*<br/>
[in] 범위 테이블 하나와 연결된 등록 레코드입니다.

*stop*<br/>
[in] `_local_unwind2`가 정지해야 하는 위치를 나타내는 어휘 수준입니다.

## <a name="remarks"></a>주의

이 메서드는 런타임 환경에서 사용됩니다. 이 메서드를 사용자의 코드에서 호출하지 마세요.

이 메서드가 종료 처리기를 실행하면 이 메서드는 현재 어휘 수준에서 시작하여 `stop`이 지정한 수준에 도달할 때까지 상위 어휘 수준으로 계속 올라갑니다. `stop`이 지정한 수준에서는 종료 처리기를 실행하지 않습니다.

## <a name="see-also"></a>참고 항목

[사전순 함수 참조](../c-runtime-library/reference/crt-alphabetical-function-reference.md)
