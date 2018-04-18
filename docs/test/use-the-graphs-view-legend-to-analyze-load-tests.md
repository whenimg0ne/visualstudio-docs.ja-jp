---
title: Visual Studio でのグラフ ビューの凡例を使用したロード テストの分析 | Microsoft Docs
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- Load Test Analyzer, graphs view legend
- load tests, graphs view legend
ms.assetid: 0f6ba8e4-1343-419c-8a9f-240cf50efed7
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: 967cc1c854689ba034077d25f61cea74d1f082a2
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2018
---
# <a name="using-the-graphs-view-legend-to-analyze-load-tests"></a>グラフ ビューの凡例を使用したロード テストの分析

ロード テスト アナライザーのグラフ ビューには凡例パネルがあり、現在選択されているグラフに関連付けられている各パフォーマンス カウンターの情報が表示されます。

![グラフ ビューの凡例](../test/media/load_viewlegend.png "Load_ViewLegend")

凡例には以下の情報が含まれています。

-   **[グラフに表示]:** チェック ボックスを使用して **[ユーザー数]** や **[Errors/Sec]** など個々のカウンターの線をグラフにプロットするかどうかを指定します。 線をグラフにプロットするには、チェック ボックスをオンにします。 プロットの線をグラフから削除するには、チェック ボックスをオフにします。 プロットの線を削除しても、カウンターの統計情報は凡例に引き続き表示されます。

-   **[範囲]:** この列にはパフォーマンス カウンターの y 軸の範囲が表示されます。 既定では、この値はサンプル データの範囲が変わると自動的に調整されます。 自動的に調整された範囲は常に最大値を超える直近の 10 の累乗になります。これには 10 の負の累乗も含まれます。 グラフには、範囲が異なるさまざまなカウンターを含めることができます。 したがって、y 軸には特定範囲のラベルではなく、各カウンターの全範囲のパーセンテージを表す 0 ～ 100 の値のラベルが付きます。 たとえば、範囲が 1,000 のカウンターの場合、y 軸のデータ ポイント 60 は、カウンターの値 600 に相当します。

    > [!NOTE]
    > 範囲を特定の値にロックすると、範囲の値の自動調整を無効にできます。 範囲をロックすると、その範囲を超える値はすべて、グラフの一番上に指定した最大値として表示されます。 範囲を特定の値にロックするには、**[プロット オプション]** ダイアログ ボックスを使用します。 詳細については、「[方法: グラフ作成カウンターのプロット オプションを指定する](../test/how-to-specify-plot-options-for-graphing-counters.md)」を参照してください。

-   **[カウンター]:** **[カウンター]**、**[インスタンス]**、**[カテゴリ]**、**[コンピューター]** という 4 つの列でパフォーマンス カウンターを一意に識別します。

-   **[色]:** **[色]** 列には、パフォーマンス カウンターのプロットされた線の色とスタイルが表示されます。 グラフのパフォーマンス カウンターの色または線のスタイルを変更するには、**[プロット オプション]** ダイアログ ボックスを使用します。 **[プロット オプション]** ダイアログ ボックスは凡例のショートカット メニューから開きます。 詳細については、「[方法: グラフ作成カウンターのプロット オプションを指定する](../test/how-to-specify-plot-options-for-graphing-counters.md)」を参照してください。

-   **統計情報:** **[最小]**、**[最大]**、**[平均]**、**[最終]** の各列は、パフォーマンス カウンターのそれぞれの統計情報を示します。 これらの値は、グラフの可視領域に表示されているデータに対応しています。 たとえば、実行の領域を拡大した場合、凡例の統計情報には拡大した領域の値のみが反映されます。 [最終] 列は、直前に完了したサンプリング間隔のパフォーマンス カウンターの値です。

    > [!NOTE]
    > [最終] 列は、ロード テストの実行中にのみロード テスト アナライザーの凡例に表示されます。

     詳細については、「[方法: グラフの領域にズーム インする](../test/how-to-zoom-in-on-a-region-of-the-graph-in-load-test-results.md)」を参照してください。

凡例の項目を選択して、以下の操作を実行できます。

-   項目を凡例とグラフの両方から削除する。 項目を右クリックして **[削除]** をクリックするか、**Delete** キーを押します。

-   グラフのプロット線を強調表示する。

-   データ グリッドに選択した項目のデータを表示する。

-   カウンターの **[プロット オプション]** ダイアログ ボックスを表示する。

> [!TIP]
> ロード テスト アナライザーのツール バーにある **[グラフのオプション]** ドロップダウン ボタンを使用して、**[凡例の表示]** をクリックすると、グラフ ビューに関連付けられている **[凡例]** パネルを表示または非表示にすることができます。

## <a name="see-also"></a>関連項目

- [方法: グラフ作成カウンターのプロット オプションを指定する](../test/how-to-specify-plot-options-for-graphing-counters.md)
- [方法 : グラフの領域にズーム インする](../test/how-to-zoom-in-on-a-region-of-the-graph-in-load-test-results.md)
- [グラフ ビューでのロード テスト結果の分析](../test/analyze-load-test-results-in-the-graphs-view.md)