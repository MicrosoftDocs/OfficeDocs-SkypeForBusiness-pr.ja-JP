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
description: アプリのピン留め、アプリのインストール、ユーザーによるカスタム アプリのアップロードを許可するアプリセットアップ ポリシーを作成、編集、管理する方法について説明します。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: 58a2b8730c4f3d02746aeb0bb3887bcd63d44918
ms.sourcegitcommit: 9946c6c1faa78617ccd7bdf115457090ebce5619
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/21/2022
ms.locfileid: "66190478"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a>Microsoft Teams のアプリのセットアップ ポリシーを管理する

管理者は、アプリのセットアップ ポリシーを使用してアプリをインストールしてピン留めし、ユーザーがカスタム アプリをアップロードできるようにします。 ピン留めは、組織内の関連するアプリの導入を促進するのに役立ちます。

* **アプリをピン留めする:** アプリセットアップ ポリシーを使用すると、ピン留めするアプリを選択し、アプリがTeams アプリ バーまたは作成メッセージ領域でユーザーに表示される順序を設定できます。 管理者は、エンド ユーザーが自分のアプリをピン留めできるかどうかを制御することもできます。 [「アプリをピン留めする」を](#pin-apps)参照してください。
* **アプリをインストールする:** アプリのセットアップ ポリシーを使用すると、ユーザーがTeamsを開始するときや会議中に、ユーザーの代わりにアプリをインストールできます。 詳細については、「アプリの [インストール](#install-apps)」を参照してください。
* **アップロードカスタム アプリ:** アプリセットアップ ポリシーを使用すると、ユーザーはカスタム アプリをTeamsにアップロードできます。 詳細については、「[アップロードカスタム アプリ](#upload-custom-apps)」を参照してください。

## <a name="pin-apps"></a>アプリをピン留めする

アプリをピン留めすると、組織内のユーザーが最も必要とするアプリを強調表示できます。 ピン留めは、Microsoft、ISV 企業、組織内の開発者によって提供されるアプリに対して機能します。 アプリのセットアップ ポリシーを使用してアプリをピン留めすると、アプリもインストールされます。 アプリセットアップ ポリシーを使用して、次のタスクを実行できます。

* Teams をカスタマイズして、ユーザーにとって最も重要なアプリを強調表示します。 表示される順序をピン留めして設定するアプリを選択します。
* ユーザーがアプリをピン留めできるかどうかを制御します。

アプリは、Teams デスクトップ クライアントの左側と、Teams モバイル クライアントの下部にあるアプリ バーにピン留めされます。

|Teams デスクトップ クライアント  |Teams モバイル クライアント |
|---------|---------|
|![デスクトップ クライアントのアプリ バー Teams。](media/app-setup-policies-desktop-app-bar.png).  |   ![モバイル クライアントのアプリ バー Teams。](media/mobile-app-ui.png)      |

メッセージング拡張機能は、作成メッセージ領域の下部にあります。

アプリをピン留めするアプリセットアップ ポリシーを作成するには、次の手順に従います。

1. [Microsoft Teams管理センター](https://admin.teams.microsoft.com)にログインします。

1. 左側のウィンドウで、**Teams アプリ** > **のセットアップ ポリシー** に移動します。

1. **[追加]** を選択します。

1. ポリシーの名前と説明を入力します。

1. **[ユーザーのピン留め]** をオンにします。

   > [!NOTE]
   > **ユーザーピン留め** 設定は、Microsoft 365 Government Community Cloud (GCC) 環境 (GCC、GCC High、DoD) のTeams管理センターで使用できますが、現在は有効ではありません。

1. **[ピン留めされたアプリ**] で、[**アプリの追加**] を選択します。

1. [ **ピン留めされたアプリの追加]** ウィンドウで、追加するアプリを検索し、[ **追加**] を選択します。 アプリのアクセス許可ポリシーでアプリをフィルター処理することもできます。

1. **[追加]** を選択します。

1. **アプリ バー** または **メッセージング拡張機能** の下で、アプリをTeamsに表示する順序で配置します。

   :::image type="content" source="media/pin-messaging-extensions.png" alt-text="[ピン留めされたアプリ] セクション"border="true":::

1. **[保存]** を選択します。

> [!NOTE]
> Microsoft Teams for Educationでは、割り当てアプリは、グローバル ポリシーに一覧表示されていない場合でも、既定でグローバル ポリシーにピン留めされます。

> [!NOTE]
> 組織内のフロントライン ワーカーの場合は、カスタマイズされたフロントライン アプリ エクスペリエンスを使用することをお勧めします。 この機能は、[F ライセンス](https://www.microsoft.com/en-us/microsoft-365/enterprise/frontline?rtc=1#office-SKUChooser-0dbn8nt)を持つユーザーのTeamsで最も関連性の高いアプリをピン留めします。 詳細については、「[現場担当者向けに Teams アプリを調整する](pin-teams-apps-based-on-license.md)」を参照してください。

## <a name="install-apps"></a>アプリをインストールする

アプリのセットアップ ポリシーを使用すると、管理者は次のタスクを実行できます。

* 既定では、個人用Teams環境にエンド ユーザー向けのアプリをインストールします。
* [メッセージング拡張機能](/microsoftteams/platform/messaging-extensions/what-are-messaging-extensions)としてエンド ユーザー向けのアプリをインストールします。
* 会議の開催者の会議にアプリをインストールします。

アプリの [アクセス許可ポリシー](teams-app-permission-policies.md) で許可されている場合、エンド ユーザーはアプリを独自にインストールできます。

アプリをインストールするアプリセットアップ ポリシーを作成するには、次の手順に従います。

1. Teams管理センターにログインし、**Teams アプリ** > **のセットアップ ポリシー** にアクセスします。

2. **[追加]** を選択します。

3. ポリシーの名前と説明を入力します。

4. [ **インストール済みアプリ**] で、[ **アプリの追加**] を選択します。

5. [ **インストール済みのアプリの追加]** ウィンドウで、ユーザーにインストールするアプリを検索します。 アプリのアクセス許可ポリシーでアプリをフィルター処理することもできます。

6. **[追加]** を選択します。

![アプリ ポリシーをインストールします。](media/install-apps-in-meeting.png)

> [!IMPORTANT]
> ユーザーは、管理者がインストールしたアプリをアンインストールできません。

## <a name="upload-custom-apps"></a>カスタム アプリをアップロードする

ユーザーがカスタム アプリをアップロードできるようにするカスタム ポリシーを作成するには、次の手順に従います。

1. Teams管理センターにログインし、**Teams アプリ** > **のセットアップ ポリシー** にアクセスします。

2. **[追加]** を選択します。

3. ポリシーの名前と説明を入力します。

4. **カスタム アプリアップロード** オンまたはオフにします。

> [!NOTE]
> この設定を変更するには、テナントの [組織全体のアプリ設定で](manage-apps.md#manage-org-wide-app-settings)**サード パーティアプリを** 許可する必要があります。

## <a name="manage-app-setup-policies"></a>アプリのセットアップ ポリシーを管理する

アプリのセットアップ ポリシーは、Microsoft Teams管理センターで管理します。 グローバル (組織全体の既定) ポリシーを使用するか、カスタム ポリシーを作成して割り当てます。 エンド ユーザーはグローバル ポリシーを取得します。 カスタム ポリシーを作成すると、グローバル ポリシーがオーバーライドされます。 グローバル管理者またはTeamsサービス管理者は、これらのポリシーを管理できます。

グローバル ポリシーの設定を編集して、目的のアプリを含めます。 組織内のさまざまなユーザー グループのTeamsをカスタマイズするには、1 つ以上のカスタム ポリシーを作成して割り当てます。

![ポリシーを管理したり、新しいポリシーを追加したりするための [アプリセットアップ ポリシー] ページ。](media/app-setup-policies-update.png)

### <a name="edit-an-app-setup-policy"></a>アプリのセットアップ ポリシーを編集する

Microsoft Teams管理センターを使用して、作成するグローバル (組織全体の既定) ポリシーやカスタム ポリシーを含むポリシーを編集できます。

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[Teams アプリ]** > **[ポリシーの設定]** の順に移動します。

2. 編集するポリシーを選択し、[ **編集]** を選択します。

3. 必要な変更を加えます。

4. **[保存]** を選択します。

### <a name="assign-a-custom-app-setup-policy-to-users-and-groups"></a>ユーザーとグループにカスタム アプリセットアップ ポリシーを割り当てる

ユーザーとグループにポリシーを割り当てる方法の詳細については、「ユーザーとグループ [にポリシーを割り当てる」を](assign-policies-users-and-groups.md)参照してください。

## <a name="faqs"></a>Faq

<!--- TBD: Incorporate these pointers in the content itself.
--->

### <a name="working-with-app-setup-policies"></a>アプリのセットアップ ポリシーの操作

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a>Microsoft Teams管理センターに含まれる組み込みのアプリセットアップ ポリシー

* **グローバル (組織全体の既定値)**: この既定のポリシーは、別のポリシーを割り当てる場合を除き、組織内のすべてのユーザーに適用されます。 グローバル ポリシーを編集して、ユーザーにとって最も重要なアプリをピン留めします。

* **FrontlineWorker**: このポリシーは、フロントライン ワーカー向けです。 組織内のフロントライン ワーカーに割り当てることができます。 作成するカスタム ポリシーと同様に、設定をアクティブにするためにポリシーをユーザーに割り当てる必要があることを理解しておくことが重要です。 詳細については、この記事の「 [ユーザーにカスタム アプリセットアップ ポリシーを割り当てる](#assign-a-custom-app-setup-policy-to-users-and-groups) 」セクションを参照してください。

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>[ピン留めされたアプリの追加] ウィンドウでアプリが見つからない理由

アプリのセットアップ ポリシーを使用して、すべてのアプリをTeamsにピン留めできるわけではありません。 一部のアプリでは、この機能がサポートされていない場合があります。 ピン留めできるアプリを見つけるには、[ピン留めされたアプリの **追加]** ウィンドウでアプリを検索します。 個人用スコープ (静的タブ) とボットを持つタブは、Teams デスクトップ クライアントにピン留めできます。これらのアプリは、[**ピン留めされたアプリの追加]** ウィンドウで使用できます。

Teams アプリ ストアには、すべてのTeamsアプリが一覧表示されます。 **[ピン留めされたアプリの追加]** ウィンドウには、ポリシーを使用してTeamsにピン留めできるアプリのみが含まれます。

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a>私はMicrosoft Teams for Education管理者です。Microsoft Teams for Educationのアプリセットアップ ポリシーについて知っておくべきこと

通話アプリはMicrosoft Teams for Educationでは使用できません。 新しいカスタム アプリセットアップ ポリシーを作成すると、アプリの一覧に通話アプリが表示されます。 ただし、アプリはTeams クライアントにピン留めされておらず、Microsoft Teams for Educationユーザーは通話アプリをTeamsに表示しません。

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a>ポリシーに追加できるピン留めされたアプリの数

Teams モバイル クライアント (iOSとAndroid) に少なくとも 2 つのアプリをピン留めする必要があります。 ポリシーに含まれるアプリが 2 つ未満の場合、モバイル クライアントはポリシー設定を反映せず、代わりに既存の構成を引き続き使用します。

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

Teamsモバイル クライアント (iOSとAndroid) は、静的タブを持つ個人用アプリをサポートします。 Teams デスクトップ クライアントにピン留めされたアプリは、Teamsモバイル クライアントに表示されます。 個人用ボットは、モバイル クライアントのチャットに表示されます。

サード パーティ製アプリ (Teams Microsoft Storeからダウンロードできます) は、モバイルに表示される前に承認する必要があります。 管理者が Microsoft for Mobile によって承認されていないアプリをピン留めすると、Teams デスクトップに表示されますが、モバイルには表示されません。 詳細については、「 [モバイル クライアント](/microsoftteams/platform/tabs/what-are-tabs#mobile-clients) 」を参照してください。

Teamsモバイル クライアントを使用すると、アクティビティ、チャット、Teamsなどのコア Teams アプリがユーザーに表示され、Shifts などの一部のファースト パーティ アプリを Microsoft からピン留めできます。

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a>ユーザーがポリシーを使用してピン留めされたアプリの順序を変更できますか?

[ユーザーピン留め] オプションがオンになっている場合、ユーザーはTeamsデスクトップ クライアントとモバイル クライアントで **ピン留め** されたアプリの順序を変更できます。 ユーザーは、Teams Web クライアントでピン留めされたアプリの順序を変更できません。

#### <a name="does-user-pinning-take-precedence"></a>ユーザーのピン留めが優先されますか

管理 ピンは常に優先されます。 **[ユーザーのピン留め**] オプションがオンになっている場合、ユーザーは、管理者のピン留めされたアプリの下にピン留めされたアプリを保持します。 **[ユーザーピン留め**] オプションがオフになっている場合、ユーザーは既存のピンを失い、アプリ バーには管理者がピン留めしたアプリのみが表示されます。

### <a name="custom-teams-apps"></a>カスタム Teams アプリ

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a>組織はカスタム Teams アプリを構築し、AppSource またはテナント アプリ カタログに発行しましたが、アプリがTeamsのアプリ バーにピン留めされている場合、アプリ アイコンは期待どおりに表示されません。 操作方法修正しますか?

アプリを送信する前に、必ずロゴ ガイドラインに従ってください。 詳細については、「 [販売者ダッシュボードの提出のチェックリスト](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)」を参照してください。

## <a name="see-also"></a>関連項目

* [Teams でのアプリの管理設定](admin-settings.md)
* [Teamsのエンド ユーザーにポリシーを割り当てる](assign-policies-users-and-groups.md)
