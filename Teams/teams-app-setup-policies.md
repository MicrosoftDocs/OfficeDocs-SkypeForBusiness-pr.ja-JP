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
description: 組織内のユーザーに対してアプリ設定ポリシーを使用して管理する方法Microsoft Teamsアプリセットアップ ポリシーを管理する方法について説明します。
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

- Teams をカスタマイズして、ユーザーにとって最も重要なアプリを強調表示します。 表示される順序をピン留めして設定するアプリを選択します。 アプリをピン留めすると、サード パーティや組織内の開発者によって構築されたアプリなど、組織内のユーザーが必要とするアプリを紹介できます。
- ユーザーがアプリを Teams にピン留めできるかどうかを制御します。
- ユーザーに代わってアプリをインストールします。 ユーザーがアプリを起動するときに、既定でインストールするアプリをTeams。 ユーザーに割り当てられているアプリのアクセス許可ポリシーで許可[](teams-app-permission-policies.md)されている場合でも、ユーザーはアプリ自体をインストールできます。

> [!Note]
> 管理者がインストールしたアプリの場合、ユーザーはそれらのアプリをアンインストールできない。

アプリは、Teams デスクトップ クライアントの側と Teams モバイル クライアント (iOS と Android) の下部にあるアプリ バーにピン留めされます。

|Teams デスクトップ クライアント  |Teams モバイル クライアント |
|---------|---------|
|![デスクトップ Teams クライアント](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![モバイル Teamsクライアント](media/mobile-app-ui.png)      |

管理者がインストールしたアプリを表示するには、アプリ バーで **[...] を選択します。デスクトップおよび** Web クライアントTeamsアプリを追加し、モバイル クライアントで上にスワイプします。

アプリセットアップ ポリシーは、管理センター Microsoft Teams管理します。 グローバル (組織全体の既定) ポリシーを使用するか、カスタム ポリシーを作成して割り当てる。  組織内のユーザーに対して、カスタム ポリシーを作成して割り当てていない場合は、グローバル ポリシーが自動的に適用されます。 これらのポリシーを管理するには、グローバル管理者または Teams サービス管理者である必要があります。

グローバル ポリシーの設定を編集して、必要なアプリを含める。 組織内のTeamsグループに合わせてカスタム ポリシーをカスタマイズするには、1 つ以上のカスタム ポリシーを作成して割り当てる必要があります。

![[アプリセットアップ ポリシー] ページ](media/app-setup-policies.png)

> [!NOTE]
> Teams for Education を使用している場合は、割り当てアプリが既定でグローバル ポリシーにピン留めされているにもかかわらず、グローバル ポリシーに表示されません。 これは、クライアント上の固定アプリの一覧で 4 番目Teamsされます。

## <a name="create-a-custom-app-setup-policy"></a>カスタム アプリ セットアップ ポリシーを作成する

管理センターの Microsoft Teamsを使用して、カスタム ポリシーを作成できます。

1. 管理センターの左側のナビゲーションMicrosoft Teams、[アプリのセットアップ ポリシー] **Teamsに**  >  **移動します**。

2. **[追加]** を選択します。

   ![[アプリセットアップ ポリシーの追加] ページ](media/app-setup-policies-add.png)

3. ポリシーの名前と説明を入力します。

4. ユーザーがカスタム アプリ **を** アップロードアプリにアップロードできるかどうかに応じて、カスタム アプリを有効またはTeams。 組織全体のアプリ設定で [サード パーティ製アプリを許可する] がオフになっている場合は、この[設定を変更できません](manage-apps.md#manage-org-wide-app-settings)。

5. アプリをピン留めしてユーザーがアプリ バーをカスタマイズできるかどうかに応じて、[ユーザーの固定を許可する] をオンまたはオフにします。

   > [!NOTE]
   > [**ユーザー** のピン留めを許可する] 設定は、Microsoft 365 Government Community Cloud (GCC) 環境 (GCC、GCC High、DoD) の Teams 管理センターで使用できますが、現在は有効です。

6. ユーザー用のアプリをインストールするには、次のタスクを実行します。

    1. [インストール **済みアプリ] で**、[アプリの **追加] を選択します**。

    2. [インストール **済みアプリの追加**] ウィンドウで、ユーザーがアプリを起動するときに自動的にインストールするアプリTeams。 アプリのアクセス許可ポリシーでアプリをフィルター処理することもできます。 アプリの一覧を選択したら、[追加] を **選択します**。

       ![[インストールされているアプリの追加] ウィンドウ](media/app-setup-policies-add-installed-apps.png)

7. アプリをピン留めするには、次の手順を実行します。

    1. [ピン **留めされたアプリ] で**、[アプリの **追加] を選択します**。

    2. [ピン留 **めされたアプリの追加** ] ウィンドウで、追加するアプリを検索し、[追加] を **選択します**。 アプリのアクセス許可ポリシーでアプリをフィルター処理することもできます。 ピン留めするアプリの一覧を選択したら、[追加] を **選択します**。

       ![[ピン留めされたアプリの追加] ウィンドウ](media/app-setup-policies-add-apps.png)

    3. アプリをアプリに表示する順序で並Teams、[保存] を **選択します**。

       ![[ピン留めされたアプリ] セクション](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a>アプリセットアップ ポリシーを編集する

Microsoft Teams管理センターを使用して、グローバル (組織全体の既定) ポリシーや作成したカスタム ポリシーなど、ポリシーを編集できます。

1. 管理センターの左側のナビゲーションMicrosoft Teams、[アプリのセットアップ ポリシー] **Teamsに**  >  **移動します**。

2. ポリシー名の左側をクリックしてポリシーを選び、**[編集]** を選択します。

3. ここで、希望する変更を行います。

4. **[保存]** を選択します。

## <a name="assign-a-custom-app-setup-policy-to-users"></a>カスタム アプリセットアップ ポリシーをユーザーに割り当てる

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="faq"></a>よくあるご質問 (FAQ)

### <a name="working-with-app-setup-policies"></a>アプリセットアップ ポリシーの操作

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a>管理センターに含まれる組み込みのアプリ Microsoft Teamsポリシー

- **グローバル (組織全体の既定値)**: この既定のポリシーは、別のポリシーを割り当てない限り、組織内のすべてのユーザーに適用されます。 グローバル ポリシーを編集して、ユーザーにとって最も重要なアプリをピン留めします。

- **FrontlineWorker:** このポリシーは、Frontline Worker 向けです。 組織内の Frontline Worker に割り当て可能です。 作成するカスタム ポリシーと同様に、設定をアクティブにするにはユーザーにポリシーを割り当てる必要があります。 詳細については、この記事の「 [カスタム](#assign-a-custom-app-setup-policy-to-users) アプリセットアップ ポリシーをユーザーに割り当てる」セクションを参照してください。

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>[ピン留めされたアプリの追加] ウィンドウにアプリが見当たらない理由

すべてのアプリをアプリ セットアップ ポリシーをTeamsにピン留めすることはできません。 一部のアプリでは、この機能がサポートされていない場合があります。 ピン留めできるアプリを見つけるには、[ピン留めされたアプリの追加] **ウィンドウでアプリを検索** します。 個人用スコープ (静的タブ) とボットを持つタブは Teams デスクトップ クライアントにピン留めできます。これらのアプリは、[ピン留めされたアプリの追加] ウィンドウ **で使用** できます。

アプリ ストアには、すべてのアプリTeams一覧が表示Teamsしてください。 [**ピン留めされたアプリの追加**] ウィンドウには、ポリシーを使用してアプリにピン留Teamsアプリだけが表示されます。

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a>Education 管理者Teamsです。Teams for Education のアプリ セットアップ ポリシーについて知りたい

通話アプリは、Teams では使用できません。 新しいカスタム アプリセットアップ ポリシーを作成すると、呼び出し元アプリがアプリの一覧に表示されます。 ただし、アプリはクライアントにピン留めTeamsされません。Teams for Education ユーザーは、Teams で通話アプリを表示しません。

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a>ポリシーに追加できるピン留めされたアプリの数

少なくとも 2 つのアプリを、モバイル クライアント (iOS Teams Android) にピン留めする必要があります。 ポリシーのアプリ数が 2 未満の場合、モバイル クライアントはポリシー設定を反映しません。代わりに、既存の構成を引き続き使用します。

ポリシーに追加できる固定アプリの数に制限はありません。

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a>ポリシーの変更が有効にされるのにかかる時間

ポリシーを編集既するか割り当てた後、変更が反映されるまでに数時間かかる場合があります。

### <a name="user-experience"></a>ユーザー エクスペリエンス

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a>ユーザーがピン留めされたアプリをすべてのアプリに表示Teams

ユーザー用にピン留めされているアプリを表示するには、インストールされているアプリの数とクライアント ウィンドウのサイズに応じて、次Teamsがあります。

|Teams デスクトップ クライアント |Teams モバイル クライアント |
|---------|---------|
|アプリの横にあるアプリ バーで、[Teams]**を選択します。その他のアプリ**。| アプリ バーの下部付近にあるアプリTeams上にスワイプします。|
|![デスクトップ クライアントのその他Teamsアプリ](media/app-setup-policies-desktop-more-apps.png)<br>   |![モバイル クライアントのアプリTeamsする](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a>モバイル エクスペリエンスについて知Teams必要がある情報

モバイル Teams (iOS および Android) では、静的タブを含む個人用アプリがサポートされています。 デスクトップ クライアントにピンTeamsされたアプリは、モバイル クライアントTeams表示されます。 個人用ボットは、モバイル クライアントのチャットに表示されます。

サード パーティ製アプリ (Teams Store からダウンロードできます) は、モバイルに表示される前に承認される必要があります。 管理者が、Microsoft for Mobile で承認されていないアプリをピンで固定すると、Teams デスクトップに表示されますが、モバイルには表示されません。 詳細については [、「モバイル クライアント](/microsoftteams/platform/tabs/what-are-tabs#mobile-clients) 」を参照してください。

Teams モバイル クライアントでは、ユーザーにはアクティビティ、チャット、Teams などのコア Teams アプリが表示され、Shifts などの一部のファースト パーティ アプリを Microsoft からピン留めできます。

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a>ユーザーがポリシーを使用してピン留めされたアプリの順序を変更できる

[ユーザーのピン留めを許可する] オプションがオンになっている場合、Teamsクライアント上の固定アプリの **順序を変更** できます。 ユーザーは、Web クライアントでピン留めされたアプリのTeams変更することはできません。

#### <a name="does-user-pinning-take-precedence"></a>ユーザーのピン留めが優先されますか

管理ピンは常に優先されます。 [ユーザー **固定を許可する]** オプションがオンになっている場合、ユーザーは、管理者固定アプリの下にピン留めされたアプリを保持します。 [ユーザー **固定を** 許可する] オプションがオフになっている場合、ユーザーは既存のピンを失い、管理者固定アプリだけがアプリ バーに表示されます。

### <a name="custom-teams-apps"></a>カスタム Teams アプリ

組織でカスタム Teams アプリを構築し、AppSource またはテナント アプリ カタログに発行しましたが、アプリが Teams のアプリ バーにピン留めされている場合、アプリ アイコンは期待した通り表示されません。 修正方法

アプリを送信する前に、ロゴのガイドラインに従う必要があります。 詳細については、販売者ダッシュボード提出の [チェックリストに関するページを参照してください](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)。

## <a name="related-topics"></a>関連項目

[Teams でのアプリの管理設定](admin-settings.md)

[ Teams でユーザーにポリシーを割り当てる](assign-policies.md)
