---
title: IDebugExpressionEvaluator2 |Microsoft Docs
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
- IDebugExpressionEvaluator2 interface
ms.assetid: cebe649f-1c77-4d33-854f-30d4f00eceb4
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 741cedadd1897395326907179b99efa690603b6b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "47535872"
---
# <a name="idebugexpressionevaluator2"></a>IDebugExpressionEvaluator2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

このトピックの最新バージョンをご覧[IDebugExpressionEvaluator2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugexpressionevaluator2)します。  
  
> [!IMPORTANT]
>  Visual Studio 2015 での式エバリュエーターの実装には、この方法は非推奨とされます。 CLR 式エバリュエーターの実装方法の詳細についてを参照してください[CLR 式エバリュエーター](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators)と[マネージ式エバリュエーターのサンプル](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)します。  
  
 式エバリュエーター (EE) の拡張のバージョンを表します。  
  
## <a name="syntax"></a>構文  
  
```  
IDebugExpressionEvaluator2 : IDebugExpressionEvaluator  
```  
  
## <a name="notes-for-implementers"></a>実装についてのメモ  
 このインターフェイスは、式エバリュエーターによって実装されます。  
  
## <a name="methods"></a>メソッド  
 メソッドだけでなく、 [IDebugExpressionEvaluator](../../../extensibility/debugger/reference/idebugexpressionevaluator.md)インターフェイスでは、このインターフェイスは、次のメソッドを実装します。  
  
|メソッド|説明|  
|------------|-----------------|  
|[GetService](../../../extensibility/debugger/reference/idebugexpressionevaluator2-getservice.md)|その一意識別子を指定したサービス オブジェクトを取得します。|  
|[PreloadModules](../../../extensibility/debugger/reference/idebugexpressionevaluator2-preloadmodules.md)|指定されたシンボル プロバイダーが指定したモジュールをプリロードします。|  
|[SetCallback](../../../extensibility/debugger/reference/idebugexpressionevaluator2-setcallback.md)|デバッガー エンジン (DE) を使用してメトリックの設定を読み取る、コールバック インターフェイスを指定するには、式エバリュエーター (EE) を有効にします。|  
|[SetCorPath](../../../extensibility/debugger/reference/idebugexpressionevaluator2-setcorpath.md)|デバッガーに読み込まれた共通言語ランタイム (CLR) のパスに設定します。|  
|[SetIDebugIDECallback](../../../extensibility/debugger/reference/idebugexpressionevaluator2-setidebugidecallback.md)|式エバリュエーターを初期化中にコールバックを渡すデバッグ エンジンを有効にします。|  
|[Terminate](../../../extensibility/debugger/reference/idebugexpressionevaluator2-terminate.md)|停止し、式エバリュエーターをクリーンアップします。|  
  
## <a name="requirements"></a>要件  
 ヘッダー: Ee.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 アセンブリ: Microsoft.VisualStudio.Debugger.Interop.dll

