---
title: "방법: STL/CLR 컨테이너에서.NET 컬렉션으로 변환 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
helpviewer_keywords:
- STL/CLR Containers [STL/CLR]
- STL/CLR, converting to .NET collections
ms.assetid: 70b2dfd9-869c-4e0f-9a29-b1ee0cb0d107
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 817f04af0f6d2c24296b5775a9863b8c34dccd30
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-convert-from-a-stlclr-container-to-a-net-collection"></a>방법: STL/CLR 컨테이너에서 .NET 컬렉션으로 변환
이 항목에서는 STL/CLR 컨테이너의 해당 하는.NET 컬렉션으로 변환 하는 방법을 보여 줍니다. 예를 들어, STL/CLR을 변환 하는 방법을 알아보겠습니다 [벡터](../dotnet/vector-stl-clr.md) .net <xref:System.Collections.Generic.ICollection%601> STL/CLR을 변환 하는 방법 및 [지도](../dotnet/map-stl-clr.md) .net <xref:System.Collections.Generic.IDictionary%602>만 프로시저는 모든 컬렉션에 대 한 유사 하 고 다시 설정 합니다.  
  
### <a name="to-create-a-collection-from-a-container"></a>컨테이너에서 컬렉션을 만들려면  
  
1.  다음 방법 중 하나를 사용 합니다.  
  
    -   컨테이너의 일부를 변환 하려면 호출는 [make_collection](../dotnet/make-collection-stl-clr.md) 작동 하 고.NET 컬렉션으로 복사 하는 begin 반복기 및 STL/CLR 컨테이너의 마지막 바로 다음 반복기 전달 합니다. 이 템플릿 함수는 템플릿 인수로 반복기는 STL/CLR을 사용 합니다. 첫 번째 예제에서는이 메서드를 보여 줍니다.  
  
    -   전체 컨테이너를 변환 하려면 적절 한.NET 컬렉션 인터페이스 또는 인터페이스 컬렉션에 컨테이너를 캐스팅 합니다. 두 번째 예제에서는이 메서드를 보여 줍니다.  
  
## <a name="example"></a>예제  
 이 예에서는 STL/CLR 만들 `vector` 5 개 요소를 추가 합니다. 그런 다음 호출 하 여.NET 컬렉션 만듭니다는 `make_collection` 함수입니다. 마지막으로 새로 만든된 컬렉션의 내용을 표시 합니다.  
  
```  
// cliext_convert_vector_to_icollection.cpp  
// compile with: /clr  
  
#include <cliext/adapter>  
#include <cliext/vector>  
  
using namespace cliext;  
using namespace System;  
using namespace System::Collections::Generic;  
  
int main(array<System::String ^> ^args)  
{  
    cliext::vector<int> primeNumbersCont;  
    primeNumbersCont.push_back(2);  
    primeNumbersCont.push_back(3);  
    primeNumbersCont.push_back(5);  
    primeNumbersCont.push_back(7);  
    primeNumbersCont.push_back(11);  
  
    System::Collections::Generic::ICollection<int> ^iColl =  
        make_collection<cliext::vector<int>::iterator>(  
            primeNumbersCont.begin() + 1,  
            primeNumbersCont.end() - 1);  
  
    Console::WriteLine("The contents of the System::Collections::Generic::ICollection are:");  
    for each (int i in iColl)  
    {  
        Console::WriteLine(i);  
    }  
}  
```  
  
```Output  
The contents of the System::Collections::Generic::ICollection are:  
3  
5  
7  
```  
  
## <a name="example"></a>예제  
 이 예에서는 STL/CLR 만들 `map` 5 개 요소를 추가 합니다. 그런 다음.NET 만듭니다 <xref:System.Collections.Generic.IDictionary%602> 할당는 `map` 에 직접 합니다. 마지막으로 새로 만든된 컬렉션의 내용을 표시 합니다.  
  
```  
// cliext_convert_map_to_idictionary.cpp  
// compile with: /clr  
  
#include <cliext/adapter>  
#include <cliext/map>  
  
using namespace cliext;  
using namespace System;  
using namespace System::Collections::Generic;  
  
int main(array<System::String ^> ^args)  
{  
    cliext::map<float, int> ^aMap = gcnew cliext::map<float, int>;  
    aMap->insert(cliext::make_pair<float, int>(42.0, 42));  
    aMap->insert(cliext::make_pair<float, int>(13.0, 13));  
    aMap->insert(cliext::make_pair<float, int>(74.0, 74));  
    aMap->insert(cliext::make_pair<float, int>(22.0, 22));  
    aMap->insert(cliext::make_pair<float, int>(0.0, 0));  
  
    System::Collections::Generic::IDictionary<float, int> ^iDict = aMap;  
  
    Console::WriteLine("The contents of the IDictionary are:");  
    for each (KeyValuePair<float, int> ^kvp in iDict)  
    {  
        Console::WriteLine("Key: {0:F} Value: {1}", kvp->Key, kvp->Value);  
    }  
}  
```  
  
```Output  
The contents of the IDictionary are:  
Key: 0.00 Value: 0  
Key: 13.00 Value: 13  
Key: 22.00 Value: 22  
Key: 42.00 Value: 42  
Key: 74.00 Value: 74  
```  
  
## <a name="see-also"></a>참고 항목  
 [STL/CLR 라이브러리 참조](../dotnet/stl-clr-library-reference.md)   
 [방법:.NET 컬렉션에서 STL/CLR 컨테이너로 변환](../dotnet/how-to-convert-from-a-dotnet-collection-to-a-stl-clr-container.md)   
 [range_adapter(STL/CLR)](../dotnet/range-adapter-stl-clr.md)