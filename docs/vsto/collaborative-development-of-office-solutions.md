---
title: Office ソリューションの共同開発
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office applications [Office development in Visual Studio], collaborative development
- Office development in Visual Studio, collaboration
- source control [Office development in Visual Studio]
- collaborative development [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 9bf85dd1ba39df35e337f1b6b80099e3d5bcd774
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
ms.locfileid: "34267777"
---
# <a name="collaborative-development-of-office-solutions"></a>Office ソリューションの共同開発
  複数の開発者は、その他の Visual Studio プロジェクトで共同作業すると同じ方法で Office プロジェクトで作業できます。 Visual Studio は、別の場所で Office がインストールされている場合でも、各コンピューターに Microsoft Office のインストールを正しく検索します。 ただし、これには注意すべき重要な考慮事項があります。  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## <a name="debug-properties-are-not-shared"></a>デバッグ プロパティは共有されません  
 デバッグ プロパティは、ソース管理で複数のユーザー間では共有されません。 Visual Basic および Visual c# プロジェクトでは、ユーザー固有のファイルのデバッグ プロパティを格納 (*ProjectName*. vbproj.user または*ProjectName*。 csproj.user)、このファイルはソース管理下にありません。 複数のユーザーがデバッグを実行する場合は、各自が手動でデバッグ プロパティを入力する必要があります。  
  
 プロジェクトがソース管理の代わりにネットワーク共有に格納されている場合は、ソリューションを開き、アセンブリをテストする開発者が共同作業できるようにする、追加の手順を実行する必要があります。  
  
## <a name="source-control-requires-checking-out-all-files"></a>ソース管理では、すべてのファイルをチェック アウトが必要です。  
 で、プロジェクトをソース管理を使用する必要がありますをチェック アウトする、ファイル内のコード ファイルの下のすべて**ソリューション エクスプ ローラー** (など、 *ThisDocument*、 *ThisWorkbook*、または*ThisAddIn*コード ファイル)、コード ファイルを変更するたびにも既定で非表示になっているファイル。 最上位のコード ファイルのみをチェックする場合、変更内容は失われます。  
  
 変更を加えた後でバックアップのすべてのファイルを確認してください。 プロジェクトでは非表示のコード ファイルの詳細については、次を参照してください。 [Visual Studio 環境における Office プロジェクト](../vsto/office-projects-in-the-visual-studio-environment.md)です。  
  
## <a name="security-for-informal-collaboration-on-a-network"></a>ネットワーク上の共同作業のセキュリティ  
 ネットワークの場所にあるすべてのドキュメント レベルのソリューション (など\\ \\ *Servername*\\*Sharename*)、完全修飾の場所に追加する必要があります使用している Microsoft Office アプリケーションで信頼できるフォルダー一覧です。 メイン フォルダーの下のサブディレクトリを含めるまたは具体的にはデバッグを追加し、信頼できるフォルダー一覧にフォルダーを作成するオプションを選択します。 これを行う方法の詳細については、次を参照してください。[ドキュメントへの信頼を付与](../vsto/granting-trust-to-documents.md)です。  
  
 ビルド時に自動的に生成される一時的な証明書は、パスワードで保護されていません。 証明書には、開発者のログイン名とその他の個人情報が含まれます。 一時的な証明書によって署名されているカスタマイズを配置する場合は、この情報にアクセスできない他のユーザー必要があります。  
  
## <a name="see-also"></a>関連項目  
 [セキュリティで保護された Office ソリューション](../vsto/securing-office-solutions.md)   
 [設計および Office ソリューションを作成します。](../vsto/designing-and-creating-office-solutions.md)   
 [Office ソリューションを構築します。](../vsto/building-office-solutions.md)  
  
  