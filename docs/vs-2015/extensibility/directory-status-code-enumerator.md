---
title: ディレクトリの状態コードの列挙子 |Microsoft Docs
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
- directory status code enumerator
- source control plug-ins, directory status enumeration
ms.assetid: 616026b5-f529-40ef-90c1-1836e116d797
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 24f6dde65def4569eb8163d281f872011be0275c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "47547191"
---
# <a name="directory-status-code-enumerator"></a>ディレクトリの状態コードの列挙子
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

このトピックの最新バージョンをご覧[ディレクトリの状態コードの列挙子](https://docs.microsoft.com/visualstudio/extensibility/directory-status-code-enumerator)します。  
  
`SccDirStatus`列挙子には、ソース管理システムでディレクトリの状態を指定する名前付き定数の値が含まれています。 この列挙体を使って、 [SccDirQueryInfo](../extensibility/sccdirqueryinfo-function.md)します。 これは、ソース管理プラグイン API のバージョン 1.2 で導入されました。  
  
## <a name="syntax"></a>構文  
  
```  
enum SccDirStatus {  
   SCC_DIRSTATUS_INVALID       = -1L,  
   SCC_DIRSTATUS_NOTCONTROLLED = 0x0000L,  
   SCC_DIRSTATUS_CONTROLLED    = 0x0001L,  
   SCC_DIRSTATUS_EMPTYPROJ     = 0x0002L  
};  
```  
  
## <a name="members"></a>メンバー  
 SCC_DIRSTATUS_INVALID  
 状態を取得できませんでした。それに依存しないでください。  
  
 SCC_DIRSTATUS_NOTCONTROLLED  
 ディレクトリはソース管理下ではありません。  
  
 SCC_DIRSTATUS_CONTROLLED  
 ディレクトリは、ソース管理下にあること。  
  
 SCC_DIRSTATUS_EMPTYPROJ  
 このディレクトリに対応するプロジェクトが空です。  
  
## <a name="see-also"></a>関連項目  
 [ソース管理プラグイン](../extensibility/source-control-plug-ins.md)   
 [SccDirQueryInfo](../extensibility/sccdirqueryinfo-function.md)

