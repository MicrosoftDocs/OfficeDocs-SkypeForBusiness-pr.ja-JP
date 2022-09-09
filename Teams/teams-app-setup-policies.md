---
title: Microsoft Teams のアプリのセットアップ ポリシーを管理する
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
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
description: アプリのピン留め、アプリのインストール、ユーザーによるカスタム アプリのアップロードを許可するアプリのセットアップ ポリシーを作成、編集、管理する方法について説明します。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: cfcd041fd755016ec04832f42c497e2b0ad51469
ms.sourcegitcommit: ebffec34c050421dc8d09a16907644657ce323f4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/09/2022
ms.locfileid: "67637010"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a>Microsoft Teams のアプリのセットアップ ポリシーを管理する

管理者は、アプリのセットアップ ポリシーを使用してアプリをインストールしてピン留めし、ユーザーがカスタム アプリをアップロードできるようにします。 ピン留めは、組織内の関連するアプリの導入を促進するのに役立ちます。

* **アプリをピン留めする:** アプリのセットアップ ポリシーを使用すると、ピン留めするアプリを選択し、Teams アプリ バーまたは作成メッセージ領域でアプリをユーザーに表示する順序を設定できます。 管理者は、エンド ユーザーが自分のアプリをピン留めできるかどうかを制御することもできます。 「[アプリをピン留めする](#pin-apps)」を参照してください。
* **アプリをインストールする:** アプリのセットアップ ポリシーを使用すると、Teams を起動するときや会議中に、ユーザーの代わりに許可されたアプリをインストールできます。 詳細については、「[アプリをインストールする](#install-apps)」を参照してください。
* **カスタム アプリをアップロードする:** アプリのセットアップ ポリシーを使用すると、ユーザーは Teams にカスタム アプリをアップロードできます。 詳細については、「[カスタム アプリをアップロードする](teams-custom-app-policies-and-settings.md)」を参照してください。

次の組み込みのアプリ セットアップ ポリシーは、既定で Microsoft Teams 管理センターで使用できます。

* **グローバル (組織全体の既定値)**: この既定のポリシーは、別のポリシーを割り当てない限り、組織内のすべてのユーザーに適用されます。 グローバル ポリシーを編集して、ユーザーにとって最も重要なアプリをピン留めします。

* **FirstlineWorker**: このポリシーは、現場担当者用です。 ポリシーをカスタマイズすることはできません。 組織内の現場担当者に割り当てることができます。

## <a name="pin-apps"></a>アプリをピン留めする

アプリをピン留めすると、組織内のユーザーが最も必要とするアプリを強調表示できます。 ピン留めは、Teams のすべての種類のアプリ (Core アプリ、Microsoft 提供のアプリ、サード パーティ製アプリ、組織内で開発されたカスタム) で機能します。 アプリのセットアップ ポリシーを使用してアプリをピン留めすると、アプリがユーザーに許可されている場合もインストールされます。 アプリのセットアップ ポリシーを使用して、次のタスクを実行できます。

* エンド ユーザー向けの Microsoft Teams をカスタマイズして、最も重要なアプリを強調表示します。 ピン留めするアプリと、アプリが表示される順序を選択します。
* ユーザーがアプリをピン留めできるかどうかを制御します。

アプリは、Teams デスクトップ クライアントの左側と Teams モバイル クライアントの下部にあるアプリ バーにピン留めされています。

|Teams デスクトップ クライアント  |Teams モバイル クライアント |
|---------|---------|
|![Teams デスクトップ クライアントのアプリ バー。](media/app-setup-policies-desktop-app-bar.png).  |   ![Teams モバイル クライアントのアプリ バー。](media/mobile-app-ui.png)      |

メッセージング拡張機能は、作成メッセージ領域の下部にあります。

アプリのセットアップ ポリシーを使用してアプリをピン留めするには、次の手順に従います。

1. Teams 管理センターにサインインし、**[Teams アプリ]** > **[[セットアップ ポリシー]](https://admin.teams.microsoft.com/policies/app-setup)** の順にアクセスします。

1. **[追加]** を選択します。

1. ポリシーの名前と説明を入力します。

1. **[ユーザーのピン留め]** をオンにします。

   > [!NOTE]
   > **[ユーザーのピン留め]** 設定は、Microsoft 365 Government Community Cloud (GCC) 環境 (GCC、GCC High、DoD) の Teams 管理センターで使用できますが、効果はありません。

1. **[ピン留めされたアプリ]** で、**[アプリの追加]** を選択します。

1. **[ピン留めされたアプリの追加]** ウィンドウで、追加するアプリを検索し、**[追加]** を選択します。 アプリのアクセス許可ポリシーでアプリをフィルター処理することもできます。

1. **[追加]** を選択します。

1. **[アプリ バー]** または **[メッセージング拡張機能]** の下で、Teams に表示する順序でアプリを配置します。

   :::image type="content" source="media/pin-messaging-extensions.png" alt-text="セットアップ ポリシーのピン留めされたアプリとピン留めされたメッセージング拡張機能のスクリーンショット。":::

1. **[保存]** を選択します。

> [!NOTE]
> Teams for Education では、割り当てアプリは、グローバル ポリシーに一覧表示されていなくても、既定でグローバル ポリシーに固定されています。

> [!NOTE]
> 組織内のフロントライン ワーカーの場合は、カスタマイズされたフロントライン アプリ エクスペリエンスを使用することをお勧めします。 Teams のカスタマイズされたフロントライン アプリ エクスペリエンスは、[[F ライセンス]](https://www.microsoft.com/en-us/microsoft-365/enterprise/frontline?rtc=1#office-SKUChooser-0dbn8nt) を持つユーザーにとって Teams で最も関連性の高いアプリをピン留めします。 詳細については、「[現場担当者向けに Teams アプリを調整する](/microsoft-365/frontline/pin-teams-apps-based-on-license?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)」を参照してください。

## <a name="install-apps"></a>アプリをインストールする

アプリ セットアップ ポリシーを使用すると、管理者は次のタスクを実行できます。

* エンド ユーザー向けのアプリを個人の Teams 環境にインストールします。
* [メッセージング拡張機能](/microsoftteams/platform/messaging-extensions/what-are-messaging-extensions)としてエンド ユーザー向けのアプリをインストールします。

アプリの [アクセス許可ポリシー](teams-app-permission-policies.md) によって許可され、Teams 管理者によってアプリが許可されている場合、エンド ユーザーは自分でアプリをインストールできます。代わりに、アプリがユーザーまたは組織に対してブロックされている場合、エンド ユーザーは [管理者の承認を要求](user-requests-approve-apps.md)できます。

アプリセットアップ ポリシーを使用してアプリをインストールするには、次の手順に従います。

1. Teams 管理センターにサインインし、**[Teams アプリ]** > **[[セットアップ ポリシー]](https://admin.teams.microsoft.com/policies/app-setup)** の順にアクセスします。
1. **[追加]** を選択します。
1. ポリシーの名前と説明を入力します。
1. **[インストール済みアプリ]** セクションで、**[アプリの追加]** を選択します。
1. **[インストール済みのアプリの追加]** ウィンドウで、ユーザーにインストールするアプリを検索します。 アプリのアクセス許可ポリシーでアプリをフィルター処理することもできます。
1. **[追加]** を選択します。

:::image type="content" source="media/install-apps-in-meeting.png" alt-text="アプリ ポリシーを使用したアプリのインストールのスクリーンショット。":::

## <a name="manage-app-setup-policies"></a>アプリのセットアップ ポリシーを管理する

アプリの設定ポリシーは、Microsoft Teams 管理センターで管理します。 グローバル (組織全体の既定) ポリシーを使用することも、カスタム ポリシーを作成して割り当てることもできます。 エンド ユーザーはグローバル ポリシーを取得します。 カスタム ポリシーを作成すると、グローバル ポリシーがオーバーライドされます。 グローバル管理者または Teams サービス管理者は、これらのポリシーを管理できます。

グローバル ポリシーの設定を編集して、必要なアプリを含めます。 組織内のさまざまなユーザー グループに合わせてチームをカスタマイズするには、1 つ以上のカスタム ポリシーを作成して割り当てます。

![ポリシーを管理したり、新しいポリシーを追加したりするための [アプリのセットアップ ポリシー] ページ。](media/app-setup-policies-update.png)

### <a name="edit-an-app-setup-policy"></a>アプリのセットアップ ポリシーを編集する

Microsoft Teams 管理センターを使用して、作成したグローバル (組織全体の既定) ポリシーやカスタム ポリシーなどのポリシーを編集できます。 ポリシーを編集既するか割り当てた後、変更が反映されるまでに数時間かかる場合があります。

1. Teams 管理センターにサインインし、**[Teams アプリ]** > **[[セットアップ ポリシー]](https://admin.teams.microsoft.com/policies/app-setup)** の順にアクセスします。
1. 編集するポリシーを選択し、**[編集]** を選択します。

1. 必要な変更を加えます。

1. **[保存]** を選択します。

### <a name="assign-a-custom-app-setup-policy-to-users-and-groups"></a>ユーザーとグループにカスタム アプリのセットアップ ポリシーを割り当てる

エンド ユーザーとグループにポリシーを割り当てる方法については、「[ユーザーとグループにポリシーを割り当てる方法](assign-policies-users-and-groups.md)」を参照してください。

## <a name="considerations-and-limitations"></a>考慮事項と制限事項

* アプリのセットアップ ポリシーを使用して、構成可能なタブを持つカスタム アプリをインストールすることはできません。
* エンド ユーザーは、管理者がインストールしたアプリをアンインストールできません。
* アプリのセットアップ ポリシーを使用してピン留めされたアプリは、ユーザーがピン留め解除できます (セットアップ ポリシーでユーザーのピン留めが許可されている場合)。
* Teams for Education では、割り当てアプリは、グローバル ポリシーに一覧表示されていなくても、既定でグローバル ポリシーに固定されています。
* ポリシーに追加できる固定アプリの最大数に制限はありません。 ただし、少なくとも 2 つのアプリを Teams モバイル クライアント (iOS および Android) にピン留めする必要があります。 ポリシーに含まれるアプリが 2 つ未満の場合、モバイル クライアントはポリシー設定を反映せず、代わりに既存の構成を引き続き使用します。
* ポリシーを編集既するか割り当てた後、変更が反映されるまでに数時間かかる場合があります。

## <a name="faqs"></a>よく寄せられる質問

### <a name="working-with-app-setup-policies"></a>アプリのセットアップ ポリシーの操作

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>[ピン留めされたアプリの追加] ウィンドウでアプリが見つからない理由

アプリのセットアップ ポリシーを使用して、すべてのアプリを Teams にピン留めできるわけではありません。 一部のアプリでは、この機能がサポートされていない場合があります。 ピン留めできるアプリを見つけるには、**[ピン留めされたアプリの追加]** ウィンドウでアプリを検索します。 個人用スコープ (静的タブ) とボットを持つタブは Teams デスクトップ クライアントにピン留めすることができ、これらのアプリは **[ピン留めされたアプリを追加]** ウィンドウで使用できます。

Teams アプリ ストアには、すべての Teams アプリが一覧表示されます。 **[ピン留めされたアプリの追加]** ウィンドウには、ポリシーを使用して Teams にピン留めできるアプリのみが含まれます。

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a>Microsoft Teams for Education 管理者です。Microsoft Teams for Education のアプリのセットアップ ポリシーについて知っておくべきことは何ですか

通話アプリは Microsoft Teams for Educationでは使用できません。 新しいカスタム アプリのセットアップ ポリシーを作成すると、アプリの一覧に通話アプリが表示されます。 ただし、アプリは Teams クライアントにピン留めされておらず、教育機関用 Teams ユーザーは Teams で通話アプリを表示しません。

### <a name="user-experience"></a>ユーザー エクスペリエンス

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a>ユーザーがピン留めされたすべてのアプリを Teams で表示する方法

ユーザーに対してピン留めされているすべてのアプリを表示するには、インストールされているアプリの数と Teams クライアント ウィンドウのサイズに応じて、次の操作を行う必要があります。

|Teams デスクトップ クライアント |Teams モバイル クライアント |
|---------|---------|
|Teams の横にあるアプリ バーで、**[... その他のアプリ]** を選択します。| Teams の下部近くのアプリ バーで、上にスワイプします。|
|![Teams デスクトップ クライアントのその他のアプリ。](media/app-setup-policies-desktop-more-apps.png)   |![Teams モバイル クライアントのその他のアプリ](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a>Teams のモバイル エクスペリエンスについて知っておくべきこと

Teams モバイル クライアント (iOS および Android) は、静的タブを持つ個人用アプリをサポートします。 Teams デスクトップ クライアントにピン留めされたアプリは、Teams モバイル クライアントに表示されます。 個人用ボットは、モバイル クライアントのチャットに表示されます。

サード パーティ製アプリ (Teams ストアからダウンロードできます) は、モバイルに表示される前に承認する必要があります。 管理者が Microsoft for Mobile によって承認されていないアプリをピン留めすると、そのアプリは Teams デスクトップには表示されますが、モバイルには表示されません。 詳細については、「[モバイル クライアント](/microsoftteams/platform/tabs/what-are-tabs#mobile-clients)」を参照してください。

Teams モバイル クライアントを使用すると、アクティビティ、チャット、Teams などの主要な Teams アプリがユーザーに表示され、Microsoft が提供するアプリの一部をピン留めできます。

#### <a name="order-of-apps-pinned-through-a-policy"></a>ポリシーを介してピン留めされたアプリの順序

**[ユーザーのピン留め]** オプションがオンになっている場合、ユーザーは Teams デスクトップおよびモバイル クライアントでピン留めされたアプリの順序を変更できます。 ユーザーは、Teams Web クライアントでピン留めされたアプリの順序を変更できません。

#### <a name="does-user-pinning-take-precedence"></a>ユーザーのピン留めが優先されますか

管理 ピンは常に優先されます。 **[ユーザーピン留め**] オプションがオンになっている場合、ユーザーによってピン留めされたアプリは、管理者によってピン留めされたアプリの下に表示されます。 **[ユーザーピン留め**] オプションがオフになっている場合、ユーザーは既存のピンを失い、管理者によってピン留めされたアプリのみがアプリ バーで使用できます。

### <a name="custom-teams-apps"></a>カスタム Teams アプリ

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a>組織がカスタム Teams アプリを構築し、AppSource またはテナント アプリ カタログに発行しましたが、アプリが Teams のアプリ バーにピン留めされている場合、アプリ アイコンは期待どおりに表示されません。 これを解決するにはどうすればいいですか?

アプリを送信する前に、必ずロゴ ガイドラインに従ってください。 詳細については、「[販売者ダッシュボードの提出のチェックリスト](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)」を参照してください。

## <a name="related-articles"></a>関連記事

* [Teams でのアプリの管理設定](admin-settings.md)
* [Teams のエンドユーザーにポリシーを割り当てる](assign-policies-users-and-groups.md)
