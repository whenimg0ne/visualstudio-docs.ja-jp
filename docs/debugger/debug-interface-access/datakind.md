---
title: DataKind |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DataKind enumeration
ms.assetid: b64be708-22d6-4360-99e7-8f4e6b196de7
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c3de9ef6128c3cd5ca6eae80a257b3dc2982cd0f
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2018
ms.locfileid: "31458191"
---
# <a name="datakind"></a>DataKind
データ値の特定のスコープを示します。  
  
## <a name="syntax"></a>構文  
  
```C++  
enum DataKind {   
   DataIsUnknown,  
   DataIsLocal,  
   DataIsStaticLocal,  
   DataIsParam,  
   DataIsObjectPtr,  
   DataIsFileStatic,  
   DataIsGlobal,  
   DataIsMember,  
   DataIsStaticMember,  
   DataIsConstant  
};  
```  
  
## <a name="elements"></a>Elements  
 DataIsUnknown  
 データ シンボルを特定できません。  
  
 DataIsLocal  
 データ項目は、ローカル変数です。  
  
 DataIsStaticLocal  
 データ項目は、静的ローカル変数です。  
  
 DataIsParam  
 データ項目は、正式なパラメーターです。  
  
 DataIsObjectPtr  
 データ項目はオブジェクト ポインター (`this`)。  
  
 DataIsFileStatic  
 データ項目は、ファイル スコープ変数です。  
  
 DataIsGlobal  
 データ項目は、グローバル変数です。  
  
 DataIsMember  
 データ項目は、オブジェクト メンバー変数です。  
  
 DataIsStaticMember  
 データ項目は、クラスの静的変数です。  
  
 DataIsConstant  
 データ項目は、定数値です。  
  
## <a name="remarks"></a>コメント  
 この列挙体の値が返された、 [idiasymbol::get_datakind](../../debugger/debug-interface-access/idiasymbol-get-datakind.md)メソッドです。  
  
## <a name="requirements"></a>要件  
 ヘッダー: cvconst.h  
  
## <a name="see-also"></a>関連項目  
 [列挙体と構造体](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaSymbol::get_dataKind](../../debugger/debug-interface-access/idiasymbol-get-datakind.md)