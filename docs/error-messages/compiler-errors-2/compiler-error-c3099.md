---
title: "컴파일러 오류 C3099 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3099
dev_langs:
- C++
helpviewer_keywords:
- C3099
ms.assetid: b3dded0f-76c9-42c1-991b-532eb8619661
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: b0303ef909d6f18cb54c70bc64ab06d415e96da5
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3099"></a>컴파일러 오류 C3099
'keyword': 관리되는 특성에 대해 [System::AttributeUsageAttribute]를 사용하고, WinRT 특성에 대해 [Windows::Foundation::Metadata::AttributeUsageAttribute]를 사용합니다.  
  
 사용 하 여 <xref:System.AttributeUsageAttribute> 선언 하려면 **/clr** 특성입니다. `Windows::Foundation::Metadata::AttributeUsageAttribute`를 사용하여 Windows 런타임 특성을 선언합니다.  
  
 /CLR 특성에 대 한 자세한 내용은 참조 [사용자 정의 특성](../../windows/user-defined-attributes-cpp-component-extensions.md)합니다. Windows 런타임에서 지원 되는 특성을 참조 하십시오. [Windows.Foundation.Metadata 네임 스페이스](http://msdn.microsoft.com/library/windows/apps/windows.foundation.metadata.aspx)  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3099 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.  
  
```  
// C3099.cpp  
// compile with: /clr /c  
using namespace System;  
[usage(10)]   // C3099  
// try the following line instead  
// [AttributeUsageAttribute(AttributeTargets::All)]  
ref class A : Attribute {};  
```