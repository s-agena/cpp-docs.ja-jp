---
title: コンパイラ エラー C2042 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2042
dev_langs:
- C++
helpviewer_keywords:
- C2042
ms.assetid: e111788f-41ce-405a-9824-a4c1c26059e6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b5b0442371b210f40d58a10b6bf1107979ea88db
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2042"></a>コンパイラ エラー C2042
'signed' と 'unsigned' が 1 つの宣言内で同時に使われています。  
  
 キーワード `signed` と `unsigned` は、1 つの宣言で使用します。  
  
 次の例では C2042 エラーが生成されます。  
  
```  
// C2042.cpp  
unsigned signed int i;   // C2042  
```  
  
 考えられる解決方法:  
  
```  
// C2042b.cpp  
// compile with: /c  
unsigned int i;  
signed int ii;  
```