---
title: "CRTThreadTraits 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRTThreadTraits
- ATLBASE/ATL::CRTThreadTraits
- ATLBASE/ATL::CRTThreadTraits::CreateThread
dev_langs: C++
helpviewer_keywords:
- CRTThreadTraits class
- threading [ATL], creation functions
- threading [ATL], CRT threads
ms.assetid: eb6e20b0-c2aa-4170-8e34-aaeeacc86343
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7c591efee96af92aea263dca9c9a95f96932087e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="crtthreadtraits-class"></a>CRTThreadTraits 클래스
이 클래스는 CRT 스레드에 대 한 만들기 함수를 제공 합니다. 스레드 CRT 함수를 사용 하는 경우에이 클래스를 사용 합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
class CRTThreadTraits
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CRTThreadTraits::CreateThread](#createthread)|(정적) CRT 함수를 사용할 수 있는 스레드를 만드는 데이 함수를 호출 합니다.|  
  
## <a name="remarks"></a>설명  
 스레드 특성은 스레드의 특정 형식에 대 한 만들기 함수를 제공 하는 클래스입니다. 생성 함수는 Windows와 동일한 서명 및 의미 체계에 [CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453) 함수입니다.  
  
 스레드 특성 클래스에서 사용 됩니다.  
  
- [CThreadPool](../../atl/reference/cthreadpool-class.md)  
  
- [CWorkerThread](../../atl/reference/cworkerthread-class.md)  
  
 스레드 CRT 함수를 사용 하지 않는, 사용 하 여 [Win32ThreadTraits](../../atl/reference/win32threadtraits-class.md) 대신 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlbase.h  
  
##  <a name="createthread"></a>CRTThreadTraits::CreateThread  
 CRT 함수를 사용할 수 있는 스레드를 만드는 데이 함수를 호출 합니다.  
  
```
static HANDLE CreateThread(
    LPSECURITY_ATTRIBUTES lpsa,
    DWORD dwStackSize,
    LPTHREAD_START_ROUTINE pfnThreadProc,
    void* pvParam,
    DWORD dwCreationFlags,
    DWORD* pdwThreadId) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `lpsa`  
 새 스레드에 대 한 보안 특성입니다.  
  
 `dwStackSize`  
 새 스레드의 스택 크기입니다.  
  
 `pfnThreadProc`  
 새 스레드의 스레드 프로시저입니다.  
  
 `pvParam`  
 스레드 프로시저에 전달할 매개 변수입니다.  
  
 `dwCreationFlags`  
 만들기 (0 또는 CREATE_SUSPENDED) 플래그 지정합니다.  
  
 `pdwThreadId`  
 [out] 성공할 경우 새로 만든 스레드의 스레드 ID를 수신 하는 DWORD 변수의 주소입니다.  
  
### <a name="return-value"></a>반환 값  
 실패 한 경우 새로 생성된 된 스레드 또는 NULL 핸들을 반환 합니다. 호출 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) 확장 오류 정보를 가져오려면 합니다.  
  
### <a name="remarks"></a>설명  
 참조 [CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453) 에 대 한 자세한 내용은이 함수에 매개 변수입니다.  
  
 이 함수 호출 [_beginthreadex](../../c-runtime-library/reference/beginthread-beginthreadex.md) 는 스레드를 만들 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../../atl/atl-class-overview.md)