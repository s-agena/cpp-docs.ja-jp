---
title: コンパイラ エラー C2626 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2626
dev_langs:
- C++
helpviewer_keywords:
- C2626
ms.assetid: 4c283ad0-251b-4571-bc18-468b9836746f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7b7b2ea1473b4226382e9aa3bd17b0bfc092f5cf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2626"></a>コンパイラ エラー C2626
'identifier': プライベートまたはプロテクト データ メンバーは、匿名構造体または共用体では許可されていません  
  
 匿名構造体または共用体のメンバーは、パブリック アクセスを持つ必要があります。  
  
 次の例では C2626 が生成されます。  
  
```  
// C2626.cpp  
int main() {  
   union {  
   protected:  
      int j;     // C2626, j is protected  
   private:  
      int k;     // C2626, k is private  
   };  
}  
```  
  
 この問題を解決するには、プライベートまたはプロテクト タグを削除します。  
  
```  
// C2626b.cpp  
int main() {  
   union {  
   public:  
      int i;   // OK, i is public  
   };  
}  
```