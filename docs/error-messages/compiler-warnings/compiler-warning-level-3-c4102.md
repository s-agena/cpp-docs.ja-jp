---
title: コンパイラの警告 (レベル 3) C4102 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4102
dev_langs:
- C++
helpviewer_keywords:
- C4102
ms.assetid: 349f308a-daf3-48c6-bd53-6c38b73f8880
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3f3ee9f8e5c55c1963207b09ec58da0254ef448c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-3-c4102"></a>コンパイラの警告 (レベル 3) C4102
'label': 参照されていないラベル  
  
 ラベルが定義されていますが、一度も参照されていません。 コンパイラはこのラベルを無視します。  
  
 次の例では C4102 警告が生成されます。  
  
```  
// C4102.cpp  
// compile with: /W3  
int main() {  
   int a;  
  
   test:   // C4102, remove the unreferenced label to resolve  
  
   a = 1;  
}  
```