---
title: Microsoft Teams のアプリのセットアップ ポリシーを管理する
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.reviewer: rarang
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 組織内のユーザーのMicrosoft Teamsでアプリ設定ポリシーを使用および管理する方法について説明します。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: 328f2676ccec6cd1450166d7032877e176d5f1cd
ms.sourcegitcommit: 745d707ec63685ce7f973785e7056628472b9c45
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2022
ms.locfileid: "64910823"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a>Microsoft Teams のアプリのセットアップ ポリシーを管理する

管理者は、アプリのセットアップ ポリシーを使用して、アプリをインストールしてピン留めし、組織内で最も使用されているアプリを昇格し、ユーザーがカスタム アプリをTeamsにアップロードするかどうかを決定できます。

- **アプリをピン留めする:** アプリセットアップ ポリシーを使用すると、ピン留めするアプリを選択し、Teams アプリ バーまたは作成メッセージ領域でユーザーに表示する順序を設定し、ユーザーが自分のアプリをピン留めできるかどうかを制御できます。 詳細については、「アプリの [ピン留め](#pin-apps)」を参照してください。
- **アプリをインストールする:** アプリのセットアップ ポリシーを使用すると、ユーザーがTeamsを開始するときや会議中に、ユーザーの代わりにアプリをインストールできます。 詳細については、「アプリの [インストール](#install-apps)」を参照してください。
- **アップロードカスタム アプリ:** アプリセットアップ ポリシーを使用すると、ユーザーはカスタム アプリをTeamsにアップロードできます。 詳細については、「[アップロードカスタム アプリ](#upload-custom-apps)」を参照してください。

## <a name="pin-apps"></a>アプリをピン留めする

> [!NOTE]
> 組織内のフロントライン ワーカーの場合は、カスタマイズされたフロントライン アプリ エクスペリエンスを使用することをお勧めします。 この機能は、[F ライセンス](https://www.microsoft.com/en-us/microsoft-365/enterprise/frontline?rtc=1#office-SKUChooser-0dbn8nt)を持つユーザーのTeamsで最も関連性の高いアプリをピン留めします。 詳細については、「[現場担当者向けに Teams アプリを調整する](pin-teams-apps-based-on-license.md)」を参照してください。

ピン留めアプリを使用すると、サード パーティまたは組織内の開発者によって構築されたアプリなど、組織内のユーザーが必要とするアプリを紹介できます。

アプリセットアップ ポリシーを使用して、次のタスクを実行できます。

- Teams をカスタマイズして、ユーザーにとって最も重要なアプリを強調表示します。 表示される順序をピン留めして設定するアプリを選択します。
- ユーザーがアプリを Teams にピン留めできるかどうかを制御します。

アプリはアプリ バーにピン留めされます。これは、Teams デスクトップ クライアントの左側と、Teams モバイル クライアント (iOS および Android) の下部にあるバーです。

|Teams デスクトップ クライアント  |Teams モバイル クライアント |
|---------|---------|
|![Teams デスクトップ クライアント。](media/app-setup-policies-desktop-app-bar.png).  |   ![Teams モバイル クライアント](media/mobile-app-ui.png)      |

メッセージング拡張機能は、作成メッセージ領域の下部にあります。

> [!NOTE]
> Microsoft Teams for Educationがある場合は、割り当てアプリがグローバル ポリシーで既定でピン留めされていることがわかりますが、現在はグローバル ポリシーに一覧表示されません。

アプリをピン留めするアプリセットアップ ポリシーを作成するには、次の手順に従います。

1. [Microsoft Teams管理センター](https://admin.teams.microsoft.com)にログインします。

1. 左側のウィンドウで、**Teams appsSetup** >  **ポリシー** に移動します。

1. **[追加]** を選択します。

1. ポリシーの名前と説明を入力します。

1. **[ユーザーのピン留め]** をオンにします。

   > [!NOTE]
   > **ユーザーピン留め** 設定は、Microsoft 365 Government Community Cloud (GCC) 環境 (GCC、GCC High、DoD) のTeams管理センターで使用できますが、現在は有効ではありません。

1. **[ピン留めされたアプリ**] で、[**アプリの追加**] を選択します。

1. [ **ピン留めされたアプリの追加]** ウィンドウで、追加するアプリを検索し、[ **追加**] を選択します。 アプリのアクセス許可ポリシーでアプリをフィルター処理することもできます。

1. **[追加]** を選択します。

1. **アプリ バー** または **メッセージング拡張機能** の下で、アプリをTeamsに表示する順序で配置します。

   ![[ピン留めされたアプリ] セクション。](media/pin-messaging-extensions.png)

1. **[保存]** を選択します。

## <a name="install-apps"></a>アプリをインストールする

個人用Teams環境のユーザーに対して既定でインストールするアプリを選択したり、[メッセージング拡張機能](/microsoftteams/platform/messaging-extensions/what-are-messaging-extensions)としてアプリをインストールしたり、会議にインストールするアプリを指定したりできます。

アプリセットアップ ポリシーを使用して、次のタスクを実行できます。

- 個人用Teams環境にユーザー向けのアプリをインストールする
- メッセージング拡張機能としてユーザー向けのアプリをインストールする
- 会議の開催者の会議にアプリをインストールする

> [!NOTE]
> ユーザーに割り当てられているアプリ [のアクセス許可ポリシー](teams-app-permission-policies.md) で許可されている場合でも、ユーザーはアプリ自体をインストールできます。

アプリをインストールするためのアプリセットアップ ポリシーを作成するには、次の手順に従います。

1. Microsoft Teams管理センターの左側のナビゲーションで、**Teams appsSetup** >  **ポリシー** に移動します。

2. **[追加]** を選択します。

3. ポリシーの名前と説明を入力します。

4. [ **インストール済みアプリ**] で、[ **アプリの追加**] を選択します。

5. [ **インストール済みのアプリの追加]** ウィンドウで、ユーザーを自動的にインストールするアプリを検索します。 アプリのアクセス許可ポリシーでアプリをフィルター処理することもできます。

6. **[追加]** を選択します。

![アプリ ポリシーをインストールします。](media/install-apps-in-meeting.png)

> [!IMPORTANT]
> ユーザーは、管理者がインストールしたアプリをアンインストールできません。

## <a name="upload-custom-apps"></a>カスタム アプリをアップロードする

Microsoft Teams管理センターを使用して、ユーザーがカスタム アプリをTeamsにアップロードできるようにするカスタム ポリシーを作成できます。

ユーザーがカスタム アプリをTeamsにアップロードできるようにするアプリセットアップ ポリシーを作成するには、次の手順に従います。

1. Microsoft Teams管理センターの左側のナビゲーションで、**Teams appsSetup** >  **ポリシー** に移動します。

2. **[追加]** を選択します。

3. ポリシーの名前と説明を入力します。

4. **ユーザーがカスタム アプリをTeams** にアップロードできるようにするかどうかに応じて、カスタム アプリアップロードオンまたはオフにします。

> [!NOTE]
> 組織全体の **アプリ設定でサード パーティアプリ** がオフになっている場合、この [設定](manage-apps.md#manage-org-wide-app-settings)を変更することはできません。

## <a name="manage-app-setup-policies"></a>アプリのセットアップ ポリシーを管理する

アプリのセットアップ ポリシーは、Microsoft Teams管理センターで管理します。 グローバル (組織全体の既定) ポリシーを使用するか、カスタム ポリシーを作成して割り当てます。  カスタム ポリシーを作成して割り当てていない場合、組織内のユーザーにはグローバル ポリシーが自動的に適用されます。 これらのポリシーを管理するには、グローバル管理者または Teams サービス管理者である必要があります。

グローバル ポリシーの設定を編集して、目的のアプリを含めます。 組織内のさまざまなユーザー グループのTeamsをカスタマイズするには、1 つ以上のカスタム ポリシーを作成して割り当てます。

![[アプリのセットアップ ポリシー] ページ。](media/app-setup-policies-update.png)

### <a name="edit-an-app-setup-policy"></a>アプリのセットアップ ポリシーを編集する

Microsoft Teams管理センターを使用して、作成するグローバル (組織全体の既定) ポリシーやカスタム ポリシーを含むポリシーを編集できます。

1. Microsoft Teams管理センターの左側のナビゲーションで、**Teams appsSetup** >  **ポリシー** に移動します。

2. 編集するポリシーを選択し、[ **編集]** を選択します。

3. 必要な変更を加えます。

4. **[保存]** を選択します。

### <a name="assign-a-custom-app-setup-policy-to-users-and-groups"></a>ユーザーとグループにカスタム アプリセットアップ ポリシーを割り当てる

ユーザーとグループにポリシーを割り当てる方法の詳細については、「ユーザーとグループ [にポリシーを割り当てる」を](assign-policies-users-and-groups.md)参照してください。

## <a name="faq"></a>よくあるご質問 (FAQ)

### <a name="working-with-app-setup-policies"></a>アプリのセットアップ ポリシーの操作

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a>Microsoft Teams管理センターに含まれる組み込みのアプリセットアップ ポリシー

- **グローバル (組織全体の既定値)**: この既定のポリシーは、別のポリシーを割り当てる場合を除き、組織内のすべてのユーザーに適用されます。 グローバル ポリシーを編集して、ユーザーにとって最も重要なアプリをピン留めします。

- **FrontlineWorker**: このポリシーは、フロントライン ワーカー向けです。 組織内のフロントライン ワーカーに割り当てることができます。 作成するカスタム ポリシーと同様に、設定をアクティブにするためにポリシーをユーザーに割り当てる必要があることを理解しておくことが重要です。 詳細については、この記事の「 [ユーザーにカスタム アプリセットアップ ポリシーを割り当てる](#assign-a-custom-app-setup-policy-to-users-and-groups) 」セクションを参照してください。

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>[ピン留めされたアプリの追加] ウィンドウでアプリが見つからない理由

アプリのセットアップ ポリシーを使用して、すべてのアプリをTeamsにピン留めできるわけではありません。 一部のアプリでは、この機能がサポートされていない場合があります。 ピン留めできるアプリを見つけるには、[ピン留めされたアプリの **追加]** ウィンドウでアプリを検索します。 個人用スコープ (静的タブ) とボットを持つタブは、Teams デスクトップ クライアントにピン留めできます。これらのアプリは、[**ピン留めされたアプリの追加]** ウィンドウで使用できます。

Teams アプリ ストアには、すべてのTeamsアプリが一覧表示されます。 **[ピン留めされたアプリの追加]** ウィンドウには、ポリシーを使用してTeamsにピン留めできるアプリのみが含まれます。

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a>私はMicrosoft Teams for Education管理者です。Microsoft Teams for Educationのアプリセットアップ ポリシーについて知っておくべきこと

通話アプリはMicrosoft Teams for Educationでは使用できません。 新しいカスタム アプリセットアップ ポリシーを作成すると、アプリの一覧に通話アプリが表示されます。 ただし、アプリはTeams クライアントにピン留めされておらず、Microsoft Teams for Educationユーザーは通話アプリをTeamsに表示しません。

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a>ポリシーに追加できるピン留めされたアプリの数

少なくとも 2 つのアプリをTeamsモバイル クライアント (iOS と Android) にピン留めする必要があります。 ポリシーに含まれるアプリが 2 つ未満の場合、モバイル クライアントはポリシー設定を反映せず、代わりに既存の構成を引き続き使用します。

ポリシーに追加できるピン留めされたアプリの数に制限はありません。

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a>ポリシー変更が有効にされるまでの所要時間

ポリシーを編集既するか割り当てた後、変更が反映されるまでに数時間かかる場合があります。

### <a name="user-experience"></a>ユーザー エクスペリエンス

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a>ユーザーがピン留めされたすべてのアプリをTeamsで表示する方法

ユーザーに対してピン留めされているすべてのアプリを表示するには、インストールされているアプリの数と、Teams クライアント ウィンドウのサイズに応じて、次の操作を行う必要があります。

|Teams デスクトップ クライアント |Teams モバイル クライアント |
|---------|---------|
|Teamsの側にあるアプリ バーで 、... を選択します **。その他のアプリ**。| Teamsの下部付近にあるアプリ バーで、上にスワイプします。|
|![Teams デスクトップ クライアントのその他のアプリ。](media/app-setup-policies-desktop-more-apps.png)   |![Teams モバイル クライアント内のその他のアプリ](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a>Teamsモバイル エクスペリエンスについて知っておくべきこと

Teamsモバイル クライアント (iOS および Android) は、静的タブを持つ個人用アプリをサポートします。 Teams デスクトップ クライアントにピン留めされたアプリは、Teamsモバイル クライアントに表示されます。 個人用ボットは、モバイル クライアントのチャットに表示されます。

サード パーティ製アプリ (Teams Store からダウンロードできます) は、モバイルに表示される前に承認する必要があります。 管理者が Microsoft for Mobile によって承認されていないアプリをピン留めすると、Teams デスクトップに表示されますが、モバイルには表示されません。 詳細については、「 [モバイル クライアント](/microsoftteams/platform/tabs/what-are-tabs#mobile-clients) 」を参照してください。

Teamsモバイル クライアントを使用すると、アクティビティ、チャット、Teamsなどのコア Teams アプリがユーザーに表示され、Shifts などの一部のファースト パーティ アプリを Microsoft からピン留めできます。

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a>ユーザーがポリシーを使用してピン留めされたアプリの順序を変更できますか?

[ユーザーピン留め] オプションがオンになっている場合、ユーザーはTeamsデスクトップ クライアントとモバイル クライアントで **ピン留め** されたアプリの順序を変更できます。 ユーザーは、Teams Web クライアントでピン留めされたアプリの順序を変更できません。

#### <a name="does-user-pinning-take-precedence"></a>ユーザーのピン留めが優先されますか

管理者ピンは常に優先されます。 **[ユーザーのピン留め**] オプションがオンになっている場合、ユーザーは、管理者のピン留めされたアプリの下にピン留めされたアプリを保持します。 **[ユーザーピン留め**] オプションがオフになっている場合、ユーザーは既存のピンを失い、アプリ バーには管理者がピン留めしたアプリのみが表示されます。

### <a name="custom-teams-apps"></a>カスタム Teams アプリ

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a>組織はカスタム Teams アプリを構築し、AppSource またはテナント アプリ カタログに発行しましたが、アプリがTeamsのアプリ バーにピン留めされている場合、アプリ アイコンは期待どおりに表示されません。 如何实现修正しますか?

アプリを送信する前に、必ずロゴ ガイドラインに従ってください。 詳細については、「 [販売者ダッシュボードの提出のチェックリスト](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)」を参照してください。

## <a name="related-articles"></a>関連記事

[Teams でのアプリの管理設定](admin-settings.md)

[ Teams でユーザーにポリシーを割り当てる](assign-policies-users-and-groups.md)
