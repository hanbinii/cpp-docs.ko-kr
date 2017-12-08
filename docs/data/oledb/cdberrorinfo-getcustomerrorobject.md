---
title: 'Cdberrorinfo:: Getcustomerrorobject | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDBErrorInfo::GetCustomErrorObject
- ATL.CDBErrorInfo.GetCustomErrorObject
- CDBErrorInfo.GetCustomErrorObject
- ATL::CDBErrorInfo::GetCustomErrorObject
- GetCustomErrorObject
dev_langs: C++
helpviewer_keywords: GetCustomErrorObject method
ms.assetid: 295c053c-b76c-47a5-adfb-333e65d2df0d
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f5d234267a0f4ab65c7a25b1a625096ffafaa403
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="cdberrorinfogetcustomerrorobject"></a>CDBErrorInfo::GetCustomErrorObject
호출 [IErrorRecords::GetCustomErrorObject](https://msdn.microsoft.com/en-us/library/ms725417.aspx) 를 사용자 지정 오류 개체에는 인터페이스에 대 한 포인터를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      HRESULT GetCustomErrorObject(   
   ULONG ulRecordNum,   
   REFIID riid,   
   IUnknown** ppObject    
) const throw( );  
```  
  
#### <a name="parameters"></a>매개 변수  
 참조 [IErrorRecords::GetCustomErrorObject](https://msdn.microsoft.com/en-us/library/ms725417.aspx) 에 *OLE DB Programmer's Reference*합니다.  
  
## <a name="return-value"></a>반환 값  
 표준 `HRESULT`입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CDBErrorInfo 클래스](../../data/oledb/cdberrorinfo-class.md)