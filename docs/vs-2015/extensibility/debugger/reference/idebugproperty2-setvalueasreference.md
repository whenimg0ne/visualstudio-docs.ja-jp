---
title: IDebugProperty2::SetValueAsReference |Microsoft Docs
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
- IDebugProperty2::SetValueAsReference
helpviewer_keywords:
- IDebugProperty2::SetValueAsReference method
ms.assetid: 341b1b89-4ab8-4e1c-abe2-fb955df5c6b0
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: aa128e570c0b55af71f87946d7c25d668b987fcd
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "47535410"
---
# <a name="idebugproperty2setvalueasreference"></a>IDebugProperty2::SetValueAsReference
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

このトピックの最新バージョンをご覧[IDebugProperty2::SetValueAsReference](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugproperty2-setvalueasreference)します。  
  
このプロパティの値を指定された参照の値に設定します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT SetValueAsReference(  
   IDebugReference2** rgpArgs,  
   DWORD              dwArgCount,  
   IDebugReference2*  pValue,  
   DWORD              dwTimeout  
);  
```  
  
```csharp  
int SetValueAsReference(  
   IDebugReference2[] rgpArgs,  
   uint               dwArgCount,  
   IDebugReference2   pValue,  
   uint               dwTimeout  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `rgpArgs`  
 [in]マネージ コードのプロパティ set アクセス操作子に渡す引数の配列。 プロパティ set アクセス操作子が引数を受け取らない場合、またはこの[IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)オブジェクトがこのようなプロパティ setter を参照しない`rgpArgs`null 値を指定する必要があります。 通常、このパラメーターは、null 値です。  
  
 `dwArgCount`  
 [in]引数の数、`rgpArgs`配列。  
  
 `pValue`  
 [in]形式での参照、 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)を使用してこのプロパティを設定する値のオブジェクト。  
  
 `dwTimeout`  
 [in]時間 (ミリ秒単位)、値を設定するためにします。 一般的な値は`INFINITE`します。 これは、すべての可能な評価が実行できる時間の長さに影響します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`; エラーを返しますそれ以外の場合のコードは、通常、次のいずれか。  
  
|Error|説明|  
|-----------|-----------------|  
|`E_SETVALUEASREFERENCE_NOTSUPPORTED`|参照から値を設定することはサポートされていません。|  
|`E_SETVALUE_VALUE_CANNOT_BE_SET`|このプロパティは、メソッドには、値を設定できません。|  
|`E_SETVALUE_VALUE_IS_READONLY`|値は読み取り専用と、設定することはできません。|  
|`E_NOTIMPL`|メソッドが実装されていません。|  
  
## <a name="see-also"></a>関連項目  
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)

