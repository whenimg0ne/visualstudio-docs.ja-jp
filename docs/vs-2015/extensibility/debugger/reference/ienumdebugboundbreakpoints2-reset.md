---
title: IEnumDebugBoundBreakpoints2::Reset |Microsoft Docs
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
- IEnumDebugBoundBreakpoints2::Reset
helpviewer_keywords:
- IEnumDebugBoundBreakpoints2::Reset
ms.assetid: 0f0522a5-6a97-4c4e-859b-cc4476e6c527
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 0ce2ae3a11c07b1e59b013871996d2c968669aee
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "47537824"
---
# <a name="ienumdebugboundbreakpoints2reset"></a>IEnumDebugBoundBreakpoints2::Reset
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

このトピックの最新バージョンをご覧[IEnumDebugBoundBreakpoints2::Reset](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/ienumdebugboundbreakpoints2-reset)します。  
  
最初の要素を列挙値をリセットします。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT Reset(  
   void  
);  
```  
  
```csharp  
int Reset();  
```  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。  
  
## <a name="remarks"></a>Remarks  
 このメソッドが呼び出された後、次回の呼び出し、[次](../../../extensibility/debugger/reference/ienumdebugboundbreakpoints2-next.md)メソッドが列挙体の最初の要素を返します。  
  
## <a name="see-also"></a>関連項目  
 [IEnumDebugBoundBreakpoints2](../../../extensibility/debugger/reference/ienumdebugboundbreakpoints2.md)

