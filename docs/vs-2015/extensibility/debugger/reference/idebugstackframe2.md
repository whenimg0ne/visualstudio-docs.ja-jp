---
title: IDebugStackFrame2 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugStackFrame2
helpviewer_keywords:
- IDebugStackFrame2 interface
ms.assetid: bd212a6a-dcc6-4756-a77a-e8dfda38b104
caps.latest.revision: 15
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 57544c6ec8d329886d12bdcf2e8c622f7da53e4e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "47537831"
---
# <a name="idebugstackframe2"></a>IDebugStackFrame2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

このトピックの最新バージョンをご覧[IDebugStackFrame2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugstackframe2)します。  
  
このインターフェイスは、特定のスレッドのコール スタックの 1 つのスタック フレームを表します。  
  
## <a name="syntax"></a>構文  
  
```  
IDebugStackFrame2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>実装についてのメモ  
 デバッグ エンジン (DE) は、スタック フレームを表すためには、このインターフェイスを実装します。  
  
## <a name="notes-for-callers"></a>呼び出し元のノート  
 呼び出す[EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md)を取得する、 [IEnumDebugFrameInfo2](../../../extensibility/debugger/reference/ienumdebugframeinfo2.md)インターフェイス。 呼び出す[次](../../../extensibility/debugger/reference/ienumdebugframeinfo2-next.md)を取得する、 [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md)を含む構造体、`IDebugStackFrame2`インターフェイス。  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
 次の表は、メソッドの`IDebugStackFrame2`します。  
  
|メソッド|説明|  
|------------|-----------------|  
|[GetCodeContext](../../../extensibility/debugger/reference/idebugstackframe2-getcodecontext.md)|このスタック フレームのコードのコンテキストを取得します。|  
|[GetDocumentContext](../../../extensibility/debugger/reference/idebugstackframe2-getdocumentcontext.md)|このスタック フレームのドキュメント コンテキストを取得します。|  
|[GetName](../../../extensibility/debugger/reference/idebugstackframe2-getname.md)|スタック フレームの名前を取得します。|  
|[GetInfo](../../../extensibility/debugger/reference/idebugstackframe2-getinfo.md)|スタック フレームの説明を取得します。|  
|[GetPhysicalStackRange](../../../extensibility/debugger/reference/idebugstackframe2-getphysicalstackrange.md)|スタック フレームに関連付けられている物理アドレスの範囲のマシンに依存する形式を取得します。|  
|[GetExpressionContext](../../../extensibility/debugger/reference/idebugstackframe2-getexpressioncontext.md)|スタック フレームとスレッドの現在のコンテキストで式の評価を行うためには、評価コンテキストを取得します。|  
|[GetLanguageInfo](../../../extensibility/debugger/reference/idebugstackframe2-getlanguageinfo.md)|スタック フレームに関連付けられている言語を取得します。|  
|[GetDebugProperty](../../../extensibility/debugger/reference/idebugstackframe2-getdebugproperty.md)|スタック フレームに関連付けられているプロパティの説明を取得します。|  
|[EnumProperties](../../../extensibility/debugger/reference/idebugstackframe2-enumproperties.md)|スタックの列挙子フレームのプロパティを作成します。|  
|[GetThread](../../../extensibility/debugger/reference/idebugstackframe2-getthread.md)|スタック フレームに関連付けられているスレッドを取得します。|  
  
## <a name="remarks"></a>Remarks  
 このインターフェイスは、デバッグ中のプログラムが (いずれかはユーザー設定のブレークポイントまたは例外によって生じた) ブレークポイントで停止された場合にのみ取得されます。 このインターフェイスは、式を評価する式のコンテキストを取得できます、レジスタの一覧を返すことが、または呼び出し履歴を取得して調べることができます。  
  
## <a name="requirements"></a>要件  
 ヘッダー: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 アセンブリ: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>関連項目  
 [コア インターフェイス](../../../extensibility/debugger/reference/core-interfaces.md)

