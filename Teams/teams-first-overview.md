---
title: 最初にMicrosoft Teamsする
author: LaszloSomi
ms.author: lsomi
manager: swerth
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: lsomi
localization_priority: Normal
search.appverid: MET150
description: このガイダンスを使用して、最初のMicrosoft TeamsワークロードとしてMicrosoft 365をOffice 365します。
ROBOTS: NOINDEX, NOFOLLOW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 81ecf9a0f963a1be577149c585424c140df2abd5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119356"
---
# <a name="roll-out-microsoft-teams-first"></a>最初にMicrosoft Teamsする

Microsoft Teams、特にリモートワークが世界中の従業員の現実である現在の前例のない時間に、従業員が互いにつながって共同作業を行うのに役立ちます。 チャット、ビデオ会議、グループ内のドキュメントOffice共同作業を行Teamsは、企業の生産性を維持するのに役立ちます。 小規模企業、非営利組織、または大規模な組織の場合でも、Microsoft 365 または Office 365 スイート内の最初のワークロードとして Teams を使い始めてから、他の Office アプリ またはサービスをデプロイできます。

この記事では、"Teams First" アプローチで行う必要がある考慮事項について説明します。

> [!IMPORTANT]
> 組織Teams初めてのクラウドデプロイ ワークロードになる可能性がある一方で、Teamsデプロイは、全体的なクラウド デプロイ戦略の一部である必要があります。

他の Microsoft 365 または Office 365 サービスを既にロールアウト済みで、Teams が (1 つ目ではなく) ロールアウトする次のワークロードである場合は、「Teams をロールアウトする方法」を[参照](./deploy-overview.md)してください。

## <a name="start-here"></a>開始するには

Teams 最初のデプロイを開始するには、少なくともいくつかの前提条件を満たす必要があります。 次の一覧は、有効にする前に組織に必要Teams示しています。

1.  ドメイン名Microsoft 365構成Office 365組織または組織

2.  Azure Active Directory接続 (AAD 接続) または同様のクラウド ID 同期ソリューション - 必要なすべての属性がテナントと同期されている  
    AAD 同期と同期される属性を理解するには、「Azure AD Connect 同期: 同期された属性[」をAzure Active Directory](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)

3.  アカウントに割り当てられている適切なユーザー ライセンスTeams  
    ライセンスの詳細Teamsについては、サービスのMicrosoft Teams[を参照してください](/office365/servicedescriptions/teams-service-description)。

4.  組織のネットワークを使用Teams  
    ネットワークの準備については、「組織のネットワークを準備する」を参照[Teams。](prepare-network.md)

5.  Exchange または Office 365: Exchange、Sharepoint、OneDrive for Business Microsoft 365 へのネットワーク アクセスを許可する: Office 365 [URL と IP](/office365/enterprise/urls-and-ip-address-ranges)アドレス範囲。

> [!NOTE]
> 2019 年 9 月 1 日より後に作成されたテナントは、Teamsモードでプロビジョニングされます。
> 
> [!IMPORTANT]
> デプロイがSkype for Business Server、2019 年 9 月 1 日より後にテナントがプロビジョニングされた場合は、Teams の共存機能を有効にするには、サポートにお問い合わせください。 ユーザーにライセンスを割り当てる前に、"組織全体のアップグレード<span class="underline">ポリシー"</span>が "島モード" に設定Teams確認してください。

## <a name="migration-starting-points"></a>移行の開始点

Microsoft 365 Teams Office 365 の開始点とオンプレミスの Skype for Business サーバーまたは Lync サーバーの存在に応じて、Teams で使用できる Skype for Business または Skype for Business と機能の使用を開始します。 次のセクションでは、上記の前提条件に加えて、基本的な機能と構成オプションについて詳しく説明します。 開始点のシナリオを次のトピックに分けしました。

**テナントTeams構成**: テナントモードとユーザー モードを使用して、受信者の動作を制御します。 これらの設定は、組織のテナント レベルまたはユーザー レベルで割り当てることができます。 詳細については、 との共存に関[する記事をSkype for Business。](coexistence-chat-calls-presence.md)

**チャット/外部通信 Teams:** チャット サービスは、組織内または組織外のチャット会話をピアツーピアまたはグループ化します。 外部通信は、フェデレーションとも呼Skype for Business。

**Teams** で会議を作成して表示する: ユーザーは常に Outlook Teams アドインを使用してオンライン会議を作成できます。PSTN ダイヤルインは、ユーザーのライセンスを取得すると、すべてのシナリオで利用できます。 Teams、Skype for Businessの予定表情報をユーザーのメールボックスに保存Exchangeします。 Teams Exchange Server クライアントがユーザーのメールボックスと対話するには、オンプレミスの Exchange サーバーが 2016 CU3 以上の 2016 CU3 以上である必要があります。 メールボックスExchangeアクセスできない場合、Teams の予定表アイコンは表示されません。ユーザーは、Teams クライアントで会議を表示、作成、または変更することはできません。

**通話機能 VoIP/PSTN Teams:** 通話は、Voice over IP (VoIP) または Public Switched Telephone Network (PSTN) です。 VoIP 接続は、ユーザーが外部Teamsダイヤルするときに PSTN 接続が発生する一方で、クライアント間でネイティブに行います。  

Teams 2 種類の PSTN 接続をサポートしています。 Microsoft 通話プラン(Microsoft がユーザーの電話番号を含むテレフォニー インフラストラクチャを提供する場合)、またはダイレクト ルーティング構成。この場合、顧客は Teams ユーザーのセッション ボーダー コントローラー (SBC) を使用してテレフォニー接続を提供します。  
詳細については、「どの通話プランが最適か[」](calling-plan-landing-page.md)を参照し、「ダイレクト[ルーティング電話システムを参照してください](direct-routing-landing-page.md)。

**Teamsと** チャネルのコラボレーション : Teams: Teams では、チームは、仕事、プロジェクト、または共通の関心を持つユーザーのグループです。 Teamsは、チャネルで作成されます。 各チャネルは、"チーム イベント" や部署名などのトピックを中心に構築され、楽しみたい場合に利用できます。 チャネルは、会議を開催し、会話を行い、ファイルをまとめて作業する場所です。 コラボレーション中

**OneDrive for Business (P2P** ファイル共有) in Teams : Teams とチャネルの外部では、Teams ユーザーは、一般的な OneDrive を使用するか、Citrix Files、DropBox、Box、Google ドライブ などの他の P2P 共有ファイル プログラムを使用して、ファイルをピアツーピアで共有できます。 一OneDriveの場合、ユーザーにはオンライン ライセンスSharePointが割り当てられている必要があります。

**アプリケーション プラットフォーム**: アプリは、組織が最新のツールを提供し、より多くの機能をTeams。 このアプリは、Microsoft が提供する、サードパーティがまたは組織の開発者が開発したタブ、メッセージング拡張機能、コネクタ、ボットの機能を組み合わせたものです。

**セキュリティと** コンプライアンスの機能: Teams には、保持ポリシー、データ損失防止 (DLP)、電子情報開示、チャネル、チャット、ファイルの法的ホールド、監査ログ検索など、コンプライアンス領域に役立つさまざまな情報があります。 詳細については、「セキュリティとコンプライアンス[」を](security-compliance-overview.md)参照Microsoft Teams。  

> [!NOTE]
> Advance eDiscovery の機能には、E5 ライセンスが必要です。

[ライセンス オプションを比較します](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)。

シナリオ[でExchange機能をMicrosoft Teams方法](exchange-teams-interact.md)と対話方法に関するページを参照してください。

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a>Skype for Business **<span class="underline"></span>** または Lync Server を使用しない組織

この開始点は、組織が現在 Skype for Business または Lync Server を利用していないと想定し、Teams が Microsoft 365 または Office 365 で初めてのアプリケーションになります。 次の表では、コア サービスのサービスを使用する場合のTeamsの構成とエンド ユーザーの機能について説明します。

<table>
<thead>
<tr class="header">
<th>アイテム</th>
<th>備考</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>テナントTeams構成</td>
<td>Teamsモードのみ、すべてのチャット機能と通話機能はTeamsされます。</td>
</tr>
<tr class="even">
<td>チャット/外部通信 (Teams</td>
<td><p>内部 (組織Microsoft 365またはOffice 365) および外部チャットによる通信が可能Teams。</p>
<p><em>注: DNS エントリは、外部アクセス用に構成する必要があります。 Skype for BusinessLync および Skype for Business 環境とのフェデレーションを許可するには、オンプレミスまたは Microsoft 365 または Office 365 に Skype for Business がない場合でも、DNS レコードがSkype for Businessされます。<br />
<a href="/office365/enterprise/external-domain-name-system-records">外部ドメイン ネーム システム レコード</a></em></p></td>
</tr>
<tr class="odd">
<td>[会議] を作成して表示Teams</td>
<td><p>アドインを使用して、内部および外部Outlook作成できます。</p>
<p>PSTN ダイヤルインとダイヤルアウト機能は、電話会議ライセンスで利用できます。</p>
<p>Teamsアクセスするには、Exchange ハイブリッドが確立されたオンプレミスの Exchange 2016 CU3+ が必要です。ハイブリッド構成ウィザードを使用してハイブリッドデプロイを作成します<a href="/exchange/hybrid-deployment/deploy-hybrid">。</a> </p>
<p>ハイブリッド構成に加Exchange、OAuth 認証Exchangeを確立します。組織と組織の間で <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help"> OAuth 認証Exchange構成Exchange Onlineします。</p>

</p></td>
</tr>
<tr class="even">
<td>通話機能<br />
VoIP/PSTN (Teams</td>
<td><p>テナントに対する内部および外部の VoIP を使用できます。</p>
<p>PSTN サービスは、Microsoft 通話プランMicrosoft 電話直接ルーティングを追加して構成できます。</p></td>
</tr>
<tr class="odd">
<td>TeamsでのチャネルとチャネルのコラボレーションTeams</td>
<td><p>コンプライアンス機能を含む完全なエクスペリエンスを得SharePoint Online ライセンスをユーザーに割り当てる必要があります。</p>
<p>既存のオンプレミス サイトとサイトSharePoint移行する必要はありません。</p></td>
</tr>
<tr class="even">
<td>OneDrive for Business (P2P ファイル共有)</td>
<td>OneDrive for Businessユーザーにオンライン ライセンスが割り当てられているSharePoint必要があります。 このライセンスを使用しない場合、ピアツーピア ファイル共有は実行できない。</td>
</tr>
<tr class="odd">
<td>アプリケーション プラットフォーム</td>
<td>ユーザーは、会社のポリシーに従って、ユーザーが使用できるアプリを使用できます。<br />
詳細については、「アプリの<a href="/microsoftteams/admin-settings">管理者設定」を参照Teams</a></td>
</tr>
<tr class="even">
<td>セキュリティとコンプライアンスの機能</td>
<td><ul>
<li><p>アイテム保持ポリシーを使用できます。</p></li>
<li><p>チャネル メッセージに対するコンプライアンスに関する電子情報開示と法的ホールドがサポートされています。</p></li>
<li><p>データ損失防止ポリシー (DLP) を使用できます。</p></li>
</ul>
<p>完全な機能セットは、Exchange Online。Exchangeオンプレミスでは、これらの機能のほとんどがサポートされています。 完全な一覧については<a href="/MicrosoftTeams/exchange-teams-interact">、「How Exchange and Teams interact 」を参照してください</a>。</p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a>ユーザーまたは Lync Server を使用しない組織Skype for Businessの有効化手順

1.  前の「ここから開始する」セクションで詳しく説明されている前提条件を満たす

2.  テナントを [Teamsのみ] モードに切り替えます (既存のテナントのみ): 共存とアップグレードの[設定を設定します](setting-your-coexistence-and-upgrade-settings.md)。

3.  会社のビジネス/会社のポリシーに従ってテナントを構成する: 組織の Microsoft Teams[設定を管理します](enable-features-office-365.md)。

4.  ユーザーにTeamsクライアントをデプロイする:[ユーザーのクライアントを取得Teams](get-clients.md)

5.  導入プログラムを推進する  
    [Microsoft Teams を導入する](adopt-microsoft-teams-landing-page.md)
    
    [Microsoft Teams の導入クイック スタートのチェックリスト](teams-adoption-quick-start-checklist.md)

6.  他のワークロードの移行を計画して、Microsoft 365またはOffice 365

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a>Skype for Business **<span class="underline">または</span>** Lync サーバーを使用している組織

この開始点は、組織がオンプレミスの Skype for Business 2019 または 2015+ または Lync 2013+ サーバーを使用すると想定しています。 オンプレミス サーバーからオンプレミス サーバーに移行する組織に関する広範なガイダンスTeams、これらのシナリオに従う必要があります。 このガイダンスは、ユーザーがTeamsで使用する最初のアプリケーションであるシナリオMicrosoft 365固有Office 365。 次の表では、コア サービスのサービスを使用する場合のTeamsの構成とエンド ユーザーの機能について説明します。

<table>
<thead>
<tr class="header">
<th>アイテム</th>
<th>備考</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>テナントTeams構成</td>
<td>[Islands mode]を選択します。</td>
</tr>
<tr class="even">
<td>チャット/外部通信 (Teams</td>
<td>独自のテナント内でのみ内部的に、外部通信 (フェデレーション) は、Skype for Businessまたは Lync サーバーの展開を介して行います。</td>
</tr>
<tr class="odd">
<td>[会議] を作成して表示Teams</td>
<td><p>アドインを使用して、内部および外部Outlook作成できます。</p>
<p>PSTN ダイヤルインとダイヤルアウト機能は、電話会議ライセンスで利用できます。</p>
<p>Teamsアクセスするには、Exchangeハイブリッドが確立されたオンプレミスの 2016 CU3+ Exchange必要があります。<br />
<a href="/exchange/hybrid-deployment/deploy-hybrid">ハイブリッド構成ウィザードを使用してハイブリッド デプロイを作成します。</a></p>
<p>管理者は、Teams 会議ポリシーの PreferredMeetingProviderForIslandsMode 属性<a href="/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps">set-csteamsmeetingpolicy</a>を使用して、Skype for Business Outlook アドインを制御できます。</p> 
</td>
</tr>
<tr class="even">
<td>通話機能<br />
VoIP/PSTN (Teams</td>
<td><p>テナントに対して内部的に VoIP を使用できます。</p>
<p>PSTN サービスまたは通話プラン サービスは、ユーザーが [のみ] エクスペリエンスに移動Teams使用できません。</p></td>
</tr>
<tr class="odd">
<td>TeamsでのチャネルとチャネルのコラボレーションTeams</td>
<td><p>コンプライアンス機能を含む完全なエクスペリエンスを得SharePoint Online ライセンスをユーザーに割り当てる必要があります。</p>
<p>既存のオンプレミス サイトとサイトSharePoint移行する必要はありません。</p></td>
</tr>
<tr class="even">
<td>OneDrive for Business (P2P ファイル共有)</td>
<td>OneDrive for Businessユーザーにオンライン ライセンスが割り当てられているSharePoint必要があります。 このライセンスを使用しない場合、ピアごとのファイル共有は実行できない。</td>
</tr>
<tr class="odd">
<td>アプリケーション プラットフォーム</td>
<td>ユーザーは、会社のポリシーに従って、ユーザーが使用できるアプリを使用できます。<br />
詳細については、「アプリの<a href="/microsoftteams/admin-settings">管理者設定」を参照Teams</a></td>
</tr>
<tr class="even">
<td>セキュリティとコンプライアンスの機能</td>
<td><ul>
<li><p>アイテム保持ポリシーを使用できます。</p></li>
<li><p>チャネル メッセージに対するコンプライアンスに関する電子情報開示と法的ホールドがサポートされています。</p></li>
<li><p>データ損失防止ポリシー (DLP) を使用できます。</p></li>
</ul>
<p>完全な機能セットは、Exchange Online。Exchangeオンプレミスでは、これらの機能のほとんどがサポートされています。 完全な一覧については、「<a href="/MicrosoftTeams/exchange-teams-interact">操作と対話のExchange方法Teams参照してください。</a></p>
<ul>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a>組織の有効化手順は、Skype for Business Server  

1.  前の「ここから開始」セクションで詳しく説明されている前提条件を満たします。

2.  テナントを諸島モードに切り替える (2019 年 9 月 1 日より後にプロビジョニングされたテナントの場合は、この変更を行うサポートにお問い合わせください)  
    [共存およびアップグレードを設定する](setting-your-coexistence-and-upgrade-settings.md)

3.  会社のビジネス/会社のポリシーに従ってテナントを構成する  
    [組織のMicrosoft Teams の設定を管理する](enable-features-office-365.md)

4.  クライアントをTeamsする  
    [Teams のクライアントを取得する](get-clients.md)

5.   導入プログラムを推進する  
    [Microsoft Teams を導入する](adopt-microsoft-teams-landing-page.md)<br/>
    [Microsoft Teams の導入クイック スタートのチェックリスト](teams-adoption-quick-start-checklist.md)

6.  他のワークロードの移行を計画して、Microsoft 365またはOffice 365

7.  ハイブリッドSkype for Business確立し、Lync サーバーと Lync サーバーに推奨されるSkype for Businessパスに従います。  
    [Skype for Business オンプレミスから Teams にアップグレードする](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a>閉じるステートメント

Microsoft Teams、すべての従業員、情報ワーカー、および Frontline ワーカーを 1 つのプラットフォームにまとめる、組織の有効化者になる場合があります。 今すぐ [開始](https://products.office.com/microsoft-teams/group-chat-software) できます。 最新のお知らせや毎月の製品更新プログラムについては、こちら から連絡 [を取り合います](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)。

また、世界中の企業が現在の COVID-19 の状況を管理する中で、Teams を組織で最大限に活用するのに役立つ一連のコンテンツを作成しました。

  - [COVID-19 のお客様](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)への取り組み

  - [2 週間: リモート作業について学習した情報](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [オンライン会議とイベントの配信](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [Teams により中小規模企業でのリモート作業をサポートする](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [ライブ イベントのデジタル変換: フロントラインからの Bob Bejan の観察](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [Microsoft IT が社員のリモート作業を実現した 9 つの方法](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)

  - [リモートで作業し、セキュリティを確保する —CISOS のヒント](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [教師と学生がリモート学習に切り替えるのを支援する](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [ユーザーとリモートで作業しながら生産性をMicrosoft Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a>サポート サービス リファレンス

Teamsは、Exchange Online、SharePoint Online、OneDrive for Business、Microsoft 365 グループに依存して、ユーザーに完全に統合された Microsoft 365 または Office 365 エクスペリエンスを提供します。 上で説明したように、Teamsサービスを完全にデプロイせずに機能します。機能は限られています。 詳細については、Teams の前提条件に関するページを参照してください。「 へようこそ[」をTeams。](teams-overview.md)

上記の各サービスの詳細については、次のリンク先を参照してください。

  - Exchange Onlineは、予定表機能を使用し、ピアツーピア メッセージを Teams。 詳細については、「操作の方法[とExchange」をTeamsしてください。](exchange-teams-interact.md)

> [!IMPORTANT]
> Teams Exchange との相互運用を行う場合は、「Exchange 組織と Exchange Online 組織の間で OAuth 認証を構成する」の説明に従って、新しい Exchange OAuth 認証プロトコルを構成[する必要があります](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)。

  - SharePointチャネルでのファイル共有に使用し、/OneDrive for Business は 1:1 またはグループ チャットでのファイル共有に使用されます。 詳細については、「How [SharePoint Online and OneDrive for Business interact with Microsoft Teams 」を参照してください](sharepoint-onedrive-interact.md)。

  - [Microsoft 365グループは](office-365-groups.md)、チームとチャネルの作成/管理に使用されます。


## <a name="related-topics"></a>関連トピック

[Microsoft Teams IT アーキテクチャとテレフォニー ソリューション ポスター](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[Skype for Business Server と Office 365 の間のハイブリッド接続を計画する](/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[アプリケーションを使用してリモート ワーカーをTeams](support-remote-work-with-teams.md)

[ユーザーとリモートでMicrosoft 365](https://aka.ms/remote-work)