---
title: Visual Studio でのロード テストの待ち時間 | Microsoft Docs
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- load tests, think times
- load tests, adding delays
- load tests, changing think times
ms.assetid: 8e03bee5-ab7b-4b40-9497-9dbe91ccb90e
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: cccf2961ceb5abecb33396433e344015143503bf
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2018
---
# <a name="edit-think-times-to-simulate-website-human-interaction-delays-in-load-tests-scenarios"></a>待ち時間を編集してロード テスト シナリオにおける Web サイトでの対話操作の遅延をシミュレートする

待ち時間は、Web サイトとの対話と次の対話の間にユーザーを待機させる動作をシミュレートするために使用されます。 待ち時間は、Web パフォーマンス テストにおける要求から次の要求までの間と、ロード テスト シナリオにおけるテスト イテレーションから次のイテレーションまでの間に発生します。 ロード テストで待ち時間を使用すると、ロード シミュレーションをより正確に作成する上で役立ちます。 ロード テストで待ち時間が使用されるか無視されるかは変更できます。 ロード テスト エディターで、ロード テストで待ち時間を使用するかどうかを変更します。

 *待ち動作のプロファイル*は、ロード テストのシナリオに適用される設定です。 この設定は、個々の Web パフォーマンス テストに保存される待ち時間をロード テストで使用するかどうかを決定します。 一部の Web パフォーマンス テストでは待ち時間を使用し、その他の Web サイトでは使用しない場合、それらの Web パフォーマンス テストを異なるシナリオに配置する必要があります。 シナリオの詳細については、「[ロード テスト シナリオの編集](../test/edit-load-test-scenarios.md)」を参照してください。

 最初に、新しいロード テスト ウィザードを使用してロード テストを作成するときに、ロード テストで待ち時間を使用するかどうかを設定します。 詳細については、「[ロード テスト シナリオの編集](../test/edit-load-test-scenarios.md)」を参照してください。

 以下では、待ち動作のプロファイルのオプションについて説明します。

**Off**

待ち時間は無視されます。 Web サーバーに高いロードをかけるために最大ロードを生成するには、この設定を使用します。 Web サーバーとユーザーの対話をより現実的に作成する場合は、使用しないでください。

**On**

待ち時間は、Web パフォーマンス テストで記録されたとおりに使用されます。 記録されているとおりに、Web パフォーマンス テストを実行する複数ユーザーを正確にシミュレートします。 ロード テストでは複数のユーザーをシミュレートするため、同じ待ち時間を使用すると、同期された仮想ユーザーの自然ではないロード パターンが作成される可能性があります。

**正規分布**

待ち時間は使用されますが、正規曲線上でのばらつきが追加されます。 要求から次の要求までの待ち時間をわずかに変化させることで、仮想ユーザーについてより現実的なシミュレーションを実行できます。

> [!NOTE]
> ロード テスト シナリオの各プロパティとその説明の完全なリストについては、「[ロード テスト シナリオのプロパティ](../test/load-test-scenario-properties.md)」を参照してください。

## <a name="changing-the-think-profile"></a>待ち動作のプロファイルの変更

### <a name="to-change-a-think-profile-in-a-load-test-scenario"></a>ロード テスト シナリオで待ち動作のプロファイルを変更するには

1.  Web パフォーマンスとロード テストのプロジェクトから、ロード テストを開きます。

2.  **ロード テスト エディター**で、**[待ち動作のプロファイル]** を変更するシナリオ ノードを選択します。 **[待ち動作のプロファイル]** は、[プロパティ] ウィンドウに表示されます。 F4 キーを押して [プロパティ] ウィンドウを表示します。

3.  [プロパティ] ウィンドウで **[待ち動作のプロファイル]** プロパティを変更します。

4.  プロパティの変更が終了したら、**[ファイル]** メニューの **[保存]** を選択します。 新しい待ち動作のプロファイルでロード テストを実行できるようになります。

## <a name="see-also"></a>関連項目

- [ロード テスト シナリオの編集](../test/edit-load-test-scenarios.md)