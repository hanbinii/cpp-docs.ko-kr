---
title: "일정 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: schedule
dev_langs: C++
helpviewer_keywords: schedule OpenMP clause
ms.assetid: 286f1fc3-6598-4837-b4c8-8b1fa3193965
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 30023c9e994300b9dcdb09509e7d0c2218aa26f3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="schedule"></a>일정
에 적용 된 [에 대 한](../../../parallel/openmp/reference/for-openmp.md) 지시문입니다.  
  
## <a name="syntax"></a>구문  
  
```  
schedule(type[,size])  
```  
  
#### <a name="parameters"></a>매개 변수  
 `type`  
 일정의 종류:  
  
-   `dynamic`  
  
-   `guided`  
  
-   `runtime`  
  
-   `static`  
  
 `size`(선택 사항)  
 반복의 크기를 지정합니다. `size`정수 여야 합니다. 경우에 유효 하지 않은 `type` 은 `runtime`합니다.  
  
## <a name="remarks"></a>설명  
 자세한 내용은 참조 [2.4.1 for 구문](../../../parallel/openmp/2-4-1-for-construct.md)합니다.  
  
## <a name="example"></a>예제  
  
```  
// omp_schedule.cpp  
// compile with: /openmp   
#include <windows.h>  
#include <stdio.h>  
#include <omp.h>  
  
#define NUM_THREADS 4  
#define STATIC_CHUNK 5  
#define DYNAMIC_CHUNK 5  
#define NUM_LOOPS 20  
#define SLEEP_EVERY_N 3  
  
int main( )   
{  
    int nStatic1[NUM_LOOPS],   
        nStaticN[NUM_LOOPS];  
    int nDynamic1[NUM_LOOPS],   
        nDynamicN[NUM_LOOPS];  
    int nGuided[NUM_LOOPS];  
  
    omp_set_num_threads(NUM_THREADS);  
  
    #pragma omp parallel  
    {  
        #pragma omp for schedule(static, 1)  
        for (int i = 0 ; i < NUM_LOOPS ; ++i)   
        {  
            if ((i % SLEEP_EVERY_N) == 0)   
                Sleep(0);  
            nStatic1[i] = omp_get_thread_num( );  
        }  
  
        #pragma omp for schedule(static, STATIC_CHUNK)  
        for (int i = 0 ; i < NUM_LOOPS ; ++i)   
        {  
            if ((i % SLEEP_EVERY_N) == 0)   
                Sleep(0);  
            nStaticN[i] = omp_get_thread_num( );  
        }  
  
        #pragma omp for schedule(dynamic, 1)  
        for (int i = 0 ; i < NUM_LOOPS ; ++i)   
        {  
            if ((i % SLEEP_EVERY_N) == 0)   
                Sleep(0);  
            nDynamic1[i] = omp_get_thread_num( );  
        }  
  
        #pragma omp for schedule(dynamic, DYNAMIC_CHUNK)  
        for (int i = 0 ; i < NUM_LOOPS ; ++i)   
        {  
            if ((i % SLEEP_EVERY_N) == 0)   
                Sleep(0);  
            nDynamicN[i] = omp_get_thread_num( );  
        }  
  
        #pragma omp for schedule(guided)  
        for (int i = 0 ; i < NUM_LOOPS ; ++i)   
        {  
            if ((i % SLEEP_EVERY_N) == 0)   
                Sleep(0);  
            nGuided[i] = omp_get_thread_num( );  
        }  
    }  
  
    printf_s("------------------------------------------------\n");  
    printf_s("| static | static | dynamic | dynamic | guided |\n");  
    printf_s("|    1   |    %d   |    1    |    %d    |        |\n",  
             STATIC_CHUNK, DYNAMIC_CHUNK);  
    printf_s("------------------------------------------------\n");  
  
    for (int i=0; i<NUM_LOOPS; ++i)   
    {  
        printf_s("|    %d   |    %d   |    %d    |    %d    |"  
                 "    %d   |\n",  
                 nStatic1[i], nStaticN[i],  
                 nDynamic1[i], nDynamicN[i], nGuided[i]);  
    }  
  
    printf_s("------------------------------------------------\n");  
}  
```  
  
```Output  
------------------------------------------------  
| static | static | dynamic | dynamic | guided |  
|    1   |    5   |    1    |    5    |        |  
------------------------------------------------  
|    0   |    0   |    0    |    2    |    1   |  
|    1   |    0   |    3    |    2    |    1   |  
|    2   |    0   |    3    |    2    |    1   |  
|    3   |    0   |    3    |    2    |    1   |  
|    0   |    0   |    2    |    2    |    1   |  
|    1   |    1   |    2    |    3    |    3   |  
|    2   |    1   |    2    |    3    |    3   |  
|    3   |    1   |    0    |    3    |    3   |  
|    0   |    1   |    0    |    3    |    3   |  
|    1   |    1   |    0    |    3    |    2   |  
|    2   |    2   |    1    |    0    |    2   |  
|    3   |    2   |    1    |    0    |    2   |  
|    0   |    2   |    1    |    0    |    3   |  
|    1   |    2   |    2    |    0    |    3   |  
|    2   |    2   |    2    |    0    |    0   |  
|    3   |    3   |    2    |    1    |    0   |  
|    0   |    3   |    3    |    1    |    1   |  
|    1   |    3   |    3    |    1    |    1   |  
|    2   |    3   |    3    |    1    |    1   |  
|    3   |    3   |    0    |    1    |    3   |  
------------------------------------------------  
  
```  
  
## <a name="see-also"></a>참고 항목  
 [절](../../../parallel/openmp/reference/openmp-clauses.md)