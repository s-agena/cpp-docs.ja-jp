---
title: サーバー |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OLE server applications [MFC]
- OLE server applications [MFC], activation
- full-server
- servers
- mini-server
- OLE server applications [MFC], server types
- server applications [MFC]
ms.assetid: e45172e8-eae3-400a-8139-0fa009a42fdc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7d153d73889520deaff12b64da36567a8b9a4087
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="servers"></a>サーバー
サーバー アプリケーション (またはコンポーネントのアプリケーション) は、コンテナー アプリケーションで OLE 項目 (コンポーネント) の使用を作成します。 ビジュアル編集サーバー アプリケーションには、ビジュアル編集や、インプレース アクティブ化もサポートしています。 OLE サーバーの別の形式は、[オートメーション サーバー](../mfc/automation-servers.md)です。 一部のサーバー アプリケーションが埋め込み項目の作成のみをサポートします。他のユーザーは、埋め込みとリンクの両方の項目の作成をサポートします。 いくつかのリンクをサポートのみ、これはまれですが。 すべてのサーバー アプリケーションは、ユーザーがアイテムを編集するときに、コンテナー アプリケーションでアクティブ化をサポートする必要があります。 アプリケーションには、コンテナーとサーバーの両方を指定できます。 つまり、両方のドキュメントにデータを組み込むしてデータを組み込んで項目として他のアプリケーションのドキュメントを作成します。  
  
 ミニサーバーは特殊なコンテナーでのみ起動できるサーバー アプリケーションです。 Microsoft の描画と Microsoft Graph miniservers の例に示します。 ミニサーバーはドキュメントがディスク上のファイルとして保存されません。 代わりからそのドキュメントを読み取るし、コンテナーに属するドキュメント内の項目に書き込みます。 その結果、ミニサーバー埋め込みにのみ、いないのリンクをサポートします。  
  
 サーバー全体のスタンドアロン アプリケーションとして実行またはコンテナー アプリケーションを起動できます。 サーバー全体では、ディスク上のファイルとして、ドキュメントを格納できます。 両方の埋め込みにのみ、埋め込みとリンク、またはリンクだけをサポートできます。 コンテナー アプリケーションのユーザーは、サーバーと、コンテナーに貼り付けコマンドで、切り取りまたはコピー コマンドを選択して、埋め込まれたアイテムを作成できます。 コンテナーにサーバーにコピー コマンドとリンク貼り付け コマンドを選択して、リンクされた項目が作成されます。 また、ユーザーは、オブジェクトの挿入 ダイアログ ボックスを使用して埋め込みまたはリンクされた項目を作成できます。  
  
 次の表は、異なる種類のサーバーの特性をまとめたものです。  
  
### <a name="server-characteristics"></a>サーバーの特性  
  
|サーバーの種類|複数のインスタンスをサポートしています|ドキュメントあたりのアイテム|インスタンスあたりのドキュメント|  
|--------------------|---------------------------------|------------------------|----------------------------|  
|ミニサーバー|[はい]|1|1|  
|SDI サーバーの完全|[はい]|1 (リンクがサポートされている場合は、1 つ以上)|1|  
|MDI フル サーバー|いいえ (は必要ありません)|1 (リンクがサポートされている場合は、1 つ以上)|0 個以上|  
  
 サーバー アプリケーションは、埋め込みまたはリンクされた項目の編集に使用される 1 つ以上のコンテナーを複数のコンテナーを同時に、サポートする必要があります。 サーバーが SDI アプリケーション (またはダイアログ ボックス インターフェイスを持つミニサーバー) の場合は、サーバーの複数のインスタンスが同時に実行できる必要があります。 これにより、各コンテナーからの要求を処理するアプリケーションの個別のインスタンス。  
  
 サーバーが MDI アプリケーションの場合は、コンテナーは、アイテムを編集する必要があるたびを新しい MDI 子ウィンドウに作成できます。 この方法では、アプリケーションの 1 つのインスタンスが複数のコンテナーをサポートできます。  
  
 サーバー アプリケーションする必要があります指定 OLE システム Dll の別のコンテナーは、そのサービスを要求したときに、サーバーの 1 つのインスタンスが既に実行されている場合の対処方法: か、サーバーの新しいインスタンスを起動または 1 つのインスタンスにすべてのコンテナーの要求を送信する必要があります、サーバー。  
  
 サーバーの詳細についてを参照してください。  
  
-   [サーバー: サーバーの実装](../mfc/servers-implementing-a-server.md)  
  
-   [サーバー: サーバー ドキュメントの実装](../mfc/servers-implementing-server-documents.md)  
  
-   [サーバー: 埋め込み先フレーム ウィンドウの実装](../mfc/servers-implementing-in-place-frame-windows.md)  
  
-   [サーバー: サーバー アイテム](../mfc/servers-server-items.md)  
  
-   [サーバー: サーバーとユーザー インターフェイス](../mfc/servers-user-interface-issues.md)  
  
## <a name="see-also"></a>関連項目  
 [OLE](../mfc/ole-in-mfc.md)   
 [コンテナー](../mfc/containers.md)   
 [コンテナー: 高度な機能](../mfc/containers-advanced-features.md)   
 [メニューとリソース (OLE)](../mfc/menus-and-resources-ole.md)   
 [登録](../mfc/registration.md)   
 [オートメーション サーバー](../mfc/automation-servers.md)

