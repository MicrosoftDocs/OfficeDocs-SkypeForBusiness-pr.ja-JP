---
title: Microsoft Teams のアプリについて知っておくべきこと
ms.reviewer: ''
description: アプリについて学習し、組織のプロファイルとビジネス要件に基づいて、Teams で使用できるアプリを決定します。
ms.topic: article
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
audience: admin
ms.service: msteams
ms.subservice: teams-apps
ms.date: 10/01/2022
ms.collection:
- M365-collaboration
- m365-frontline
- highpri
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020; intro-overview; intro-hub-or-landing
ms.openlocfilehash: adabe9321307bb9696636ae7ab882775705dcd27
ms.sourcegitcommit: 6e85f3f70f8488ab827ac352c0f324b6dfd4b856
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2022
ms.locfileid: "68376995"
---
# <a name="understand-microsoft-teams-apps"></a>Microsoft Teams アプリを理解する

Teams のアプリは、ユーザーが職場のツールやサービスをまとめ、他のユーザーと共同作業するのに役立ちます。 たとえば、エンド ユーザーは、他のユーザーとすばやく共同で作業するために Teams にピン留めされた予定表アプリ、Teams チャネルで Web サービスの品質をユーザーに通知するボット機能を備えたアプリ、チャネル内のさまざまなエンド ユーザーとタスクを共有して割り当てるアプリなどを使用します。 Microsoft Teams アプリは、ローカルに展開する必要のない Web ベースの SaaS アプリです。

管理者は、エンド ユーザーの広範な要件と組織の IT ポリシー、標準、リスク プロファイルのバランスを取るアプリ ガバナンス プロセスを設定します。

検証済みのセキュリティで保護された Teams アプリの広範な [カタログ](https://appsource.microsoft.com/marketplace/apps?product=office%3Bteams&page=1) では、組織が毎日必要とするツールとサービスへのアクセスをエンド ユーザーに提供します。 Teams 管理センターでは、アプリを管理するためのエンタープライズ レベルのコントロールと構成を管理者に提供します。 会議、チャット、チャネルなどのさまざまなコンテキストで、各ユーザーのアプリの可用性を制御します。

この記事は、アプリの種類と、ユーザーがそれらのアプリにアクセスする場所を理解することに役立ちます。 アプリの使用方法の詳細については、「[エンドユーザー向けアプリの概要](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0)」を参照してください。

エンド ユーザーが Teams で使用できるアプリの種類は次のとおりです。

* [Teams の一部であるコア アプリ](#core-apps)。
* [Microsoft によって作成されたその他のアプリ](#microsoft-provided-apps)。
* パートナーによる[サード パーティ製アプリ](#third-party-apps-validated-by-microsoft) (Microsoft によって検証されます)。
* 独自の組織によって作成された[カスタム アプリ](#custom-apps)。

## <a name="core-apps"></a>コア アプリ

アクティビティ フィード、チーム、チャット、予定表、通話、ファイル、割り当て (教育テナント) などの一部の Teams 機能は既定で使用でき、エンド ユーザーが簡単にアクセスできるように既定でピン留めされています。 現場担当者の場合は、アクティビティ、シフト、チャット、通話のみが使用でき、ピン留めされます。 管理者は、[セットアップ ポリシー](/microsoftteams/teams-app-setup-policies)を使用してこの既定の動作を変更できます。

:::image type="content" source="media/core-apps-pinned1.png" alt-text="コア アプリは、既定で Teams にピン留めされたアプリです。" lightbox="media/core-apps-pinned2.png":::

## <a name="microsoft-provided-apps"></a>Microsoft 提供のアプリ

Microsoft には、生産性と共同作業を向上させるための多くのアプリがあります。 ユーザーとエンド ユーザーは、Teams 管理センターでパブリッシャーとしてリストされている Microsoft を探すか、Teams ストアのプロバイダーとして一覧表示することで、これらのアプリを見つけることができます。

Teams には、リスト、Tasks、称賛、承認などを含む一連の組み込みアプリが付属しています。 Teams の初期展開時に、おすすめのアプリ (Planner など) を含めることをお勧めします。

:::image type="content" source="media/microsoft-apps-in-tac1.png" alt-text="Teams 管理センターの Microsoft アプリの一覧を示すスクリーンショット。" lightbox="media/microsoft-apps-in-tac2.png":::

## <a name="third-party-apps-validated-by-microsoft"></a>Microsoft による検証済みのサード パーティ製アプリ

Microsoft 提供のアプリに加えて、Microsoft 検証済みのサードパーティ製アプリを使用できます。 Microsoft は、Teams ストアでこれらのアプリを使用できるようにする前に、これらのアプリの機能性とセキュリティを検証します。 アプリ検証の利点を理解するには、[サード パーティ製アプリの検証](overview-of-app-validation.md)を参照してください。

:::image type="content" source="media/3p-apps-in-teams.png" alt-text="Teams ストアにあるサード パーティ製アプリの例のスクリーンショット。":::

## <a name="custom-apps"></a>カスタム アプリ

組織内の開発者によって作成されたアプリは、カスタム アプリ (または基幹業務アプリ) と呼ばれます。 組織は、組織固有の要件に応じてカスタム アプリの作成を委託する場合があります。 あなたは組織全体または特定のユーザーに対して、このようなアプリを許可またはブロックする管理能力を保持しています。 組織内の開発者は、Teams と [Microsoft Power Platform](/microsoftteams/platform/samples/teams-low-code-solutions) の統合を使用して、カスタムのローコード ソリューションを構築できます。

管理者がカスタム アプリの使用を許可した後、エンド ユーザーは Teams ストアの左側のナビゲーションで **組織のビルド** を選択することで、そのようなアプリを見つけることができます。

:::image type="content" source="media/built-for-your-org1.png" alt-text="Teams デスクトップ アプリの Teams ストアにあるカスタム アプリのスクリーンショット。" lightbox="media/built-for-your-org2.png":::

詳細については、「 [カスタム アプリとサイドロードされたアプリについて理解して管理](custom-app-overview.md)する」を参照してください。

## <a name="about-app-templates"></a>アプリ テンプレートについて

Microsoft は、アプリ開発方法を使用して、機能と運用に対応したサンプル アプリを作成して提供します。 まとめて、これらのアプリは Teams 用のアプリ テンプレートと呼ばれ、次の目的で提供されます。

* Teams でのコラボレーションのユース ケースをいくつか示します。
* アプリ開発のベスト プラクティスとメソッドを紹介します。
* 開発者が独自のアプリを作成するために拡張できるオープンソース アプリを提供します。

組織の開発者は、提供されたソース コードを簡単に変更してアプリ テンプレートをカスタマイズします。 これらのアプリをエンド ユーザー向けのカスタム アプリとして提供して、組織のニーズを満たします。

詳細については、「[Microsoft Teams アプリ テンプレート](https://adoption.microsoft.com/microsoft-teams/app-templates/)」を参照してください。

## <a name="understand-app-capabilities"></a>アプリの機能を理解する

エンド ユーザーが Teams 内で作業できる豊富なエクスペリエンスを提供するために、アプリ開発者は次のアプリ機能を使用します。 メッセージング拡張機能を使用すると、ユーザーは Web サービス Teams クライアントを操作できます。 外部システムでアクションを検索または開始します。 操作の結果は、書式設定されたカードとして Teams クライアントに送信できます。 会議機能拡張アプリは、開発者のアプリを会議内に統合し、応答性の高い会議エクスペリエンスを提供します。

ボットは、チャットボットまたは会話ボットとも呼ばれます。 ボットは、単純な反復タスクを実行するアプリです。 ボットの操作には、簡単な質問と回答や、サービスやサポートへのアクセスを提供する複雑な会話などがあります。 ユーザーは、1 対 1 またはチャネルでチャットできます。 たとえば、Polly アプリを使用して、クイック アンケートを作成したり、フィードバックを受け取ったり、脈拍チェックを行ったりすることができます。

タブは、チャネルやチャットの上部にピン留めされた Teams 対応の Web ページです。 タブを使用すると、Web に似たエクスペリエンスでコンテンツやサービスを操作できます。 チーム内のチャネルの一部、グループ チャット、個々のユーザーの個人用アプリとしてタブを追加できます。

Webhook とコネクタは、エンド ユーザーが頻繁に使用するサービス (Jira Cloud や Bitbucket など) からコンテンツと更新プログラムをチャネル会話に直接配信します。 この機能を使用するアプリは、外部アプリと通信したり、外部サービスからの通知やメッセージを送受信したりできます。

メッセージング拡張機能は、エンド ユーザーが会話から離れることなく、アプリのコンテンツを挿入したり、メッセージに対して操作したりするためのショートカットです。 メッセージング拡張機能には、エンド ユーザーが外部コンテンツをすばやく検索し、メッセージやアクション コマンドに挿入するための検索コマンドを含めることができます。

Teams の機能にマップされている一般的なユース ケースを表示するには、「ユース [ケースを Teams アプリの機能にマップする](/microsoftteams/platform/concepts/design/map-use-cases)」を参照してください。

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

## <a name="related-article"></a>関連記事

* [Teams 用アプリ テンプレートの詳細については、こちらを参照してください](/microsoftteams/platform/samples/app-templates)。
