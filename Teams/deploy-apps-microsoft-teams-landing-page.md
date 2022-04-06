---
title: Microsoft Teamsのアプリについて知る
ms.reviewer: ''
description: アプリについて説明し、組織のプロファイルとビジネス要件に基づいて、Teamsで許可するアプリを決定します。
ms.topic: article
author: guptaashish
ms.author: guptaashish
manager: prkosh
audience: admin
ms.date: 04/05/2022
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bb3d38060a9538196795e3da7b325840321814d8
ms.sourcegitcommit: 4847f24e8c644336d2b2f48aa09e2cf91360e4dd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2022
ms.locfileid: "64686394"
---
# <a name="about-apps-in-microsoft-teams"></a>Microsoft Teams のアプリについて

アプリは、職場のツールとサービスをまとめ、他のユーザーと共同作業する優れた方法です。 アプリを使用すると、エンド ユーザーの生産性が向上し、共同作業が可能になり、日常的なタスクで効果的になります。 組織は、アプリを使用して顧客と接続し、サービスを提供し、情報を共有します。 アプリを使用すると、ユーザーはチャット、会議、チャネルのTeamsの効果を高めることができます。 たとえば、Teamsでピン留めされた予定表を使用してすばやく共同作業を行うエンド ユーザー、Teams チャネル内の Web サービスの QoS をユーザーに通知するボット機能を備えたアプリ、チャネル内のさまざまなエンド ユーザーにタスクを共有して割り当てるアプリなどがあります。

ストア内の検証済みおよびセキュリティで保護されたアプリの豊富な選択により、エンド ユーザーは組織が毎日必要とするツールやサービスにアクセスできます。 Microsoft Teams アプリは、デプロイする必要のない Web ベースの SaaS アプリです。 エンド ユーザーは、ユーザーが提供するアクセス許可のみに基づいて、Teamsでアプリを使用できます。 管理者は、組織のユーザーに対するアプリの使用を承認またはブロックするだけです。 会議、チャット、チャネルをまたがるすべてのユーザーに対するアプリの可用性を制御します。

エンド ユーザーに必要なアプリを提供するには、アプリの種類と、ユーザーがそれらのアプリにアクセスする場所を理解してください。 アプリの使用の詳細については、「[エンド ユーザー向けのアプリの概要」を](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0)参照してください。

<!--- Commenting the previous content as part of this article revamp.

Apps let users find content from their favorite services and share it in Teams. They let you do tasks such as pin services at the top of a channel, automate notifications using bots, or share and assign tasks.

--->

エンド ユーザーがTeamsで使用できるさまざまな種類のアプリは次のとおりです。

* [Teamsの一部であるコア アプリ](#core-apps)。
* [Microsoft によって作成されたその他のアプリ](#microsoft-provided-apps)。
* パートナーによる[サード パーティ製アプリ](#third-party-apps-validated-by-microsoft) (Microsoft によって検証)。
* 独自の組織によって作成された[カスタム アプリ](#custom-apps)。

## <a name="core-apps"></a>コア アプリ

アクティビティ フィード、Teams チャネル、チャット、予定表、通話などの一部の既定の機能は、エンド ユーザーが簡単にアクセスできるように既定で使用でき、固定されています。 管理者は、 [セットアップ ポリシー](/microsoftteams/teams-app-setup-policies)を使用して既定の動作を変更できます。

:::image type="content" source="media/core-apps-pinned1.png" alt-text="コア アプリは、既定でTeamsにピン留めされたアプリです。" lightbox="media/core-apps-pinned2.png":::

## <a name="microsoft-provided-apps"></a>Microsoft 提供のアプリ

Microsoft は、生産性とコラボレーションを向上させるための多くのアプリを提供しています。 管理者とエンド ユーザーは、管理センターのPublisherとして Microsoft を検索するか、チーム ストアでプロバイダーとして一覧表示することで、これらのアプリを見つけることができます。

Teams には、リスト、Tasks、称賛、承認などを含む一連の組み込みアプリが付属しています。 Teams の初期展開時に、おすすめのアプリ (Planner など) を含めることをお勧めします。

:::image type="content" source="media/microsoft-apps-in-tac1.png" alt-text="Teams管理センターの Microsoft アプリ" lightbox="media/microsoft-apps-in-tac2.png":::

## <a name="third-party-apps-validated-by-microsoft"></a>Microsoft によって検証されたサード パーティ製アプリ

Microsoft が提供するアプリに加えて、Microsoft が検証したサード パーティ製アプリも使用できます。 Microsoft は、これらのアプリをTeams ストアで利用できるようにする前に、これらのアプリの機能とセキュリティを検証します。 アプリの検証の利点を理解するには、 [サード パーティ製アプリの検証に関する](overview-of-app-validation.md)説明を参照してください。

:::image type="content" source="media/3p-apps-in-teams.png" alt-text="Teams ストア内のサード パーティ製アプリの例":::

## <a name="custom-apps"></a>カスタム アプリ

組織内の開発者によって作成されたアプリは、カスタム アプリと呼ばれます。 このようなアプリの開発は、組織の特定の要件に対して委託され、そのようなアプリを許可または禁止する制御があります。 組織内の開発者は、[Microsoft Power Platform](/microsoftteams/platform/samples/teams-low-code-solutions) とのTeams統合を使用して、カスタムの低コード ソリューションをすばやく構築できます。

管理者がカスタム アプリの使用を許可すると、エンド ユーザーは、ストアの左側のナビゲーションで **組織の [ビルド]** をクリックしてそのようなアプリTeams見つけます。

:::image type="content" source="media/built-for-your-org1.png" alt-text="デスクトップ アプリのTeams ストア内のカスタム アプリTeams" lightbox="media/built-for-your-org2.png":::

### <a name="understand-sideloading-of-custom-apps"></a>カスタム アプリのサイドローディングを理解する

カスタム アプリを開発し、エンド ユーザーに配布する前に、開発者はアプリをストアに追加してテストし、自分でテストするか、アプリをサイドロードするチームでテストします。 このメソッドは、アプリのサイドローディングと呼ばれ、カスタム アプリにのみ適用されます。

開発者は、アプリをサイドロードして、開発中のアプリをテストするために、特定のチームのメンバーがアプリを利用できるようにします。 サイドローディングが許可されている場合、管理者の承認は必要ありません。 管理者は、任意の開発者のサイドローディングを禁止できます。

サイドローディングを禁止した場合でも、開発者は [テスト テナント](/microsoftteams/platform/concepts/build-and-test/prepare-your-o365-tenant)でアプリをテストできます。 カスタム アプリの開発が完了すると、開発者は管理者にカスタム アプリをエンド ユーザーに配布するよう要求します。 詳細については、 [カスタム アプリを発行する方法を](/microsoftteams/upload-custom-apps)参照してください。 管理者は、特定のユーザーに対してカスタム アプリの使用を許可または禁止できます。

### <a name="about-app-templates"></a>アプリ テンプレートについて

Teams用のアプリ テンプレートは、一般的なユース ケースを示し、アプリ開発のベスト プラクティスを紹介し、開発者がカスタム アプリを作成するために拡張できるオープンソース アプリを提供するために Microsoft によって作成された、機能する運用環境対応のサンプル アプリです。 組織の開発者は、GitHubで使用できるコードを簡単に変更して、組織のニーズに合わせてアプリ テンプレートをカスタマイズします。 管理者は、エンド ユーザー向けのカスタム アプリとしてこれらのアプリを提供します。

詳細については、「[Microsoft Teams アプリ テンプレート](https://adoption.microsoft.com/microsoft-teams/app-templates/)」を参照してください。

## <a name="understand-app-capabilities"></a>アプリの機能を理解する

エンド ユーザーがTeams内で作業できるようにする豊富なエクスペリエンスを提供するために、アプリ開発者は次のアプリ機能を利用します。 メッセージング拡張機能を使用すると、ユーザーは Web サービスTeamsクライアントと対話できます。 外部システムでアクションを検索または開始します。 対話の結果を、リッチ フォーマットされたカードとしてTeams クライアントに送信できます。 会議機能拡張アプリは、会議内で開発者のアプリを統合し、会議内の応答性の高いエクスペリエンスを提供します。

ボットは、チャットボットまたは会話型ボットとも呼ばれます。 これは、単純で反復的なタスクを実行するアプリです。 ボットの操作は、簡単な質問と回答にすることも、サービスやサポートへのアクセスを提供する複雑な会話である場合もあります。 ユーザーは、ビット 1 対 1 またはチャネルでチャットできます。 たとえば、Polly アプリを使用して、クイックアンケートを作成し、フィードバックを得て、パルス チェックを行うことができます。

タブは、チャネルまたはチャットの上部にピン留めされたTeams対応の Web ページです。 タブを使用すると、Web に似たエクスペリエンスでコンテンツやサービスを操作できます。 個々のユーザーのチーム、グループ チャット、または個人用アプリ内のチャネルの一部としてタブを追加できます。

Webhook とコネクタは、エンド ユーザーが頻繁に使用するサービス (Jira Cloud や Bitbucket など) からコンテンツと更新プログラムをチャネル会話に直接配信します。 この機能を使用するアプリは、外部アプリと通信でき、外部サービスから通知やメッセージを送受信できます。

メッセージング拡張機能は、アプリ コンテンツを挿入したり、エンド ユーザーが会話から離れることなくメッセージを操作したりするためのショートカットです。 メッセージング拡張機能には、エンド ユーザーが外部コンテンツをすばやく検索し、メッセージまたはアクション コマンドに挿入するための検索コマンドを含めることができます。

Teams機能にマップされている一般的なユース ケースを表示するには、「[ユース ケースをアプリ機能にマップTeams](/microsoftteams/platform/concepts/design/map-use-cases)」を参照してください。

<!--- TBD: Admins do many considerations and decisions around app adoption and app governance. These are to be covered in a separate article. Commenting the below content for now as part of this article revamp.

## Apps deployment decisions

Teams provides a great out-of-the-box collaboration experience for your organization, and most organizations find that the default settings work for them. This article helps you decide whether to change any of the default settings, based on your organization's profile and business requirements, then it walks you through each change. We've split the settings into two groups, starting with the core set of [changes you're more likely to make](#core-deployment-decisions). The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.

## Core deployment decisions

These are the apps settings that most organizations want to change (if the Teams default settings don't work for them).

### App availability settings

Teams provides many apps published by Microsoft and by third parties to engage users, support productivity, and integrate commonly used business services into Teams.
Get apps from the Teams Store. By default, all apps, including custom apps that you've submitted via the [Teams Store approval process](/microsoftteams/platform/publishing/apps-publish#microsoft-teams-app-approval-process), are turned on for all users. For example, users can use the Planner app to build and manage team tasks in Teams.

By default, all Microsoft-provided, third-party, and custom apps are available, and you can turn individual apps on or off. There are org-wide settings that let you turn all third-party and/or custom apps on or off for your entire organization.

| Ask yourself | Action |
|--------------|--------|
|Will you change the default Teams apps settings? | For more information about policies and settings that you can use to manage apps in your organization, see [Admin settings for apps in Microsoft Teams](admin-settings.md).|

### App permissions and other considerations

Apps are consented to by users and managed by the admin or IT pro through policies. However, app permissions and risk profile are defined in the app itself.

| Ask yourself | Action |
|--------------|--------|
|<br>Which apps do I want to allow access to? Which ones do I not want to allow access to?  | <ul><li>See [Microsoft Teams apps permissions and considerations](app-permissions.md) for a list of things you should consider when allowing access to an app, bot, tab, or connector.</li><li>See [Manage your apps in the Microsoft Teams admin center](manage-apps.md) for information about making an app available to users in your organization.</li></ul>|

--->

<!--- TBD: Rewrite this to talk about bots and tabs as a capability of apps. Admins do not govern bots, tabs, etc. Admins only govern apps that contain capabilities such as connectors, bots, etc. This writeup gives an impression that admins manage apps + bots + tabs + connectors, etc.

### Bots for private chats and channels

Bots are automated programs that respond to queries or give updates and notifications about details users find interesting or want to stay informed about. Bots allow users to interact with cloud services such as task management, scheduling, and polling in a Teams chat. Teams supports bots in private chats and channels. Administrators can control whether the use of bots is allowed in a Microsoft 365 or Office 365 organization.

| Ask yourself | Action |
|--------------|--------|
|Do I want to allow custom bots in my organization?|For more information about adding bots, see [Add bots for private chats and channels in Microsoft Teams](/microsoftteams/platform/bots/what-are-bots). For information about turning custom bots on or off, see [Admin settings for apps in Microsoft Teams](admin-settings.md).|

### Built-in and custom tabs

Owners and team members can add tabs to a channel, private chat, and group chat to help integrate their cloud services. Add tabs to help users access and manage the data they need or use the most. In channels, the Conversations and Files tabs are created by default. In every private chat, the Conversations, Files, Organization, and Activity tabs are created by default. In addition to these built-in tabs, you can design and add custom tabs. To learn about turning Teams apps on or off for your organization, read [Admin settings for apps in Teams](admin-settings.md).

| Ask yourself | Action |
|--------------|--------|
|Do I want to allow custom tabs in my organization?|For more information, see [Use built-in and custom tabs in Teams](/microsoftteams/platform/tabs/what-are-tabs).|

### Custom connectors

Connectors keep your team current by delivering content and updates from services you frequently use directly into a channel. With connectors, your Teams users can receive updates from popular services such as Trello, Wunderlist, GitHub, and Azure DevOps Services in their Teams chats.

| Ask yourself | Action |
|--------------|--------|
|Do I want to allow users to create custom connectors?|For more information, see [Use custom connectors in Teams](office-365-custom-connectors.md).|

--->

<!--- TBD: Activity reports is not part of app overview. Commenting for now. To be reused in a different article later.

### Activity reports

You can use activity reports to see how users in your organization are using Teams. For example, if some don't use Teams yet, they might not know how to get started or understand how they can use Teams to be more productive and collaborative. Your organization can use the activity reports to decide where to prioritize training and communication efforts. To view activity reports, you must be a global admin in Microsoft 365 or Office 365, Teams service admin, or Skype for Business admin.

| Ask yourself | Action |
|--------------|--------|
| <br>Who needs to see the activity reports, and do they have the correct permissions to view them? |<ul><li>If you don't want to assign an admin role to a user, you can [assign the Reports reader role](teams-activity-reports.md#reports-reader-role).</li><li>See [Roles and permissions](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) and [View and assign roles](/azure/active-directory/users-groups-roles/directory-manage-roles-portal) for information about assigning admin roles in Azure Active Directory.</li></ul> |

--->
