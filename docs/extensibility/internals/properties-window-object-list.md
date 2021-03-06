---
title: プロパティ ウィンドウ オブジェクトのリスト |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Properties window, object list
ms.assetid: 6c159c9d-345d-4b23-8ddd-9839d338b62f
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b6b7d238f7ce64122ac18a52dab59afb063ce47e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2018
ms.locfileid: "31130137"
---
# <a name="properties-window-object-list"></a>プロパティ ウィンドウ オブジェクトの一覧
オブジェクトの一覧で、**プロパティ**ウィンドウがドロップダウン リストを 1 つまたは複数の選択したウィンドウ内で使用できる他のオブジェクトへの選択を変更することができます。 呼び出しをトリガー内でのこの一覧から別のオブジェクトを選択すると<xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer.SelectObjects%2A>に新しいオブジェクトが選択されている環境を通知します。 表示される情報、**プロパティ**ウィンドウは、新しく選択したオブジェクトに関連付けられたプロパティを表示する変更です。  
  
## <a name="the-object-list"></a>オブジェクトの一覧  
 オブジェクトの一覧は、2 つのフィールドで構成されています: (太字で表示されます) オブジェクトの名前とオブジェクトの種類。  
  
 太字でオブジェクトの種類の左側に表示されるオブジェクト名が、オブジェクト自体から取得されるを使用して、`Name`プロパティによって提供される、<xref:Microsoft.VisualStudio.OLE.Interop.IProvideClassInfo>インターフェイスです。 <xref:Microsoft.VisualStudio.OLE.Interop.IProvideClassInfo.GetClassInfo%2A>、、唯一の方法で<xref:Microsoft.VisualStudio.OLE.Interop.IProvideClassInfo>、返します<xref:Microsoft.VisualStudio.OLE.Interop.ITypeInfo>インターフェイスのコクラスのです。 **プロパティ**ウィンドウを使用して<xref:Microsoft.VisualStudio.OLE.Interop.IProvideClassInfo>ドロップダウン リストでオブジェクト名として表示されるコクラスの名前を取得します。  
  
 オブジェクトがない場合、`Name`プロパティ、名前は、名前、オブジェクトの一覧の領域に表示されません。 オブジェクトの一覧に表示名を使用する場合は、オブジェクトに Name プロパティを追加できます。  
  
 COM オブジェクトを実装しない場合<xref:Microsoft.VisualStudio.OLE.Interop.IProvideClassInfo>、**プロパティ**ウィンドウには、一覧の左側にあるオブジェクト名の代わりにインターフェイス名が表示されます。  
  
## <a name="see-also"></a>関連項目  
 [プロパティの拡張](../../extensibility/internals/extending-properties.md)