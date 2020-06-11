---
title: Microsoft Teams を最初にロールアウトする
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
description: Microsoft Teams を最初の Microsoft 365 または Office 365 のワークロードとして展開するには、このガイダンスを使用します。
ROBOTS: NOINDEX, NOFOLLOW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 84408fdb6d58e755d0eb4c775d1954f22791264c
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691003"
---
# <a name="roll-out-microsoft-teams-first"></a>Microsoft Teams を最初にロールアウトする

Microsoft Teams を使用すると、従業員が世界中の従業員の現実である、現在のかつてない時間帯に、相互に接続して共同作業を行うことができます。 チーム内でチャットしたり、ビデオ会議を行ったり、Office ドキュメントの共同作業を行ったりすると、会社の生産性を維持できます。 小規模ビジネス、非営利団体、大企業向けのいずれの場合も、他の Office アプリやサービスを展開する前に、Microsoft 365 または Office 365 スイートの最初のワークロードとして Teams を使用することができます。

この記事では、"Teams First" アプローチで行う必要がある考慮事項について説明します。

> [!IMPORTANT]
> Teams は組織の最初のクラウドに展開されますが、チームの展開は、クラウド展開戦略全体の一部にする必要があります。

他の Microsoft 365 または Office 365 サービスを既にロールアウトしている場合に、(最初ではなく) 次のワークロードがロールアウトされるようになった場合は、[チームをロールアウトする方法](How-to-roll-out-teams.md)から開始します。

## <a name="start-here"></a>開始するには

チームの最初の展開を始めるには、少なくともいくつかの前提条件を満たしている必要があります。 次のリストは、Teams を有効にする前に、組織に必要な場所を示しています。

1.  ドメイン名で構成された Microsoft 365 または Office 365 の組織

2.  Azure Active Directory connectivity (AAD connect) または同様のクラウド id 同期ソリューション–テナントに同期される必須属性がすべて含まれています。  
    AAD 同期と同期される属性について理解するには、「 [AZURE AD Connect sync: 属性が Azure Active Directory に同期](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)されている」を参照してください。

3.  Teams に割り当てられている適切なユーザーライセンス  
    Teams のライセンスについて理解するには、「 [Microsoft Teams サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)」を参照してください。

4.  Teams 用に準備された組織のネットワーク  
    ネットワークの準備について理解するには、「 [Teams 用に組織のネットワークを準備](prepare-network.md)する」を参照してください。

5.  Microsoft 365 または Office 365 で、Exchange、Sharepoint、OneDrive for Business へのネットワークアクセスを許可する: [office 365 url と IP アドレス範囲](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)。

> [!NOTE]
> 2019年9月1日以降に作成されたテナントは、Teams 専用モードでプロビジョニングされます。
> 
> [!IMPORTANT]
> Skype for Business Server を展開していて、テナントが2019年9月1日以降にプロビジョニングされている場合は、サポートに連絡して、Teams の共存機能を有効にしてください。 Teams のライセンスをユーザーに割り当てる<span class="underline">前に</span>、"組織全体のアップグレードポリシー" が "アイランドモード" に設定されていることを確認してください。

## <a name="migration-starting-points"></a>移行開始ポイント

出発点と、オンプレミスの Skype for Business または Lync server の存在に応じて、Teams で利用可能な Microsoft 365 または Office 365 および機能への旅。 以下のセクションでは、上記の前提条件に加え、基本的な機能と構成オプションについて説明します。 出発点のシナリオは、次のトピックに分類されています。

**テナントチームの構成**: テナントとユーザーモードは、受信者の動作を制御するために使用されます。 これらの設定は、テナントレベルまたは組織内のユーザーレベルで割り当てることができます。 詳細については、「 [Skype For business を使用した共存](coexistence-chat-calls-presence.md)」を参照してください。

**Teams でのチャット/外部通信**: チャットサービスは、組織内外でのピアツーピアまたはグループチャットの会話を指します。 外部通信は、Skype for Business のフェデレーションとも呼ばれます。

**Teams で会議を作成して表示**する: ユーザーがライセンスを取得した後は、常に Outlook Teams アドインと PSTN ダイヤルインを使ってオンライン会議を作成できます。 チームと Skype for Business ストアの予定表の情報をユーザーの Exchange メールボックスに保存します。 チームクライアントがユーザーのメールボックスを操作できるようにするには、オンプレミスの Exchange server が Exchange Server 2016 CU3 以降で以上である必要があります。 Exchange メールボックスにアクセスできない場合、Teams の予定表アイコンは表示されず、ユーザーは Teams クライアントで会議の表示、作成、または変更を行うことはできません。

**Teams での通話機能 VoIP/PSTN**: 通話は、ボイスオーバー IP (VoIP) または公衆交換電話網 (PSTN) になります。 VoIP 接続は Teams クライアント間でネイティブに実行されますが、ユーザーが外部の電話番号にダイヤルすると、PSTN 接続が発生します。  

Teams は、2種類の PSTN 接続をサポートしています。 Microsoft が、ユーザーの電話番号などのテレフォニーインフラストラクチャを提供している場合、または直接ルーティング構成である場合は、microsoft の通話プランを利用できます。これは、顧客がチームユーザーのセッションボーダーコントローラー (SBC) 経由でテレフォニー接続を提供する場合です。  
詳細については、「[通話プランが適切かどうか](calling-plan-landing-page.md)を確認する」および「[電話システムのダイレクトルーティング](direct-routing-landing-page.md)」を参照してください。

**Teams でのチームとチャネルの共同作業**: teams では、teams は、仕事、プロジェクト、または一般的な関心事のためにまとめられたユーザーのグループです。 チームはチャネルで構成されています。 各チャネルは、"チームイベント"、"部署名" などのトピック、または楽しいもので構成されています。 チャネルでは、会議を開催したり、会話をしたり、ファイルを共同編集したりすることができます。 共同作業中

**Teams での onedrive For business (P2P ファイル共有)**: チームとチャネルの外部では、チームユーザーは、OneDrive for business または Citrix のファイル、DropBox、Box、Google ドライブなどの P2P 共有ファイルプログラムを使用して、ピアツーピアファイルを共有できます。 OneDrive for business の場合、ユーザーには SharePoint Online ライセンスが割り当てられている必要があります。

**アプリケーションプラットフォーム**: アプリでは、チームを最大限に活用できるように、組織のための既定のツールを提供しています。 このアプリは、Microsoft が提供する、サードパーティがまたは組織の開発者が開発したタブ、メッセージング拡張機能、コネクタ、ボットの機能を組み合わせたものです。

**セキュリティとコンプライアンスの機能:** Teams には、アイテム保持ポリシー、データ損失防止 (DLP)、チャネル、チャット、ファイルの電子情報開示と法的保持、監査ログの検索など、コンプライアンスの領域に役立つさまざまな情報が用意されています。 詳細については、「 [Microsoft Teams でセキュリティとコンプライアンス](security-compliance-overview.md)を確認する」を参照してください。  

> [!NOTE]
> アドバンス eDiscovery 機能には E5 ライセンスが必要です。

[ライセンスのオプションを比較](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)します。

お客様のシナリオで使用できるコンプライアンス機能については、「 [Exchange と Microsoft Teams の相互作用](exchange-teams-interact.md)」を参照してください。

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a>Skype for Business または Lync server を使用して**<span class="underline">いない</span>** 組織

この出発点は、現在、組織が Skype for Business または Lync server を使用していないことを前提としており、Teams は Microsoft 365 または Office 365 の最初のアプリケーションとなります。 次の表では、コアサービスの Teams の高レベルの構成とエンドユーザー向け機能について詳しく説明します。

<table>
<thead>
<tr class="header">
<th>項目</th>
<th>メモ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>テナントチームの構成</td>
<td>Teams 専用モード、すべてのチャット機能と通話機能が Teams のみに含まれている</td>
</tr>
<tr class="even">
<td>Teams でのチャット/外部通信</td>
<td><p>Internal (Microsoft 365 または Office 365 組織内) と Teams からの外部チャット通信</p>
<p><em>注: DNS エントリは、外部アクセス用に構成されている必要があります。 Skype for Business DNS レコードが必要なのは、Skype for business がオンプレミスではなく、または Microsoft 365 または Office 365 を使用していない場合でも、Lync と Skype for business の環境とのフェデレーションを許可することです。<br />
<a href="https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records">外部ドメイン名システムレコード</a></em></p></td>
</tr>
<tr class="odd">
<td><em>Teams で会議を作成して表示する</em></td>
<td><p><em>Outlook アドインを使用して会議を作成できる</em></p>
<p><em>PSTN ダイヤルインとダイヤルアウト機能は、電話会議ライセンスで利用できます。<br />
注: チームの予定表にアクセスするには、exchange ハイブリッドが確立された Exchange 2016 CU3 以降で + オンプレミスの展開が必要:<a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">ハイブリッド構成ウィザードを使用したハイブリッド展開の作成</a><br />
Exchange ハイブリッド構成に加えて、exchange OAuth 認証を確立する: <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help">exchange と Exchange Online 組織の間の oauth 認証を構成</a>する</em></p></td>
</tr>
<tr class="even">
<td>通話機能<br />
Teams での VoIP/PSTN</td>
<td><p>テナントの内部および外部の VoIP が利用可能</p>
<p>PSTN サービスは、Microsoft 電話システムを使って構成できます。さらに、Microsoft 通話プランまたは直接ルーティングを追加することもできます。</p></td>
</tr>
<tr class="odd">
<td>Teams でのチームとチャネルのコラボレーション</td>
<td><p>コンプライアンス機能などの完全なエクスペリエンスを実現するには、SharePoint Online ライセンスをユーザーに割り当てる必要があります。</p>
<p>既存のオンプレミスの SharePoint サイトの移行は必須ではありません。</p></td>
</tr>
<tr class="even">
<td>OneDrive for Business (P2P ファイル共有)</td>
<td>OneDrive for Business では、ユーザーに SharePoint Online ライセンスが割り当てられている必要があります。 このライセンスがない場合、ピアツーピアファイル共有はできません。</td>
</tr>
<tr class="odd">
<td>アプリケーションプラットフォーム</td>
<td>ユーザーは会社のポリシーに従って、利用可能なアプリを使用できるようになります。<br />
詳細情報: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Teams のアプリの管理設定</a></td>
</tr>
<tr class="even">
<td>セキュリティとコンプライアンスの機能</td>
<td><ul>
<li><p>アイテム保持ポリシーを使用できます</p></li>
<li><p>チャネルメッセージのコンプライアンスのための電子情報開示と法的保持はサポートされています</p></li>
<li><p>データ損失防止ポリシー (DLP) を使用できます。</p></li>
</ul>
<p>Exchange Online で利用できるフル機能セット exchange オンプレミスでは、これらの機能のほとんどがサポートされています。「Exchange とチームが全リストを<a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">操作する方法</a>」を参照してください。</p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a>Skype for Business または Lync Server を使用していない組織向けの有効化手順

1.  上の [ここから始めてください] セクションで前提条件を満たす

2.  テナントを Teams 専用モード (既存のテナントのみ) に切り替える:[共存とアップグレードの設定を設定](setting-your-coexistence-and-upgrade-settings.md)します。

3.  会社のビジネス/会社のポリシーに従ってテナントを構成する:[組織の Microsoft Teams の設定を管理](enable-features-office-365.md)します。

4.  チームクライアントをユーザーに展開する:[チームのクライアントを取得](get-clients.md)する

5.  導入プログラムを推進する  
    [Microsoft Teams を導入する](adopt-microsoft-teams-landing-page.md)
    
    [Microsoft Teams の導入クイック スタートのチェックリスト](teams-adoption-quick-start-checklist.md)

6.  他のワークロードの Microsoft 365 または Office 365 への移行を計画する

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a>Skype for Business または Lync server**<span class="underline">を使用している</span>** 組織

この出発点は、組織が Skype for Business 2019 または 2015 + または Lync 2013 + server をオンプレミスで利用していることを前提としています。 オンプレミスのサーバーから Teams に移行する組織向けの広範なガイダンスは、これらのシナリオについて説明されています。 このガイダンスは、Teams が Microsoft 365 または Office 365 で使用する最初のアプリケーションであるシナリオに固有のものです。 次の表では、コアサービスの Teams の高レベルの構成とエンドユーザー向け機能について詳しく説明します。

<table>
<thead>
<tr class="header">
<th>項目</th>
<th>メモ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>テナントチームの構成</td>
<td>アイランド モード</td>
</tr>
<tr class="even">
<td>Teams でのチャット/外部通信</td>
<td>自分のテナント内でのみ内部で利用できる外部通信 (フェデレーション) は、Skype for Business または Lync server の展開を通じて行われます。</td>
</tr>
<tr class="odd">
<td>Teams で会議を作成して表示する</td>
<td><p>Outlook アドインを使用して会議を作成できる</p>
<p>PSTN ダイヤルインとダイヤルアウト機能は、電話会議ライセンスで利用できます。<br />
チームの予定表へのアクセスには、exchange 2016 CU3 以降で + オンプレミスの展開が必要です。 Exchange ハイブリッドが確立されています。<br />
<a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">ハイブリッド構成ウィザードを使ってハイブリッド展開を作成する</a></p></td>
</tr>
<tr class="even">
<td>通話機能<br />
Teams での VoIP/PSTN</td>
<td><p>テナントの内部の VoIP が利用可能</p>
<p>PSTN または通話プランサービスは、ユーザーが Teams のみに移行されるまでは利用できません。</p></td>
</tr>
<tr class="odd">
<td>Teams でのチームとチャネルのコラボレーション</td>
<td><p>コンプライアンス機能などの完全なエクスペリエンスを実現するには、SharePoint Online ライセンスをユーザーに割り当てる必要があります。</p>
<p>既存のオンプレミスの SharePoint サイトの移行は必須ではありません。</p></td>
</tr>
<tr class="even">
<td>OneDrive for Business (P2P ファイル共有)</td>
<td>OneDrive for Business では、ユーザーに SharePoint Online ライセンスが割り当てられている必要があります。 このライセンスがないと、ピア間でのファイル共有はできません。</td>
</tr>
<tr class="odd">
<td>アプリケーションプラットフォーム</td>
<td>ユーザーは会社のポリシーに従って、利用可能なアプリを使用できるようになります。<br />
詳細情報: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Teams のアプリの管理設定</a></td>
</tr>
<tr class="even">
<td>セキュリティとコンプライアンスの機能</td>
<td><ul>
<li><p>アイテム保持ポリシーを使用できます</p></li>
<li><p>チャネルメッセージのコンプライアンスのための電子情報開示と法的保持はサポートされています</p></li>
<li><p>データ損失防止ポリシー (DLP) を使用できます。</p></li>
</ul>
<p>Exchange Online で利用できるすべての機能セット、Exchange オンプレミスは、次の機能をサポートしています。</p>
<p><a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">Exchange と Teams の連携</a></p>
<ul>
<li><p>すべてのリストの場合</p></li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a>Skype for Business Server を使用する組織向けの有効化手順  

1.  上の [ここから始めてください] セクションで、前提条件を満たしているかをご説明します。

2.  テナントを諸島モードに切り替える (9/1/2019 の後にプロビジョニングされたテナントの場合は、この変更を行うためにサポートに連絡してください)  
    [共存およびアップグレードを設定する](setting-your-coexistence-and-upgrade-settings.md)

3.  会社のビジネス/会社のポリシーに従ってテナントを構成する  
    [組織のMicrosoft Teams の設定を管理する](enable-features-office-365.md)

4.  Teams クライアントを展開する  
    [Teams のクライアントを取得する](get-clients.md)

5.   導入プログラムを推進する  
    [Microsoft Teams を導入する](adopt-microsoft-teams-landing-page.md)<br/>
    [Microsoft Teams の導入クイック スタートのチェックリスト](teams-adoption-quick-start-checklist.md)

6.  他のワークロードの Microsoft 365 または Office 365 への移行を計画する

7.  Skype for business ハイブリッドを確立し、Skype for Business および Lync サーバーの推奨されるアップグレードパスに従います。  
    [Skype for Business オンプレミスから Teams にアップグレードする](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a>終了明細書

Microsoft Teams は、組織が1つのプラットフォームですべての従業員、インフォメーションワーカー、および Firstline worker をまとめるためのイネーブラーとして使用することができます。 今すぐ[作業](https://products.office.com/microsoft-teams/group-chat-software)を始めることができます。 最新のお知らせと毎月の製品更新プログラムについては、[こちら](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)をご覧ください。

さらに、世界中の会社が現在の COVID-19 の状況を管理しているため、チームを活用して組織への影響を最大限に高めるために役立つ一連のコンテンツが作成されました。

  - [COVID-19 でのお客様への確約](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)

  - [2週間以内: リモート作業について学習しました](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [オンライン会議とイベントの配信](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [Teams により中小規模企業でのリモート作業をサポートする](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [ライブイベントのデジタル変換: ボブが frontline からの1月の所見](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [Microsoft IT が社員のリモート作業を実現した 9 つの方法](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)

  - [リモートで作業する、セキュリティを維持する、CISOs のヒント](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [教師と学生がリモートラーニングに切り替えることができるように支援する](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [Microsoft Teams を使用してリモートで作業しながら生産性を維持する](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a>サポートサービスリファレンス

チームは Exchange Online、SharePoint Online、OneDrive for Business、Microsoft 365 グループを利用して、完全に統合された Microsoft 365 または Office 365 エクスペリエンスをユーザーに提供します。 上で説明したように、チームは、機能が制限されている場合に、これらのサービスを完全に展開することなく機能します。 チームとその前提条件の詳細については、「 [teams へようこそ](teams-overview.md)」を参照してください。

上記の各サービスの詳細については、以下のリンクを参照してください。

  - Exchange Online は、予定表機能に使用され、Teams でピア to ピアメッセージを保存します。 詳細については、「 [Exchange とチームの相互作用](exchange-teams-interact.md)」を参照してください。

> [!IMPORTANT]
> オンプレミスの Exchange との Teams の相互運用機能については、「 [exchange と Exchange Online の間の oauth 認証の構成](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)」の説明に従って、新しい Exchange OAuth 認証プロトコルを構成する必要があります。

  - SharePoint はチャネルでのファイル共有に使用されますが、OneDrive for Business は1:1 またはグループチャットでのファイル共有に使用されます。 詳細については、「 [SharePoint Online と OneDrive For business が Microsoft Teams とどのように連携するか](sharepoint-onedrive-interact.md)」を参照してください。

  - [Microsoft 365 グループ](office-365-groups.md)は、チームとチャネルの作成/管理に使用されます。


## <a name="related-topics"></a>関連項目

[Microsoft Teams IT アーキテクチャとテレフォニー ソリューション ポスター](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[Skype for Business Server と Office 365 の間のハイブリッド接続を計画する](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[Teams を使用したリモートワーカーのサポート](support-remote-work-with-teams.md)

[Microsoft 365 でリモートで作業する](https://aka.ms/remote-work)
