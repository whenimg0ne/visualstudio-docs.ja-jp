---
title: FIELD_INFO_FIELDS |Microsoft Docs
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
- FIELD_INFO_FIELDS
helpviewer_keywords:
- FIELD_INFO_FIELDS enumeration
ms.assetid: a69487d2-e701-4165-804a-8a011df9a3bd
caps.latest.revision: 15
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c181d1483dc33e8931436c24fc3cf681d182ab34
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "47546037"
---
# <a name="fieldinfofields"></a>FIELD_INFO_FIELDS
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

このトピックの最新バージョンをご覧[FIELD_INFO_FIELDS](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/field-info-fields)します。  
  
取得するには、どのような情報を指定します、 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)オブジェクト。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
enum enum_FIELD_INFO_FIELDS {   
   FIF_FULLNAME  = 0x0001,  
   FIF_NAME      = 0x0002,  
   FIF_TYPE      = 0x0004,  
   FIF_MODIFIERS = 0x0008,  
   FIF_ALL       = 0xffffffff,  
   FIF_NONE      = 0x0000  
};  
typedef DWORD FIELD_INFO_FIELDS;  
```  
  
```csharp  
public enum enum_FIELD_INFO_FIELDS {  
   FIF_FULLNAME  = 0x0001,  
   FIF_NAME      = 0x0002,  
   FIF_TYPE      = 0x0004,  
   FIF_MODIFIERS = 0x0008,  
   FIF_ALL       = 0xffffffff,  
   FIF_NONE      = 0x0000  
};  
```  
  
## <a name="members"></a>メンバー  
 FIF_FULLNAME  
 初期化/使用、`bstrFullName`フィールドに、 [FIELD_INFO](../../../extensibility/debugger/reference/field-info.md)構造体。  
  
 FIF_NAME  
 初期化/使用、`bstrName`フィールドに、`FIELD_INFO`構造体。  
  
 FIF_TYPE  
 初期化/使用、`bstrType`フィールドに、`FIELD_INFO`構造体。  
  
 FIF_MODIFIERS  
 初期化/使用、`bstrModifiers`フィールドに、`FIELD_INFO`構造体。  
  
## <a name="remarks"></a>Remarks  
 これらの値がへの引数として渡されることも、 [GetInfo](../../../extensibility/debugger/reference/idebugfield-getinfo.md)のどのフィールドを指定するメソッド、 [FIELD_INFO](../../../extensibility/debugger/reference/field-info.md)構造体が初期化するには。  
  
 これらの値が使用されることも、`dwFields`のメンバー、`FIELD_INFO`フィールドが使用し、有効なときは、構造体。  
  
 これらのフラグは、演算と組み合わせることがあります`OR`します。  
  
## <a name="requirements"></a>要件  
 ヘッダー: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 アセンブリ: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>関連項目  
 [列挙型](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [FIELD_INFO](../../../extensibility/debugger/reference/field-info.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [GetInfo](../../../extensibility/debugger/reference/idebugfield-getinfo.md)

