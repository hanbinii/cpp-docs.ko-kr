---
title: "Implements:: casttounknown 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Implements::CastToUnknown
dev_langs: C++
helpviewer_keywords: CastToUnknown method
ms.assetid: ca3324f7-4136-406b-8698-7389f4f3d3c7
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 942b816af70a8c47c9168f55185d6817f69ccd46
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="implementscasttounknown-method"></a>Implements::CastToUnknown 메서드
기본 IUnknown 인터페이스에 대 한 포인터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
__forceinline IUnknown* CastToUnknown();  
```  
  
## <a name="return-value"></a>반환 값  
 항상이 작업에 성공 하 고 IUnknown 포인터를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 내부 도우미 함수입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [Implements 구조체](../windows/implements-structure.md)