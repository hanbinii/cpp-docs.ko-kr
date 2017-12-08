---
title: not | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
apitype: DLLExport
f1_keywords:
- std::not
- std.not
- Not
dev_langs: C++
helpviewer_keywords: not function
ms.assetid: d2ddbd5c-33c0-4aff-8961-feac155b4ba1
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 62a6cba9111bc5c60ad286b3409ff76257fc4cfc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="not"></a>not
!에 대한 대안 연산자와 함께 사용되었습니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
#define not !  
  
```  
  
## <a name="remarks"></a>설명  
 매크로가 ! 연산자를 생성합니다.  
  
## <a name="example"></a>예제  
  
```  
// iso646_not.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <iso646.h>  
  
int main( )  
{  
   using namespace std;  
   int a = 0;  
  
   if (!a)  
      cout << "a is zero" << endl;  
  
   if (not(a))  
      cout << "a is zero" << endl;  
}  
```  
  
```Output  
a is zero  
a is zero  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<iso646.h>