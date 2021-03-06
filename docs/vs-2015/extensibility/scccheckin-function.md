---
title: SccCheckin 関数 |Microsoft Docs
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
- SccCheckin
helpviewer_keywords:
- SccCheckin function
ms.assetid: e3f26ac2-6163-42e1-a764-22cfea5a3bc6
caps.latest.revision: 17
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 27d2f5fc2bec3f7e082593e3adcd65a0407f0bc2
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "47536251"
---
# <a name="scccheckin-function"></a>SccCheckin 関数
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

このトピックの最新バージョンをご覧[SccCheckin 関数](https://docs.microsoft.com/visualstudio/extensibility/scccheckin-function)します。  
  
この関数は、変更を保存して、新しいバージョンを作成、ソース管理システムに以前のチェック アウトしたファイルをチェックインします。 この関数は、カウントにチェックインするファイルの名前の配列と呼びます。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
SCCRTN SccCheckin (  
   LPVOID    pvContext,  
   HWND      hWnd,  
   LONG      nFiles,  
   LPSTR*    lpFileNames,  
   LPCSTR    lpComment,  
   LONG      fOptions,  
   LPCMDOPTS pvOptions  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 pvContext  
 [in]ソース管理プラグイン コンテキスト構造体。  
  
 hWnd  
 [in]SCC のプラグインが提供される任意のダイアログ ボックスの親として使用できる IDE ウィンドウへのハンドル。  
  
 nFiles  
 [in]選択にチェックインするファイルの数。  
  
 lpFileNames  
 [in]チェックインするファイルの完全修飾パス名の配列。  
  
 lpComment  
 [in]各チェックインされている選択したファイルに適用されるコメントです。 これは`NULL`とコメントに、ソース管理プラグインを入力する必要があります。  
  
 方法は限られて  
 [in]コマンドのフラグ、0 または`SCC_KEEP_CHECKEDOUT`します。  
  
 pvOptions  
 [in]SCC プラグインに固有のオプションです。  
  
## <a name="return-value"></a>戻り値  
 この関数のソース管理プラグイン実装は、次の値のいずれかを返すが必要です。  
  
|[値]|説明|  
|-----------|-----------------|  
|SCC_OK|ファイル正常にチェックします。|  
|SCC_E_FILENOTCONTROLLED|選択したファイルはソース コード管理下ではありません。|  
|SCC_E_ACCESSFAILURE|ソース管理システムのネットワークまたは競合の問題の可能性へのアクセスに問題が発生しました。 再試行をお勧めします。|  
|SCC_E_NONSPECIFICERROR|不特定のエラーです。 ファイルがチェックインされません。|  
|SCC_E_NOTCHECKEDOUT|ユーザーがチェックインできないように、ファイルはチェックされません。|  
|SCC_E_CHECKINCONFLICT|チェックインを実行できませんでした。<br /><br /> -別のユーザーが事前チェックし、`bAutoReconcile`が false であった。<br /><br /> - または -<br /><br /> に (たとえば、ファイルはバイナリ) とき、自動マージを実行できません。|  
|SCC_E_VERIFYMERGE|ファイルは、自動マージにしましたが、ユーザーの検証保留中のチェックインされていません。|  
|SCC_E_FIXMERGE|ファイルは、自動マージにしましたが、手動で解決する必要のあるマージの競合によりチェックインされていません。|  
|SCC_E_NOTAUTHORIZED|この操作を実行できません。|  
|SCC_I_OPERATIONCANCELED|操作が完了する前に取り消されました。|  
|SCC_I_RELOADFILE|ファイルまたはプロジェクトを再読み込みする必要があります。|  
|SCC_E_FILENOTEXIST|ローカル ファイルが見つかりませんでした。|  
  
## <a name="remarks"></a>Remarks  
 コメントは、チェックインされているすべてのファイルに適用されます。 コメントの引数を指定できます、`null`文字列の場合、ソース管理プラグインは各ファイルのコメントの文字列のユーザーを求めることもできます。  
  
 `fOptions`引数の値が指定することができます、`SCC_KEEP_CHECKEDOUT`でファイルを確認し、もう一度チェック アウトするユーザーの意図を示すフラグ。  
  
## <a name="see-also"></a>関連項目  
 [ソース管理プラグインの API 関数](../extensibility/source-control-plug-in-api-functions.md)

