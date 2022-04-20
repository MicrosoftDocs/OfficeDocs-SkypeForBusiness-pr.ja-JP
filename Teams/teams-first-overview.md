---
title: 最初にMicrosoft Teamsロールアウトする
author: LaszloSomi
ms.author: lsomi
manager: swerth
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: lsomi
ms.localizationpriority: medium
search.appverid: MET150
description: このガイダンスを使用して、最初のMicrosoft 365またはOffice 365ワークロードとしてMicrosoft Teamsをロールアウトします。
ROBOTS: NOINDEX, NOFOLLOW
appliesto:
- Microsoft Teams
ms.openlocfilehash: f6dba57003aaa58b9d0b72e7e866da261bed578e
ms.sourcegitcommit: 1d990582e2deb5f55ba9adada3e17377f792a141
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2022
ms.locfileid: "64922688"
---
# <a name="roll-out-microsoft-teams-first"></a>最初にMicrosoft Teamsロールアウトする

Microsoft Teamsは、特にリモートワークが世界中の従業員の現実である現在の前例のない時期に、従業員のつながりを維持し、相互に共同作業するのに役立ちます。 Teams内のOfficeドキュメントでチャット、ビデオ会議、共同作業を行うことができると、企業は生産性を維持できます。 小規模ビジネス、非営利団体、大規模な組織のいずれであっても、他のOffice アプリやサービスをデプロイする前に、Microsoft 365またはOffice 365 スイート内の最初のワークロードとしてTeamsを開始できます。

この記事では、"Teams First" アプローチで行う必要がある考慮事項について詳しく説明します。

> [!IMPORTANT]
> Teamsは、組織初のクラウドデプロイ ワークロードにすることができますが、Teamsのデプロイは、全体的なクラウドデプロイ戦略の一部である必要があります。

他のMicrosoft 365またはOffice 365サービスを既にロールアウトしていて、Teamsが次にロールアウトするワークロードである場合は (最初のワークロードではなく) 、[Teamsをロールアウトする方法](./deploy-overview.md)から始めます。

## <a name="start-here"></a>開始するには

Teams最初のデプロイを開始するには、少なくともいくつかの前提条件を満たす必要があります。 次の一覧では、Teamsを有効にする前に組織に対して何を行う必要があるかを示します。

1.  ドメイン名で構成されたMicrosoft 365またはOffice 365組織

2.  Azure Active Directory接続 (AAD接続) または同様のクラウド ID 同期ソリューション - 必要なすべての属性をテナントと同期する  
    AAD同期と同期される属性を理解するには、「[Azure AD Connect同期: Azure Active Directoryに同期された属性」を](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)参照してください。

3.  Teamsに割り当てられた適切なユーザー ライセンス  
    Teamsライセンスについて理解するには、[Microsoft Teamsサービスの説明](/office365/servicedescriptions/teams-service-description)を参照してください。

4.  Teams用に準備された組織のネットワーク  
    ネットワークの準備については、「[組織のネットワークをTeamsに準備する」を参照してください](prepare-network.md)。

5.  Microsoft 365またはOffice 365のExchange、SharePoint、OneDrive for Businessへのネットワーク アクセスを許可します。[URL と IP アドレス範囲をOffice 365します](/office365/enterprise/urls-and-ip-address-ranges)。

> [!NOTE]
> 2019 年 9 月 1 日以降に作成されたテナントは、Teamsのみモードでプロビジョニングされます。
> 
> [!IMPORTANT]
> Skype for Business Serverデプロイ済みで、テナントが 2019 年 9 月 1 日以降にプロビジョニングされた場合は、サポートに問い合わせて、Teamsの共存機能を有効にしてください。 Teams ライセンスをユーザーに割り当てる<span class="underline">前に</span>、"組織全体のアップグレード ポリシー" が "アイランド モード" に設定されていることを確認してください。

## <a name="migration-starting-points"></a>移行の開始点

開始点とオンプレミス Skype for Businessまたは Lync サーバーの存在に応じて、Teamsで利用できるMicrosoft 365またはOffice 365と機能への移行。 以降のセクションでは、上記の前提条件に加えて、基本的な機能と構成オプションについて詳しく説明します。 開始点のシナリオを次のトピックに分解しました。

**テナントTeams構成**: テナントモードとユーザー モードは、受信者の動作を制御するために使用されます。 これらの設定は、テナント レベルまたは組織内のユーザー レベルで割り当てることができます。 詳細については、「[Skype for Businessとの共存](coexistence-chat-calls-presence.md)」を参照してください。

**Teamsでのチャット/外部通信**: チャット サービスは、組織内および組織内または組織の外部でピアツーピアまたはグループチャットの会話を参照します。 外部通信は、Skype for Businessではフェデレーションとも呼ばれます。

**Teamsで会議を作成して表示** する: ユーザーは、Outlook Teams アドインを使用してオンライン会議を作成できます。PSTN ダイヤルインは、ユーザーがライセンスを取得すると、すべてのシナリオで使用できます。 TeamsとSkype for Businessは、予定表情報をユーザーのExchangeメールボックスに格納します。 オンプレミス Exchange サーバーは、Teams クライアントがユーザーのメールボックスと対話できるようにするには、2016 CU3 以降をExchange Serverする必要があります。 Exchangeメールボックスにアクセスしないと、Teamsの予定表アイコンが表示されず、ユーザーはTeams クライアントで会議を表示、作成、変更できなくなります。

**Teamsでの VoIP/PSTN 機能の呼び出し**: 通話は、Voice over IP (VoIP) または公衆交換電話網 (PSTN) にすることができます。 VoIP 接続は、Teams クライアント間でネイティブに行われますが、PSTN 接続は、ユーザーが外部の電話番号にダイヤルしたときに発生します。  

Teamsは、2 種類の PSTN 接続をサポートします。 Microsoft 通話プラン。Microsoft がユーザーの電話番号を含むテレフォニー インフラストラクチャを提供する場合、またはダイレクト ルーティング構成を提供する場合、顧客は、Teams ユーザーに対してセッション ボーダー コントローラー (SBC) 経由のテレフォニー接続を提供します。  
詳細については、「[どの通話プランが適していますか?](calling-plan-landing-page.md)」と[「ダイレクト ルーティング電話システム](direct-routing-landing-page.md)」を参照してください。

**TeamsでのTeamsとチャネルのコラボレーション**: Teamsでは、チームは、仕事、プロジェクト、または共通の関心事のためにまとめられた人々のグループです。 Teamsはチャネルで構成されます。 各チャネルは、"チーム イベント" などのトピック、部署名、または単に楽しみのために構築されます。 チャネルは、会議を開催し、会話を行い、ファイルをまとめて作業する場所です。 コラボレーション中

**TeamsのOneDrive for Business (P2P ファイル共有)**: Teamsとチャネルの外部では、Teams ユーザーは、ビジネス向けのOneDriveまたは Citrix Files、DropBox、Box、Google ドライブなどの他の P2P 共有ファイル プログラムを使用して、ファイルをピアツーピアで共有できます。 ビジネス向けのOneDriveでは、ユーザーに SharePoint Online ライセンスが割り当てられている必要があります。

**アプリケーション プラットフォーム**: アプリは、組織がTeamsを最大限に活用するためのすぐに使えるツールを提供します。 このアプリは、Microsoft が提供する、サードパーティがまたは組織の開発者が開発したタブ、メッセージング拡張機能、コネクタ、ボットの機能を組み合わせたものです。

**セキュリティとコンプライアンス機能:** Teamsには、アイテム保持ポリシー、データ損失防止 (DLP)、チャネル、チャット、ファイルの電子情報開示と訴訟ホールド、監査ログ検索など、コンプライアンス領域に役立つさまざまな情報があります。 詳細については、[Microsoft Teamsのセキュリティとコンプライアンスに関するページを参照](security-compliance-overview.md)してください。  

> [!NOTE]
> 高度な電子情報開示機能には、E5 ライセンスが必要です。

[ライセンス オプションを比較します](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)。

シナリオで使用できるコンプライアンス機能については、[ExchangeとMicrosoft Teamsの対話方法](exchange-teams-interact.md)に関するページを参照してください。

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a>Skype for Businessまたは Lync Server **<span class="underline">のない</span>** 組織

この開始点は、組織が現在Skype for Businessまたは Lync Server を利用せず、TeamsがMicrosoft 365またはOffice 365の最初のアプリケーションであることを前提としています。 次の表では、コア サービスのTeamsに対する高レベルの構成とエンド ユーザーの機能について詳しく説明します。

<table>
<thead>
<tr class="header">
<th>アイテム</th>
<th>メモ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>テナントTeams構成</td>
<td>Teamsのみモードで、すべてのチャット機能と通話機能はTeamsのみになります。</td>
</tr>
<tr class="even">
<td>Teamsでのチャット/外部コミュニケーション</td>
<td><p>Teamsから可能な内部 (Microsoft 365内またはOffice 365組織内) と外部チャット通信。</p>
<p><em>注: 外部アクセス用に DNS エントリを構成する必要があります。 オンプレミス、Microsoft 365、Office 365にSkype for Businessがない場合でも、Lync およびSkype for Business環境とのフェデレーションを許可するには、Skype for Business DNS レコードが必要です。<br />
<a href="/office365/enterprise/external-domain-name-system-records">外部ドメイン ネーム システム レコード</a></em></p></td>
</tr>
<tr class="odd">
<td>Teamsで会議を作成して表示する</td>
<td><p>Outlook アドインを使用して内部および外部の会議を作成できます。</p>
<p>PSTN ダイヤルイン機能とダイヤルアウト機能は、電話会議ライセンスで使用できます。</p>
<p>予定表へのアクセスTeams、ハイブリッドが確立されたExchangeで展開された 2016 CU3 以降のオンプレミスExchange必要があります。<a href="/exchange/hybrid-deployment/deploy-hybrid">ハイブリッド構成ウィザードを使用してハイブリッド展開を作成します。</a> </p>

ハイブリッド構成をExchangeするだけでなく、Exchange OAuth 認証を確立します。[ExchangeとExchange Online組織の間で OAuth 認証を構成します](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)。 

</p></td>
</tr>
<tr class="even">
<td>機能の呼び出し<br />
Teamsの VoIP/PSTN</td>
<td><p>テナントに対して内部的および外部的に VoIP を使用できます。</p>
<p>PSTN サービスは、Microsoft 電話 システムを使用して構成できるほか、Microsoft 通話プランまたはダイレクト ルーティングを追加することもできます。</p></td>
</tr>
<tr class="odd">
<td>TeamsでのTeamsとチャネルのコラボレーション</td>
<td><p>コンプライアンス機能を含む完全なエクスペリエンスを実現するには、SharePoint Online ライセンスをユーザーに割り当てる必要があります。</p>
<p>既存のオンプレミス SharePoint サイトの移行は必要ありません。</p></td>
</tr>
<tr class="even">
<td>OneDrive for Business (P2P ファイル共有)</td>
<td>OneDrive for Businessでは、ユーザーにSharePoint Online ライセンスを割り当てる必要があります。 このライセンスがない場合、ピアツーピア ファイル共有は不可能です。</td>
</tr>
<tr class="odd">
<td>アプリケーション プラットフォーム</td>
<td>ユーザーは、会社のポリシーに従って、指定されたアプリを使用できます。<br />
詳細情報: <a href="/microsoftteams/admin-settings">Teamsのアプリの管理者設定</a></td>
</tr>
<tr class="even">
<td>セキュリティとコンプライアンスの機能</td>
<td><ul>
<li><p>アイテム保持ポリシーを使用できます。</p></li>
<li><p>チャネル メッセージのコンプライアンスに関する電子情報開示と訴訟ホールドがサポートされています。</p></li>
<li><p>データ損失防止ポリシー (DLP) を使用できます。</p></li>
</ul>
<p>Exchange Onlineで使用できる完全な機能セット。Exchangeオンプレミスでは、これらの機能のほとんどをサポートしています。 完全な一覧については、「<a href="/MicrosoftTeams/exchange-teams-interact">ExchangeとTeamsの対話方法</a>」を参照してください。</p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a>Skype for Businessまたは Lync Server のない組織の有効化手順

1.  上記の「ここから始める」セクションで詳しく説明されている前提条件を満たす

2.  テナントをTeamsのみモードに切り替えます (既存のテナントの場合のみ): [共存とアップグレードの設定を設定します](setting-your-coexistence-and-upgrade-settings.md)。

3.  会社のビジネス/会社のポリシーに従ってテナントを構成する:[組織のMicrosoft Teams設定を管理](enable-features-office-365.md)します。

4.  Teams クライアントをユーザーに展開する: [Teamsのクライアントを取得する](get-clients.md)

5.  導入プログラムを推進する  
    [Microsoft Teams を導入する](adopt-microsoft-teams-landing-page.md)
    
    [Microsoft Teams の導入クイック スタートのチェックリスト](teams-adoption-quick-start-checklist.md)

6.  他のワークロードをMicrosoft 365またはOffice 365に移行する計画を開始する

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a>Skype for Businessまたは Lync サーバー **<span class="underline">を持つ</span>** 組織

この開始点は、組織がオンプレミスで 2019 または 2015 以降または Lync 2013+ サーバー Skype for Business利用することを前提としています。 オンプレミス サーバーからTeamsに移行する組織に関する広範なガイダンスが既に用意されており、これらのシナリオに従う必要があります。 このガイダンスは、TeamsがMicrosoft 365またはOffice 365で使用する最初のアプリケーションであるシナリオに固有です。 次の表では、コア サービスのTeamsに対する高レベルの構成とエンド ユーザーの機能について詳しく説明します。

<table>
<thead>
<tr class="header">
<th>アイテム</th>
<th>メモ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>テナントTeams構成</td>
<td>アイランド モード。</td>
</tr>
<tr class="even">
<td>Teamsでのチャット/外部コミュニケーション</td>
<td>独自のテナント内でのみ内部で、外部通信 (フェデレーション) は、Skype for Businessまたは Lync サーバーの展開を介して行われます。</td>
</tr>
<tr class="odd">
<td>Teamsで会議を作成して表示する</td>
<td><p>Outlook アドインを使用して内部および外部の会議を作成できます。</p>
<p>PSTN ダイヤルイン機能とダイヤルアウト機能は、電話会議ライセンスで使用できます。</p>
<p>予定表へのアクセスTeams、Exchangeハイブリッドが確立された 2016 CU3 以降のオンプレミスExchange必要があります。<br />
<a href="/exchange/hybrid-deployment/deploy-hybrid">ハイブリッド構成ウィザードを使用してハイブリッド展開を作成します。</a></p>
<p>管理者は、Teams会議ポリシーの PreferredMeetingProviderForIslandsMode 属性 (<a href="/powershell/module/skype/set-csteamsmeetingpolicy">set-csteamsmeetingpolicy</a>) を使用して、Skype for Business Outlook アドインを制御できます。</p> 
</td>
</tr>
<tr class="even">
<td>機能の呼び出し<br />
Teamsの VoIP/PSTN</td>
<td><p>テナントに対して内部的に VoIP を使用できます。</p>
<p>PSTN サービスまたは通話プラン サービスは、ユーザーが Teams Only エクスペリエンスに移動するまで使用できません。</p></td>
</tr>
<tr class="odd">
<td>TeamsでのTeamsとチャネルのコラボレーション</td>
<td><p>コンプライアンス機能を含む完全なエクスペリエンスを実現するには、SharePoint Online ライセンスをユーザーに割り当てる必要があります。</p>
<p>既存のオンプレミス SharePoint サイトの移行は必要ありません。</p></td>
</tr>
<tr class="even">
<td>OneDrive for Business (P2P ファイル共有)</td>
<td>OneDrive for Businessでは、ユーザーにSharePoint Online ライセンスを割り当てる必要があります。 このライセンスを使用しない場合、ファイル共有は不可能です。</td>
</tr>
<tr class="odd">
<td>アプリケーション プラットフォーム</td>
<td>ユーザーは、会社のポリシーに従って、指定されたアプリを使用できます。<br />
詳細情報: <a href="/microsoftteams/admin-settings">Teamsのアプリの管理者設定</a></td>
</tr>
<tr class="even">
<td>セキュリティとコンプライアンスの機能</td>
<td><ul>
<li><p>アイテム保持ポリシーを使用できます。</p></li>
<li><p>チャネル メッセージのコンプライアンスに関する電子情報開示と訴訟ホールドがサポートされています。</p></li>
<li><p>データ損失防止ポリシー (DLP) を使用できます。</p></li>
</ul>
<p>Exchange Onlineで使用できる完全な機能セット。Exchangeオンプレミスでは、これらの機能のほとんどをサポートしています。 完全な一覧については、「<a href="/MicrosoftTeams/exchange-teams-interact">ExchangeとTeamsの対話方法</a>」を参照してください。</p>
<ul>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a>Skype for Business Serverを使用する組織の有効化手順  

1.  上記の「ここから始める」セクションで詳しく説明されている前提条件を確認してください。

2.  テナントをアイランド モードに切り替える (2019 年 9 月 1 日以降にプロビジョニングされたテナントの場合は、この変更を行うにはサポートにお問い合わせください)  
    [共存およびアップグレードを設定する](setting-your-coexistence-and-upgrade-settings.md)

3.  会社のビジネス/会社のポリシーに従ってテナントを構成する  
    [組織のMicrosoft Teams の設定を管理する](enable-features-office-365.md)

4.  Teams クライアントをデプロイする  
    [Teams のクライアントを取得する](get-clients.md)

5.   導入プログラムを推進する  
    [Microsoft Teams を導入する](adopt-microsoft-teams-landing-page.md)<br/>
    [Microsoft Teams の導入クイック スタートのチェックリスト](teams-adoption-quick-start-checklist.md)

6.  他のワークロードをMicrosoft 365またはOffice 365に移行する計画を開始する

7.  ハイブリッドSkype for Business確立し、Skype for Business サーバーと Lync サーバーに推奨されるアップグレード パスに従う  
    [Skype for Business オンプレミスから Teams にアップグレードする](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a>Closing ステートメント

Microsoft Teamsは、組織がすべての従業員、インフォメーション ワーカー、フロントライン ワーカーを 1 つのプラットフォームにまとめるための有効な機能です。 今すぐ [作業を開始](https://products.office.com/microsoft-teams/group-chat-software) できます。 最新のお知らせと毎月の製品の更新については、こちらから連絡を取り合 [うことができます](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)。

さらに、世界中の企業が現在の COVID-19 の状況を管理しているため、組織の最大の影響のためにTeamsを利用するのに役立つ一連のコンテンツを作成しました。

  - [COVID-19 での顧客へのコミットメント](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)

  - [2 週間後: リモート作業について学習したこと](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [オンライン会議とイベントの配信](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [Teams により中小規模企業でのリモート作業をサポートする](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [ライブ イベントのデジタル変換: フロントラインからの Bob Bejan の観察](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [Microsoft IT が社員のリモート作業を実現した 9 つの方法](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)

  - [リモートで作業し、セキュリティを確保する -CISO のヒント](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [教師と学生がリモート ラーニングに切り替えるのを支援する](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [Microsoft Teamsを使用してリモートで作業しながら生産性を維持する](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a>サポート サービスリファレンス

Teamsは、Exchange Online、SharePoint Online、OneDrive for Business、Microsoft 365 グループに依存して、ユーザーに完全に統合されたMicrosoft 365またはOffice 365エクスペリエンス。 前述のように、Teamsはこれらのサービスを完全にデプロイせずに機能します。機能は限られています。 Teamsとその前提条件の詳細については、「[Teamsへようこそ](teams-overview.md)。

上記の各サービスの詳細については、次のリンクに従ってください。

  - Exchange Onlineは、予定表機能とピア ツー ピア メッセージをTeamsに格納するために使用されます。 詳細については、「[ExchangeとTeamsの対話方法」を](exchange-teams-interact.md)参照してください

> [!IMPORTANT]
> Exchangeオンプレミスとの相互運用をTeamsするには、「ExchangeとExchange Online組織の間で OAuth 認証を構成する」の説明に従って、新しい[Exchange OAuth 認証プロトコルを構成](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)する必要があります。

  - SharePointはチャネルでのファイル共有に使用され、/OneDrive for Businessは 1:1 またはグループ チャットでのファイル共有に使用されます。 詳細については、「[オンラインとOneDrive for Business SharePoint Microsoft Teamsとの対話方法](sharepoint-onedrive-interact.md)」を参照してください。

  - [Microsoft 365 グループ](office-365-groups.md)は、チームとチャネルの作成/管理に使用されます。


## <a name="related-topics"></a>関連項目

[Microsoft Teams IT アーキテクチャとテレフォニー ソリューション ポスター](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[Skype for Business Server と Office 365 の間のハイブリッド接続を計画する](/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[Teamsを使用してリモート ワーカーをサポートする](support-remote-work-with-teams.md)

[Microsoft 365を使用してリモートで作業する](https://aka.ms/remote-work)
