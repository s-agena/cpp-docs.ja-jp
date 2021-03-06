---
title: _locking 定数 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- _LK_RLCK
- _LK_NBLCK
- _LK_LOCK
- _LK_NBRLCK
- _LK_UNLCK
dev_langs:
- C++
helpviewer_keywords:
- LK_UNLCK constant
- LK_NBRLCK constant
- _LK_NBRLCK constant
- _LK_NBLCK constant
- _LK_LOCK constant
- LK_NBLCK constant
- _LK_UNLCK constant
- LK_RLCK constant
- _LK_RLCK constant
- LK_LOCK constant
ms.assetid: c3dc92c8-60e3-4d29-9f50-5d217627c8ad
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 588c286cbad5e0097394a38eed34c09fc04af3ea
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="locking-constants"></a>_locking 定数
## <a name="syntax"></a>構文  
  
```  
  
#include <sys/locking.h>  
  
```  
  
## <a name="remarks"></a>コメント  
 `_locking` 関数の呼び出しにおける *mode* 引数によって、実行されるロック操作が指定されます。  
  
 *mode* 引数は、次のマニフェスト定数のいずれかである必要があります。  
  
 `_LK_LOCK`  
 指定したバイトをロックします。 バイトをロックできない場合は、関数によって 1 秒後に再試行されます。 10 回試行した後、バイトをロックできなかった場合、関数はエラーを返します。  
  
 `_LK_RLCK`  
 `_LK_LOCK` と同じ。  
  
 `_LK_NBLCK`  
 指定したバイトをロックします。 バイトをロックできない場合、関数はエラーを返します。  
  
 `_LK_NBRLCK`  
 `_LK_NBLCK` と同じ。  
  
 `_LK_UNLCK`  
 指定したバイトをロック解除します。 (バイトはすでにロックされている必要があります)。  
  
## <a name="see-also"></a>参照  
 [_locking](../c-runtime-library/reference/locking.md)   
 [グローバル定数](../c-runtime-library/global-constants.md)