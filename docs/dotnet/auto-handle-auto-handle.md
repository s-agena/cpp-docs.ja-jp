---
title: auto_handle::auto_handle |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- auto_handle::auto_handle
- msclr.auto_handle.auto_handle
- auto_handle.auto_handle
- msclr::auto_handle::auto_handle
dev_langs:
- C++
helpviewer_keywords:
- auto_handle method
ms.assetid: 0b68ab31-023c-4224-9601-9231412c4e13
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: af9ca3d472aa3c942b86d338a6b6f8f25a573ca8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="autohandleautohandle"></a>auto_handle::auto_handle
`auto_handle`コンス トラクターです。  
  
## <a name="syntax"></a>構文  
  
```  
auto_handle();  
auto_handle(  
   _element_type ^ _ptr  
);  
auto_handle(  
   auto_handle<_element_type> % _right  
);  
template<typename _other_type>  
auto_handle(  
   auto_handle<_other_type> % _right  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `_ptr`  
 所有するオブジェクト。  
  
 `_right`  
 既存の `auto_handle`。  
  
## <a name="example"></a>例  
  
```  
// msl_auto_handle_auto_handle.cpp  
// compile with: /clr  
#include "msclr\auto_handle.h"  
  
using namespace System;  
using namespace msclr;  
ref class RefClassA {  
protected:  
   String^ m_s;     
public:  
   RefClassA(String^ s) : m_s(s) {  
      Console::WriteLine( "in RefClassA constructor: " + m_s );  
   }  
   ~RefClassA() {  
      Console::WriteLine( "in RefClassA destructor: " + m_s );  
   }  
  
   virtual void PrintHello() {  
      Console::WriteLine( "Hello from {0} A!", m_s );  
   }  
};  
  
ref class RefClassB : RefClassA {  
public:     
   RefClassB( String^ s ) : RefClassA( s ) {}  
   virtual void PrintHello() new {  
      Console::WriteLine( "Hello from {0} B!", m_s );  
   }  
};  
  
int main()  
{  
   {  
      auto_handle<RefClassA> a(gcnew RefClassA( "first" ) );  
      a->PrintHello();  
   }  
  
   {  
      auto_handle<RefClassB> b(gcnew RefClassB( "second" ) );  
      b->PrintHello();  
      auto_handle<RefClassA> a(b); //construct from derived type  
      a->PrintHello();  
      auto_handle<RefClassA> a2(a); //construct from same type  
      a2->PrintHello();  
   }  
  
   Console::WriteLine("done");  
}  
```  
  
```Output  
in RefClassA constructor: first  
Hello from first A!  
in RefClassA destructor: first  
in RefClassA constructor: second  
Hello from second B!  
Hello from second A!  
Hello from second A!  
in RefClassA destructor: second  
done  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー ファイル** \<msclr\auto_handle.h >  
  
 **Namespace** msclr  
  
## <a name="see-also"></a>関連項目  
 [auto_handle メンバー](../dotnet/auto-handle-members.md)   
 [auto_handle::operator =](../dotnet/auto-handle-operator-assign.md)   
 [auto_handle::~auto_handle](../dotnet/auto-handle-tilde-auto-handle.md)