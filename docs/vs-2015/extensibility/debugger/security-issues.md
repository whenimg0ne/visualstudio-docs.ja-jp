---
title: セキュリティの問題 |Microsoft Docs
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
- security [Debugging SDK]
- debugging [Debugging SDK], security
ms.assetid: d6ffff0a-afb4-4f38-86d8-476c881c4e4b
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 0459f7e91fbced71dda0bb401ffe056b5cd49f52
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "47534431"
---
# <a name="security-issues"></a>セキュリティ上の問題
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

このトピックの最新バージョンをご覧[セキュリティの問題](https://docs.microsoft.com/visualstudio/extensibility/debugger/security-issues)します。  
  
Visual Studio を使用してプログラムをデバッグするために必要なアクセス許可は、開発者がプログラムを実行する必要があるものと同じです。 これは、ほとんどの状況が (インターネット インフォメーション サービスなどの他のサービスに関連するいくつかの状況はより高いレベルのアクセス許可である必要があります) のリモート デバッグが含まれます。  
  
 Visual Studio の実行中に、プロセス デバッグ マネージャー (PDM) は、ローカル コンピューター上のデバッグ プロセスを追跡します。 リモートでのリモート デバッグを処理し、PDM を使用できるようにするために開発者 msvsmon.exe と呼ばれるプログラムを起動します。 (その msvsmon.exe がサービスではないと、そのコンピューターにリモート デバッグを有効にするのには手動で開始する必要がありますに注意してください)。Visual Studio (または msvsmon.exe) が実行されていない場合は、デバッグ プロセスが追跡ありません。  
  
 つまり、開発者が自分が特別なアクセス許可なしで開始されたプログラムをデバッグできます。 開発者は、その他の人が同じセキュリティ グループのメンバーである場合は、他のユーザーによって開始されたプロセスをデバッグもできます。 リモート デバッグを有効にする必要があるだけで、必要なをコピーするファイルをリモート コンピューターし、msvsmon.exe を開始し、(を参照してください[設定 Up the Remote Tools のデバイスで](http://msdn.microsoft.com/library/90f45630-0d26-4698-8c1f-63f85a12db9c)の詳細)。  
  
## <a name="see-also"></a>関連項目  
 [タスクのデバッグ](../../extensibility/debugger/debugging-tasks.md)   
 [プロセス デバッグ マネージャー](../../extensibility/debugger/process-debug-manager.md)   
 [デバイスのリモート ツールのセットアップ](http://msdn.microsoft.com/library/90f45630-0d26-4698-8c1f-63f85a12db9c)

