---
title: _open_osfhandle | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _open_osfhandle
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _open_osfhandle
- open_osfhandle
dev_langs:
- C++
helpviewer_keywords:
- open_osfhandle function
- file handles [C++], associating
- _open_osfhandle function
ms.assetid: 30d94df4-7868-4667-a401-9eb67ecb7855
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 8d214df5d1e1cd3a48336723cecbf530402eafe3
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="openosfhandle"></a>_open_osfhandle
C 런타임 파일 설명자를 기존 운영 체제 파일 핸들에 연결합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      int _open_osfhandle (  
   intptr_t osfhandle,  
   int flags   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `osfhandle`  
 운영 체제 파일 핸들입니다.  
  
 `flags`  
 허용되는 연산의 유형입니다.  
  
## <a name="return-value"></a>반환 값  
 정상적으로 실행되면 `_open_osfhandle`은 C 런타임 파일 설명자를 반환합니다. 그렇지 않으면-1을 반환 합니다.  
  
## <a name="remarks"></a>설명  
 `_open_osfhandle` 함수는 C 런타임 파일 설명자를 할당하고 `osfhandle`에서 지정한 운영 체제 파일 핸들에 연결합니다. `flags` 인수는 Fcntl.h에 정의된 매니페스트 상수 중 하나 이상으로 구성된 정수 식입니다. 매니페스트 상수를 두 개 이상 사용하여 `flags` 인수를 구성하면 해당 상수는 비트 OR 연산자를 사용하여 결합됩니다(**&#124;**).  
  
 Fcntl.h는 다음 매니페스트 상수를 정의합니다.  
  
 **_O_APPEND**  
 모든 쓰기 작업 전에 파일 포인터를 파일 끝에 배치합니다.  
  
 **_O_RDONLY**  
 읽기 전용으로 파일을 엽니다.  
  
 **_O_TEXT**  
 파일을 텍스트(변환됨) 모드에서 엽니다.  
  
 **_O_WTEXT**  
 파일을 유니코드(변환된 UTF-16) 모드에서 엽니다.  
  
 `_open_osfhandle`을 사용하여 열린 파일을 닫으려면 `_close`를 호출합니다. 기본 핸들도 `_close`에 대한 호출에 의해 닫히므로 원래 핸들에 대해 Win32 함수 `CloseHandle`을 호출할 필요가 없습니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_open_osfhandle`|\<io.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="libraries"></a>라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## <a name="see-also"></a>참고 항목  
 [파일 처리](../../c-runtime-library/file-handling.md)