---
title: 'エラー: サーバーに自動的にステップ インできません |。Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.causality_no_server_response
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- remote debugging, notification error
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b9e7b3c45e49425c07c545f2a04673887fc8cac7
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2018
ms.locfileid: "44278674"
---
# <a name="error-unable-to-automatically-step-into-the-server"></a>エラー : サーバーに自動的にステップ インできません。
このエラーは次のように表示されます。  
  
 サーバーに自動的にステップ インできません。 デバッガーは、リモート プロシージャが実行される前に通知されませんでした。  
  
 Web サービスにステップ インしようとしているときに、このエラーが発生することができます (を参照してください[XML Web サービスへのステップ実行](https://msdn.microsoft.com/library/8e67de38-bf5f-41cc-a457-1b88ce63d764))。 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] が正しくセットアップされていない場合に発生する可能性があります。  
  
 考えられる原因:  
  
-   [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] アプリケーションの web.config ファイルでデバッグを "true" に設定していません (「 [方法: .NET アプリケーションのデバッグを有効にする](../debugger/how-to-enable-debugging-for-aspnet-applications.md)」を参照してください)。  
  
-   いずれかのバージョンの [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] が Visual Studio のインストール後にインストールされました。 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] は Visual Studio のインストール前にインストールする必要があります。 この問題を解決する、Windows を使用して、**コントロール パネル] > [プログラムと機能**Visual Studio のインストールを修復します。  
  
## <a name="see-also"></a>関連項目  
 [リモート デバッグ エラーとトラブルシューティング](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [Remote Debugging](../debugger/remote-debugging.md)