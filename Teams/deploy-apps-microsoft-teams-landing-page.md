---
title: アプリについてMicrosoft Teams
ms.reviewer: ''
description: アプリについて学習し、組織のプロファイルとビジネス要件にTeamsに基づいて、アプリで許可するアプリを決定します。
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
ms.openlocfilehash: f8579d7c2c49749058c174aa71430803dce63286
ms.sourcegitcommit: 2ce3e95401ac06c0370a54862372a94ec6291d01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2022
ms.locfileid: "64643021"
---
# <a name="about-apps-in-microsoft-teams"></a>Microsoft Teams のアプリについて

アプリは、職場のツールやサービスを集め、他のユーザーと共同作業を行う最適な方法です。 アプリを使用すると、エンド ユーザーは、毎日のタスクで生産性、共同作業、効果的な作業を行うことができます。 組織は、アプリを使用して顧客との接続、サービスの提供、情報の共有を行います。 アプリを使用すると、ユーザーはチャット、会議、チャネルTeamsより効果的になります。 たとえば、エンド ユーザーが Teams のピン留めされた予定表を使用して他のユーザーとすばやく共同作業を行う場合、ボット機能を備えるアプリは、Teams チャネル内の Web サービスの QoS をユーザーに通知し、チャネル内のさまざまなエンド ユーザーにタスクを共有して割り当てるアプリです。

ストア内の検証済みアプリとセキュリティで保護されたアプリの広範な選択により、エンド ユーザーは、組織が毎日必要とするツールやサービスにアクセスできます。 Microsoft Teamsは、デプロイする必要はない Web ベースの SaaS アプリです。 エンド ユーザーは、ユーザーが提供Teamsに基づいてアプリを使用できます。 管理者は、組織のユーザーに対するアプリの使用を承認またはブロックします。 会議、チャット、チャネルをまたがって、すべてのユーザーのアプリの可用性を制御できます。

エンド ユーザーに必要なアプリを提供するには、アプリの種類とユーザーがそれらのアプリにアクセスする場所について説明します。 アプリの使用の詳細については、「エンドユーザー向け [アプリの概要」を参照してください。](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0)

<!--- Commenting the previous content as part of this article revamp.

Apps let users find content from their favorite services and share it in Teams. They let you do tasks such as pin services at the top of a channel, automate notifications using bots, or share and assign tasks.

--->

エンド ユーザーがアプリケーションで使用できるさまざまな種類のアプリはTeams。

* [アプリの一部であるコア Teams](#core-apps)。
* [Microsoft によって作成されたその他のアプリ](#microsoft-provided-apps)。
* [パートナーによるサード パーティ製](#third-party-apps-validated-by-microsoft) アプリ (Microsoft によって検証済み)。
* [独自の組織](#custom-apps) によって作成されたカスタム アプリ。

## <a name="core-apps"></a>コア アプリ

アクティビティ フィード、Teams チャネル、チャット、予定表、通話などの一部の既定の機能は、エンド ユーザーが簡単にアクセスするために既定で使用できます。 管理者は、セットアップ ポリシーを使用して既定の動作 [を変更できます](/microsoftteams/teams-app-setup-policies)。

:::image type="content" source="media/core-apps-pinned1.png" alt-text="コア アプリは、既定で既定でTeamsアプリです。" lightbox="media/core-apps-pinned2.png":::

## <a name="microsoft-provided-apps"></a>Microsoft が提供するアプリ

Microsoft では、生産性とコラボレーションを向上させるために多くのアプリを提供しています。 ユーザーとエンド ユーザーは、管理センターで Publisher として表示されている Microsoft を探したり、チーム ストアでプロバイダーとして表示したりして、これらのアプリを見つける可能性があります。

Teams には、リスト、Tasks、称賛、承認などを含む一連の組み込みアプリが付属しています。 Teams の初期展開時に、おすすめのアプリ (Planner など) を含めることをお勧めします。

:::image type="content" source="media/microsoft-apps-in-tac1.png" alt-text="管理センター Teams Microsoft アプリ" lightbox="media/microsoft-apps-in-tac2.png":::

## <a name="third-party-apps-validated-by-microsoft"></a>Microsoft によって検証されたサード パーティ製アプリ

Microsoft が提供するアプリに加えて、Microsoft が検証したサード パーティ製アプリを使用できます。 Microsoft は、これらのアプリを Microsoft Store で利用できる前に、これらのアプリの機能Teamsします。

<!--- TBD: Link to the new article later when it is created.
To understand the benefits of app validation, see [validation of third-party apps]().

--->

:::image type="content" source="media/3p-apps-in-teams.png" alt-text="Teams Store のサード パーティ製アプリの例":::

<!--- TBD: Check the relevance of this link here.
For more information, see [Microsoft Teams App Security and Compliance](/microsoft-365-app-certification/teams/teams-apps).
--->

## <a name="custom-apps"></a>カスタム アプリ

組織内の開発者によって作成されたアプリは、カスタム アプリと呼ばれる。 このようなアプリの開発は、組織の特定の要件に対して委託され、そのようなアプリを許可または禁止するコントロールがあります。 組織内の開発者は、Microsoft Power Platform との統合を使用して、カスタムの低Teams[を迅速に構築できます](/microsoftteams/platform/samples/teams-low-code-solutions)。

管理者がカスタム アプリの使用を許可すると、エンド ユーザーは、組織の左側のナビゲーションにある [ビルド] をクリックして、このようなアプリTeamsします。

:::image type="content" source="media/built-for-your-org1.png" alt-text="カスタム アプリは、Teams デスクトップ アプリTeamsストアに保存されます" lightbox="media/built-for-your-org2.png":::

### <a name="understand-sideloading-of-custom-apps"></a>カスタム アプリのサイドローディングについて

カスタム アプリを開発し、エンド ユーザーに配布する前に、開発者はアプリをストアに追加してテストし、独自にテストするか、アプリをサイドロードするチームでテストします。 このメソッドはアプリのサイドローディングと呼ばされ、カスタム アプリにのみ適用されます。

開発者は、アプリをサイドロードして、特定のチームのメンバー (通常は開発中のアプリをテストする場合) に使用できます。 サイドローディングが許可されている場合、管理者の承認は必要ない。 管理者は、どの開発者に対してでもサイドローディングを禁止できます。

サイドローディングを許可しなき場合でも、開発者はテスト テナントでアプリを [テストできます](/microsoftteams/platform/concepts/build-and-test/prepare-your-o365-tenant)。 カスタム アプリの開発が完了すると、開発者は管理者にカスタム アプリをエンド ユーザーに配布する必要があります。 詳細については、カスタム アプリ [を発行する方法に関するページを参照してください](/microsoftteams/upload-custom-apps)。 管理者は、特定のユーザーに対してカスタム アプリの使用を許可または禁止できます。

### <a name="about-app-templates"></a>アプリ テンプレートについて

Teams 用のアプリ テンプレートは、一般的な使用例を示し、アプリ開発のベスト プラクティスを紹介し、開発者がカスタム アプリを作成するために拡張できるオープン ソース アプリを提供するために、Microsoft が作成した機能的で運用可能なサンプル アプリです。 組織の開発者は、組織のニーズに合わせてアプリ テンプレートをカスタマイズし、組織で使用できるコードを簡単に変更GitHub。 管理者は、これらのアプリをエンド ユーザーのカスタム アプリとして提供します。

詳細については、「アプリ テンプレート[のMicrosoft Teamsを参照してください](https://adoption.microsoft.com/microsoft-teams/app-templates/)。

## <a name="understand-app-capabilities"></a>アプリの機能について

メッセージング アプリには、チャネルまたはチャット内のアプリのコンテンツが含まれます。 会議機能拡張アプリは、会議内で開発者のアプリを統合し、応答性の高い会議中のエクスペリエンスを提供します。 さまざまな機能を提供するために、アプリ開発者は次のアプリ機能を利用します。

ボットは、回答、更新、および支援を提供します。 これらの 1 対 1 またはチャネル内でチャットできます。 タスク管理やスケジュール設定などについて支援できます。 たとえば、Polly アプリを使用して、迅速なアンケートの作成、フィードバックの取得、パルス チェックを行います。

チャネルの上部にピン留めされたタブを使用すると、Web のようなエクスペリエンスでコンテンツやサービスを操作できます。
コネクタは、頻繁に使用するサービス (Jira Cloud や Bitbucket など) からコンテンツと更新をチャネル会話に直接配信します。

メッセージング拡張機能は、エンド ユーザーが会話から離れることなく、アプリのコンテンツを挿入したり、メッセージに対して操作したりするショートカットです。 メッセージング拡張機能には、エンド ユーザーが外部コンテンツをすばやく検索し、メッセージまたはアクション コマンドに挿入する検索コマンドを使用できます。

アプリケーション機能にマップされている一般的な使用Teams、アプリケーション機能に使用する使用例Teams[参照してください](/microsoftteams/platform/concepts/design/map-use-cases)。

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
