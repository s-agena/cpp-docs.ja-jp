---
title: deque::empty (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::deque::empty
dev_langs:
- C++
helpviewer_keywords:
- empty member [STL/CLR]
ms.assetid: 6ff3dd07-ebdf-47f9-b0d2-8a3229390d3b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 5e951cbf8e6ba1599749bc5864a5e54bcd8ffccd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="dequeempty-stlclr"></a>deque::empty (STL/CLR)
要素が存在しないかどうかをテストします。  
  
## <a name="syntax"></a>構文  
  
```  
bool empty();  
```  
  
## <a name="remarks"></a>コメント  
 このメンバー関数は、被制御シーケンスが空の場合に true を返します。 等価である[deque::size (STL/CLR)](../dotnet/deque-size-stl-clr.md)`() == 0`です。 これを使用するには、deque が空かどうかをテストします。  
  
## <a name="example"></a>例  
  
```  
// cliext_deque_empty.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    System::Console::WriteLine("empty() = {0}", c1.empty());   
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    System::Console::WriteLine("empty() = {0}", c1.empty());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
size() = 3  
empty() = False  
size() = 0  
empty() = True  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/deque >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [deque::size (STL/CLR)](../dotnet/deque-size-stl-clr.md)