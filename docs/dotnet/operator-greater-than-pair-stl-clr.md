---
title: 演算子&gt;(組) (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::pair::operator>
dev_langs:
- C++
helpviewer_keywords:
- operator> member [STL/CLR]
ms.assetid: c392a696-3425-49c8-9ddf-be2f2d2dd42e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 30b388bbe60d252c15ca77c749f48e5b2b8a8e87
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="operatorgt-pair-stlclr"></a>演算子&gt;(組) (STL/CLR)
比較よりも大きい値のペア。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename Value1,  
    typename Value2>  
    bool operator>(pair<Value1, Value2>% left,  
        pair<Value1, Value2>% right);  
```  
  
#### <a name="parameters"></a>パラメーター  
 左へ  
 比較する左のペア。  
  
 右  
 比較する右のペア。  
  
## <a name="remarks"></a>コメント  
 演算子関数を返します`right` `<` `left`です。 テストするために使用するかどうか`left`が後に順序付け`right`とき要素によって比較対象の要素では 2 つのペア。  
  
## <a name="example"></a>例  
  
```  
// cliext_pair_operator_gt.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
    cliext::pair<wchar_t, int> c2(L'x', 4);   
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);   
  
    System::Console::WriteLine("[x 3] > [x 3] is {0}",   
        c1 > c1);   
    System::Console::WriteLine("[x 4] > [x 3] is {0}",   
        c2 > c1);   
    return (0);   
    }  
  
```  
  
```Output  
[x, 3]  
[x, 4]  
[x 3] > [x 3] is False  
[x 4] > [x 3] is True  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext ユーティリティ/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [ペア (STL/CLR)](../dotnet/pair-stl-clr.md)   
 [演算子 = = (組) (STL/CLR)](../dotnet/operator-equality-pair-stl-clr.md)   
 [operator! = (組) (STL/CLR)](../dotnet/operator-inequality-pair-stl-clr.md)   
 [演算子\<(組) (STL/CLR)](../dotnet/operator-less-than-pair-stl-clr.md)   
 [operator > = (組) (STL/CLR)](../dotnet/operator-greater-or-equal-pair-stl-clr.md)   
 [operator<= (pair) (STL/CLR)](../dotnet/operator-less-or-equal-pair-stl-clr.md)