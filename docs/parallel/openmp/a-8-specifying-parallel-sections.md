---
title: 並列部分を指定する A.8 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: cf399304-121e-4c07-9829-47e0dbc2ef10
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: acb28f4e7e99ea09696d116ab031778fcf9ff919
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="a8---specifying-parallel-sections"></a>A.8 並行セクションの指定
次の例では、(の[2.4.2](../../parallel/openmp/2-4-2-sections-construct.md) [14] ページ) 関数*xaxis*、 *yaxis*、および*zaxis*同時に実行することができます。 最初の`section`ディレクティブは省略可能です。  なおすべて`section`ディレクティブの構文の範囲で表示する必要は、`parallel sections`を構築します。  
  
```  
#pragma omp parallel sections  
{  
    #pragma omp section  
        xaxis();  
    #pragma omp section  
        yaxis();  
    #pragma omp section  
        zaxis();  
}  
```