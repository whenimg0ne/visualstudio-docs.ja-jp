---
title: イベントの説明 |Microsoft Docs
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
- debugging [Debugging SDK], events
ms.assetid: 09f61652-7e16-4bb0-8055-f61a84bf384e
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 160cd1558401e488dec82e79627f306ef98e75ef
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "47548020"
---
# <a name="event-descriptions"></a>イベントの説明
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

このトピックの最新バージョンをご覧[イベントの説明](https://docs.microsoft.com/visualstudio/extensibility/debugger/event-descriptions)します。  
  
各イベントの種類には、特定の目的があります。  
  
## <a name="events-and-the-reasons-for-their-use"></a>イベントとその使用する理由  
  
|event|説明|  
|-----------|-----------------|  
|ドキュメントのイベントをアクティブ化します。|デバッグ エンジン (DE) が、IDE を開くか、フォア グラウンドにドキュメントを表示するときに発生します。|  
|ブレークポイントがバインドされているか、ブレークポイントのエラー イベント|ブレークポイントがバインドされている場合またはブレークポイントがバインドできないし、エラーが返されますと送信されます。|  
|ブレークポイントがバインドされていないイベント|バインドされたブレークポイントをコードからバインド解除すると発生します。|  
|イベントを停止することができます。|ユーザーがコードで指定した時点で停止するにはあるかどうかを判断する、IDE に送信されます。|  
|ブレークポイント イベント|コードまたはデータのブレークポイントがヒットしたときに発生します。|  
|ドキュメントのテキストのイベント|ドキュメント内のテキストが変更されたときに発生します。 これらのイベントがを介して送信されません、`IDebugEventCallBack2::Event`メソッド。|  
|エンジンのイベントを作成します。|エンジンが最初に作成されたときに送信します。|  
|エントリ ポイント イベント|デバッグ中のプログラムが初期化コードを実行し、その最初のユーザー エントリ ポイントに達したときに送信します。|  
|例外イベント|実行中のプログラムが例外をヒットしたときに送信されます。|  
|式の評価の完了イベント|非同期の式の評価が完了すると送信されます。|  
|シンボルのイベントを検索します。|モジュールのシンボルを検索するユーザーに確認する必要があります、DE たびに送信されます。|  
|読み込み完了イベント|送信のみと初期プログラムの読み込みが完了し、最初のコードは、プログラムで実行されます。|  
|メッセージ イベント|ユーザーに送信されたメッセージを送信します。|  
|モジュール読み込みイベント|新しいモジュールがロードまたはアンロードされるときに送信します。|  
|文字列の出力イベント|プログラムがデバッグ出力を書き込むときに送信されます。|  
|作成し、破棄イベント|Visual Studio IDE は状態の追跡、デバッグ中のプログラムのために作成またはプロセス、プログラム、プロパティ、セッション、およびスレッドの破棄を発表に送信されます。|  
|手順の完了イベント|ステップの完了時に送信されます。|  
|スレッド名の変更イベント|スレッドの名前を変更したときに送信されます。|  
|プログラム名の変更イベント|プログラムの名前を変更したときに送信されます。|  
  
## <a name="see-also"></a>関連項目  
 [イベントの送信](../../extensibility/debugger/sending-events.md)

