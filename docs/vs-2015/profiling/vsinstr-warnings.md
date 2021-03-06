---
title: VSInstr の警告 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- instrumentation, VSInstr tool
- warnings
- VSInstr tool
- warnings, VSInstr tool
- performance tools, VSInstr tool
ms.assetid: 47512bc9-a8e9-4628-883a-d9888edab786
caps.latest.revision: 25
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 993ea5f9a6acd07439ce2e551928683e635a13af
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "47536226"
---
# <a name="vsinstr-warnings"></a>VSInstr の警告
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

このトピックの最新バージョンをご覧[VSInstr の警告](https://docs.microsoft.com/visualstudio/profiling/vsinstr-warnings)します。  
  
次の表に、VSInstr.exe ツールで発行される警告をリストします。 NOWARN オプションに警告番号を指定することで、警告を非表示にできます。  
  
|警告番号|説明|  
|--------------------|-----------------|  
|**VSP2000**|内部エラーです。 この実行可能ファイルのモジュール ファイル名を取得できません。|  
|**VSP2001**|\<assembly name> は、厳密な名前付きのアセンブリです。 実行するには、再署名する必要があります。<br /><br /> この警告は、署名付きのアセンブリがインストルメントされたときに発生します。 sn.exe ツールを使用して、バイナリを再署名するか、厳密な名前の必要性を一時的に無効にすることができます。 詳細については、「[Sn.exe (厳密名ツール)](http://msdn.microsoft.com/library/c1d2b532-1b8e-4c7a-8ac5-53b801135ec6)」を参照してください。|  
|**VSP2002**|ファイル \<filename> で関数 \<funcname> が見つかりませんでした。<br /><br /> この警告は、関数が指定したファイルで見つからない場合に発生します。|  
|**VSP2003**|ファイル \<filename> で関数 \<funcname> へのクロス ジャンプが見つかりませんでした。<br /><br /> この警告は、VSInstr でクロス ジャンプを無効にできない場合に発生します。 クロス ジャンプはコードの最適化に使用されます。|  
|**VSP2004**|関数 \<funcname> は、EXCLUDE コマンド ライン スイッチを使用して除外されましたが、クロス ジャンプが含まれていたため省略することはできませんでした。<br /><br /> この警告は、EXCLUDE オプションを使用して除外された関数がインストルメンテーション プロセスに必要である場合に発生します。 プロファイラーは、必要な関数を自動的に含めます。|  
|**VSP2005**|内部のインストルメンテーション エラー \<error text><br /><br /> この警告は、インストルメンテーションを実行できない場合に発生します。 エラー テキストを確認して、修正できるかどうかを判断します。|  
|**VSP2006**|\<name> の PDB が見つかりませんでした<br /><br /> この警告は、PDB ファイルが検索パスに存在しないか、バイナリと一致しない場合に発生します。|  
|**VSP2007**|\<filename> はインストルメント可能なコードを含んでいません。<br /><br /> この警告は、バイナリ ファイル内の関数がすべて除外されている場合や、指定されたファイルにリソースしか含まれていない場合に発行されます。|  
|**VSP2008**|セキュリティ属性を \<name> から取得できません。 エラー コード \<code><br /><br /> この警告は、ユーザーが READ_DAC アクセス許可を持っていない場合に発生します。 インストルメンテーション プロセス中に、プロファイラーはバイナリの元の DACL を保持しようとします。 元のバイナリは新しいバイナリと置き換えられるため、元のバイナリの DACL をコピーして新しいバイナリに適用する必要があります。 ユーザーが元のバイナリに対する READ_DAC アクセス許可を持たない場合、この操作は失敗することがあります。|  
|**VSP2009**|\<name> でセキュリティ属性を設定できません。 エラー コード \<error number><br /><br /> この警告は、ユーザーが WRITE_DAC アクセス許可を持っていない場合に発生します。 インストルメンテーション プロセス中に、プロファイラーはバイナリの元の DACL を保持しようとします。 元のバイナリは新しいバイナリと置き換えられるため、元のバイナリの DACL をコピーして新しいバイナリに適用する必要があります。 ユーザーが新しいバイナリに対する WRITE_DAC アクセス許可を持たない場合、この操作は失敗することがあります。|  
|**VSP2010**|-INCLUDE/-EXCLUDE オプションにより、関数はインストルメンテーション用に特別に選択されていません|  
|**VSP2011**|Include/Exclude funcspec \<name> は、どの関数とも一致しません|  
|**VSP2012**|コード カバレッジ用にインストルメント化可能なコードがイメージに含まれていません。<br /><br /> プロファイラーでは、次のようなコードはインストルメント化されません。<br /><br /> -   静的な CRT 関数<br />-   NonUserCodeAttribute の属性付きマネージド メソッド<br />-   DebuggerHiddenAttribute の属性付きマネージド メソッド<br />-   MASM ブロック<br /><br /> この警告は、このフィルターを適用した後にコードが残らない場合に生成されます。|  
|**VSP2013**|このイメージをインストルメント化するには、32 ビット プロセスとして実行する必要があります。 CLR ヘッダー フラグは、これを反映するように更新されました。<br /><br /> プロファイラーは、64 ビット オペレーティング システムが WOW64 エミュレーターで 32 ビット プロセスを開けるように、バイナリを変更します。 ライブラリ (DLL) の場合、既存の 64 ビット プロセスに読み込まれたときに失敗する場合があります。 この警告はユーザーに依存関係を知らせるものです。|  
|**VSP2014**|結果となるインストルメント化されたイメージは無効であり、実行されない可能性があります。<br /><br /> このメッセージは、インストルメント化された最終的なアセンブリに無効な PE ヘッダーがある場合に発生します。|  
  
## <a name="see-also"></a>関連項目  
 [VSInstr](../profiling/vsinstr.md)



