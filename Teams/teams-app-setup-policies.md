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
ms.openlocfilehash: 94e33421043b0cad195489d78e2eb96c95bb222e
ms.sourcegitcommit: da2a70a9b5e05d0fd7ecc150b451f5805667514c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2021
ms.locfileid: "50756183"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a>Microsoft Teams のアプリのセットアップ ポリシーを管理する

管理者は、アプリセットアップ ポリシーを使用して、次のタスクを実行できます。

- Teams をカスタマイズして、ユーザーにとって最も重要なアプリを強調表示します。 ピン留めするアプリを選び、表示される順序を設定します。 アプリをピン留めすると、サードパーティや組織内の開発者が作成したアプリなど、組織内のユーザーが必要とするアプリを紹介できます。
- ユーザーがアプリを Teams にピン留めできるかどうかを制御します。
- ユーザーの代わりにアプリをインストールします。 ユーザーが Teams を起動するときに、既定でインストールするアプリを選択します。 ユーザーに割り当てられているアプリのアクセス許可ポリシーで許可[](teams-app-permission-policies.md)されている場合でも、ユーザーはアプリを自分でインストールできます。

> [!Note]
> 管理者がインストールしたアプリの場合、ユーザーはそれらのアプリをアンインストールできます。

アプリは、Teams デスクトップ クライアントの横と Teams モバイル クライアント (iOS および Android) の下部にあるアプリ バーにピン留めされます。

|Teams デスクトップ クライアント  |Teams モバイル クライアント |
|---------|---------|
|![Teams デスクトップ クライアント](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![Teams モバイル クライアント](media/mobile-app-ui.png)      |

管理者がインストールしたアプリを表示するには、アプリ バーで **[...Teams デスクトップおよび** Web クライアント内のその他のアプリと、モバイル クライアントで上にスワイプします。

Microsoft Teams 管理センターでアプリセットアップ ポリシーを管理します。 グローバル (組織全体の既定) ポリシーを使用するか、カスタム ポリシーを作成して割り当てる。  カスタム ポリシーを作成して割り当てていない場合、組織内のユーザーにはグローバル ポリシーが自動的に適用されます。 これらのポリシーを管理するには、グローバル管理者または Teams サービス管理者である必要があります。

グローバル ポリシーの設定を編集して、必要なアプリを含める。 組織内のユーザーのグループごとに Teams をカスタマイズするには、1 つ以上のカスタム ポリシーを作成して割り当てる必要があります。

![[アプリセットアップ ポリシー] ページ](media/app-setup-policies.png)

> [!NOTE]
> Teams for Education をお持ちである場合は、割り当てアプリが既定でグローバル ポリシーにピン留めされているにもかかわらず、グローバル ポリシーに表示されません。 これは、Teams クライアントにピン留めされたアプリの一覧で 4 番目のアプリになります。

## <a name="create-a-custom-app-setup-policy"></a>カスタム アプリセットアップ ポリシーを作成する

Microsoft Teams 管理センターを使用して、カスタム ポリシーを作成できます。

1. Microsoft Teams 管理センターの左側のナビゲーションで **、Teams アプリのセットアップ** ポリシー  >  **に移動します**。

2. **[追加]** を選択します。

   ![[アプリセットアップ ポリシーの追加] ページ](media/app-setup-policies-add.png)

3. ポリシーの名前と説明を入力します。

4. ユーザーがカスタム アプリ **を** Teams にアップロードできるかどうかに応じて、カスタム アプリのアップロードをオンまたはオフにします。 組織全体のアプリ設定で [サード パーティ製アプリを許可する] がオフになっている場合、この設定[を変更できません](manage-apps.md#manage-org-wide-app-settings)。

5. アプリをピン留めしてユーザーがアプリ バーをカスタマイズできるかどうかに応じて、ユーザーのピン留めを許可する機能のオンとオフを切り替えます。

   > [!NOTE]
   > [ユーザーのピン留めを許可する] 設定は、Microsoft 365 Government Community Cloud (GCC) 環境 (GCC、GCC High、DoD) の Teams 管理センターで使用できますが、現在は有効な機能はありません。

6. ユーザー用のアプリをインストールするには、次のタスクを実行します。

    1. [インストール **されているアプリ] で、[** アプリの **追加] を選択します**。

    2. [インストール済 **みアプリの追加** ] ウィンドウで、ユーザーが Teams を起動するときに自動的にインストールするアプリを検索します。 アプリのアクセス許可ポリシーでアプリをフィルター処理することもできます。 アプリの一覧を選択したら、[追加] を選択 **します**。

       ![[インストールされているアプリの追加] ウィンドウ](media/app-setup-policies-add-installed-apps.png)

7. アプリをピン留めするには、次の手順を実行します。

    1. [ピン **留めされたアプリ] で**、[アプリの **追加] を選択します**。

    2. [ピン留 **めされたアプリの追加** ] ウィンドウで、追加するアプリを検索し、[追加] を選択 **します**。 アプリのアクセス許可ポリシーでアプリをフィルター処理することもできます。 ピン留めするアプリの一覧を選択したら、[追加] を選択 **します**。

       ![[ピン留めされたアプリの追加] ウィンドウ](media/app-setup-policies-add-apps.png)

    3. アプリを Teams に表示する順序で配置し、[保存] を選択 **します**。

       ![[ピン留めされたアプリ] セクション](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a>アプリセットアップ ポリシーを編集する

Microsoft Teams 管理センターを使用して、作成したグローバル (組織全体の既定) ポリシーやカスタム ポリシーなどのポリシーを編集できます。

1. Microsoft Teams 管理センターの左側のナビゲーションで **、Teams アプリのセットアップ** ポリシー  >  **に移動します**。

2. ポリシー名の左側をクリックしてポリシーを選び、**[編集]** を選択します。

3. ここで、希望する変更を行います。

4. **[保存]** を選択します。

## <a name="assign-a-custom-app-setup-policy-to-users"></a>カスタム アプリセットアップ ポリシーをユーザーに割り当てる

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="faq"></a>よくあるご質問 (FAQ)

### <a name="working-with-app-setup-policies"></a>アプリセットアップ ポリシーを使用する

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターに含まれる組み込みのアプリセットアップ ポリシー

- **グローバル (組織全体の既定)**: この既定のポリシーは、別のポリシーを割り当てない限り、組織内のすべてのユーザーに適用されます。 グローバル ポリシーを編集して、ユーザーにとって最も重要なアプリをピン留めします。

- **FrontlineWorker:** このポリシーは、Frontline Worker 向けです。 組織内の Frontline Worker に割り当てできます。 作成するカスタム ポリシーと同様に、設定をアクティブにするにはユーザーにポリシーを割り当てる必要があります。 詳細については、この記事の「カスタム アプリセットアップ ポリシー [を](#assign-a-custom-app-setup-policy-to-users) ユーザーに割り当てる」セクションを参照してください。

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>[ピン留めされたアプリの追加] ウィンドウでアプリが見当たらない

アプリセットアップ ポリシーを使用して、すべてのアプリを Teams にピン留めすることはできません。 一部のアプリでは、この機能がサポートされていない場合があります。 ピン留めできるアプリを見つけるには、[ピン留めされたアプリの追加] ウィンドウ **でアプリを検索** します。 個人用の範囲 (静的なタブ) とボットを含むタブは、Teams デスクトップ クライアントにピン留めできます。これらのアプリは、[ピン留めされたアプリの追加] ウィンドウ **で使用** できます。

Teams アプリ ストアには、すべての Teams アプリが一覧表示されます。 [ **ピン留めされたアプリの追加]** ウィンドウには、ポリシーを通じて Teams にピン留めできるアプリだけが含まれます。

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a>私は Teams for Education の管理者です。Teams for Education のアプリセットアップ ポリシーについて知りたい情報

通話アプリは、Teams for Education では利用できません。 新しいカスタム アプリセットアップ ポリシーを作成すると、通話アプリがアプリの一覧に表示されます。 ただし、アプリは Teams クライアントにピン留めされていないので、Teams for Education ユーザーには Teams の通話アプリは表示されません。

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a>ポリシーに追加できるピン留めされたアプリの数

少なくとも 2 つのアプリを Teams モバイル クライアント (iOS と Android) にピン留めする必要があります。 ポリシーのアプリ数が 2 未満の場合、モバイル クライアントはポリシー設定を反映するのではなく、引き続き既存の構成を使用します。

ポリシーに追加できるピン留めされたアプリの数に制限はありません。

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a>ポリシーの変更が有効にされるのにどれくらい時間がかかるか

ポリシーを編集既するか割り当てた後、変更が反映されるまでに数時間かかる場合があります。

### <a name="user-experience"></a>ユーザー エクスペリエンス

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a>ユーザーが Teams でピン留めされたアプリを表示する方法

ユーザー用にピン留めされているアプリをすべて表示するには、インストールされているアプリの数と Teams クライアント ウィンドウのサイズによっては、次の操作が必要になる場合があります。

|Teams デスクトップ クライアント |Teams モバイル クライアント |
|---------|---------|
|Teams の横にあるアプリ バーで **、[...その他のアプリ**。| Teams の下部付近にあるアプリ バーで、上にスワイプします。|
|![Teams デスクトップ クライアントのその他のアプリ](media/app-setup-policies-desktop-more-apps.png)<br>   |![Teams モバイル クライアントのその他のアプリ](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a>Teams モバイル エクスペリエンスについて知りたい情報

現在、Teams モバイル クライアント (iOS および Android) は、静的タブを含む個人用アプリをサポートしません。 ポリシーに設定されているアプリによっては、Teams デスクトップ クライアントにピン留めされたアプリが Teams モバイル クライアントに表示されない場合があります。 個人用ボットは、モバイル クライアントのチャットに引き続き表示されます。

Teams モバイル クライアントを使用すると、ユーザーにはアクティビティ、チャット、Teams などの主要な Teams アプリが表示され、Shifts などの Microsoft の一部のファースト パーティ アプリをピン留めすることができます。

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a>ユーザーがポリシーを使用してピン留めされたアプリの順序を変更できる

[ユーザーのピン留めを許可する] オプションがオンになっている場合、ユーザーは Teams デスクトップクライアントとモバイル クライアントでピン留めされたアプリの **順序を変更** できます。 ユーザーは、Teams Web クライアントにピン留めされたアプリの順序を変更することはできません。

#### <a name="does-user-pinning-take-precedence"></a>ユーザーのピン留めが優先される

ユーザーに割り当てられたアプリセットアップ ポリシーが変更され、ユーザー アプリのピン留めがブロックされた場合、Teams はアプリ バーにピン留めされたアプリを削除します。 ユーザー アプリのピン留めを許可するポリシーが変更された場合、ユーザーは以前にピン留めしたアプリを再ピン留めする必要があります。

### <a name="custom-teams-apps"></a>カスタム Teams アプリ

組織でカスタム Teams アプリを作成し、AppSource またはテナント アプリ カタログに発行しましたが、アプリが Teams のアプリ バーにピン留めされている場合、アプリ アイコンが期待した方法で表示されません。 修正方法

アプリを提出する前に、ロゴのガイドラインに従う必要があります。 詳細については、「販売者ダッシュボード提出 [のチェックリスト」を参照してください](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)。

## <a name="related-topics"></a>関連項目

[Teams でのアプリの管理設定](admin-settings.md)

[ Teams でユーザーにポリシーを割り当てる](assign-policies.md)
