---
title: 후위 식
ms.date: 11/04/2016
helpviewer_keywords:
- operators [C++], postfix
- postfix expressions
- expressions [C++], postfix
ms.assetid: 7ac62a57-06df-422f-b012-a75b37d7cb9b
ms.openlocfilehash: eb6e6e8914cf260df09581232066caf3f873c04e
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58779263"
---
# <a name="postfix-expressions"></a>후위 식

후위 식은 기본 식 또는 후위 연산자가 기본 식 뒤에 오는 식으로 구성됩니다. 다음 표에서는 후위 연산자를 보여 줍니다.

### <a name="postfix-operators"></a>후위 연산자

|연산자 이름|연산자 표기법|
|-------------------|-----------------------|
|[첨자 연산자](../cpp/subscript-operator.md)|**[ ]**|
|[함수 호출 연산자](../cpp/function-call-operator-parens.md)|**( )**|
|[명시적 형식 변환 연산자](../cpp/explicit-type-conversion-operator-parens.md)|*type-name* **( )**|
|[멤버 액세스 연산자](../cpp/member-access-operators-dot-and.md)|**.** 또는 **->**|
|[후 위 증가 연산자](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|**++**|
|[후 위 감소 연산자](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|**--**|

다음 구문에서는 가능한 후위 식을 설명합니다.

```
primary-expression
postfix-expression[expression]postfix-expression(expression-list)simple-type-name(expression-list)postfix-expression.namepostfix-expression->namepostfix-expression++postfix-expression--cast-keyword < typename > (expression )typeid ( typename )
```

합니다 *후 위 식* 위의 기본 식 또는 다른 후 위 식일 수 있습니다.  참조 **기본 식**합니다.  후위 식은 왼쪽에서 오른쪽까지 그룹화되므로 식이 다음과 같이 연결될 수 있습니다.

```cpp
func(1)->GetValue()++
```

위 식에서 `func` 은 기본 식 `func(1)` 는 함수 후 위 식 `func(1)->GetValue` 클래스의 멤버를 지정 하는 후 위 식 `func(1)->GetValue()` 다른 함수 후 위 식이 며 전체 식은은 GetValue의 반환 값을 증가 하는 후 위 식이입니다.  이 식은 1을 인수로 전달하는 함수를 호출하거나 클래스의 포인터를 반환 값으로 가져오라는 의미입니다.  그런 다음 호출 `GetValue()` 해당 클래스를 반환 하는 값 증가 합니다.

위에 나열된 식은 할당 식입니다. 이는 이 식의 결과가 r-value여야 한다는 의미입니다.

후위 식 형식

```cpp
simple-type-name ( expression-list )
```

생성자의 호출을 나타냅니다.  simple-type-name이 기본 형식인 경우 식 목록은 단일 식이어야 하며 이 식은 식 값의 기본 형식으로의 캐스트를 나타냅니다.  이 형식의 캐스트 식은 생성자를 모방합니다.  이 형식을 사용하면 기본 형식 및 클래스를 같은 구문을 사용하여 생성할 수 있기 때문에 이 형식은 특히 템플릿 클래스를 정의할 때 유용합니다.

*cast 키워드가* 중 하나인 **dynamic_cast**, **static_cast** 하거나 **reinterpret_cast**합니다.  자세한 내용은에서 확인할 수 있습니다 **dynamic_cast**를 **static_cast** 하 고 **reinterpet_cast**합니다.

합니다 **typeid** 연산자는 후 위 식으로 간주 됩니다.  참조 **typeid 연산자**합니다.

## <a name="formal-and-actual-arguments"></a>형식 및 실제 인수

호출하는 프로그램은 "실제 인수"에서 호출되는 함수에 정보를 전달합니다. 호출되는 함수는 해당하는 "형식 인수"를 사용하여 정보에 액세스합니다.

함수가 호출되면 다음 작업이 수행됩니다.

- 모든 실제 인수(호출자가 제공한 인수)가 계산됩니다. 이 인수가 계산되는 암시적 순서는 없지만 함수에 진입하기 전에 인수가 모두 계산되고 의도하지 않은 결과가 모두 완료됩니다.

- 식 목록에서 해당하는 실제 인수를 사용하여 각 형식 인수가 초기화됩니다. 형식 인수는 함수 헤더에 선언되며 함수 본문에 사용되는 인수입니다. 실제 인수를 올바른 형식으로 변환할 때 초기화에 의해 표준 변환과 사용자 정의 변환이 둘 다 수행되는 것처럼 변환이 수행됩니다. 다음 코드는 수행된 초기화를 개념적으로 보여 줍니다.

    ```cpp
    void Func( int i ); // Function prototype
    ...
    Func( 7 );          // Execute function call
    ```

   호출 전의 개념적 초기화는 다음과 같습니다.

    ```cpp
    int Temp_i = 7;
    Func( Temp_i );
    ```

   괄호 구문 대신 등호 구문을 사용하는 것처럼 초기화가 수행됩니다. 함수에 값을 전달하기 전에 `i`의 복사본을 만듭니다. (자세한 내용은 [이니셜라이저](../cpp/initializers.md) 하 고 [변환](../cpp/user-defined-type-conversions-cpp.md)).

   따라서 함수 프로토타입 (선언) 형식의 인수에 대 한 호출 하는 경우 **긴**, 호출 프로그램 형식의 실제 인수를 제공 하는 경우 **int**를 사용 하 여 실제 인수가 승격 됩니다는 유형으로 표준 형식 변환을 **긴** (참조 [표준 변환](../cpp/standard-conversions.md)).

   형식 인수의 형식에 대한 표준 또는 사용자 정의 변환이 없는 실제 인수를 제공하는 것은 오류입니다.

   클래스 형식의 실제 인수의 경우 클래스의 생성자를 호출하여 형식 인수가 초기화됩니다. (참조 [생성자](../cpp/constructors-cpp.md) 이러한 특수 클래스 멤버 함수에 대 한 자세한 내용은 합니다.)

- 함수 호출이 실행됩니다.

다음 프로그램 조각은 함수 호출을 보여 줍니다.

```cpp
// expre_Formal_and_Actual_Arguments.cpp
void func( long param1, double param2 );

int main()
{
    long i = 1;
    double j = 2;

    // Call func with actual arguments i and j.
    func( i, j );
}

// Define func with formal parameters param1 and param2.
void func( long param1, double param2 )
{
}
```

때 `func` 정식 매개 변수가 main에서 호출 됩니다 `param1` 값으로 초기화 됩니다 `i` (`i` 형식으로 변환 됩니다 **긴** 표준을 사용 하 여 올바른 형식에 해당 하도록 변환) 및 정식 매개 변수가 `param2` 의 값으로 초기화 됩니다 `j` (`j` 형식으로 변환 됩니다 **double** 표준 변환을 사용 하 여).

## <a name="treatment-of-argument-types"></a>인수 형식 처리

const 형식으로 선언된 형식 인수는 함수 본문 내에서 변경할 수 없습니다. 함수는 형식이 아닌 모든 인수를 변경할 수 있습니다 **const**합니다. 그러나 변경 함수에 로컬 이며 실제 인수가 형식이 아닌 개체에 대 한 참조 하지 않는 한 실제 인수의 값 영향을 주지 않습니다 **const**합니다.

다음 함수는 이러한 개념을 몇 가지 보여 줍니다.

```cpp
// expre_Treatment_of_Argument_Types.cpp
int func1( const int i, int j, char *c ) {
   i = 7;   // C3892 i is const.
   j = i;   // value of j is lost at return
   *c = 'a' + j;   // changes value of c in calling function
   return i;
}

double& func2( double& d, const char *c ) {
   d = 14.387;   // changes value of d in calling function.
   *c = 'a';   // C3892 c is a pointer to a const object.
    return d;
}
```

## <a name="ellipses-and-default-arguments"></a>줄임표 및 기본 인수

함수는 줄임표(`...`) 또는 기본 인수 메서드 중 하나를 사용하여 함수 정의에 지정된 것보다 적은 인수를 받도록 선언할 수 있습니다.

줄임표는 선언에 인수가 필요할 수 있지만 숫자와 형식은 지정되지 않음을 나타냅니다. 이는 C++의 장점인 형식 안전성을 없애기 때문에 일반적으로 좋지 않은 C++ 프로그래밍 관행입니다. 형식 및 실제 인수 형식을 보여 주는 함수보다는 줄임표로 선언된 함수에 다양한 변환이 적용됩니다.

- 형식의 실제 인수 이면 **float**, 형식으로 승격 됩니다 **double** 함수 호출 전에 합니다.

- Signed / unsigned **char**하십시오 **짧은**, enumerated 형식 또는 부호 있는 또는 부호 없는 비트 필드는 변환 **int** 정수 계열 확장을 사용 하 여 합니다.

- 클래스 형식의 인수는 데이터 구조 값에 의해 전달됩니다. 사본은 클래스의 복사 생성자(있을 경우) 호출을 통해서가 아닌 이진 복사를 통해 만들어집니다.

줄임표를 사용할 경우 인수 목록 마지막에 선언해야 합니다. 가변 개수의 인수를 전달 하는 방법에 대 한 자세한 내용은 설명을 참조 하십시오 [va_arg, va_start 및 va_list](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md) 에 *런타임 라이브러리 참조*합니다.

CLR 프로그래밍의 기본 인수에 대 한 정보를 참조 하세요. [가변 인수 목록 (...) (C++/CLI) ](../extensions/variable-argument-lists-dot-dot-dot-cpp-cli.md).

기본 인수를 사용하면 함수 호출에 아무것도 제공되지 않은 경우 인수가 가정하는 값을 지정할 수 있습니다. 다음 코드는 기본 인수의 작동 방법을 보여 줍니다. 기본 인수 지정 제한에 대 한 자세한 내용은 참조 [기본 인수](../cpp/default-arguments.md)합니다.

```cpp
// expre_Ellipses_and_Default_Arguments.cpp
// compile with: /EHsc
#include <iostream>

// Declare the function print that prints a string,
// then a terminator.
void print( const char *string,
            const char *terminator = "\n" );

int main()
{
    print( "hello," );
    print( "world!" );

    print( "good morning", ", " );
    print( "sunshine." );
}

using namespace std;
// Define print.
void print( const char *string, const char *terminator )
{
    if( string != NULL )
        cout << string;

    if( terminator != NULL )
        cout << terminator;
}
```

앞의 프로그램은 두 개의 인수를 사용하는 `print` 함수를 선언합니다. 그러나 두 번째 인수 *종결자*, 기본값, `"\n"`합니다. `main`에 대 한 처음 두 호출 `print` 인쇄 된 문자열을 종결 하는 새 줄을 제공 하는 기본 두 번째 인수를 허용 합니다. 세 번째 호출은 두 번째 인수에 대해 명시적 값을 지정합니다. 프로그램의 출력:

```Output
hello,
world!
good morning, sunshine.
```

## <a name="see-also"></a>참고자료

[식의 형식](../cpp/types-of-expressions.md)