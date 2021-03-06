---
title: 컬렉션(C++/CX)
ms.date: 11/19/2018
ms.assetid: 914da30b-aac5-4cd7-9da3-a5ac08cdd72c
ms.openlocfilehash: 850ac0f4801a13a5407f8fe008740bbfa21cc02c
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57745428"
---
# <a name="collections-ccx"></a>컬렉션(C++/CX)

C + + /CX 프로그램 가능 표준 템플릿 라이브러리 (STL) 컨테이너 또는 다른 모든 사용자 정의 컬렉션 형식을 자유롭게 사용할 합니다. 그러나 전달 하는 경우 컬렉션 앞뒤로 전체 Windows 런타임 응용 프로그램 이진 인터페이스 (ABI)에서, 예를 들어 XAML 컨트롤 또는 JavaScript 클라이언트로-Windows 런타임 컬렉션 형식을 사용 해야 합니다.

컬렉션 및 관련된 형식 및 C +에 대 한 인터페이스를 정의 하는 Windows 런타임 + CX collection.h 헤더 파일의 구체적 c + + 구현을 제공 합니다. 다음 그림에서는 컬렉션 형식 간의 관계를 보여 줍니다.

![C&#43;&#43;&#47;컬렉션 형식에 대 한 /CX 상속 트리](../cppcx/media/cppcxcollectionsinheritancetree.png "C&#43;&#43;&#47;컬렉션 형식에 대 한 /CX 상속 트리")

- [Platform::Collections::Vector 클래스](../cppcx/platform-collections-vector-class.md) 는 [std::vector 클래스](../standard-library/vector-class.md)와 유사합니다.

- [Platform::Collections::Map 클래스](../cppcx/platform-collections-map-class.md) 는 [std::map 클래스](../standard-library/map-class.md)와 유사합니다.

- [Platform::Collections::VectorView 클래스](../cppcx/platform-collections-vectorview-class.md) 및[Platform::Collections::MapView 클래스](../cppcx/platform-collections-mapview-class.md) 는 `Vector` 및 `Map`의 읽기 전용 버전입니다.

- 반복기는 [Platform::Collections Namespace](../cppcx/platform-collections-namespace.md)에서 정의됩니다. 이러한 반복기는 STL 반복기에 대한 요구 사항을 충족하며 모든 [Windows::Foundation::Collections](../standard-library/algorithm-functions.md#find)인터페이스 형식 또는  [Platform::Collections](../standard-library/algorithm-functions.md#count_if)구체적 형식에 대해 [std::find](/uwp/api/windows.foundation.collections) , [std::count_if](../cppcx/platform-collections-namespace.md) 및 기타 STL 알고리즘을 사용할 수 있게 만듭니다. 예를 들어,이 C#에서 만들어진 하 고 STL 알고리즘을 적용 하는 Windows 런타임 구성 요소 컬렉션을 반복할 수 있습니다 의미 합니다.

   > [!IMPORTANT]
   > 프록시 반복기 `VectorIterator` 및 `VectorViewIterator` 는 프록시 개체 `VectoryProxy<T>` 및 `ArrowProxy<T>` 를 활용하여 STL 컨테이너에 사용할 수 있게 만듭니다. 자세한 내용은 이 문서 뒷부분의 "VectorProxy 요소"를 참조하세요.

- C + + /cli CX 컬렉션 형식은 STL 컨테이너 지 원하는 동일한 스레드 보안 보장 합니다.

- [Windows::Foundation::Collections::IObservableVector](/uwp/api/Windows.Foundation.Collections.IObservableVector_T_) 및 [Windows::Foundation::Collections::IObservableMap](/uwp/api/Windows.Foundation.Collections.IObservableMap_K_V_) 은 컬렉션이 다양한 방식으로 변경될 때 발생하는 이벤트를 정의합니다. 이러한 인터페이스를 구현하여  [Platform::Collections::Map](../cppcx/platform-collections-map-class.md) 및 [Platform::Collections::Vector](../cppcx/platform-collections-vector-class.md) 는 XAML 컬렉션을 사용한 데이터 바인딩을 지원합니다. 예를 들어, `Vector` 에 데이터 바인딩된 `Grid`가 있는 경우 컬렉션에 항목을 추가하면 변경 내용이 Grid UI에 반영됩니다.

## <a name="vector-usage"></a>Vector 사용법

클래스에 다른 Windows 런타임 구성 요소에 시퀀스 컨테이너를 전달할 때 사용 하 여 [Windows::Foundation::Collections:: IVector\<T >](/uwp/api/Windows.Foundation.Collections.IVector_T_) 매개 변수 또는 반환 형식 및 [Platform::Collections::Vector\<T >](../cppcx/platform-collections-vector-class.md) 를 구체적 구현으로 합니다. 공용 반환 값 또는 매개 변수에서 `Vector` 형식을 사용하려고 하면 컴파일러 오류 C3986이 발생합니다. `Vector` 를 `IVector`로 변경하여 이 오류를 해결할 수 있습니다.

> [!IMPORTANT]
> 자체 프로그램 안에서 시퀀스를 전달하는 경우에는 `Vector` 보다 효율적인 `std::vector` 또는 `IVector`를 사용합니다. ABI 너머로 컨테이너를 전달할 때만 `IVector` 를 사용합니다.
>
> Windows 런타임 형식 시스템에서는 가변된 배열의 개념이 없습니다 및 IVector 전달할 수 있으므로 < platform:: array\<T >> 반환 값 또는 메서드 매개 변수로 합니다. ABI 전반에서 가변 배열 또는 시퀀스의 시퀀스를 전달하려면 `IVector<IVector<T>^>`를 사용합니다.

`Vector<T>` 는 컬렉션의 항목을 추가, 제거 및 액세스하는 데 필요한 메서드를 제공하며, `IVector<T>`로 암시적으로 변환할 수 있습니다. 또한 `Vector<T>`인스턴스에서 STL 알고리즘을 사용할 수 있습니다. 다음 예제에서는 몇 가지 기본 사용법을 보여 줍니다. 여기에 사용된 [begin 함수](../cppcx/begin-function.md) 및 [end 함수](../cppcx/end-function.md) 는 `Platform::Collections` 네임스페이스가 아니라 `std` 네임스페이스에서 가져온 것입니다.

[!code-cpp[cx_collections#01](../cppcx/codesnippet/CPP/collections/class1.cpp#01)]

사용 하는 기존 코드가 있다면 `std::vector` Windows 런타임 구성 요소에서 다시 사용, 중 하나를 사용 하려는 `Vector` 사용 하는 생성자를 `std::vector` 또는 생성 하는 반복기의 쌍을 `Vector` 에 전달 하는 시점를 abi 전반에서 컬렉션입니다. 다음 예제에서는 효율적인 초기화를 위해 `Vector` 에서 `std::vector`이동 생성자를 사용하는 방법을 보여 줍니다. 이동 작업 후 원래 `vec` 변수는 더 이상 유효하지 않습니다.

[!code-cpp[cx_collections#02](../cppcx/codesnippet/CPP/collections/class1.cpp#02)]

이후의 특정 시점에 ABI 너머로 전달해야 하는 문자열의 벡터가 있는 경우 문자열을 처음에 `std::wstring` 형식으로 만들지 아니면 `Platform::String^` 형식으로 만들지를 결정해야 합니다. 문자열에 대한 처리를 많이 수행해야 하면 `wstring`을 사용하고, 그렇지 않으면 문자열을 `Platform::String^` 형식으로 만들고 나중에 변환하는 비용을 방지합니다. 또한 이러한 문자열을 내부적으로 `std:vector` 에 넣을지 아니면 `Platform::Collections::Vector` 에 넣을지도 결정해야 합니다. 일반적으로 `std::vector` 를 사용한 다음 ABI 너머로 컨테이너를 전달해야 할 때만 `Platform::Vector` 를 만듭니다.

## <a name="value-types-in-vector"></a>Vector의 값 형식

[Platform::Collections::Vector](../cppcx/platform-collections-vector-class.md) 에 저장될 모든 요소는 암시적으로 또는 제공하는 사용자 지정 [std::equal_to](../standard-library/equal-to-struct.md) 비교 연산자를 사용하여 같음 비교를 지원해야 합니다. 모든 참조 형식과 모든 스칼라 형식은 같음 비교를 암시적으로 지원합니다. [Windows::Foundation::DateTime](/uwp/api/windows.foundation.datetime)과 같은 스칼라 값이 아닌 형식이나 `objA->UniqueID == objB->UniqueID`와 같은 사용자 지정 비교의 경우 사용자 지정 함수 개체를 제공해야 합니다.

## <a name="vectorproxy-elements"></a>VectorProxy 요소

[Platform::Collections::VectorIterator](../cppcx/platform-collections-vectoriterator-class.md) 하 고 [Platform::Collections::VectorViewIterator](../cppcx/platform-collections-vectorviewiterator-class.md) 를 사용 하도록 설정 `range for` 루프와 같은 알고리즘 [std:: sort](../standard-library/algorithm-functions.md#sort) 를사용하여[ IVector\<T >](/uwp/api/Windows.Foundation.Collections.IVector_T_) 컨테이너입니다. 그러나 `IVector` 요소는 C++ 포인터 역참조를 통해 액세스할 수 없습니다. 이 요소는 [GetAt](/uwp/api/windows.foundation.collections.ivector-1.getat) 및 [SetAt](/uwp/api/windows.foundation.collections.ivector-1.setat) 메서드를 통해서만 액세스할 수 있습니다. 이러한 반복기는 프록시 클래스를 사용 하는 따라서 `Platform::Details::VectorProxy<T>` 하 고 `Platform::Details::ArrowProxy<T>` 통해 개별 요소에 대 한 액세스를 제공 하기 __\*__, __->__, 및  __\[]__ 표준 라이브러리를 통해 필요에 따라 연산자입니다. 엄밀히 말해 `IVector<Person^> vec`지정 시 `*begin(vec)` 의 형식은 `VectorProxy<Person^>`입니다. 그러나 프록시 개체는 사용자 코드에 거의 표시되지 않습니다. 이러한 프록시 개체는 내부적으로 반복기에만 사용되므로 문서화되지 않지만 메커니즘의 작동 방식을 알면 유용합니다.

`range for` 컨테이너에 대해 `IVector` 루프를 사용할 때는 반복기 변수가 `auto&&` 요소에 올바르게 바인딩되도록 `VectorProxy` 를 사용합니다. `auto` 또는 `auto&`를 사용하면 컴파일러 경고 C4239가 발생하고 `VectoryProxy` 가 경고 텍스트에 언급됩니다.

다음 그림에서는 `range for` 에 대한 `IVector<Person^>`루프를 보여 줍니다. 64번 줄의 중단점에서 실행이 중지됩니다. **간략한 조사식** 창에서 반복기 변수 `p` 가 실제로는 `VectorProxy<Person^>` 및 `m_v` 멤버 변수가 있는 `m_i` 라는 것을 확인할 수 있습니다. 그러나 이 변수에 대해 `GetType` 을 호출하면 `Person` 인스턴스 `p2`와 동일한 형식이 반환됩니다. `VectorProxy` 및 `ArrowProxy` 는 **간략한 조사식**, 디버거 특정 컴파일러 오류 또는 기타 위치에 나타날 수 있지만 일반적으로 해당 항목을 명시적으로 코딩할 필요는 없습니다.

![범위의 VectorProxy&#45;기반 for 루프](../cppcx/media/vectorproxy-1.png "범위의 VectorProxy&#45;루프에 대 한 기준")

프록시 개체를 코딩해야 하는 시나리오 중 하나는 `dynamic_cast` 요소 컬렉션에서 특정 형식의 XAML 개체를 찾을 때 등에 요소에 대해 `UIElement` 를 수행해야 하는 경우입니다. 이 경우 먼저 요소를 [Platform::Object](../cppcx/platform-object-class.md)^으로 캐스팅한 다음 동적 캐스팅을 수행해야 합니다.

```cpp
void FindButton(UIElementCollection^ col)
{
    // Use auto&& to avoid warning C4239
    for (auto&& elem : col)
    {
        Button^ temp = dynamic_cast<Button^>(static_cast<Object^>(elem));
        if (nullptr != temp)
        {
            // Use temp...
        }
    }
}
```

## <a name="map-usage"></a>Map 사용법

항목을 삽입할에서 조회 하는 방법을 보여 주는이 예제는 [Platform::Collections::Map](../cppcx/platform-collections-map-class.md), 다음 다시 돌아와 `Map` 는 읽기 전용 [Windows::Foundation::Collections::IMapView] 으로/uwp/api / Windows.Foundation.Collections.IMapView_K_V_) 형식입니다.

[!code-cpp[cx_collections#04](../cppcx/codesnippet/CPP/collections/class1.cpp#04)]

일반적으로 내부 맵 기능에는 성능상 `std::map` 형식을 사용하는 것이 좋습니다. ABI 전반에서 컨테이너를 전달해야 하는 경우 [std::map](../cppcx/platform-collections-map-class.md) 에서 [Platform::Collections::Map](../standard-library/map-class.md) 을 생성하고 `Map` 을 [Windows::Foundation::Collections::IMap](/uwp/api/Windows.Foundation.Collections.IMap_K_V_)으로 반환합니다. 공용 반환 값 또는 매개 변수에서 `Map` 형식을 사용하려고 하면 컴파일러 오류 C3986이 발생합니다. `Map` 를 `IMap`로 변경하여 이 오류를 해결할 수 있습니다. 조회 또는 삽입 수가 많지 않고 ABI 너머로 컬렉션을 자주 전달하는 경우 등에는 `Platform::Collections::Map` 을 변환할 필요 없이 처음부터 `std::map`을 사용하는 것이 경제적일 수 있습니다. 어떤 경우든, 조회 및 삽입 작업은 세 가지 형식의 성능을 가장 크게 저하시키기 때문에 `IMap` 에서 사용하지 않는 것이 좋습니다. `IMap` 으로의 변환은 ABI 너머로 컨테이너를 전달할 때만 수행합니다.

## <a name="value-types-in-map"></a>Map의 값 형식

[Platform::Collections::Map](../cppcx/platform-collections-map-class.md) 의 요소는 정렬됩니다. `Map` 에 저장될 모든 요소는 암시적으로 또는 제공하는 사용자 지정 [stl::less](../standard-library/less-struct.md) 비교 연산자를 사용하여 엄격한 강력하지 않은 순서 지정으로 보다 작음 비교를 지원해야 합니다. 스칼라 형식은 암시적으로 비교를 지원합니다. `Windows::Foundation::DateTime`과 같은 스칼라 값이 아닌 형식이나 `objA->UniqueID < objB->UniqueID`와 같은 사용자 지정 비교의 경우 사용자 지정 비교 연산자를 제공해야 합니다.

## <a name="collection-types"></a>컬렉션 형식

컬렉션은 네 가지 범주로 구분됩니다(수정 가능한 버전 및 읽기 전용 버전의 시퀀스 컬렉션과 연결 컬렉션). 또한 C + + /cli CX는 컬렉션 액세스를 간소화 하는 세 가지 반복기 클래스를 제공 하 여 컬렉션을 향상 시킵니다.

수정 가능한 컬렉션의 요소는 변경할 수 있지만 읽기 전용 컬렉션( *뷰*라고 함)의 요소는 읽을 수만 있습니다. 요소를 [Platform::Collections::Vector](../cppcx/platform-collections-vector-class.md) 하거나[Platform::Collections::VectorView](../cppcx/platform-collections-vectorview-class.md) 반복기 또는 컬렉션의를 사용 하 여 컬렉션에 액세스할 수 [vector:: getat](../cppcx/platform-collections-vector-class.md#getat) 및 인덱스입니다. 연결 컬렉션의 요소 컬렉션을 사용 하 여 액세스할 수 있습니다 [map:: lookup](../cppcx/platform-collections-map-class.md#lookup) 및 키입니다.

[Platform::Collections::Map 클래스](../cppcx/platform-collections-map-class.md)<br/>
수정 가능한 연결 컬렉션입니다. 맵 요소는 키/값 쌍입니다. 키를 조회하여 연결된 값을 검색하고 모든 키/값 쌍에서 반복하는 작업이 둘 다 지원됩니다.

`Map` 및 `MapView` 는 `<K, V, C = std::less<K>>`템플릿 기반이므로 비교 연산자를 사용자 지정할 수 있습니다.  또한 `Vector` 및 `VectorView` 는 `<T, E = std::equal_to<T>>` 템플릿 기반이며 `IndexOf()`의 동작을 사용자 지정할 수 있습니다. 이는 주로 값 구조체의 `Vector` 및 `VectorView` 에 중요합니다. 예를 들어, 벡터를 만들\<Windows::Foundation::DateTime >, DateTime 오버 로드 하지 않으므로 사용자 지정 비교 연산자를 제공 해야 합니다는 = = 연산자입니다.

[Platform::Collections::MapView 클래스](../cppcx/platform-collections-mapview-class.md)<br/>
읽기 전용 버전의 `Map`입니다.

[Platform::Collections::Vector Class](../cppcx/platform-collections-vector-class.md)<br/>
수정 가능한 시퀀스 컬렉션입니다. `Vector<T>` 는 constant-time 임의 액세스 및 amortized-constant-time [추가](../cppcx/platform-collections-vector-class.md#append) 작업을 지원합니다.

[Platform::Collections::VectorView 클래스](../cppcx/platform-collections-vectorview-class.md)<br/>
읽기 전용 버전의 `Vector`입니다.

[Platform::Collections::InputIterator 클래스](../cppcx/platform-collections-inputiterator-class.md)<br/>
STL 입력 반복기의 요구 사항을 충족하는 STL 반복기입니다.

[Platform::Collections::VectorIterator 클래스](../cppcx/platform-collections-vectoriterator-class.md)<br/>
STL 변경 가능 임의 액세스 반복기의 요구 사항을 충족하는 STL 반복기입니다.

[Platform::Collections::VectorViewIterator 클래스](../cppcx/platform-collections-vectorviewiterator-class.md)<br/>
STL  `const` 임의 액세스 반복기의 요구 사항을 충족하는 STL 반복기입니다.

### <a name="begin-and-end-functions"></a>begin() 및 end() 함수

처리 하는 데 STL의 사용을 간소화 하 `Vector`, `VectorView`, `Map`, `MapView`, 및 `Windows::Foundation::Collections` 개체를 C + + CX의 오버 로드를 지원 합니다 [begin 함수](../cppcx/begin-function.md) 및 [끝 함수](../cppcx/end-function.md) 비 멤버 함수입니다.

다음 표에서는 사용 가능한 반복기 및 함수를 보여 줍니다.

|반복기|함수|
|---------------|---------------|
|[Platform::Collections::VectorIterator\<T>](../cppcx/platform-collections-vectoriterator-class.md)<br /><br /> (내부적으로 저장 [Windows::Foundation::Collections:: IVector\<T >](/uwp/api/Windows.Foundation.Collections.IVector_T_) 및 int)|[begin](../cppcx/begin-function.md)/ [end](../cppcx/end-function.md)([Windows::Foundation::Collections:: IVector\<T >](/uwp/api/Windows.Foundation.Collections.IVector_T_))|
|[Platform::Collections::VectorViewIterator\<T>](../cppcx/platform-collections-vectorviewiterator-class.md)<br /><br /> (내부적으로 저장 [IVectorView\<T >](/uwp/api/Windows.Foundation.Collections.IVectorView_T_)^ 및 int)|[시작할](../cppcx/begin-function.md)/ [끝](../cppcx/end-function.md) ([IVectorView\<T >](/uwp/api/Windows.Foundation.Collections.IVectorView_T_)^)|
|[Platform::Collections::InputIterator\<T>](../cppcx/platform-collections-inputiterator-class.md)<br /><br /> (내부적으로 저장 [IIterator\<T >](/uwp/api/Windows.Foundation.Collections.IIterator_T_)^ 및 T)|[시작할](../cppcx/begin-function.md)/ [끝](../cppcx/end-function.md) ([IIterable\<T >](/uwp/api/Windows.Foundation.Collections.IIterable_T_))|
|[Platform::Collections::InputIterator<IKeyValuePair\<K, V>^>](../cppcx/platform-collections-inputiterator-class.md)<br /><br /> (내부적으로 저장 [IIterator\<T >](/uwp/api/Windows.Foundation.Collections.IIterator_T_)^ 및 T)|[시작할](../cppcx/begin-function.md)/ [끝](../cppcx/end-function.md) ([IMap\<K, V >](/uwp/api/Windows.Foundation.Collections.IMap_K_V_)합니다.|
|[Platform::Collections::InputIterator<IKeyValuePair\<K, V>^>](../cppcx/platform-collections-inputiterator-class.md)<br /><br /> (내부적으로 저장 [IIterator\<T >](/uwp/api/Windows.Foundation.Collections.IIterator_T_)^ 및 T)|[시작할](../cppcx/begin-function.md)/ [끝](../cppcx/end-function.md) (Windows [:: Foundation::Collections::IMapView]/uwp/api/Windows.Foundation.Collections.IMapView_K_V_))|

### <a name="collection-change-events"></a>컬렉션 변경 이벤트

`Vector` 및 `Map` 은 컬렉션 개체가 변경되거나 다시 설정된 경우 또는 컬렉션의 요소가 삽입, 제거 또는 변경된 경우에 발생하는 이벤트를 구현하여 XAML 컬렉션에서 데이터 바인딩을 지원합니다. 데이터 바인딩을 지원하는 고유한 형식을 작성할 수 있지만 이러한 형식이 봉인되기 때문에 `Map` 또는 `Vector` 에서 상속할 수는 없습니다.

[Windows::Foundation::Collections::VectorChangedEventHandler](/uwp/api/windows.foundation.collections.vectorchangedeventhandler) 및 [Windows::Foundation::Collections::MapChangedEventHandler](/uwp/api/windows.foundation.collections.mapchangedeventhandler) 대리자는 컬렉션 변경 이벤트에 대한 이벤트 처리기의 서명을 지정합니다. [Windows::Foundation::Collections::CollectionChange](/uwp/api/windows.foundation.collections.collectionchange) public enum 클래스와 `Platform::Collection::Details::MapChangedEventArgs` 및 `Platform::Collections::Details::VectorChangedEventArgs` ref 클래스는 이벤트의 원인을 확인하기 위해 이벤트 인수를 저장합니다. 합니다 `*EventArgs` 형식에 정의 된 합니다 `Details` 네임 스페이스를 생성 하거나 사용 하는 경우 명시적으로 사용할 필요가 없기 때문에 `Map` 또는 `Vector`합니다.

## <a name="see-also"></a>참고자료

[형식 시스템](../cppcx/type-system-c-cx.md)<br/>
[Visual c + + 언어 참조](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[네임 스페이스 참조](../cppcx/namespaces-reference-c-cx.md)
