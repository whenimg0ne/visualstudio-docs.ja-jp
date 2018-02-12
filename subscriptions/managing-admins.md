---
title: "Visual Studio サブスクリプション管理者ポータルで管理者権限を管理する"
Author: evanwindom
Ms.author: jaunger
Manager: evelynp
Ms.date: 1/19/2018
Ms.topic: Get-Started-Article
Description: Learn how manage admins & super admins in the Visual Studio Subscriptions Administrator Portal.
Ms.prod: vs-subscription
Ms.technology: vs-subscriptions
Searchscope: VS Subscription
ms.openlocfilehash: 83bf27d5aaa99c2095ad8a1fafd7541df90f316b
ms.sourcegitcommit: b18844078a30d59014b48a9c247848dea188b0ee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2018
---
# <a name="managing-administrator-rights-in-the-visual-studio-subscriptions-administrator-portal"></a>Visual Studio サブスクリプション管理者ポータルで管理者権限を管理する

## <a name="overview"></a>概要 
Visual Studio サブスクリプション管理者ポータル (https://manage.visualstudio.com) には、2 つの管理ロールがあります。

**スーパー管理者:** 最初に組織を設定したときには、主要または通知連絡先が既定でスーパー管理者になります。 主要または通知連絡先は、追加のスーパー管理者または管理者を割り当てることを選択できます。 スーパー管理者は、個々のサブスクライバーのサブスクリプションを管理するだけでなく、他の管理者やスーパー管理者を追加または削除することもできます。 システムに 3 人以上のスーパー管理者がいる場合、セキュリティのために、スーパー管理者は最後の 2 人を除くすべての管理者を削除できます。 

**管理者:** 管理者は、スーパー管理者に割り当てられた契約のサブスクライバーを管理できます。  個人にサブスクリプションを割り当て、サブスクリプションを編集し、サブスクリプションの再割り当てまたは削除を行うことができます   (管理者はスーパー管理者によって任命されます)。  

## <a name="adding-an-administrator-with-super-admin-rights"></a>スーパー管理者権限を**持つ**管理者を追加する:

1. 既にスーパー管理者権限を持っているアカウントを使用して、[Visual Studio サブスクリプション管理者ポータル](https://manage.visualstudio.com)にサインインします。

2. ページの上部にある **[管理者の管理]** タブをクリックします (スーパー管理者のみがこのタブにアクセスできます。スーパー管理者権限のない管理者は、**[サブスクライバーの管理]** タブを使用して個々のサブスクライバーを管理します)。

3. **[追加]** をクリックして新しい管理者を作成します。 

4. [管理者の追加] ポップアップ ウィンドウで、必要な詳細情報をすべて入力します。
  - 組織が既に Azure Active Directory (AAD) に登録している場合は、**[名前]** フィールドに名前を入力し、ドロップダウン リストで正しい項目を選択します。 新規ユーザーの場合は、フルネームを入力し、"*ID が見つかりませんでした*" という通知を無視します。
  - 正しいユーザーが特定されると、[サインイン電子メール アドレス] フィールドに自動的に設定されます。 設定されない場合は、新しい管理者の電子メール アドレスを入力します。

5. **[契約]** のドロップダウン リストをクリックして、新しい管理者に管理させる **PCN** を選択します。 設定する PCN に複数の契約がある場合は、契約の一部またはすべてへのアクセス権を管理者に付与することができます。 

**契約に関する備考:** 使用できる契約が 1 つしかない場合、[契約] のドロップダウン機能は無効になります。  すべての契約は、構成しているユーザーにスーパー管理者権限が付与される場合は、[すべて] の契約が自動的にオンになります。

6. この管理者のスーパー管理者権限を有効にするには、**[スーパー管理者]** ボックスをクリックします。  

7. この管理者の追加を完了するには、**[追加]** をクリックします。

**管理者の追加中に発生する可能性のあるエラー:** 管理者を追加しようとすると、エラー メッセージが表示されることがあります。 このエラーは、追加されるスーパー管理者の電子メール アドレスが会社の AAD に登録されていない場合に発生する可能性があります。 新しい管理者の追加を完了するには、エラーを無視して、**[追加]** をもう一度クリックします。 

8. スーパー管理者が作成されると、管理者一覧に表示され、スーパー管理者の状態を示す緑色のチェック マークがアカウントに表示されます。 

### <a name="optional--add-a-different-notification-email"></a>省略可能: 別の通知メールを追加します。
組織が電子メールを受信するためのアドレス/アカウントが別にある場合は、"連絡用" アドレスを入力することもできます。 **[Add a different notification email for receiving communication]\(連絡の受信用に別の通知電子メール アドレスを追加する\)** を選択します。 

*例:* 林さんは会社の資格情報を使用してサインインするときに rene@contoso.com を使用しています。  ただし、林さんの会社は、このアドレスをディレクトリ アクセスの管理にのみ使用しています。  林さんは電子メールの送受信時に rene.collado@contoso.com を使用しているので、スーパー管理者は、"ようこそ" のメールが林さんに確実に届くように、2 番目のアドレスを入力しました。  会社がこのような方法で構成されていない場合は、単にサインイン電子メール アドレスを入力するだけで十分です。

## <a name="adding-an-administrator-without-super-admin-rights"></a>スーパー管理者権限を**持たない**管理者を追加する:

スーパー管理者権限を持たない管理者を追加するには、前述の手順を同様に実行する必要がありますが、次の点を考慮してください。
-  スーパー管理者権限を持たない管理者を追加する場合、追加の電子メール アドレスを追加する必要はありません。また、スーパー管理者のチェックボックスはオフのままにします。
-  スーパー管理者権限を持たないユーザーの場合、[管理者の管理] のプロファイル構成エントリに緑色のチェック アイコンが表示されません。