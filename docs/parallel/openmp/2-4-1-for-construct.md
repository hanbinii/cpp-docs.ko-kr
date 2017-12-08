---
title: "2.4.1 for 구문 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 27d2cbce-786b-4819-91d3-d55b2cc57a5e
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 92f3af3fa84043d9e8755136ab66e345e455ff1b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="241-for-construct"></a>2.4.1 for 구문
**에 대 한** 지시문 병렬로 연결 된 루프의 반복을 실행할지를 지정 하는 반복 작업 공유 생성자를 식별 합니다. 반복 된 **에 대 한** 루프 실행을 바인딩하는 병렬 구문 팀에 이미 있는 스레드 간에 배포 됩니다. 구문은 **에 대 한** 구문은 다음과 같습니다.  
  
```  
#pragma omp for [clause[[,] clause] ... ] new-linefor-loop  
```  
  
 절은 다음 중 하나입니다.  
  
 **개인 (** *변수 목록* **)**  
  
 **firstprivate (** *변수 목록* **)**  
  
 **lastprivate (** *변수 목록* **)**  
  
 **감소 (** *연산자* **:** *변수 목록***)**  
  
 **정렬**  
  
 **일정 (** *종류*[, *chunk_size*]**)**  
  
 **nowait**  
  
 **에 대 한** 지시문에서는 해당 구조에 제한 **에 대 한** 루프입니다. 특히, 해당 **에 대 한** 루프 정식 셰이프 있어야 합니다.:  
  
 **에 대 한 (** *init expr* **;** *var 논리 op b*; *incr expr***)**  
  
 *init expr*  
 다음 중 하나:  
  
 *var* = *lb*  
  
 *정수 형식 var* = *lb*  
  
 *incr expr*  
 다음 중 하나:  
  
 ++*var*  
  
 *var* ++  
  
 -- *var*  
  
 *var* --  
  
 *var* += *incr*  
  
 *var* -= *incr*  
  
 *var* = *var* + *incr*  
  
 *var* = *incr* + *var*  
  
 *var* = *var* - *incr*  
  
 *var*  
 부호 있는 정수 변수입니다. 이 변수는 공유 그렇지 않은 경우 암시적으로 만들어질 개인 기간 동안에 **에 대 한**합니다.   본문 내에서이 변수를 수정 하지 않아야는 **에 대 한** 문. 변수를 지정 하지 않으면 **lastprivate**, 루프는 결정적이 지 않습니다 후 해당 값입니다.  
  
 *op 논리*  
 다음 중 하나:  
  
 <  
  
 \<=  
  
 >  
  
 \>=  
  
 *lb*, *b*, 및 *incr*  
 루프 고정 정수 식입니다. 이러한 식의 평가 하는 동안 동기화가 있습니다. 따라서 모든 평가 부작용 확정 되지 않은 결과 생성합니다.  
  
 정규 형식 루프의 반복 루프를 항목에 대해 계산할 수 있도록 확인 합니다. 형식의 값으로이 계산이 수행 됩니다 *var*, 정수 계열 확장 후 합니다. 경우에 특히에 값 *b* - *lb* + *incr* 형식 결과 확정적 한다는 점에서 나타낼 수 없습니다. 또한 if *논리 op* 는 < 또는 \<다음 = *incr expr* 수행 해야 하는 *var* 루프의 반복 될 때마다 증가 합니다.   경우 *논리 op* 은 > 또는 > = 다음 *incr expr* 수행 해야 하는 *var* 루프의 각 반복에서 감소 합니다.  
  
 **일정** 절이 지정 방법을의 반복 된 **에 대 한** 루프는 팀의 스레드 분할 됩니다. 프로그램의 정확성 스레드 실행을 특정 반복에 종속 되지 않아야 합니다. 값 *chunk_size*를 지정 하는 경우, 양수 값으로 루프 고정 정수 식 이어야 합니다. 이 식의 평가 하는 동안 동기화가 있습니다. 따라서 모든 평가 부작용 확정 되지 않은 결과 생성합니다. 일정 *종류* 다음 중 하나일 수 있습니다.  
  
 표 2-1 **일정** 절 *종류* 값  
  
|||  
|-|-|  
|정적|때 **일정 (정적** *chunk_size***)** 반복으로 지정 된 크기의 청크로 나뉩니다. 지정 된 *chunk_size*합니다. 청크는 스레드 번호 순서 대로 라운드 로빈 방식으로 팀의 스레드에 정적으로 할당 됩니다. No *chunk_size* 를 지정 하는 각 스레드에 할당 하는 하나의 청크 크기가 약 같은 것 청크로 반복 나뉩니다.|  
|dynamic|때 **일정 (동적** *chunk_size***)** 지정, 청크를 포함 하는 일련의 반복 횟수는 나뉩니다 *chunk_size* 반복 합니다. 각 청크 할당에 대 한 대기 중인 스레드에 할당 됩니다. 스레드는 반복의 청크를 실행 하 고 그런 다음 할당할 청크가 없습니다 남을 때까지 그 다음 할당을 기다립니다. 참고 할당할 마지막 청크는 더 적은 수의 반복을 있을 수 있습니다. No *chunk_size* 지정, 기본값은 1입니다.|  
|문제 해결|때 **일정 (문제 해결,** *chunk_size***)** 반복 청크 크기를 줄여 채웁니다 스레드에 할당 된 지정 된 합니다. 이때 스레드가 완료 반복의 할당 된 해당 청크 하는 경우 더 이상 없을 때까지 다른 청크 동적으로 할당 됩니다. 에 대 한는 *chunk_size* 1 인 각 청크 크기가 약에서 할당 되지 않은 반복 횟수의 스레드 수로 나눈 값입니다. 이러한 크기 감소 지 수 적으로 1로 약 합니다. 에 대 한는 *chunk_size* 값을 가진 *k* 1 보다 큰 경우 크기가 감소 약 기하급수적으로 *k*한다는 점을 제외 하 고 마지막 청크 보다 적은 있을 수 있습니다  *k* 반복 합니다. No *chunk_size* 지정, 기본값은 1입니다.|  
|런타임(runtime)|때 **schedule (runtime)** 지정에 대 한 일정은 런타임이 될 때까지 지연 의사 결정 합니다. 일정 *종류* 환경 변수를 설정 하 여 런타임 시 청크 크기를 선택할 수 있습니다 및 **OMP_SCHEDULE**합니다. 이 환경 변수를 설정 하지 않으면 결과 일정 구현 시 정의 됩니다. 때 **schedule (runtime)** 지정 된 *chunk_size* 지정 하면 안 됩니다.|  
  
 명시적으로 정의 된 없을 경우에서 **일정** 절, 기본 **일정** 구현 시 정의 됩니다.  
  
 OpenMP 규격 프로그램이 제대로 실행 하기 위해 특정 일정에 따라 되지는지 않습니다. 프로그램 일정에 의존 하지 않아야 *종류* 같은 일정의 구현에서 변형 이름이 있을 수 있기 때문에 위 설명에 정확 하 게 준수 *종류* 간에 서로 다른 컴파일러입니다. 설명은 특정 상황에 적합 한 일정을 선택 데 사용할 수 있습니다.  
  
 **정렬** 절 있어야 때 **정렬** 지시문 바인딩할는 **에 대 한** 생성 합니다.  
  
 끝에 암시적 장벽은는 **에 대 한** 하지 않는 경우 만들는 **nowait** 절을 지정 합니다.  
  
 에 대 한 제한 된 **에 대 한** 지시문은 다음과 같습니다.  
  
-   **에 대 한** 루프 구조화 된 블록 수 있어야 하며이으로 실행 하지 종료 해야 또한는 **나누기** 문.  
  
-   루프의 값은 식의 제어는 **에 대 한** 와 관련 된 루프는 **에 대 한** 지시문 팀의 모든 스레드에 대해 동일 해야 합니다.  
  
-   **에 대 한** 루프 반복 변수는 부호 있는 정수 형식이 있어야 합니다.  
  
-   단일 **일정** 절에 나타날 수 있습니다는 **에 대 한** 지시문입니다.  
  
-   단일 **정렬** 절에 나타날 수 있습니다는 **에 대 한** 지시문입니다.  
  
-   단일 **nowait** 절에 나타날 수 있습니다는 **에 대 한** 지시문입니다.  
  
-   지정 되지 않은 경우 또는 모든 면에서 영향을 얼마나 자주는 *chunk_size*, *lb*, *b*, 또는 *incr* 식 발생 합니다.  
  
-   값은 *chunk_size* 식 팀의 모든 스레드에 대해 동일 해야 합니다.  
  
## <a name="cross-references"></a>교차 참조:  
  
-   **개인**, **firstprivate**, **lastprivate**, 및 **감소** 절에서 참조 [섹션 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) 25 페이지.  
  
-   **OMP_SCHEDULE** 환경 변수 참조 [섹션 4.1](../../parallel/openmp/4-1-omp-schedule.md) 코어 48 개 페이지에 있습니다.  
  
-   **정렬** 생성을 참조 하십시오. [섹션 2.6.6](../../parallel/openmp/2-6-6-ordered-construct.md) 페이지 22.  
  
-   [부록 D](../../parallel/openmp/d-using-the-schedule-clause.md), 페이지, 93 일정 절을 사용 하 여 대 한 자세한 내용을 제공 합니다.