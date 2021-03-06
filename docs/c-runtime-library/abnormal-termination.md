---
title: _abnormal_termination | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- _abnormal_termination
apilocation:
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr90.dll
- msvcr120.dll
- msvcrt.dll
- msvcr80.dll
- msvcr100.dll
apitype: DLLExport
f1_keywords:
- _abnormal_termination
dev_langs:
- C++
helpviewer_keywords:
- _abnormal_termination
ms.assetid: 952970a4-9586-4c3d-807a-db729448c91c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f70520b60ccfaf1af5b223bcb4ea1a90639aa484
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="abnormaltermination"></a>_abnormal_termination
システムが終了ハンドラーの内部リストの実行中に、[try-finally ステートメント](../cpp/try-finally-statement.md)の `__finally` ブロックが入力されているかどうかを示します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
int   _abnormal_termination(  
   );  
```  
  
## <a name="return-value"></a>戻り値  
 システムがスタックを*アンワインド*する場合は `true`、それ以外は `false` です。  
  
## <a name="remarks"></a>コメント  
 これは、アンワインドの例外を管理するために使用される内部関数で、ユーザー コードから呼び出されるものではありません。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|_abnormal_termination|excpt.h|  
  
## <a name="see-also"></a>参照  
 [try-finally ステートメント](../cpp/try-finally-statement.md)