---
title: "컴파일러 오류 C3372 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3372
dev_langs:
- C++
helpviewer_keywords:
- C3372
ms.assetid: 38ee39ed-03ff-4e6d-9104-f1977b96645d
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 8f81bccba2dc03a87d2a3d87bb7048d07cf28509
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3372"></a>컴파일러 오류 C3372
coclass의 'source' 특성에 대한 인터페이스를 하나 이상 지정해야 합니다.  
  
 특정 특성의 경우 인터페이스 이름을 매개 변수로 전달해야 합니다.  
  
 다음 샘플에서는 C3372를 생성합니다.  
  
```  
// C3372.cpp  
#include <windows.h>  
[module(name="MyModule")];  
  
[ object, uuid(373a1a4c-469b-11d3-a6b0-00c04f79ae8f) ]  
__interface IMyIface {  
   HRESULT f1();  
};  
// to resolve, pass an interface name to the source attribute  
// for example, source(IMyIface)  
[ coclass, uuid(373a1a4d-469b-11d3-a6b0-00c04f79ae8f), source,   
  default(IMyIface) ] // C3372  
class CMyClass {  
};  
  
int main() {  
}  
```