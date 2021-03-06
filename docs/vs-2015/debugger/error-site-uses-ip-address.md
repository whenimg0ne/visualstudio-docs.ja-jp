---
title: 'エラー: サイトは IP アドレスの使用 |Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.error.webdbg_siteusesipaddress
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- debugger, Web application errors
ms.assetid: b2b8ddc8-746d-46e3-87a6-b956b1ee048d
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 93d64f06db4b1f070da4f0963ed879ef64e4cb33
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "47544942"
---
# <a name="error-site-uses-ip-address"></a>エラー : サイトは IP アドレスを使用しています
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

このトピックの最新バージョンをご覧[エラー: サイトを使用して IP アドレス](https://docs.microsoft.com/visualstudio/debugger/error-site-uses-ip-address)します。  
  
このエラーは、IP アドレスを使用している Web アプリケーションに、デバッガーが自動アタッチしようとしたときに発生します。 これを変更する場合に発生**Web サイトの識別**に**特定の IP アドレスを使用して、** IIS でします。  
  
 自動アタッチが機能するには、コンピューター名だけでなく、IP アドレスを指定したプロジェクトを作成する必要があります。 そうしないと、コンピューター名は localhost に変更されるため、DEBUG 動詞を IIS に送信するときにエラーが発生します。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
1.  使用して手動のアタッチ (デバッグ メニューから選択**プロセスにアタッチ**)。  
  
     または  
  
2.  変更、 **IIS Web サイトの識別**設定します。  
  
## <a name="see-also"></a>関連項目  
 [Web アプリケーションのデバッグ : エラーおよびトラブルシューティング](../debugger/debugging-web-applications-errors-and-troubleshooting.md)



