---
title: IDebugContainerField |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugContainerField
helpviewer_keywords:
- IDebugContainerField interface
ms.assetid: a8bbe061-c382-4fe9-a193-3f7d12216041
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4bee04d21e3181d4590f26b64c794164ab1a84b6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2018
ms.locfileid: "31105227"
---
# <a name="idebugcontainerfield"></a>IDebugContainerField
このインターフェイスは、シンボルまたはその他のシンボルまたは型用のコンテナーである型を表します。  
  
## <a name="syntax"></a>構文  
  
```  
IDebugContainerField : IDebugField  
```  
  
## <a name="notes-for-implementers"></a>実装についてのメモ  
 シンボル プロバイダーを実装する同一のオブジェクトにこのインターフェイスを実装する、 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)インターフェイスです。 このインターフェイスは、すべてのインターフェイスのコンテナーを表す基本クラスではもです。  
  
## <a name="notes-for-callers"></a>呼び出し元のノート  
 多くのインターフェイスの多くのメソッドは、このインターフェイスを返します。 使用してより専門的なインターフェイスがこのインターフェイスから取得できるこれはすべてのコンテナーの基本クラスであるため、 [QueryInterface](/cpp/atl/queryinterface)です。 このようなインターフェイスに含まれる[IDebugArrayField](../../../extensibility/debugger/reference/idebugarrayfield.md)、 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)、 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)、および[IDebugPropertyField](../../../extensibility/debugger/reference/idebugpropertyfield.md)です。  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
 メソッドだけでなく、 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)インターフェイス、このインターフェイスは、次のメソッドを実装します。  
  
|メソッド|説明|  
|------------|-----------------|  
|[EnumFields](../../../extensibility/debugger/reference/idebugcontainerfield-enumfields.md)|コンテナーのフィールドの列挙子を作成します。|  
  
## <a name="remarks"></a>コメント  
 配列 (コンテナーの変数)、(メソッドと変数のコンテナー) のクラスおよびメソッド (パラメーターおよびローカル変数のコンテナー) は、コンテナーのすべての例を示します。  
  
## <a name="requirements"></a>要件  
 ヘッダー: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 アセンブリ: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>関連項目  
 [シンボル プロバイダー インターフェイス](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)