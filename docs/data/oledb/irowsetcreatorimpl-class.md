---
title: "IRowsetCreatorImpl 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::IRowsetCreatorImpl
- ATL.IRowsetCreatorImpl
- ATL::IRowsetCreatorImpl<T>
- ATL.IRowsetCreatorImpl<T>
- IRowsetCreatorImpl
dev_langs: C++
helpviewer_keywords: IRowsetCreatorImpl class
ms.assetid: 92cc950f-7978-4754-8d9a-defa63867d82
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d511061c3daf4bf5a755404d63663542eb8438ee
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="irowsetcreatorimpl-class"></a>IRowsetCreatorImpl 클래스
동일한 기능을 수행 `IObjectWithSite` 하지만 또한 OLE DB 속성을 사용 하면 **DBPROPCANSCROLLBACKWARDS DBPROPCANFETCHBACKWARDS**합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template < class T >  
class ATL_NO_VTABLE IRowsetCreatorImpl   
   : public IObjectWithSiteImpl< T >  
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 클래스에서 파생 **IRowsetCreator**합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[SetSite](../../data/oledb/irowsetcreatorimpl-setsite.md)|행 집합 개체를 포함 하는 사이트를 설정 합니다.|  
  
## <a name="remarks"></a>설명  
 이 클래스에서 상속 [IObjectWithSite](http://msdn.microsoft.com/library/windows/desktop/ms693765) 재정의 [IObjectWithSite::SetSite](http://msdn.microsoft.com/library/windows/desktop/ms683869)합니다. 공급자 명령 또는 세션 개체를 행 집합을 만들 때 호출 `QueryInterface` 있으면 행 집합 개체에서 `IObjectWithSite` 및 호출 `SetSite` 행 집합 개체를 전달 **IUnkown** 사이트 인터페이스로 인터페이스입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)