---
title: list::const_reverse_iterator (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::list::const_reverse_iterator
dev_langs:
- C++
helpviewer_keywords:
- const_reverse_iterator member [STL/CLR]
ms.assetid: d9a9a1ec-df5f-411f-9918-beb5838ffa63
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 6b2f7e53b08891562a652bb0c91b6f4b05a46e83
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="listconstreverseiterator-stlclr"></a>list::const_reverse_iterator (STL/CLR)
被制御シーケンスの定数反転反復子の型。  
  
## <a name="syntax"></a>構文  
  
```  
typedef T4 const_reverse_iterator;  
```  
  
## <a name="remarks"></a>コメント  
 この型が指定されていない型のオブジェクトを表します`T4`被制御シーケンスの定数反転反復子として使用されることができます。  
  
## <a name="example"></a>例  
  
```  
// cliext_list_const_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c" reversed   
    cliext::list<wchar_t>::const_reverse_iterator crit = c1.rbegin();   
    cliext::list<wchar_t>::const_reverse_iterator crend = c1.rend();   
    for (; crit != crend; ++crit)   
        System::Console::Write(" {0}", *crit);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
c b a  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/一覧 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [一覧 (STL/CLR)](../dotnet/list-stl-clr.md)   
 [list::reverse_iterator (STL/CLR)](../dotnet/list-reverse-iterator-stl-clr.md)