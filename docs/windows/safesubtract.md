---
title: SafeSubtract | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: SafeSubtract
dev_langs: C++
helpviewer_keywords: SafeSubtract function
ms.assetid: c2712ddc-173f-46a1-b09c-e7ebbd9e68b2
caps.latest.revision: "5"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: 98114ebc7baee41970177e9c390f65fa5521544a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="safesubtract"></a>SafeSubtract
오버플로 방지 하는 방식으로 두 개의 숫자를 뺍니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<typename T, typename U>  
inline bool SafeSubtract (  
   T t,  
   U u,  
   T& result  
) throw ();  
```  
  
#### <a name="parameters"></a>매개 변수  
 [in] `t`  
 빼기의 첫 번째 숫자입니다. T 형식이어야 합니다.  
  
 [in] `u`  
 뺄 수 `t`합니다. U 형식이어야 합니다.  
  
 [out] `result`  
 매개 변수가 있는 `SafeSubtract` 결과 저장 합니다.  
  
## <a name="return-value"></a>반환 값  
 `true`오류가 발생 하지 않으면; `false` 오류가 발생 합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는의 일부 [SafeInt 라이브러리](../windows/safeint-library.md) 용인지 단일 빼기 작업의 인스턴스를 만들지 않고 및는 [SafeInt 클래스](../windows/safeint-class.md)합니다.  
  
> [!NOTE]
>  이 메서드는 단일 수학 연산을 보호해야 하는 경우에만 사용해야 합니다. 작업이 여러 개 있으면 개별 독립 실행형 함수를 호출하는 대신 `SafeInt` 클래스를 사용해야 합니다.  
  
 T와 U 템플릿 형식에 대 한 자세한 내용은 참조 [SafeInt 함수](../windows/safeint-functions.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** safeint.h  
  
 **Namespace:** microsoft:: utilities  
  
## <a name="see-also"></a>참고 항목  
 [SafeInt 함수](../windows/safeint-functions.md)   
 [SafeInt 라이브러리](../windows/safeint-library.md)   
 [SafeInt 클래스](../windows/safeint-class.md)   
 [SafeAdd](../windows/safeadd.md)