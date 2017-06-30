---
title: "DBGPROP_ATTRIB_FLAGS | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: DBGPROP_ATTRIB_FLAGS
apilocation: scrobj.dll
f1_keywords: 
  - "DBGPROP_ATTRIB_FLAGS"
helpviewer_keywords: 
  - "DBGPROP_ATTRIB_FLAGS"
ms.assetid: 90314496-527b-4357-9df8-125a360bf216
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# DBGPROP_ATTRIB_FLAGS
`IDebugProperty` のさまざまな属性について説明します。  `DebugPropertyInfo` 構造体のメンバーです。  
  
## 構文  
  
```  
enum { DBGPROP_ATTRIB_NO_ATTRIB  =0x00000000,    DBGPROP_ATTRIB_VALUE_IS_INVALID  =0x00000008,    DBGPROP_ATTRIB_VALUE_IS_EXPANDABLE  =0x00000010,    DBGPROP_ATTRIB_VALUE_READONLY  =0x00000800,    DBGPROP_ATTRIB_ACCESS_PUBLIC  =0x00001000,    DBGPROP_ATTRIB_ACCESS_PRIVATE  =0x00002000,    DBGPROP_ATTRIB_ACCESS_PROTECTED  =0x00004000,    DBGPROP_ATTRIB_ACCESS_FINAL  =0x00008000,    DBGPROP_ATTRIB_STORAGE_GLOBAL  =0x00010000,    DBGPROP_ATTRIB_STORAGE_STATIC  =0x00020000,    DBGPROP_ATTRIB_STORAGE_FIELD  =0x00040000,    DBGPROP_ATTRIB_STORAGE_VIRTUAL  =0x00080000,    DBGPROP_ATTRIB_TYPE_IS_CONSTANT  =0x00100000,    DBGPROP_ATTRIB_TYPE_IS_SYNCHRONIZED  =0x00200000,    DBGPROP_ATTRIB_TYPE_IS_VOLATILE  =0x00400000,    DBGPROP_ATTRIB_HAS_EXTENDED_ATTRIBS  =0x00800000    DBGPROP_ATTRIB_VALUE_IS_RETURN_VALUE  =0x08000000, };   
```  
  
## メンバー  
 DBGPROP\_ATTRIB\_NO\_ATTRIB  
 属性がないことを示します。  
  
 DBGPROP\_ATTRIB\_VALUE\_IS\_INVALID  
 `DebugPropertyInfo::bstrValue` 内の値が無効であることを示します。  
  
 DBGPROP\_ATTRIB\_VALUE\_IS\_EXPANDABLE  
 参照またはプロパティが子を持つことを示します。  
  
 DBGPROP\_ATTRIB\_VALUE\_READONLY  
 値が読み取り専用であることを示します。  
  
 DBGPROP\_ATTRIB\_ACCESS\_PUBLIC  
 パブリック アクセスを持つオブジェクトであることを示します。  
  
 DBGPROP\_ATTRIB\_ACCESS\_PRIVATE  
 プライベート アクセスを持つオブジェクトであることを示します。  
  
 DBGPROP\_ATTRIB\_ACCESS\_PROTECTED  
 保護されたアクセスを持つオブジェクトであることを示します。  
  
 DBGPROP\_ATTRIB\_ACCESS\_FINAL  
 最終的なアクセスを持つオブジェクトであることを示します。  
  
 DBGPROP\_ATTRIB\_STORAGE\_GLOBAL  
 グローバル ストレージであることを示します。  
  
 DBGPROP\_ATTRIB\_STORAGE\_STATIC  
 静的ストレージであることを示します。  
  
 DBGPROP\_ATTRIB\_STORAGE\_FIELD  
 オブジェクトがプロパティであることを示します。  
  
 DBGPROP\_ATTRIB\_STORAGE\_VIRTUAL  
 仮想ストレージであることを示します。  
  
 DBGPROP\_ATTRIB\_TYPE\_IS\_CONSTANT  
 オブジェクトの型が定数であることを示します。  
  
 DBGPROP\_ATTRIB\_TYPE\_IS\_SYNCHRONIZED  
 このスロットがスレッド同期されることを示します。  
  
 DBGPROP\_ATTRIB\_TYPE\_IS\_VOLATILE  
 このスロットが永続ストレージに関して揮発性であることを示します。  
  
 DBGPROP\_ATTRIB\_HAS\_EXTENDED\_ATTRIBS  
 このスロットの属性がこれらの定義済みビット以上であることを示します。  
  
 DBGPROP\_ATTRIB\_VALUE\_IS\_RETURN\_VALUE  
 値が関数からの戻り値であることを示します。  
  
## 解説  
 これらのフラグは、オブジェクトの子のフィルター処理にも使用されます。  値は、ビットごとの OR と組み合わせることができます。  
  
## 参照  
 [IDebugProperty インターフェイス](../../winscript/reference/idebugproperty-interface.md)   
 [DebugPropertyInfo 構造体](../../winscript/reference/debugpropertyinfo-structure.md)