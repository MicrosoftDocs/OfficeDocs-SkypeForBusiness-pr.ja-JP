---
title: Microsoft Teams のチャット、チーム、チャネル、およびアプリ
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.subservice: teams-chat
audience: admin
search.appverid: MET150
description: Microsoft Teams のチャット、チーム、アプリ、およびチャネルの Teams 設定を構成するための詳細なガイダンスが含まれています。
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.quickstartteamsadmin
- intro-get-started
- seo-marvel-apr2020
- seo-marvel-may2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 10063b2b6c8c0f92de8d949578133b2577ff6d9f
ms.sourcegitcommit: ed7d3b12d4bfe48863de873360c2ae90bbb15530
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/30/2022
ms.locfileid: "69194918"
---
# <a name="chat-teams-channels--apps-in-microsoft-teams"></a>Microsoft Teams のチャット、チーム、チャネル、およびアプリ

Teams provides a great out-of-the-box collaboration experience for your organization, and most organizations find that the default settings work for them. This article helps you decide whether to change any of the default settings, based on your organization's profile and business requirements, then it walks you through each change. We've split the settings into two groups, starting with the core set of [changes you're more likely to make](#core-deployment-decisions). The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.

開始するには、短い Teams チャット、チーム、およびチャネルのビデオをご覧ください (4:30 分):

<br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE476Yj?autoplay=false]

You can use [Advisor for Teams](use-advisor-teams-roll-out.md) to help you roll out Microsoft Teams. Advisor for Teams walks you through your Teams rollout. It assesses your Microsoft 365 environment and identifies the most common configurations that you may need to update or modify before you can successfully roll out Teams.

> [!TIP]
> Teams の初期展開時に、おすすめのアプリ (Planner など) を含めることをお勧めします。 [Teams の](deploy-apps-microsoft-teams-landing-page.md)導入を推進する際に、他の Teams アプリを追加します。

 > [!Note]
 > 別のプラットフォームでの Teams の機能についての詳細は、 [プラットフォームごとの Teams の機能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)を参照してください。

## <a name="chat-deployment-prerequisites"></a>チャットの展開に関する前提条件

Before you roll out Teams across your organization, take time to confirm that your environment is ready for Teams. Review [Prepare your organization's network for Teams](prepare-network.md) and make any required changes to your environment.

|確認事項|アクション |
|------------|-------|
|Teams を展開するために組織の準備が整っているか?|この質問に回答するには、次を参照してください。 <ul><li>[Teams 用に組織のネットワークを準備する](prepare-network.md)</li><li>[URL と IP アドレスの範囲](office-365-urls-ip-address-ranges.md)</li><li>[チームを作成するときの Microsoft 365 グループの計画](plan-office-365-groups.md)</li></ul>|

## <a name="core-deployment-decisions"></a>展開に関する重要な決定事項

次に示すチャット、チーム、およびチャネルの設定は、ほとんどの組織が変更を必要とするものです (既定の設定では適切に機能しない場合)。

### <a name="teams-administrators"></a>Teams の管理者

Teams provides a set of custom administrator roles that can be used to manage Teams for your organization. The roles provide various capabilities to administrators.

| 確認事項 | アクション |
|--------------|--------|
|Teams 通信管理者の役割を誰に割り当てるか?|Teams 管理者の役割の詳細については、「[Microsoft Teams の管理者ロールを使用して Teams を管理する](using-admin-roles.md)」を参照してください。|
|Teams 通信サポート エンジニアの役割を誰に割り当てるか?|管理者の役割を割り当てるには、「[Active Directory で管理者の役割と管理者以外の役割をユーザーに割り当てる](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)」を参照してください。|
|Teams 通信サポート スペシャリストの役割を誰に割り当てるか?||

### <a name="teams-owners-and-members"></a>Teams の所有者とメンバー

In addition to administrator roles, Teams lets you assign owner and member user roles, and selectively give them moderator capabilities (if moderation has been set up) to control who can perform certain actions within a channel. Moderation allows you to control who can start new posts in a channel, add and remove team members as moderators, and control whether team members can reply to existing channel messages.

|確認事項|アクション |
|------------|-------|
|各役割に誰を割り当てるか? | 各役割の機能を比較するには「[Microsoft Teams でチームの所有者、モデレーター、メンバーを割り当てる](assign-roles-permissions.md)」を参照してください。
|ユーザー役割を割り当てるにはどうすればよいか? | 役割を割り当てたり変更したりするには、「[ユーザー役割の割り当て](assign-roles-permissions.md)」を参照してください。
|チャネルで投稿したり、返信したりできるユーザーを制御する必要があるか? | モデレートを構成するには、「[Microsoft Teams でチャネル モデレートをセットアップして管理する](manage-channel-moderation-in-teams.md)」を参照してください。

### <a name="messaging-policies"></a>メッセージング ポリシー

Messaging policies control which chat and channel messaging features are available to users in Teams. For example, who can edit and delete sent messages, who can use chat, who can use memes in conversations, and more. By default, users are assigned the global messaging policy and all features are **On**. You can use the default global policy or create one or more custom messaging policies for people in your organization.

|確認事項|アクション |
|------------|-------|
|グローバル メッセージング ポリシーをカスタマイズするか?|Microsoft Teams 管理センターを使用したグローバル メッセージング ポリシーの変更や新しいポリシーの追加に関する詳細については、「[Teams でのメッセージング ポリシーを管理する](messaging-policies-in-teams.md)」を参照してください。|
|複数のメッセージング ポリシーが必要か?|メッセージング ポリシーを PowerShell で作成して割り当てる場合は、「[PowerShell スクリプトのサンプル: メッセージング ポリシーの作成と割り当て](scripts/powershell-script-teams-messaging-policy-edu.md)」を参照してください。|
|どのユーザーのグループにどのメッセージング ポリシーを割り当てるかについて判断する方法は?|CsTeamsMessagingPolicy コマンドレットの詳細については、「[Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)」を参照してください。|

### <a name="external-access"></a>外部アクセス

External access (federation) lets your users communicate with people outside of your organization via chat. By turning this on and adding domains to the allowed list, your users can communicate with users in other domains and organizations. External access is turned on by default.

|確認事項|アクション |
|------------|-------|
|<ul><li>外部会議をオフにして、組織のチャットをしますか?</li><li>有効にする場合は、自分の組織との通信を許可するドメインを制限するか?</li></ul> |<br>外部会議とチャットをオンまたはオフにするには、「[外部会議とチャットの管理](manage-external-access.md)」を参照してください。|

### <a name="guest-access"></a>ゲスト アクセス

Guest access in Teams lets individuals outside your organization access teams and channels. You can use the guest access settings to control which features guests can or can't use. Guest access is turned on by default. To learn more, see [Guest access in Teams](./guest-access.md).

> [!NOTE]
> 外部アクセスとゲスト アクセスの詳細ついては、[「Microsoft Teams の別の組織のユーザーと通信する」](communicate-with-users-from-other-organizations.md) を参照してください。

|確認事項|アクション |
|------------|-------|
|自分の組織のゲスト アクセスをオフにするか?|ゲスト アクセスのオンとオフを切り替えるには、「[Teams でゲスト アクセスをオンまたはオフにする](set-up-guests.md)」を参照してください。|
|有効にする場合、自分の組織でゲストが使用できる機能をカスタマイズするか?|ゲスト アクセス機能の有効/無効をカスタマイズする場合は、「[Teams のゲスト アクセスを許可する](teams-dependencies.md)」を参照してください。|

### <a name="private-channels"></a>プライベート チャネル

プライベート チャネルを使用すると、チーム メンバーのサブセットは、他のチーム メンバーが表示またはアクセスできないプライベート 空間で共同作業を行うことができます。 既にチームのメンバーである限り、ゲストを含む全てのユーザーをプライベート チャネルのメンバーとして追加できます。

|確認事項|アクション |
|------------|-------|
|チームの所有者とメンバーにプライベート チャネルの作成を許可するか?|組織のプライベート チャネル ポリシーを設定するには、「[Microsoft Teams でチャネル ポリシーを管理する](teams-policies.md)」を参照してください。|

### <a name="shared-channels"></a>共有チャネル

共有チャネルを使用すると、チームのメンバーではないユーザーをチャネルに追加できます。 これには、組織外のユーザーが含まれます。 共有チャネルは、組織外のユーザーがディレクトリのゲスト アカウントを必要としないという点で、ゲスト アクセスよりも利点があります。

|確認事項|アクション |
|------------|-------|
|共有チャネルとゲスト アクセスを使用する場合|「[Microsoft Teams の共有チャネル](shared-channels.md)」を参照してください。|
|<ul><li>チームの所有者に共有チャネルの作成を許可するか?</li><li>チーム所有者が組織外のユーザーとチャネルを共有できるか?</li><li>ユーザーが組織外の共有チャネルに参加することを許可するか?</li></ul> |<br>組織の共有チャネル ポリシーを設定するには、「[Microsoft Teams でチャネル ポリシーを管理する](teams-policies.md)」を参照してください。|

### <a name="teams-settings"></a>Teams の設定

Teams settings let you set up your teams for features such as email integration, cloud storage options, organization tab, meeting room device setup, and search scope. When you make changes to these settings, they apply to all the teams in your organization. To learn more, see [Teams settings](enable-features-office-365.md#teams-settings).

|確認事項|アクション |
|------------|-------|
|自分の組織に合わせて Teams の設定をカスタマイズするか? | Teams の設定とカスタマイズ方法の詳細は、「[Teams の設定](enable-features-office-365.md#teams-settings)」を参照してください。|

### <a name="teams-clients"></a>Teams のクライアント

Teams supports a number of clients from web to desktop to mobile, and the default configuration lets users choose whichever clients they want. To learn more, see [Get clients for Teams](get-clients.md).

|確認事項|アクション |
|------------|-------|
|自分の組織に合わせて Teams クライアントの利用可能性をカスタマイズするか?|「[Teams アプリのハードウェア要件](hardware-requirements-for-the-teams-app.md)」を確認してください。 |
|自分の組織に合わせて Teams クライアントの設定をカスタマイズするか?|詳細については、「[MSI を使用した Teams のインストール](msi-deployment.md)」を参照してください。|

### <a name="teams-usage-reporting"></a>Teams の使用状況レポート

The Global Admin, Teams Service Admin, and Reports Readers roles can view Teams usage reports. To learn more, see the [Microsoft 365 usage analytics](/microsoft-365/admin/usage-analytics/usage-analytics).

|確認事項|アクション |
|------------|-------|
|<br> 誰が Teams の使用状況レポートの確認を必要としていて、レポートを表示するための適切な役割が割り当てられているか? |<ul><li>そのユーザーが管理者でない場合は、[レポート閲覧者の役割を割り当てます](teams-activity-reports.md#reports-reader-role)。</li><li>Azure Active Directory で管理者の役割を割り当てる方法については、「[役割とアクセス許可](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)」および「[役割の表示と割り当て](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)」を参照してください。|

### <a name="teams-default-apps"></a>Teams の既定のアプリ

Teams provides a number of first-party (Microsoft provided) and third-party apps to engage users, support productivity, and integrate commonly used business services into Teams. Get apps from the Teams Store. Apps are turned on by default in Teams.

Teams でのアプリのロールアウトと管理の詳細については、 [アプリ管理](deploy-apps-microsoft-teams-landing-page.md) に関する詳細なガイダンスを参照してください。

## <a name="additional-deployment-decisions"></a>その他の展開に関する決定事項

次の設定は、組織のニーズと構成に基づいて変更できます。

### <a name="teams-licensing"></a>Teams のライセンス

Teams は多くの Microsoft 365 ライセンスの一部として提供されています。

|確認事項|アクション |
|------------|-------|
|展開しようとしている Teams のすべての機能を使用するために必要なライセンスをユーザーが所持しているか? | ライセンス要件の詳細については、「[Microsoft Teams サービスのサービスの説明](/office365/servicedescriptions/teams-service-description)」を参照してください。|

### <a name="exchange-and-sharepoint-interoperability"></a>Exchange と SharePoint の相互運用性

For the full Teams experience, every user should be enabled for Exchange, SharePoint, and Microsoft 365 group creation. The following articles outline information related to Exchange mailboxes hosted in various environments, how Exchange and Teams interact, and similar considerations for SharePoint and OneDrive.

|確認事項|アクション |
|------------|-------|
| 現在の Exchange および SharePoint の展開で Teams の必要な機能を展開できるか? |Teams での Exchange と SharePoint の詳細については、次を参照してください。<ul><li> [Exchange と Teams の連携](exchange-teams-interact.md)</li><li>[Teams との SharePoint Online と OneDrive の連携](sharepoint-onedrive-interact.md)|

### <a name="teams-limits-and-specifications"></a>Teams の制限と仕様

Teams のエンタープライズ展開を計画している場合は、1 つのチームの最大メンバー数やユーザーが作成可能なチーム数の上限など、関連する制限と仕様について考慮する必要があります。

|確認事項|アクション |
|------------|-------|
| Teams の展開でどのような制限が問題になる可能性があるか? | 詳細については、「[Teams の制限と仕様](limits-specifications-teams.md)」を参照してください。 |

### <a name="urls-and-ports"></a>URL とポート

Organizations that maintain fine-grained control of their internet traffic should read [URLs and IP address ranges](/office365/enterprise/urls-and-ip-address-ranges) for an up-to-date list of the URLs, IP addresses, ports, and protocols that must be correctly configured for Teams. Microsoft is continuously improving the Microsoft 365 services and adding new functionality, which means the required ports, URLs, and IP addresses may change over time. We recommend that you subscribe via RSS to receive notifications when this information is updated or changed. At a minimum, make sure you've opened the ports listed above in [Chat deployment prerequisites](#chat-deployment-prerequisites).

|確認事項|アクション |
|------------|-------|
| ユーザーが Teams を使用できるようにするためにインターネット アクセスのルールが必要か、それとも最低限必要なポートを開くだけで十分か? | 詳細については、「[URL と IP アドレス範囲](office-365-urls-ip-address-ranges.md)」を参照してください。|

### <a name="governance-naming-conventions-who-can-create-teams"></a>ガバナンス (命名規則、チームの作成が可能なユーザー)

Your organization might require that you implement controls on how teams are named and classified, who can create teams, and team expiration, retention, and archiving. This is called governance. You can use Azure Active Directory (Azure AD) to configure each of these areas.

| 確認事項 | アクション |
|--------------|--------|
|チームの作成が可能なユーザーに関する制御の実施が必要になるか?| 「[Teams でのガバナンスを計画する](plan-teams-governance.md)」を参照してください。|
|チームの命名に関する制御の実施が必要になるか?|「[Azure Active Directory での Microsoft 365 グループに対する名前付けポリシーの強制](/azure/active-directory/users-groups-roles/groups-naming-policy)」を参照してください。|

### <a name="teams-application-policy-side-rail-control"></a>Teams のアプリケーション ポリシー (サイドレール制御)

A pinned app shows up in the side rail in Teams. By creating Teams application policies, you can preconfigure sets of pinned Teams apps to personalize Teams for select groups of users. By default, the **Allow external apps in Microsoft Teams** setting is turned on.

| 確認事項 | アクション |
|--------------|--------|
|事前に構成した固定の Teams アプリケーションのセットを作成する必要があるか? | 「[Teams でのアプリの管理設定](admin-settings.md)」を参照してください。|
|該当するアプリのグループ化を受け取るグループの決定方法は?|「[Teams アプリのアクセス許可と考慮事項](app-permissions.md)」を参照してください。|

### <a name="archiving-and-compliance"></a>アーカイブとコンプライアンス

Your organization might require that you implement controls on how teams are archived and the types of data that are held in certain types of teams. Read [Overview of security and compliance in Teams](security-compliance-overview.md) to learn which Teams settings are turned on by default.

| 確認事項 | アクション |
|--------------|--------|
|チームの保持期間を構成する必要があるか?|保持ポリシーを設定する場合は、「[Teams の保持ポリシーを設定する](retention-policies.md)」を参照してください。|
|チームのアーカイブを構成する必要があるか?|チームをアーカイブまたは復元する場合は、「[チームのアーカイブまたは復元](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)」を参照してください。|
|追加のコンプライアンス設定を構成する必要があるか?|セキュリティとコンプライアンスの詳細については、「[Teams のセキュリティとコンプライアンスの概要](security-compliance-overview.md)」を参照してください。|

### <a name="conditional-access"></a>条件付きアクセス

Teams relies heavily on Exchange and SharePoint for core productivity scenarios, including meetings, calendars, interop chats, and file sharing. Conditional access policies that are set for these cloud apps apply to Teams when a user signs in directly to Teams, on any client. Conditional access policies that are set for the Teams cloud app control aspects such as whether users can access Teams services from certain networks.

| 確認事項 | アクション |
|--------------|--------|
|<br>Teams に対する条件付きアクセスを構成する必要があるか?|<ul><li>アクセス ポリシーのしくみについては、「[Teams で条件付きアクセス ポリシーはどのように機能しますか?](security-compliance-overview.md#how-conditional-access-policies-work-for-teams)」を参照してください。</li><li>Teams の多要素認証を設定する場合は、次を参照してください。<ul><li>[クイック スタート: Azure Active Directory の条件付きアクセスを使用して特定のアプリケーションに対して MFA を必要にする](/azure/active-directory/conditional-access/app-based-mfa)</li><li>[Azure Active Directory の条件付きアクセス設定に関するリファレンス](/azure/active-directory/conditional-access/technical-reference)</li></ul></ul>|

### <a name="education-edu"></a>教育機関 (EDU)

教育機関の業務に従事する IT 担当者は、教育機関向け Teams を利用できます。この Teams には、学生、教職員、および広範な業務に応じた教育機関に固有のシナリオに適合する多数の機能が備わっています。

| 確認事項 | アクション |
|--------------|--------|
|教育機関固有の Teams テンプレートを使用するか? |教育機関向け Teams の詳細については、「[Microsoft Education ガバナンスに関するよく寄せられる質問 (管理者向け)](plan-teams-governance-edu.md)」を参照してください。|
|範囲設定された検索を展開するか?|教育機関向け Teams をセットアップする場合は、「[クイックスタート: 教育機関向け Teams の管理](teams-quick-start-edu.yml)」を参照してください。|
|ユーザー アカウントのプロビジョニングのために Teams と学校データ同期サービスを統合するか?|[教育機関管理者向けの Teams のリソース](resources-teams-edu.md)|

### <a name="government---gcc-considerations"></a>政府機関: GCC に関する考慮事項

Office 365 for Government (GCC: Government Community Cloud) の使用は、米国連邦、州、地方、民族、または領土の政府機関など、政府の規制と要件の対象になるデータを扱う機関で Office 365 の展開を推進している IT 担当者の要件を満たすのに適しています。

| 確認事項 | アクション |
|--------------|--------|
| Office 365 for Government GCC – GCC 環境に Teams を展開する必要があるか? | 展開に関する考慮事項については、「[Office 365 for Government: GCC 展開の計画](plan-for-government-gcc.md)」を参照してください。|

## <a name="next-steps"></a>次のステップ

- チャット、チーム、チャネル、およびアプリの[導入を推進する](adopt-microsoft-teams-landing-page.md)。
- お勧めのアプリ (Planner など) を Teams の初期ロールアウトに組み込む。 [Teams の](deploy-apps-microsoft-teams-landing-page.md)導入を推進する際に、他の Teams アプリを追加します。
- [ミーティングと会議を展開する](deploy-meetings-microsoft-teams-landing-page.md)
- [クラウド ボイスを展開する](cloud-voice-landing-page.md)
