---
title: "Asyncbase:: Firecompletion 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: async/Microsoft::WRL::AsyncBase::FireCompletion
dev_langs: C++
helpviewer_keywords: FireCompletion method
ms.assetid: b5e29d6d-52e7-4148-a7f3-a313b1359819
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2f5478b7ea3777230eb4adcb9f94cd15cbb9cd9d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="asyncbasefirecompletion-method"></a>AsyncBase::FireCompletion 메서드
완료 이벤트 처리기를 호출 하거나 내부 진행률 대리자를 다시 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void FireCompletion(  
   void  
) override;  
  
virtual void FireCompletion();  
```  
  
## <a name="remarks"></a>설명  
 FireCompletion()의 첫 번째 버전에는 내부 진행률 대리자 변수에 다시 설정합니다. 두 번째 버전은 비동기 작업이 완료 될 경우 완료 이벤트 처리기를 호출 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** async.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [AsyncBase 클래스](../windows/asyncbase-class.md)