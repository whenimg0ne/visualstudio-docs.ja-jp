---
title: IDiaSymbol::findChildrenExByVA |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::findChildrenExByVA
ms.assetid: 29080009-36e4-4697-acd7-50f2e3e1bf1b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e1db325da7688c2c3dd8d2b87c301922d168c1ad
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2018
ms.locfileid: "31465318"
---
# <a name="idiasymbolfindchildrenexbyva"></a>IDiaSymbol::findChildrenExByVA
指定された仮想アドレスで有効なシンボルの子を取得します。  
  
## <a name="syntax"></a>構文  
  
```C++  
HRESULT findChildrenExByVA (   
   enum SymTagEnum   symtag,  
   LPCOLESTR         name,  
   DWORD             compareFlags,  
   DWORD             address,  
   IDiaEnumSymbols** ppResult  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `symtag`  
 [in]タグを指定します、シンボルの子を取得するので定義されている、 [SymTagEnum 列挙型](../../debugger/debug-interface-access/symtagenum.md)です。 設定`SymTagNull`すべての子を取得します。  
  
 `name`  
 [in]取得する子の名前を指定します。 設定`NULL`すべての子を取得します。  
  
 `compareFlags`  
 [in]名前の一致に適用する比較オプションを指定します。 値から、 [NameSearchOptions 列挙型](../../debugger/debug-interface-access/namesearchoptions.md)列挙体は、単独または組み合わせて使用できます。  
  
 `address`  
 [in]仮想アドレスを指定します。  
  
 `ppResult`  
 [out]返します、 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)子の記号の一覧を含むオブジェクトを取得します。  
  
## <a name="return-value"></a>戻り値  
 返します`S_OK`シンボルの少なくとも 1 つの子が見つかりましたが、または返す`S_FALSE`場合は子が見つかりませんでした。 エラー コードを返しますそれ以外の場合。  
  
## <a name="remarks"></a>コメント  
 返されるローカル シンボルには、ライブの範囲の情報が含まれます。  
  
## <a name="requirements"></a>要件  
 ヘッダー: Dia2.h  
  
 ライブラリ: diaguids.lib  
  
 DLL: msdia100.dll  
  
## <a name="see-also"></a>関連項目  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [SymTagEnum 列挙型](../../debugger/debug-interface-access/symtagenum.md)   
 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)   
 [Idiasession::findchildren](../../debugger/debug-interface-access/idiasession-findchildren.md)   
 [NameSearchOptions 列挙型](../../debugger/debug-interface-access/namesearchoptions.md)