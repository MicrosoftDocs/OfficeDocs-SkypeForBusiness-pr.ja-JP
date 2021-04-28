---
title: Microsoft Teams のアプリのセットアップ ポリシーを管理する
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: rarang
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 組織内のユーザー向け Microsoft Teams でアプリセットアップ ポリシーを使用および管理する方法について説明します。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: ebfcff8ce7215e34e3c17e9c09f3a56d249d5b40
ms.sourcegitcommit: 1ee9b1857f472a5b95352f7471c0cf21be6ea0c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2021
ms.locfileid: "52059201"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a>Microsoft Teams のアプリのセットアップ ポリシーを管理する

管理者は、アプリセットアップ ポリシーを使用して、次のタスクを実行できます。

- Teams をカスタマイズして、ユーザーにとって最も重要なアプリを強調表示します。 表示される順序をピン留めして設定するアプリを選択します。 ピン留めアプリを使用すると、組織内のユーザーが必要とするアプリ (サード パーティまたは組織内の開発者によって構築されたアプリなど) を紹介できます。
- ユーザーがアプリを Teams にピン留めできるかどうかを制御します。
- ユーザーに代わってアプリをインストールします。 Teams を起動するときに、ユーザーに既定でインストールされているアプリを選択します。 ユーザーに割り当てられているアプリのアクセス許可ポリシーで許可[](teams-app-permission-policies.md)されている場合でも、ユーザーはアプリ自体をインストールできます。

> [!Note]
> 管理者がインストールしたアプリの場合、ユーザーはそれらのアプリをアンインストールできない。

アプリは、Teams デスクトップ クライアントの側と Teams モバイル クライアント (iOS と Android) の下部にあるアプリ バーに固定されます。

|Teams デスクトップ クライアント  |Teams モバイル クライアント |
|---------|---------|
|![Teams デスクトップ クライアント](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![Teams モバイル クライアント](media/mobile-app-ui.png)      |

管理者がインストールしたアプリを表示するには、アプリ バーで **[..] を選択します。Teams デスクトップ** および Web クライアント内の他のアプリと、モバイル クライアントで上にスワイプします。

Microsoft Teams 管理センターでアプリセットアップ ポリシーを管理します。 グローバル (組織全体の既定) ポリシーを使用するか、カスタム ポリシーを作成して割り当てる。  カスタム ポリシーを作成して割り当てていない場合、組織内のユーザーにはグローバル ポリシーが自動的に適用されます。 これらのポリシーを管理するには、グローバル管理者または Teams サービス管理者である必要があります。

グローバル ポリシーの設定を編集して、必要なアプリを含める。 組織内のユーザーのグループごとに Teams をカスタマイズするには、1 つ以上のカスタム ポリシーを作成して割り当てる必要があります。

![[アプリのセットアップ ポリシー] ページ](media/app-setup-policies.png)

> [!NOTE]
> Teams for Education を使用している場合は、割り当てアプリがグローバル ポリシーで既定でピン留めされているのに、グローバル ポリシーに表示されません。 Teams クライアント上の固定されたアプリの一覧の 4 番目のアプリになります。

## <a name="create-a-custom-app-setup-policy"></a>カスタム アプリセットアップ ポリシーを作成する

Microsoft Teams 管理センターを使用して、カスタム ポリシーを作成できます。

1. Microsoft Teams 管理センターの左側のナビゲーションで、[Teams アプリのセットアップ ポリシー **]**  >  **に移動します**。

2. **[追加]** を選択します。

   ![[アプリセットアップ ポリシーの追加] ページ](media/app-setup-policies-add.png)

3. ポリシーの名前と説明を入力します。

4. ユーザーがカスタム アプリ **を** Teams にアップロードできるかどうかに応じて、カスタム アプリのアップロードをオンまたはオフにします。 組織全体のアプリ設定で [サード パーティ製アプリを許可する] がオフになっている場合は、この設定[を変更できません](manage-apps.md#manage-org-wide-app-settings)。

5. アプリをピン留めしてユーザーにアプリ バーをカスタマイズできるかどうかに応じて、[ユーザーのピン留めを許可する] をオンまたはオフにします。

   > [!NOTE]
   > [ **ユーザー** ピン留めを許可する] 設定は、Microsoft 365 Government Community Cloud (GCC) 環境 (GCC、GCC High、DoD) の Teams 管理センターで使用できますが、現在は効果がありません。

6. ユーザー用のアプリをインストールするには、次のタスクを実行します。

    1. [インストール **済みアプリ] で**、[アプリの **追加] を選択します**。

    2. [インストール済 **みアプリの追加** ] ウィンドウで、Teams の起動時に自動的にインストールするアプリを検索します。 アプリのアクセス許可ポリシーでアプリをフィルター処理することもできます。 アプリの一覧を選択したら、[追加] を **選択します**。

       ![[インストール済みアプリの追加] ウィンドウ](media/app-setup-policies-add-installed-apps.png)

7. アプリをピン留めするには、次の手順を実行します。

    1. [固定 **されたアプリ] で**、[アプリの **追加] を選択します**。

    2. [固定 **アプリの追加] ウィンドウ** で、追加するアプリを検索し、[追加] を **選択します**。 アプリのアクセス許可ポリシーでアプリをフィルター処理することもできます。 ピン留めするアプリの一覧を選択したら、[追加] を **選択します**。

       ![[固定アプリの追加] ウィンドウ](media/app-setup-policies-add-apps.png)

    3. Teams に表示する順序でアプリを配置し、[保存] を **選択します**。

       ![[固定されたアプリ] セクション](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a>アプリセットアップ ポリシーを編集する

Microsoft Teams 管理センターを使用して、作成したグローバル (組織全体の既定) ポリシーやカスタム ポリシーなど、ポリシーを編集できます。

1. Microsoft Teams 管理センターの左側のナビゲーションで、[Teams アプリのセットアップ ポリシー **]**  >  **に移動します**。

2. ポリシー名の左側をクリックしてポリシーを選び、**[編集]** を選択します。

3. ここで、希望する変更を行います。

4. **[保存]** を選択します。

## <a name="assign-a-custom-app-setup-policy-to-users"></a>ユーザーにカスタム アプリセットアップ ポリシーを割り当てる

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="faq"></a>よくあるご質問 (FAQ)

### <a name="working-with-app-setup-policies"></a>アプリのセットアップ ポリシーを使用する

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターに含まれている組み込みのアプリセットアップ ポリシー

- **グローバル (組織全体の既定値)**: この既定のポリシーは、別のポリシーを割り当てない限り、組織内のすべてのユーザーに適用されます。 グローバル ポリシーを編集して、ユーザーにとって最も重要なアプリをピン留めします。

- **FrontlineWorker**: このポリシーは、Frontline Workers 用です。 組織内の Frontline Worker に割り当てできます。 作成するカスタム ポリシーと同様に、設定をアクティブにするには、ユーザーにポリシーを割り当てる必要があります。 詳細については、この記事の「 [ユーザー](#assign-a-custom-app-setup-policy-to-users) にカスタム アプリセットアップ ポリシーを割り当てる」セクションを参照してください。

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>[固定されたアプリの追加] ウィンドウでアプリが見当たらない理由

アプリセットアップ ポリシーを使用して、すべてのアプリを Teams にピン留めすることはできません。 一部のアプリでは、この機能がサポートされていない場合があります。 ピン留めできるアプリを検索するには、[固定されたアプリの追加] **ウィンドウでアプリを検索** します。 個人用スコープ (静的タブ) とボットを持つタブは、Teams デスクトップ クライアントにピン留めできます。これらのアプリは、[固定されたアプリの追加] ウィンドウ **で使用** できます。

Teams アプリ ストアには、すべての Teams アプリが一覧表示されます。 [ **固定アプリの追加]** ウィンドウには、ポリシーを使用して Teams にピン留めできるアプリだけが含まれます。

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a>私は Teams for Education 管理者です。Teams for Education のアプリセットアップ ポリシーについて知る必要がある情報

通話アプリは、Teams for Education では使用できません。 新しいカスタム アプリセットアップ ポリシーを作成すると、呼び出し元アプリがアプリの一覧に表示されます。 ただし、アプリは Teams クライアントにピン留めされていないので、Teams for Education ユーザーは Teams で通話アプリを表示しません。

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a>ポリシーに追加できる固定アプリの数

少なくとも 2 つのアプリを Teams モバイル クライアント (iOS と Android) にピン留めする必要があります。 ポリシーのアプリ数が 2 未満の場合、モバイル クライアントはポリシー設定を反映しません。代わりに、既存の構成を引き続き使用します。

ポリシーに追加できる固定アプリの数に制限はありません。

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a>ポリシーの変更を有効にするにはどのくらいの時間がかかるか

ポリシーを編集既するか割り当てた後、変更が反映されるまでに数時間かかる場合があります。

### <a name="user-experience"></a>ユーザー エクスペリエンス

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a>ユーザーが Teams でピン留めされたアプリを表示する方法

ユーザーに固定されているアプリを表示するには、インストールされているアプリの数と Teams クライアント ウィンドウのサイズに応じて、次の操作を行う必要があります。

|Teams デスクトップ クライアント |Teams モバイル クライアント |
|---------|---------|
|Teams の横にあるアプリ バーで **、[..] を選択します。その他のアプリ**。| Teams の下部近くのアプリ バーで、上にスワイプします。|
|![Teams デスクトップ クライアントのその他のアプリ](media/app-setup-policies-desktop-more-apps.png)<br>   |![Teams モバイル クライアントの他のアプリ](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a>Teams モバイル エクスペリエンスについて知る必要がある情報

Teams モバイル クライアント (iOS と Android) は、静的タブを含む個人用アプリをサポートします。 Teams デスクトップ クライアントにピン留めされたアプリは、Teams モバイル クライアントに表示されます。 個人用ボットは、モバイル クライアントのチャットに表示されます。

モバイルに表示する前に、サード パーティ製アプリ (Teams Store からダウンロードできます) を承認する必要があります。 管理者がアプリをピンで固定する場合、Microsoft for Mobile では承認されていないアプリは Teams デスクトップに表示されますが、モバイルには表示されません。 詳細については [、「モバイル クライアント」](/microsoftteams/platform/tabs/what-are-tabs#mobile-clients) を参照してください。

Teams モバイル クライアントを使用すると、ユーザーにはアクティビティ、チャット、Teams などの主要な Teams アプリが表示され、Shifts などの Microsoft のファースト パーティ アプリをピン留めできます。

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a>ユーザーがポリシーを使用してピン留めされたアプリの順序を変更できる

[ユーザーの固定を許可する] オプションがオンになっている場合、ユーザーは Teams デスクトップクライアントとモバイル クライアントで固定されたアプリの **順序を変更** できます。 ユーザーは、Teams Web クライアント上の固定されたアプリの順序を変更することはできません。

#### <a name="does-user-pinning-take-precedence"></a>ユーザーのピン留めが優先されますか

管理ピンは常に優先されます。 [ユーザー **の固定を許可する** ] オプションがオンの場合、ユーザーは固定されたアプリを管理者固定アプリの下に保持します。 [ユーザー **ピン留** めを許可する] オプションがオフの場合、ユーザーは既存のピンを失い、管理者固定アプリだけがアプリ バーに表示されます。

### <a name="custom-teams-apps"></a>カスタム Teams アプリ

組織はカスタム Teams アプリを構築し、AppSource またはテナント アプリ カタログに発行しましたが、アプリが Teams のアプリ バーにピン留めされている場合、アプリ アイコンは期待通り表示されません。 修正方法

アプリを送信する前に、ロゴのガイドラインに従う必要があります。 詳細については、「販売者ダッシュボードの [チェックリストの提出」を参照してください](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)。

## <a name="related-topics"></a>関連項目

[Teams でのアプリの管理設定](admin-settings.md)

[ Teams でユーザーにポリシーを割り当てる](assign-policies.md)
