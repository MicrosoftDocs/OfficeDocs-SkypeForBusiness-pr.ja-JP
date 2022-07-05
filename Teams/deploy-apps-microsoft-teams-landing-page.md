---
title: Microsoft Teams のアプリについて知っておくべきこと
ms.reviewer: ''
description: アプリについて学習し、組織のプロファイルとビジネス要件に基づいて、Teams で使用できるアプリを決定します。
ms.topic: article
author: guptaashish
ms.author: guptaashish
manager: prkosh
audience: admin
ms.date: 04/05/2022
ms.service: msteams
ms.subservice: teams-apps
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020; intro-overview; intro-hub-or-landing
ms.openlocfilehash: f802506ff815745aaf555501e37171ebddfc7f91
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615863"
---
# <a name="about-apps-in-microsoft-teams"></a>Microsoft Teams のアプリについて

アプリは、職場のツールとサービスをまとめ、他のユーザーと共同作業する優れた方法です。 アプリは、エンド ユーザーの日常業務における生産性向上、共同作業、効率化に役立ちます。 組織は、顧客とつながり、サービスを提供し、情報を共有するためにアプリを使用します。 アプリを使用すると、ユーザーは Teams チャット、会議、チャネルの効果を高めることができます。 たとえば、エンド ユーザーが Teams でピン留めされた予定表を使用して他のユーザーとすばやく共同で作業したり、Teams チャネルで Web サービスの QoS をユーザーに通知するボット機能を備えたアプリ、チャネル内のさまざまなエンド ユーザーとタスクを共有し割り当てるアプリなどがあります。

ストア内の検証済みの安全なアプリの豊富な選択により、エンド ユーザーは組織が毎日必要とするツールやサービスにアクセスできます。 Microsoft Teams アプリは、展開する必要のない Web ベースの SaaS アプリです。 エンド ユーザーは、お客様から提供された[アクセス許可](https://admin.teams.microsoft.com/policies/app-permission)のみに基づいて Teams でアプリを使用できます。 管理者であるお客様は、組織のユーザーに対するアプリの使用を承認またはブロックするだけです。 会議、チャット、チャネルを問わず、すべてのユーザーに対するアプリの可用性を制御します。

エンド ユーザーに必要なアプリを提供するために、アプリの種類と、ユーザーがそれらのアプリにアクセスする場所を理解してください。 アプリの使用方法の詳細については、「[エンドユーザー向けアプリの概要](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0)」を参照してください。

<!--- Commenting the previous content as part of this article revamp.

Apps let users find content from their favorite services and share it in Teams. They let you do tasks such as pin services at the top of a channel, automate notifications using bots, or share and assign tasks.

--->

エンド ユーザーが Teams で使用できるアプリの種類は次のとおりです。

* [Teams の一部であるコア アプリ](#core-apps)。
* [Microsoft によって作成されたその他のアプリ](#microsoft-provided-apps)。
* パートナーによる[サード パーティ製アプリ](#third-party-apps-validated-by-microsoft) (Microsoft によって検証されます)。
* 独自の組織によって作成された[カスタム アプリ](#custom-apps)。

## <a name="core-apps"></a>コア アプリ

アクティビティ フィード、Teams チャネル、チャット、予定表、通話などの一部の既定の機能が利用でき、エンド ユーザーが簡単にアクセスできるよう、既定でピン留めされています。 管理者であるお客様は、[セットアップ ポリシー](/microsoftteams/teams-app-setup-policies)を使用して既定の動作を変更できます。

:::image type="content" source="media/core-apps-pinned1.png" alt-text="コア アプリは、既定で Teams にピン留めされたアプリです。" lightbox="media/core-apps-pinned2.png":::

## <a name="microsoft-provided-apps"></a>Microsoft 提供のアプリ

Microsoft には、生産性と共同作業を向上させるための多くのアプリがあります。 これらのアプリは、管理センターで Microsoft が発行元として一覧表示されているか、チーム ストアでプロバイダーとして一覧表示されているか確認することで、お客様やエンド ユーザーが見つけることができます。

Teams には、リスト、Tasks、称賛、承認などを含む一連の組み込みアプリが付属しています。 Teams の初期展開時に、おすすめのアプリ (Planner など) を含めることをお勧めします。

:::image type="content" source="media/microsoft-apps-in-tac1.png" alt-text="Microsoft Teams 管理センターの Microsoft アプリ" lightbox="media/microsoft-apps-in-tac2.png":::

## <a name="third-party-apps-validated-by-microsoft"></a>Microsoft による検証済みのサード パーティ製アプリ

Microsoft 提供のアプリに加えて、Microsoft 検証済みのサードパーティ製アプリを使用できます。 Microsoft は、Teams ストアでこれらのアプリを使用できるようにする前に、これらのアプリの機能性とセキュリティを検証します。 アプリ検証の利点を理解するには、[サード パーティ製アプリの検証](overview-of-app-validation.md)を参照してください。

:::image type="content" source="media/3p-apps-in-teams.png" alt-text="Teams ストアのサード パーティ製アプリの例":::

## <a name="custom-apps"></a>カスタム アプリ

組織内の開発者が作成したアプリは、カスタム アプリと呼ばれます。 このようなアプリの開発は、ご所属の組織の特定の要件に合わせて委託され、お客様はそのようなアプリを許可または禁止する制御があります。 組織内の開発者は、Teams の [Microsoft Power Platform](/microsoftteams/platform/samples/teams-low-code-solutions) との統合を使用すると、カスタムのローコード (わずかなコードを記述するだけで使用できる) ソリューションをすばやく構築できます。

管理者がカスタム アプリの使用を許可した後、エンド ユーザーは Teams ストアの左側のナビゲーションで **[組織向けに開発]** をクリックしてそのアプリを見つけます。

:::image type="content" source="media/built-for-your-org1.png" alt-text="Teams デスクトップ アプリの Teams ストアにあるカスタム アプリ" lightbox="media/built-for-your-org2.png":::

### <a name="understand-sideloading-of-custom-apps"></a>カスタム アプリのサイドローディングを理解する

カスタム アプリを開発し、エンド ユーザーに配布する前に、開発者はアプリをストアに追加して自分でテストするか、アプリをサイドロードするチームと連携してテストします。 この方法は、アプリのサイドローディングと呼ばれ、カスタム アプリにのみ適用されます。

開発者は、開発中のアプリのテスト用に、特定のチームのメンバーがアプリを利用できるようにするために、アプリをサイドロードできます。 サイドローディングが許可されている場合、管理者の承認は必要ありません。 管理者は、任意の開発者のサイドローディングを禁止できます。

サイドローディングを禁止した場合でも、開発者は[テスト テナント](/microsoftteams/platform/concepts/build-and-test/prepare-your-o365-tenant)でアプリをテストできます。 カスタム アプリの開発が完了すると、開発者はカスタム アプリをエンド ユーザーに配布するよう管理者に要求します。 詳細については、[カスタム アプリを発行する方法](/microsoftteams/upload-custom-apps)を参照してください。 管理者であるお客様は、特定のユーザーに対してカスタム アプリの使用を許可または禁止できます。

### <a name="about-app-templates"></a>アプリ テンプレートについて

Teams 用のアプリ テンプレートは、Microsoft が作成した機能的で本番環境に対応したサンプル アプリであり、一般的なユース ケースを示し、アプリ開発のベスト プラクティスを紹介し、開発者がカスタム アプリを作成するために拡張できるオープンソース アプリを提供します。 組織の開発者は、GitHub で公開されたコードを簡単に変更して、アプリ テンプレートを組織のニーズに合わせてカスタマイズします。 管理者であるお客様は、エンド ユーザー向けのカスタム アプリとしてこれらのアプリを提供します。

詳細については、「[Microsoft Teams アプリ テンプレート](https://adoption.microsoft.com/microsoft-teams/app-templates/)」を参照してください。

## <a name="understand-app-capabilities"></a>アプリの機能を理解する

エンド ユーザーが Teams 内で作業できる豊富なエクスペリエンスを提供するために、アプリ開発者は次のアプリ機能を利用します。 メッセージング拡張機能を使用すると、ユーザーは Web サービス Teams クライアントを操作できます。 外部システムでアクションを検索または開始します。 操作の結果は、書式設定されたカードとして Teams クライアントに送信できます。 会議機能拡張アプリは、開発者のアプリを会議内に統合し、応答性の高い会議エクスペリエンスを提供します。

ボットは、チャットボットまたは会話ボットとも呼ばれます。 ボットは、単純な反復タスクを実行するアプリです。 ボットの操作には、簡単な質問と回答や、サービスやサポートへのアクセスを提供する複雑な会話などがあります。 ユーザーは、1 対 1 またはチャネルでチャットできます。 たとえば、Polly アプリを使用して、クイック アンケートを作成したり、フィードバックを受け取ったり、脈拍チェックを行ったりすることができます。

タブは、チャネルやチャットの上部にピン留めされた Teams 対応の Web ページです。 タブを使用すると、Web に似たエクスペリエンスでコンテンツやサービスを操作できます。 チーム内のチャネルの一部、グループ チャット、個々のユーザーの個人用アプリとしてタブを追加できます。

Webhook とコネクタは、エンド ユーザーが頻繁に使用するサービス (Jira Cloud や Bitbucket など) からコンテンツと更新プログラムをチャネル会話に直接配信します。 この機能を使用するアプリは、外部アプリと通信したり、外部サービスからの通知やメッセージを送受信したりできます。

メッセージング拡張機能は、エンド ユーザーが会話から離れることなく、アプリのコンテンツを挿入したり、メッセージに対して操作したりするためのショートカットです。 メッセージング拡張機能には、エンド ユーザーが外部コンテンツをすばやく検索し、メッセージやアクション コマンドに挿入するための検索コマンドを含めることができます。

Teams 機能にマップされている一般的なユース ケースを表示するには、「[ユース ケースを Teams アプリ機能にマップする](/microsoftteams/platform/concepts/design/map-use-cases)」を参照してください。

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
| Who needs to see the activity reports, and do they have the correct permissions to view them? |<ul><li>If you don't want to assign an admin role to a user, you can [assign the Reports reader role](teams-activity-reports.md#reports-reader-role).</li><li>See [Roles and permissions](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) and [View and assign roles](/azure/active-directory/users-groups-roles/directory-manage-roles-portal) for information about assigning admin roles in Azure Active Directory.</li></ul> |

--->
