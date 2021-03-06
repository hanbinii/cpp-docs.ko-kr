---
title: Module::MethodReleaseNotifier 클래스
ms.date: 09/17/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::MethodReleaseNotifier
- module/Microsoft::WRL::Module::MethodReleaseNotifier::Invoke
- module/Microsoft::WRL::Module::MethodReleaseNotifier::method_
- module/Microsoft::WRL::Module::MethodReleaseNotifier::MethodReleaseNotifier
- module/Microsoft::WRL::Module::MethodReleaseNotifier::object_
helpviewer_keywords:
- Microsoft::WRL::Module::MethodReleaseNotifier class
- Microsoft::WRL::Module::MethodReleaseNotifier::Invoke method
- Microsoft::WRL::Module::MethodReleaseNotifier::method_ data member
- Microsoft::WRL::Module::MethodReleaseNotifier::MethodReleaseNotifier, constructor
- Microsoft::WRL::Module::MethodReleaseNotifier::object_ data member
ms.assetid: 5c2902be-964b-488f-9f1c-adf504995cbc
ms.openlocfilehash: 41b7cfb2601cd2023e895dbcf1a56e85fe65b35d
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58784794"
---
# <a name="modulemethodreleasenotifier-class"></a>Module::MethodReleaseNotifier 클래스

현재 모듈의 마지막 개체가 해제될 때 이벤트 처리기를 호출합니다. 이벤트 처리기 개체와 해당 포인터를-a-메서드 멤버 지정 됩니다.

## <a name="syntax"></a>구문

```cpp
template<typename T>
class MethodReleaseNotifier : public ReleaseNotifier;
```

### <a name="parameters"></a>매개 변수

*T*<br/>
멤버 함수가 이벤트 처리기 개체의 형식입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

이름                                                                                                 | 설명
---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------
[Module::MethodReleaseNotifier::MethodReleaseNotifier](#methodreleasenotifier-methodreleasenotifier) | `Module::MethodReleaseNotifier` 클래스의 새 인스턴스를 초기화합니다.

### <a name="public-methods"></a>Public 메서드

이름                                                                   | 설명
---------------------------------------------------------------------- | -------------------------------------------------------------------------------------------
[Module::MethodReleaseNotifier::Invoke](#methodreleasenotifier-invoke) | 현재 연결 된 이벤트 처리기를 호출 `Module::MethodReleaseNotifier` 개체입니다.

### <a name="protected-data-members"></a>보호된 데이터 멤버

이름                                                                    | 설명
----------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------
[Module::MethodReleaseNotifier::method_](#methodreleasenotifier-method) | 현재 이벤트 처리기에 대 한 포인터를 보유 `Module::MethodReleaseNotifier` 개체입니다.
[Module::MethodReleaseNotifier::object_](#methodreleasenotifier-object) | 멤버 함수가 이벤트 처리기를 현재 개체에 대 한 포인터를 보유 `Module::MethodReleaseNotifier` 개체입니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`ReleaseNotifier`

`MethodReleaseNotifier`

## <a name="requirements"></a>요구 사항

**헤더:** module.h

**네임스페이스:** Microsoft::WRL

## <a name="methodreleasenotifier-invoke"></a>Module::MethodReleaseNotifier::Invoke

현재 연결 된 이벤트 처리기를 호출 `Module::MethodReleaseNotifier` 개체입니다.

```cpp
void Invoke();
```

## <a name="methodreleasenotifier-method"></a>Module::MethodReleaseNotifier::method_

현재 이벤트 처리기에 대 한 포인터를 보유 `Module::MethodReleaseNotifier` 개체입니다.

```cpp
void (T::* method_)();
```

## <a name="methodreleasenotifier-methodreleasenotifier"></a>Module::MethodReleaseNotifier::MethodReleaseNotifier

`Module::MethodReleaseNotifier` 클래스의 새 인스턴스를 초기화합니다.

```cpp
MethodReleaseNotifier(
   _In_ T* object,
   _In_ void (T::* method)(),
   bool release) throw() :
            ReleaseNotifier(release), object_(object),
            method_(method);
```

### <a name="parameters"></a>매개 변수

*object*<br/>
개체 멤버 함수가 이벤트 처리기입니다.

*method*<br/>
멤버 함수 매개 변수의 *개체* 이벤트 처리기입니다.

*release*<br/>
지정할 `true` 내부 호출을 사용 하도록 설정 하려면 [모듈:: ReleaseNotifier::Release()](module-releasenotifier-class.md#releasenotifier-release) 메서드를 지정이 고, 그렇지 `false`합니다.

## <a name="methodreleasenotifier-object"></a>Module::MethodReleaseNotifier::object_

멤버 함수가 이벤트 처리기를 현재 개체에 대 한 포인터를 보유 `Module::MethodReleaseNotifier` 개체입니다.

```cpp
T* object_;
```
