---
title: '方法: リソース スクリプト ファイルを作成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- rc files, creating
- .rc files, creating
- resource script files, creating
ms.assetid: 82be732a-cdcd-4a58-8de7-976d1418f86b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a15352640a39ff6adc3b5a956a1f32c9fd414272
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="how-to-create-a-resource-script-file"></a>方法: リソース スクリプト ファイルを作成する
> [!NOTE]
>  リソース エディターは Express Edition では使用できません。  
>   
>  これは Windows デスクトップ アプリケーションだけに適用できます。 .NET 言語のプロジェクトでは、リソース スクリプト ファイルを使用しません。 詳細については、「 [リソース ファイル (Visual Studio)](../windows/resource-files-visual-studio.md)」を参照してください。  
  
### <a name="to-create-a-new-resource-script-rc-file"></a>リソース スクリプト (.rc) ファイルを新規作成するには  
  
1.  `Solution Explorer`で、"MyProject" などの既存のプロジェクト フォルダーにフォーカスを移します。  
  
    > [!NOTE]
    >  プロジェクト フォルダーをソリューション エクスプローラーの [ソリューション] フォルダーと混同しないでください。 [ソリューション] フォルダーにフォーカスを移すと、**[新しい項目の追加]** ダイアログ ボックスで選択した項目 (手順 3) とは異なった項目になります。  
  
2.  **[プロジェクト]** メニューの **[新しい項目の追加]** をクリックします。  
  
3.  **[新しい項目の追加]** ダイアログ ボックスで、 **[Visual C++]** フォルダーをクリックし、右側のペインの **[リソース ファイル (.rc)]** を選択します。  
  
4.  **[プロジェクト名]** ボックスにリソース スクリプト ファイルの名前を入力し、 **[開く]** をクリックします。  
  
 これで、新しいリソースを [作成](../windows/how-to-create-a-resource.md) して .rc ファイルに追加できます。  
  
> [!NOTE]
>  リソース スクリプト (.rc ファイル) を追加できるのは、Visual Studio IDE に読み込まれる既存のプロジェクトだけです。 プロジェクトの外側にあるスタンドアロンの .rc ファイルは作成できません。 [リソース テンプレート](../windows/how-to-use-resource-templates.md) (.rct ファイル) はいつでも作成できます。  
  
 必要条件  
  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [リソース ファイル (Visual Studio)](../windows/resource-files-visual-studio.md)   
 [リソース エディター](../windows/resource-editors.md)