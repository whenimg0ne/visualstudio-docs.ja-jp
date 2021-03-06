---
title: 'チュートリアル: デザイン時のデバッグ |Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
- JScript
- VB
- CSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], design-time
- breakpoints, design-time debugging
- Immediate window, design-time debugging
- design-time debugging
ms.assetid: 35bfdd2c-6f60-4be1-ba9d-55fce70ee4d8
caps.latest.revision: 23
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dd63fca37bbb55f99ecb99a18596c128451bd807
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "47540333"
---
# <a name="walkthrough-debugging-at-design-time"></a>チュートリアル : デザイン時のデバッグ
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

このトピックの最新バージョンをご覧[チュートリアル: デザイン時にデバッグ](https://docs.microsoft.com/visualstudio/debugger/walkthrough-debugging-at-design-time)します。  
  
Visual Studio を使用する**イミディ エイト**ウィンドウで、アプリケーションが実行されていないときに、関数またはサブルーチンを実行します。 関数またはサブルーチンにブレークポイントが含まれているとき、適切なポイントで実行を中断します。 デバッガー ウィンドウを使用して、プログラムの状態を確認できます。 この機能は、デザイン時のデバッグと呼ばれます。  
  
 次に、この機能の操作手順を説明します。  
  
### <a name="to-hit-breakpoints-from-the-immediate-window"></a>[イミディエイト] ウィンドウからブレークポイントにヒットするには  
  
1.  次のコードを Visual Basic コンソール アプリケーションに貼り付けます。  
  
    ```  
    Module Module1  
  
        Sub Main()  
            MySub()  
        End Sub  
  
        Function MyFunction() As Decimal  
            Static i As Integer  
            i = i + 1  
            Dim s As String  
  
            s = "Add Breakpoint here"  
            Return 4  
        End Function  
  
        Sub MySub()  
            MyFunction()  
        End Sub  
    End Module  
    ```  
  
2.  `s="Add BreakPoint Here"` という行にブレークポイントを設定します。  
  
3.  次の入力、**イミディ エイト**ウィンドウ。 `?MyFunction<enter>`  
  
4.  ブレークポイントにヒットしたことと、呼び出し履歴が正確であることを確認します。  
  
5.  **デバッグ** メニューのをクリックして**続行**、まだデザイン モードであることを確認します。  
  
6.  次の入力、**イミディ エイト**ウィンドウ。 `?MyFunction<enter>`  
  
7.  次の入力、**イミディ エイト**ウィンドウ。 `?MySub<enter>`  
  
8.  ブレークポイントにヒットし、静的変数の値を確認することを確認`i`で、**ローカル**ウィンドウ。 3 という値が表示されます。  
  
9. 呼び出し履歴が正確であることを確認します。  
  
10. **デバッグ** メニューのをクリックして**続行**、まだデザイン モードであることを確認します。  
  
## <a name="see-also"></a>関連項目  
 [デバッガーのセキュリティ](../debugger/debugger-security.md)   
 [デバッガーの基本事項](../debugger/debugger-basics.md)



