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
ms.openlocfilehash: bbad8813d9f417643d48a0f1807c2e4c2ccb39cf
ms.sourcegitcommit: 5c59f9bf5a9477607b378c23fa3c8670930dc428
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2021
ms.locfileid: "53646308"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a>Microsoft Teams のアプリのセットアップ ポリシーを管理する

管理者は、アプリセットアップ ポリシーを使用して、アプリをインストールしてピン留めし、組織内で最も使用されているアプリを昇格し、ユーザーがカスタム アプリを Teams にアップロードする必要がある場合に決定できます。

- **アプリ** のピン留め: アプリセットアップ ポリシーを使用すると、ピン留めするアプリを選択したり、ユーザーに表示される順序を設定したり、ユーザーが自分のアプリを Teams アプリ バーにピン留めできるかどうかを制御できます。 詳細については、「アプリをピン留め [する」を参照してください](#pin-apps)。
- **アプリのインストール:** アプリセットアップ ポリシーを使用すると、ユーザーが会議中や会議中にアプリをTeamsにアプリをインストールできます。 詳細については、「アプリのインストール」 [を参照してください](#install-apps)。
- **アップロード アプリのセットアップ ポリシーを** 使用すると、ユーザーがカスタム アプリをカスタム アプリにアップロードTeams。 詳細については、「カスタム アプリのアップロード[を参照してください](#upload-custom-apps)。

## <a name="pin-apps"></a>アプリをピン留めする

アプリをピン留めすると、サード パーティや組織内の開発者によって構築されたアプリなど、組織内のユーザーが必要とするアプリを紹介できます。

アプリセットアップ ポリシーを使用して、次のタスクを実行できます。

- Teams をカスタマイズして、ユーザーにとって最も重要なアプリを強調表示します。 表示される順序をピン留めして設定するアプリを選択します。
- ユーザーがアプリを Teams にピン留めできるかどうかを制御します。

アプリは、Teams デスクトップ クライアントの側と Teams モバイル クライアント (iOS と Android) の下部にあるアプリ バーにピン留めされます。

|Teams デスクトップ クライアント  |Teams モバイル クライアント |
|---------|---------|
|![デスクトップ Teams クライアント](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![モバイル Teamsクライアント](media/mobile-app-ui.png)      |

> [!NOTE]
> 割り当てMicrosoft Teams for Educationがグローバル ポリシーに既定でピン留めされている場合でも、現時点ではグローバル ポリシーに表示されません。 これは、クライアント上の固定アプリの一覧で 4 番目Teamsされます。

アプリをピン留めするアプリ セットアップ ポリシーを作成するには、次の手順を実行します。

1. 管理センターの左側のナビゲーションMicrosoft Teams、[アプリのセットアップ ポリシー] **Teamsに**  >  **移動します**。

2. **[追加]** を選択します。

3. ポリシーの名前と説明を入力します。

4. アプリをピン留めしてユーザーがアプリ バーをカスタマイズできるかどうかに応じて、[ユーザーの固定を許可する] をオンまたはオフにします。

   > [!NOTE]
   > [**ユーザー** のピン留めを許可する] 設定は、Microsoft 365 Government Community Cloud (GCC) 環境 (GCC、GCC High、DoD) の Teams 管理センターで使用できますが、現在は有効です。

5. [ピン **留めされたアプリ] で**、[アプリの **追加] を選択します**。

6. [ピン留 **めされたアプリの追加** ] ウィンドウで、追加するアプリを検索し、[追加] を **選択します**。 アプリのアクセス許可ポリシーでアプリをフィルター処理することもできます。

7. **[追加]** を選択します。

8. アプリをアプリに表示する順序で並Teams。

   ![[ピン留めされたアプリ] セクション](media/app-setup-policies-new-policy-setup.png)

9. **[保存]** を選択します。

## <a name="install-apps"></a>アプリをインストールする

個人用 Teams 環境のユーザーに既定でインストールするアプリを選択し、メッセージング拡張機能としてアプリを[](/microsoftteams/platform/messaging-extensions/what-are-messaging-extensions)インストールし、会議にインストールするアプリを指定できます。

アプリセットアップ ポリシーを使用して、次のタスクを実行できます。

- 個人用環境にユーザー用のアプリをTeamsする
- ユーザー向けアプリをメッセージング拡張機能としてインストールする
- 会議開催者向け会議にアプリをインストールする

> [!NOTE]
> ユーザーに割り当てられているアプリのアクセス[](teams-app-permission-policies.md)許可ポリシーで許可されている場合でも、ユーザーはアプリ自体をインストールできます。

アプリをインストールするアプリ セットアップ ポリシーを作成するには、次の手順を実行します。

1. 管理センターの左側のナビゲーションMicrosoft Teams、[アプリのセットアップ ポリシー] **Teamsに**  >  **移動します**。

2. **[追加]** を選択します。

3. ポリシーの名前と説明を入力します。

4. [インストール **済みアプリ] で**、[アプリの **追加] を選択します**。

5. [インストール **済みアプリの追加** ] ウィンドウで、ユーザー用に自動的にインストールするアプリを検索します。 アプリのアクセス許可ポリシーでアプリをフィルター処理することもできます。

6. **[追加]** を選択します。

![アプリ ポリシーをインストールします。](media/install-apps-in-meeting.png)

> [!IMPORTANT]
> ユーザーは、管理者によってインストールされているアプリをアンインストールできない。

## <a name="upload-custom-apps"></a>アップロード アプリを作成する

管理センターの Microsoft Teamsを使用して、カスタム アプリをカスタム アプリにアップロードできるカスタム ポリシーを作成Teams。

ユーザーがカスタム アプリをアプリにアップロードできるアプリ セットアップ ポリシーを作成するにはTeams手順を実行します。

1. 管理センターの左側のナビゲーションMicrosoft Teams、[アプリのセットアップ ポリシー] **Teamsに**  >  **移動します**。

2. **[追加]** を選択します。

3. ポリシーの名前と説明を入力します。

4. ユーザーがカスタム アプリ **を** アップロードアプリにアップロードできるかどうかに応じて、カスタム アプリを有効またはTeams。

> [!NOTE]
> 組織全体のアプリ設定で [サード パーティ製アプリを許可する] がオフになっている場合は、この[設定を変更できません](manage-apps.md#manage-org-wide-app-settings)。

## <a name="manage-app-setup-policies"></a>アプリセットアップ ポリシーを管理する

アプリセットアップ ポリシーは、管理センター Microsoft Teams管理します。 グローバル (組織全体の既定) ポリシーを使用するか、カスタム ポリシーを作成して割り当てる。  カスタム ポリシーを作成して割り当てていない場合、組織内のユーザーにはグローバル ポリシーが自動的に適用されます。 これらのポリシーを管理するには、グローバル管理者または Teams サービス管理者である必要があります。

グローバル ポリシーの設定を編集して、必要なアプリを含める。 組織内のTeamsグループに合わせてカスタム ポリシーをカスタマイズするには、1 つ以上のカスタム ポリシーを作成して割り当てる必要があります。

![[アプリセットアップ ポリシー] ページ](media/app-setup-policies.png)

### <a name="edit-an-app-setup-policy"></a>アプリセットアップ ポリシーを編集する

Microsoft Teams管理センターを使用して、グローバル (組織全体の既定) ポリシーや作成したカスタム ポリシーなど、ポリシーを編集できます。

1. 管理センターの左側のナビゲーションMicrosoft Teams、[アプリのセットアップ ポリシー] **Teamsに**  >  **移動します**。

2. 編集するポリシーを選択し、[編集] を **選択します**。

3. 必要な変更を行います。

4. **[保存]** を選択します。

### <a name="assign-a-custom-app-setup-policy-to-users"></a>カスタム アプリセットアップ ポリシーをユーザーに割り当てる

ユーザーにポリシーを割り当てる方法の詳細については、「ユーザーとグループにポリシーを割り当 [てる」を参照してください](assign-policies-users-and-groups.md)。

## <a name="faq"></a>よくあるご質問 (FAQ)

### <a name="working-with-app-setup-policies"></a>アプリセットアップ ポリシーの操作

#### <a name="can-i-assign-an-app-setup-policy-to-a-group"></a>アプリセットアップ ポリシーをグループに割り当て可能

PowerShell を使用して、アプリセットアップ ポリシーをグループに割り当てることができます。 PowerShell を使用してグループにポリシーを割り当てる方法の詳細については、「ユーザーとグループにポリシーを割り当 [てる」を参照してください](assign-policies-users-and-groups.md#use-the-powershell-option)。

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a>管理センターに含まれる組み込みのアプリ Microsoft Teamsポリシー

- **グローバル (組織全体の既定値)**: この既定のポリシーは、別のポリシーを割り当てない限り、組織内のすべてのユーザーに適用されます。 グローバル ポリシーを編集して、ユーザーにとって最も重要なアプリをピン留めします。

- **FrontlineWorker:** このポリシーは、Frontline Worker 向けです。 組織内の Frontline Worker に割り当て可能です。 作成するカスタム ポリシーと同様に、設定をアクティブにするにはユーザーにポリシーを割り当てる必要があります。 詳細については、この記事の「 [カスタム](#assign-a-custom-app-setup-policy-to-users) アプリセットアップ ポリシーをユーザーに割り当てる」セクションを参照してください。

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>[ピン留めされたアプリの追加] ウィンドウにアプリが見当たらない理由

すべてのアプリをアプリ セットアップ ポリシーをTeamsにピン留めすることはできません。 一部のアプリでは、この機能がサポートされていない場合があります。 ピン留めできるアプリを見つけるには、[ピン留めされたアプリの追加] **ウィンドウでアプリを検索** します。 個人用スコープ (静的タブ) とボットを持つタブは Teams デスクトップ クライアントにピン留めできます。これらのアプリは、[ピン留めされたアプリの追加] ウィンドウ **で使用** できます。

アプリ ストアには、すべてのアプリTeams一覧が表示Teamsしてください。 [**ピン留めされたアプリの追加**] ウィンドウには、ポリシーを使用してアプリにピン留Teamsアプリだけが表示されます。

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a>管理者Microsoft Teams for Educationです。アプリのセットアップ ポリシーについて知りたいMicrosoft Teams for Education

呼び出し元アプリは、Microsoft Teams for Education。 新しいカスタム アプリセットアップ ポリシーを作成すると、呼び出し元アプリがアプリの一覧に表示されます。 ただし、アプリはクライアントにピン留めTeams、Microsoft Teams for Educationユーザーには通話アプリが表示Teams。

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

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a>組織でカスタム Teams アプリを構築し、AppSource またはテナント アプリ カタログに発行しましたが、アプリが Teams のアプリ バーにピン留めされている場合、アプリ アイコンは期待した通り表示されません。 修正方法

アプリを送信する前に、ロゴのガイドラインに従う必要があります。 詳細については、販売者ダッシュボード提出の [チェックリストに関するページを参照してください](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)。

## <a name="related-topics"></a>関連項目

[Teams でのアプリの管理設定](admin-settings.md)

[ Teams でユーザーにポリシーを割り当てる](assign-policies-users-and-groups.md)
