---
title: データ連結 ActiveX コントロールのデバッグ |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- data-bound controls, ActiveX
- ActiveX controls, debugging
- controls [Visual Studio], ActiveX
ms.assetid: 9f6e1f00-e25b-48a9-8484-7e67a1232461
caps.latest.revision: 18
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6642b3687e4459cc001aef14ce0c1186231f8c97
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "47539470"
---
# <a name="debugging-a-data-bound-activex-control"></a>データ連結 ActiveX コントロールのデバッグ
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

このトピックの最新バージョンをご覧[データ連結 ActiveX コントロールのデバッグ](https://docs.microsoft.com/visualstudio/debugger/debugging-a-data-bound-activex-control)します。  
  
データ ソース コントロールに連結する ActiveX コントロールを開発している場合、独自のコンテナー アプリケーションを作成し、そのコンテナーを使用して ActiveX コントロールをデバッグできます。  
  
 たとえば、ダイアログ ベースの MFC アプリケーションを作成して、ダイアログ ボックスにデータ連結コントロールとデータ ソース コントロールを配置します。 この MFC アプリケーションは、データ連結 ActiveX コントロールをデバッグするためのコンテナー実行可能ファイルとして、ランタイム テストに使用できます。  
  
## <a name="using-the-test-container"></a>テスト コンテナーの使用  
 簡単に変更できるコンテナーでコントロールまたはコンテナーのさまざまなインターフェイスをサポートする場合は、デバッグ セッションの実行可能ファイルとして ActiveX テスト コンテナーを使用します。 ActiveX テスト コンテナーで次のようにクリックします。**オプション**から、**コンテナー**  メニューのさまざまなインターフェイスを有効にします。 詳細については、次を参照してください。[テスト プロパティとテスト コンテナーでイベント](http://msdn.microsoft.com/library/626867cf-fe53-4c30-8973-55bb93ef3917)します。  
  
 デバッグ中にコンテナーのコードにステップ インする必要がある場合は、デバッグ バージョンのコンテナーを使用するか、デバッグ バージョンの ActiveX テスト コンテナーを使用します。 詳細については、次を参照してください。 [TSTCON サンプル: ActiveX コントロール テスト コンテナー](http://msdn.microsoft.com/en-us/72fa40ef-27d3-400c-813f-10b03236e600)します。  
  
## <a name="see-also"></a>関連項目  
 [COM および ActiveX のデバッグ](../debugger/com-and-activex-debugging.md)   
 [ActiveX コントロール](http://msdn.microsoft.com/library/52aaec4d-3889-402e-b57d-758078f8ac57)



