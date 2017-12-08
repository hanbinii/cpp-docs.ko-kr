---
title: "Runtimeclassbaset:: Getimplementediids 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::RuntimeClassBaseT::GetImplementedIIDS
dev_langs: C++
helpviewer_keywords: GetImplementedIIDS method
ms.assetid: adae54da-521d-4add-87f5-242fbd85f33b
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1f2eb153220c6c0b46948f6d52ebe15857e999c7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="runtimeclassbasetgetimplementediids-method"></a>RuntimeClassBaseT::GetImplementedIIDS 메서드
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<  
   typename T  
>  
__forceinline static HRESULT GetImplementedIIDS(  
   _In_ T* implements,  
   _Out_ ULONG *iidCount,  
   _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 `implements` 매개 변수의 형식입니다.  
  
 `implements`  
 매개 변수로 지정 된 형식에 대 한 포인터 `T`합니다.  
  
 `iidCount`  
 검색할 인터페이스 Id의 최대 수입니다.  
  
 `iids`  
 이 작업이 완료 되는 경우 성공적으로, 인터페이스 형식에서 구현 된 Id의 배열을 `T`합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 s_ok이 고 그렇지 않으면 오류를 설명 하는 HRESULT입니다.  
  
## <a name="remarks"></a>설명  
 인터페이스를 지정 된 형식에서 구현 되는 Id의 배열을 검색 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>참고 항목  
 [RuntimeClassBaseT 구조체](../windows/runtimeclassbaset-structure.md)