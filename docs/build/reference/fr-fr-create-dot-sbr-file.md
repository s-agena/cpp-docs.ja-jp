---
title: -、Fr-fr (を作成します。Sbr ファイル) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLWCECompilerTool.BrowseInformation
- VC.Project.VCCLCompilerTool.BrowseInformation
- /fr
- VC.Project.VCCLCompilerTool.BrowseInformationFile
- VC.Project.VCCLWCECompilerTool.BrowseInformationFile
dev_langs:
- C++
helpviewer_keywords:
- /FR compiler option [C++]
- -FR compiler option [C++]
- FR compiler option [C++]
- symbolic browser information
ms.assetid: 3fd8f88b-3924-4feb-9393-287036a28896
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e6f61a3360c820a2d47d54f7c174af484079d154
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="fr-fr-create-sbr-file"></a>/FR、/Fr (.sbr ファイルの作成)
.sbr ファイルを作成します。  
  
## <a name="syntax"></a>構文  
  
```  
/FR[pathname[\filename]]  
/Fr[pathname[\filename]]  
```  
  
## <a name="remarks"></a>コメント  
 ビルド処理中、Microsoft Browse Information File Maintenance Utility (BSCMAKE) はこれらのファイルを使って BSC ファイルを作成します。このファイルは、ブラウザー情報を表示するために使います。  
  
 **/FR** は、完全なシンボリック情報を含む .sbr ファイルを作成します。  
  
 **/Fr** は、ローカル変数に関する情報を含まない .sbr ファイルを作成します。  
  
 `filename`を指定しない場合、.sbr ファイルはソース ファイルと同じベース名を取得します。  
  
 
  **/Fr** は非推奨とされます。代わりに **/FR** を使用してください。 詳しくは、 [Compiler Options Listed by Category](../../build/reference/compiler-options-listed-by-category.md)の「非推奨とされた削除済みのコンパイラ オプション」をご覧ください。  
  
> [!NOTE]
>  .sbr 拡張子を変更しないでください。 BSCMAKE では、中間ファイルにその拡張子を含める必要があります。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  ナビゲーション ウィンドウで、 **[C/C++]**、 **[ブラウザー情報]** プロパティ ページを選択してください。  
  
3.  **[ブラウザー情報ファイル]** か **[ブラウザー情報の有効化]** プロパティを変更します。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BrowseInformation%2A> 」および「 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BrowseInformationFile%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [出力ファイル (/F) オプション](../../build/reference/output-file-f-options.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)   
 [パス名の指定](../../build/reference/specifying-the-pathname.md)