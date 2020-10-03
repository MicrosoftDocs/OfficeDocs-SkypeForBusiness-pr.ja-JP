---
title: Microsoft Teams のアプリのセットアップ ポリシーを管理する
author: lanachin
ms.author: v-lanac
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
description: 組織内のユーザーに対して Microsoft Teams でアプリセットアップポリシーを使用および管理する方法について説明します。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: d3928bd15ab5b023c025024f2dbf05c404adeee6
ms.sourcegitcommit: fae47764336b47c65e9e24b9abd6fe23ad9fc1a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2020
ms.locfileid: "48341107"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a>Microsoft Teams のアプリのセットアップ ポリシーを管理する

> [!NOTE]
> 組織全体のアプリ設定を有効にしている場合、 **カスタムアプリとの対話を許可**すると、Microsoft Teams 管理センターにまだアプリセットアップポリシーが表示されないことがあります。 この機能は現在展開中であり、間もなく組織内で利用可能になります。

管理者は、アプリセットアップポリシーを使って、次のタスクを実行できます。

- Teams をカスタマイズして、ユーザーにとって最も重要なアプリを強調表示します。 ピン留めするアプリを選択し、表示される順序を設定します。 アプリを固定すると、サードパーティによって構築されたアプリや組織内の開発者によって構築されたアプリなど、組織内のユーザーが必要とするアプリを紹介できます。
- ユーザーがアプリを Teams にピン留めできるかどうかを制御します。
- [ユーザーの代わりにアプリをインストールする **(プレビュー中)**] を選びます。 ユーザーが Teams を起動したときに既定でインストールされるアプリを選択します。 ユーザーに割り当てられている [アプリのアクセス許可のポリシー](teams-app-permission-policies.md) で許可されている場合は、ユーザーがアプリ自体をインストールできることを覚えておいてください。

アプリは、Teams のデスクトップクライアントの側のバーであり、Teams のモバイルクライアント (iOS と Android) の下部にある、アプリバーに固定されています。

|Teams のデスクトップクライアント  |Teams モバイルクライアント |
|---------|---------|
|![Teams のデスクトップクライアント](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![Teams モバイルクライアント](media/mobile-app-ui.png)      |

アプリバーでプレインストールされているアプリを確認するには、[ユーザー] を選択します **。** チームのデスクトップと web クライアントでその他のアプリを追加し、モバイルクライアントで上にスワイプします。

アプリセットアップポリシーは、Microsoft Teams 管理センターで管理します。 グローバル (組織全体の既定) ポリシーを使用するか、カスタムポリシーを作成して割り当てます。  カスタム ポリシーを作成して割り当てていない場合、組織内のユーザーにはグローバル ポリシーが自動的に適用されます。 これらのポリシーを管理するには、グローバル管理者または Teams サービス管理者である必要があります。

グローバルポリシーの設定を編集して、目的のアプリを含めます。 組織内のさまざまなユーザーグループのチームをカスタマイズするには、1つ以上のカスタムポリシーを作成して割り当てます。

![[アプリセットアップポリシー] ページ](media/app-setup-policies.png)

> [!NOTE]
> 教育機関向けの Teams をお持ちの場合は、現時点ではグローバルポリシーで割り当てアプリが既定で固定されていることを知っておくことが重要です。現在のところ、グローバルポリシーには表示されません。 チームクライアントの固定されたアプリの一覧で4番目のアプリになります。

## <a name="create-a-custom-app-setup-policy"></a>カスタムアプリセットアップポリシーを作成する

Microsoft Teams 管理センターを使用して、カスタムポリシーを作成することができます。

1. Microsoft Teams 管理センターの左のナビゲーションで、[ **Teams アプリ**  >  **セットアップポリシー**] に移動します。
2. [ **追加**] を選びます。
    ![[アプリセットアップポリシーの追加] ページ](media/app-setup-policies-add.png)
3. ポリシーの名前と説明を入力します。
4. ユーザーがカスタムアプリをチームにアップロードできるかどうかに応じて、 **カスタムアプリのアップロード**を有効または無効にします。 [組織全体のアプリ設定](manage-apps.md#manage-org-wide-app-settings)で**サードパーティ製のアプリ**が無効になっている場合、この設定を変更することはできません。
5. ユーザーがアプリをカスタマイズ **できる**ようにするかどうかに応じて、ユーザーの固定を有効または無効にします。
6. ユーザー用のアプリ **(プレビュー版)** をインストールするには、次のタスクを実行します。

    1. [ **インストールされているアプリ**] で、[ **アプリの追加**] を選択します。
    2. [ **インストールされているアプリの追加** ] ウィンドウで、ユーザーが Teams を起動したときに自動的にインストールするアプリを検索します。 アプリのアクセス許可ポリシーによってアプリをフィルター処理することもできます。 アプリの一覧を選択したら、[ **追加**] を選択します。

        ![[インストールされているアプリの追加] ウィンドウ](media/app-setup-policies-add-installed-apps.png)

7. アプリを固定するには、次の操作を行います。

    1. [ **固定**されたアプリ] で、[ **アプリの追加**] を選びます。
    2. [固定された **アプリの追加** ] ウィンドウで、追加するアプリを検索し、[ **追加**] を選択します。 アプリのアクセス許可ポリシーによってアプリをフィルター処理することもできます。 ピン留めするアプリのリストを選択したら、[ **追加**] を選択します。

         ![[固定アプリの追加] ウィンドウ](media/app-setup-policies-add-apps.png)

    3. Teams で表示する順序でアプリを配置し、[ **保存**] を選択します。

        ![[固定されたアプリ] セクション](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a>アプリのセットアップポリシーを編集する

Microsoft Teams 管理センターを使って、作成するグローバル (組織全体の既定) ポリシーやカスタムポリシーなどのポリシーを編集できます。

1. Microsoft Teams 管理センターの左のナビゲーションで、[ **Teams アプリ**  >  **セットアップポリシー**] に移動します。
2. ポリシー名の左側をクリックしてポリシーを選択し、[ **編集**] を選択します。
3. ここで、必要な変更を行います。
4. **[保存]** を選択します。

## <a name="assign-a-custom-app-setup-policy-to-users"></a>ユーザーにカスタムアプリセットアップポリシーを割り当てる

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="faq"></a>FAQ

### <a name="working-with-app-setup-policies"></a>アプリセットアップポリシーを使用する

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターには、組み込みのアプリセットアップポリシーが含まれています。

- **グローバル (組織全体の既定)**: この既定のポリシーは、別のポリシーを割り当てない限り、組織内のすべてのユーザーに適用されます。 グローバルポリシーを編集して、ユーザーにとって最も重要なアプリをピン留めします。
- **Firstlineworker**: このポリシーは、firstline worker に対して使用されます。 組織内の Firstline Worker に割り当てることができます。 作成するカスタムポリシーなど、設定をアクティブにするユーザーにポリシーを割り当てる必要があることを知っておくことが重要です。 詳細については、この記事の「 [ユーザーにカスタムアプリセットアップポリシーを割り当てる](#assign-a-custom-app-setup-policy-to-users) 」セクションを参照してください。

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>[ピン留めしたアプリの追加] ウィンドウでアプリが見つからないのはなぜですか。

アプリセットアップポリシーを使用して、すべてのアプリを Teams にピン留めすることはできません。 一部のアプリでは、この機能がサポートされていない可能性があります。 ピン留めできるアプリを見つけるには、[ **ピン留め** されたアプリの追加] ウィンドウでアプリを検索します。 個人用のスコープ (静的タブ) とボットを含むタブは、Teams のデスクトップクライアントにピン留めすることができます。これらのアプリは、[固定された **アプリの追加** ] ウィンドウで利用できます。

Teams アプリストアには、すべての Teams アプリが一覧表示されていることに注意してください。 [ **固定アプリの追加** ] ウィンドウには、ポリシーを通じてチームにピン留めできるアプリのみが含まれています。

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a>私は教育管理者向けのチームです。Teams で教育機関向けアプリセットアップポリシーについて知っておくべきこと

通話アプリは、教育担当の Teams では利用できません。 新しいカスタムアプリのセットアップポリシーを作成すると、アプリの一覧に呼び出し元のアプリが表示されます。 ただし、アプリは Teams クライアントにはピン留めされておらず、教育機関のチームではチーム内の通話アプリを見ることはできません。

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a>固定されたアプリの数をポリシーに追加する方法

少なくとも2つのアプリが Teams モバイルクライアント (iOS と Android) にピン留めされている必要があります。 ポリシーのアプリが2つ未満の場合、モバイルクライアントはポリシーの設定を反映せず、代わりに既存の構成を使い続けます。

ポリシーに追加できる固定されたアプリの数に制限はありません。

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a>ポリシーの変更が有効になるまでにかかる時間

ポリシーを編集または割り当てると、変更が有効になるまでに数時間かかる場合があります。

### <a name="user-experience"></a>ユーザー エクスペリエンス

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a>ユーザーが Teams で固定されたすべてのアプリを表示するにはどうすればよいですか?

ユーザーに対して固定されているすべてのアプリを表示するには、インストールされているアプリの数とチームクライアントウィンドウのサイズに応じて、次の操作が必要になることがあります。

|Teams のデスクトップクライアント |Teams モバイルクライアント |
|---------|---------|
|Teams のサイドにあるアプリバーで、[...] を選びます。 **その他のアプリ**。| チームの下部付近にあるアプリバーで、上にスワイプします。|
|![Teams デスクトップクライアントでのその他のアプリ](media/app-setup-policies-desktop-more-apps.png)<br>   |![Teams モバイルクライアントでのその他のアプリ](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a>Teams モバイルエクスペリエンスについて知っておくべきこと

現在、Teams モバイルクライアント (iOS と Android) では、静的なタブを持つ個人用アプリはサポートされていません。 ポリシーに設定されているアプリによっては、Teams のデスクトップクライアントに固定されたアプリが Teams のモバイルクライアントに表示されない場合があります。 携帯電話クライアントのチャットには、個人用のボットが引き続き表示されます。

Teams のモバイルクライアントでは、ユーザーにはアクティビティ、チャット、Teams などの主要な Teams アプリが表示され、シフトなどの一部のサードパーティ製アプリを Microsoft からピン留めすることができます。

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a>ユーザーがポリシーによって固定されたアプリの順序を変更できる

ユーザーは、[ **ユーザーによる固定** ] オプションがオンになっている場合は、チームのデスクトップとモバイルクライアントで固定されたアプリの順序を変更できます。 ユーザーは、Teams web クライアントで固定されたアプリの順序を変更することはできません。

#### <a name="does-user-pinning-take-precedence"></a>ユーザーによる固定が優先される

ユーザーに割り当てられているアプリセットアップポリシーが、ユーザーアプリの固定をブロックするように変更されている場合、チームはアプリバーに固定されているすべてのアプリを削除します。 ユーザーアプリの固定を許可するようにポリシーを変更した場合、ユーザーは以前に固定されたアプリを再ピンする必要があります。

### <a name="custom-teams-apps"></a>カスタム Teams アプリ

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a>組織では、カスタム Teams アプリを構築し、AppSource またはテナントのアプリカタログに公開していますが、アプリが Teams のアプリバーにピン留めされている場合、アプリのアイコンは期待どおりに表示されません。 問題を解決するにはどうすればよいですか?

アプリを申請する前に、ロゴガイドラインに従っていることを確認してください。 詳細については、「 [販売業者ダッシュボードの申請のチェックリスト](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)」を参照してください。

## <a name="related-topics"></a>関連項目

[Teams でのアプリの管理設定](admin-settings.md)

[チームのユーザーにポリシーを割り当てる](assign-policies.md)
