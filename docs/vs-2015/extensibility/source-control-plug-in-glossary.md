---
title: ソース管理プラグインの用語集 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- glossary [Visual Studio SDK]
- source control plug-ins, glossary
ms.assetid: f224bbc9-38fc-4c80-ab09-51dcc8969f8e
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 69bb35df7f03294e0ece6c7a7d4306d8cdf4f03b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "47537554"
---
# <a name="source-control-plug-in-glossary"></a>ソース管理プラグインの用語集
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

このトピックの最新バージョンをご覧[ソース管理プラグインの用語集](https://docs.microsoft.com/visualstudio/extensibility/source-control-plug-in-glossary)します。  
  
次の便利な用語と定義は、ソース管理プラグインの SDK ドキュメントに適用されます。  
  
## <a name="definitions"></a>定義  
 チェックイン  
 ユーザーが作業コピーを変更すると、ユーザーは、作業用コピーを中央のソース管理リポジトリから変更を送信する必要があります。 これには、他のユーザーに提供されるファイルの新しいリビジョンが作成されます。 このプロセスには、チェックインは呼び出されます。  
  
 チェック アウト  
 変更を目的のリポジトリを知らせる、リポジトリから作業用コピーを要求する操作。 作業コピーは、プロジェクトがチェック アウトした時点の状態を反映します。  
  
 クライアント  
 ソース コード管理システムを使用するプログラム。 このドキュメントでは、Visual Studio IDE になります。  
  
 コメント  
 ソース管理操作が実行されると、ユーザーがのリビジョンにアタッチできる変更を説明するメッセージ。  
  
 競合  
 状況 2 人のユーザーが同じファイルの同じリージョンに変更をチェックインしようとします。 通常、マージを実行する必要があります。  
  
 ディレクトリ  
 クライアント側のローカル フォルダーは、"ディレクトリ"と呼ばれます。 これは、ユーザーが実際に変更を使用するコピーです。 特定のプロジェクトの多くの作業コピーがあります。通常、各開発者は自分のコピーが存在します。  
  
 Get  
 Get 操作では、ユーザーの作業コピー最新の状態をリポジトリのコピーが表示されます。 、チェック アウトとは異なり、ユーザーが最新のコピーを必要がありますだけですが、変更を加えないしようとしています。 ときに、get が実行されます。  
  
 履歴  
 すべてのチェック アウト、チェックイン、更新プログラム、タグ、およびソース管理リポジトリでのリリースの概要では通常します。  
  
 IDE  
 通常、Visual Studio 統合開発環境を指します。 ただし、ソース コントロールのプラグイン API を認識するその他のクライアント環境に参照もでした。  
  
 マージ  
 プロセスを以前のファイルからすべての機能が組み込まれている新しいファイルを形成する 2 つまたは複数のソースの中にコード ファイルが結合されます。 この概念は、ファイル上で 2 つ以上の開発者を場所作業同時にバージョン管理に不可欠です。  
  
 プロジェクト  
 ソース管理フォルダーは、プロジェクトとも呼ばれます。 Visual Studio では、プロジェクトまたはソリューションとのリレーションシップがありません。  
  
 プラグイン  
 ソース管理プラグイン API を実装することでソース管理機能を提供する DLL です。  
  
 リポジトリ  
 マスター コピーをソース管理システムでは、プロジェクトの完全なリビジョン履歴を格納します。 各プロジェクトには、1 つのリポジトリがあります。  
  
 リビジョン  
 ファイルの履歴またはファイルのセット、コミットされた変更。 リビジョンは、いずれかのスナップショットでは、プロジェクトの継続的に変化します。  
  
## <a name="see-also"></a>関連項目  
 [ソース管理プラグイン](../extensibility/source-control-plug-ins.md)

