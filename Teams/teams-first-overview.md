---
title: Microsoft Teams を最初に展開する
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
description: このガイダンスを使用して、Microsoft Teams を最初の Microsoft 365 または 365 ワークロードOffice展開します。
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
# <a name="roll-out-microsoft-teams-first"></a>Microsoft Teams を最初に展開する

Microsoft Teams は、特にリモートワークが世界中の従業員の現実である現在の例のない時間に、従業員が互いにつながって共同作業を行うのを支援します。 Teams 内でチャット、ビデオ会議、共同作業を行Officeは、企業の生産性を維持するのに役立ちます。 小規模企業、非営利団体、または大規模な組織の場合は、Microsoft 365 または Office 365 スイートの最初の作業負荷として Teams を使い始めてから、他の Office アプリまたはサービスを展開できます。

この記事では、"Teams First" アプローチで行う必要がある考慮事項について詳しい説明します。

> [!IMPORTANT]
> Teams は組織初のクラウド展開ワークロードになりますが、Teams の展開は全体的なクラウド展開戦略の一部である必要があります。

既に他の Microsoft 365 または Office 365 サービスをロールアウト済みで、Teams が (最初のサービスではなく) 展開する次の作業負荷である場合は [、Teams](./deploy-overview.md)を展開する方法から開始します。

## <a name="start-here"></a>開始するには

Teams First 展開を開始するには、少なくともいくつかの前提条件を満たす必要があります。 次の一覧は、Teams を有効にする前に組織に必要な設定を示しています。

1.  Microsoft 365 または Office 365 組織がドメイン名で構成されている

2.  Azure Active Directory 接続 (AAD 接続) または同様のクラウド ID 同期ソリューション – すべての必須属性がテナントと同期されている  
    AAD 同期と同期された属性を理解するには、「Azure AD Connect 同期: Azure Active Directory に同期された [属性」を参照してください。](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)

3.  Teams に割り当てられている適切なユーザー ライセンス  
    Teams のライセンスについて理解するには [、Microsoft Teams サービスの説明を参照してください](/office365/servicedescriptions/teams-service-description)。

4.  Teams 用に準備された組織のネットワーク  
    ネットワークの準備について理解するには、「組織のネットワーク [を Teams 用に準備する」を参照してください](prepare-network.md)。

5.  Microsoft 365 または Office 365: Office [365 の URL](/office365/enterprise/urls-and-ip-address-ranges)と IP アドレス範囲で、Exchange、Sharepoint、OneDrive for Business へのネットワーク アクセスを許可します。

> [!NOTE]
> 2019 年 9 月 1 日より後に作成されたテナントは、Teams のみモードでプロビジョニングされます。
> 
> [!IMPORTANT]
> Skype for Business Server を展開し、2019 年 9 月 1 日より後にテナントがプロビジョニングされた場合は、Teams の共存機能を有効にするには、サポートにお問い合わせください。 Teams ライセンスをユーザーに割り当てる前に、"組織全体のアップグレード <span class="underline">ポリシー"</span> が "島モード" に設定されている必要があります。

## <a name="migration-starting-points"></a>移行の開始点

Microsoft 365 または Office 365 への旅と Teams で利用できる機能は、開始点とオンプレミスの Skype for Business または Lync サーバーの存在に応じて異なる。 以下のセクションでは、上記の前提条件に加えて、基本的な機能と構成オプションについて詳しく説明します。 開始点のシナリオを次のトピックに分解しました。

**Tenant Teams 構成**: テナント モードとユーザー モードを使用して、受信者の動作を制御します。 これらの設定は、テナント レベルまたは組織内のユーザー レベルで割り当てることができます。 詳細については [、「Skype for Business との共存」を参照してください](coexistence-chat-calls-presence.md)。

**Teams でのチャット/外部** 通信: チャット サービスは、組織内および組織内外のピアツーピアまたはグループ チャットの会話を参照します。 外部通信は、Skype for Business ではフェデレーションとも呼ばれます。

**Teams での** 会議の作成と表示: ユーザーは Outlook Teams アドインを使用してオンライン会議をいつでも作成できます。PSTN ダイヤルインは、ユーザーのライセンスが取得された後、すべてのシナリオで利用できます。 Teams と Skype for Business では、予定表情報がユーザーの Exchange メールボックスに保存されます。 Teams クライアントがユーザー Exchange Server操作するには、オンプレミスの Exchange サーバーが 2016 CU3 以上である必要があります。 Exchange メールボックスにアクセスしない場合、Teams の予定表アイコンは表示されません。ユーザーは Teams クライアントで会議を表示、作成、または変更することはできません。

**Teams での通話機能 VoIP/PSTN: 通話** には、音声オーバー IP (VoIP) または公衆交換電話網 (PSTN) を使用できます。 VoIP 接続は Teams クライアント間でネイティブで行い、PSTN 接続はユーザーが外部の電話番号をダイヤルするときに発生します。  

Teams では、2 種類の PSTN 接続がサポートされています。 Microsoft 通話プラン。Microsoft がユーザーの電話番号を含むテレフォニー インフラストラクチャ、または直接ルーティング構成を提供する場合、顧客は Teams ユーザーのセッション ボーダー コントローラー (SBC) を使用してテレフォニー接続を提供します。  
詳細については、「最適な [通話プラン](calling-plan-landing-page.md) 」と「電話システムダイレクト ルーティング」 [を参照してください](direct-routing-landing-page.md)。

**Teams でのチームとチャネル** の共同作業: Teams では、チームは、作業、プロジェクト、共通の関心のためにまとめるユーザーのグループです。 チームはチャネルで作り上げされています。 各チャネルは、"チーム イベント"、部門名、または単に楽しみのために、トピックを中心に構築されています。 チャネルは、会議を開催し、会話を行い、ファイルで一緒に作業する場所です。 共同作業中

Teams での **OneDrive for Business (P2P** ファイル共有) : Teams およびチャネルの外部では、Teams ユーザーは OneDrive for Business または Citrix Files、DropBox、Box、Google Drive などの他の P2P 共有ファイル プログラムを使用して、ピアツーピアでファイルを共有できます。 OneDrive for Business の場合、ユーザーには SharePoint Online ライセンスが割り当てられている必要があります。

**アプリケーション プラットフォーム**: アプリは、組織が Teams をより多く利用するための、組み込みツールを提供します。 このアプリは、Microsoft が提供する、サードパーティがまたは組織の開発者が開発したタブ、メッセージング拡張機能、コネクタ、ボットの機能を組み合わせたものです。

**セキュリティとコンプライアンスの機能:** Teams には、アイテム保持ポリシー、データ損失防止 (DLP)、電子情報開示、チャネル、チャットとファイルの法的保留、監査ログの検索など、コンプライアンス領域に役立つさまざまな情報があります。 詳細については [、「Microsoft Teams のセキュリティとコンプライアンス」を参照してください](security-compliance-overview.md)。  

> [!NOTE]
> Advance eDiscovery の機能を使用するには、E5 ライセンスが必要です。

[ライセンス オプションを比較します](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)。

Exchange [と Microsoft Teams が対話して](exchange-teams-interact.md) 、シナリオで使用できるコンプライアンス機能を確認する方法について説明します。

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a>Skype **<span class="underline"></span>** for Business または Lync Server がない組織

この開始点は、組織が現在 Skype for Business または Lync Server を利用していないと仮定し、Teams が Microsoft 365 または Office 365 の最初のアプリケーションになります。 次の表では、主要サービス用の Teams の高レベルの構成とエンド ユーザーの機能について説明します。

<table>
<thead>
<tr class="header">
<th>アイテム</th>
<th>備考</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>テナント Teams の構成</td>
<td>Teams のみモード、すべてのチャット機能と通話機能は Teams のみになります。</td>
</tr>
<tr class="even">
<td>Teams でのチャット/外部コミュニケーション</td>
<td><p>Teams から内部 (Microsoft 365 または Office 365 組織内) および外部チャット通信が可能。</p>
<p><em>注: DNS エントリは、外部アクセス用に構成する必要があります。 Lync および Skype for Business 環境とのフェデレーションを許可するには、Skype for Business をオンプレミスまたは Microsoft 365 または Office 365 にインストールしていなくても、Skype for Business DNS レコードが必要です。<br />
<a href="/office365/enterprise/external-domain-name-system-records">外部ドメイン ネーム システム レコード</a></em></p></td>
</tr>
<tr class="odd">
<td>Teams で会議を作成して表示する</td>
<td><p>Outlook アドインを使用して、内部会議と外部会議を作成できます。</p>
<p>PSTN ダイヤルインとダイヤルアウト機能は、電話会議ライセンスで利用できます。</p>
<p>Teams の予定表へのアクセスには、Exchange ハイブリッドが確立された Exchange 2016 CU3+ オンプレミスが必要です。ハイブリッド構成ウィザードを使用してハイブリッド展開 <a href="/exchange/hybrid-deployment/deploy-hybrid">を作成します。</a> </p>
<p>Exchange ハイブリッド構成に加えて、Exchange OAuth 認証を確立します。Exchange と Exchange Online 組織の間で <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help"> OAuth 認証を構成します。"</p>

</p></td>
</tr>
<tr class="even">
<td>通話機能<br />
Teams の VoIP /PSTN</td>
<td><p>テナントの内部および外部の VoIP を使用できます。</p>
<p>PSTN サービスは、Microsoft 電話システムを介して構成したり、Microsoft 通話プランまたは直接ルーティングを追加したりして構成できます。</p></td>
</tr>
<tr class="odd">
<td>Teams でのチームとチャネルの共同作業</td>
<td><p>コンプライアンス機能を含む完全なエクスペリエンスを得る場合は、SharePoint Online ライセンスをユーザーに割り当てる必要があります。</p>
<p>既存のオンプレミスの SharePoint サイトを移行する必要はありません。</p></td>
</tr>
<tr class="even">
<td>OneDrive for Business (P2P ファイル共有)</td>
<td>OneDrive for Business では、ユーザーに SharePoint Online ライセンスが割り当てられている必要があります。 このライセンスがない場合、ピアツーピアのファイル共有は行えなされます。</td>
</tr>
<tr class="odd">
<td>アプリケーション プラットフォーム</td>
<td>ユーザーは、会社のポリシーに従って、ユーザーが使用できるアプリを使用できます。<br />
詳細については、以下を参照してください: <a href="/microsoftteams/admin-settings">Teams のアプリの管理者設定</a></td>
</tr>
<tr class="even">
<td>セキュリティとコンプライアンスの機能</td>
<td><ul>
<li><p>アイテム保持ポリシーを使用できます。</p></li>
<li><p>チャネル メッセージのコンプライアンスに関する電子情報開示と法的ホールドがサポートされています。</p></li>
<li><p>データ損失防止ポリシー (DLP) を使用できます。</p></li>
</ul>
<p>Exchange Online で利用できる完全な機能セットExchange オンプレミスでは、これらのほとんどの機能がサポートされています。 完全な一覧については、「Exchange と Teams の <a href="/MicrosoftTeams/exchange-teams-interact">対話方法」を参照してください</a>。</p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a>Skype for Business または Lync Server を使用しない組織の有効化手順

1.  上の 「ここから開始」セクションで詳しく説明されている前提条件を満たす

2.  テナントを Teams のみモードに切り替える (既存のテナントの場合のみ):共存と [アップグレードの設定を設定します](setting-your-coexistence-and-upgrade-settings.md)。

3.  会社のビジネス/会社のポリシーに従ってテナントを構成する: 組織の [Microsoft Teams 設定を管理します](enable-features-office-365.md)。

4.  Teams クライアントをユーザーに展開する: [Teams のクライアントを取得する](get-clients.md)

5.  導入プログラムを推進する  
    [Microsoft Teams を導入する](adopt-microsoft-teams-landing-page.md)
    
    [Microsoft Teams の導入クイック スタートのチェックリスト](teams-adoption-quick-start-checklist.md)

6.  他のワークロードを Microsoft 365 または 365 Officeする計画を開始する

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a>Skype **<span class="underline"></span>** for Business または Lync サーバーを使用している組織

この開始点は、組織が Skype for Business 2019 または 2015+ または Lync 2013+ サーバーをオンプレミスで使用すると想定しています。 オンプレミス サーバーから Teams に移行する組織に関する広範なガイダンスが既に存在し、これらのシナリオに従う必要があります。 このガイダンスは、Teams が Microsoft 365 または Office 365 で使用する最初のアプリケーションであるシナリオに固有です。 次の表では、主要サービス用の Teams の高レベルの構成とエンド ユーザーの機能について説明します。

<table>
<thead>
<tr class="header">
<th>アイテム</th>
<th>備考</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>テナント Teams の構成</td>
<td>諸島モード。</td>
</tr>
<tr class="even">
<td>Teams でのチャット/外部コミュニケーション</td>
<td>自分のテナント内でのみ内部的に、外部通信 (フェデレーション) は Skype for Business または Lync サーバーの展開を介して行います。</td>
</tr>
<tr class="odd">
<td>Teams で会議を作成して表示する</td>
<td><p>Outlook アドインを使用して、内部会議と外部会議を作成できます。</p>
<p>PSTN ダイヤルインとダイヤルアウト機能は、電話会議ライセンスで利用できます。</p>
<p>Teams の予定表へのアクセスには、Exchange ハイブリッドが確立された Exchange 2016 CU3+ オンプレミスが必要です。<br />
<a href="/exchange/hybrid-deployment/deploy-hybrid">ハイブリッド構成ウィザードを使用してハイブリッド展開を作成します。</a></p>
<p>管理者は、Teams 会議ポリシーの PreferredMeetingProviderForIslandsMode 属性<a href="/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps"> (set-csteamsmeetingpolicy)</a>を使用して Skype for Business Outlook アドインを制御できます。</p> 
</td>
</tr>
<tr class="even">
<td>通話機能<br />
Teams の VoIP /PSTN</td>
<td><p>テナント内部での VoIP を使用できます。</p>
<p>PSTN または通話プランのサービスは、ユーザーが Teams 専用のエクスペリエンスに移動されるまで利用できません。</p></td>
</tr>
<tr class="odd">
<td>Teams でのチームとチャネルの共同作業</td>
<td><p>コンプライアンス機能を含む完全なエクスペリエンスを得る場合は、SharePoint Online ライセンスをユーザーに割り当てる必要があります。</p>
<p>既存のオンプレミスの SharePoint サイトを移行する必要はありません。</p></td>
</tr>
<tr class="even">
<td>OneDrive for Business (P2P ファイル共有)</td>
<td>OneDrive for Business では、ユーザーに SharePoint Online ライセンスが割り当てられている必要があります。 このライセンスがない場合は、ピアごとのファイル共有は行えなされます。</td>
</tr>
<tr class="odd">
<td>アプリケーション プラットフォーム</td>
<td>ユーザーは、会社のポリシーに従って、ユーザーが使用できるアプリを使用できます。<br />
詳細については、以下を参照してください: <a href="/microsoftteams/admin-settings">Teams のアプリの管理者設定</a></td>
</tr>
<tr class="even">
<td>セキュリティとコンプライアンスの機能</td>
<td><ul>
<li><p>アイテム保持ポリシーを使用できます。</p></li>
<li><p>チャネル メッセージのコンプライアンスに関する電子情報開示と法的ホールドがサポートされています。</p></li>
<li><p>データ損失防止ポリシー (DLP) を使用できます。</p></li>
</ul>
<p>Exchange Online で利用できる完全な機能セットExchange オンプレミスでは、これらのほとんどの機能がサポートされています。 完全な一覧については、「Exchange と <a href="/MicrosoftTeams/exchange-teams-interact">Teams の対話方法」を参照してください。</a></p>
<ul>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a>Skype for Business Server を使用する組織の有効化手順  

1.  上の 「ここから始める」セクションで詳しく説明されている前提条件をご説明します。

2.  テナントを諸島モードに切り替える (2019 年 9 月 1 日より後にプロビジョニングされたテナントの場合は、この変更を行うサポートにお問い合わせください)  
    [共存およびアップグレードを設定する](setting-your-coexistence-and-upgrade-settings.md)

3.  会社のビジネス/会社のポリシーに従ってテナントを構成する  
    [組織のMicrosoft Teams の設定を管理する](enable-features-office-365.md)

4.  Teams クライアントを展開する  
    [Teams のクライアントを取得する](get-clients.md)

5.   導入プログラムを推進する  
    [Microsoft Teams を導入する](adopt-microsoft-teams-landing-page.md)<br/>
    [Microsoft Teams の導入クイック スタートのチェックリスト](teams-adoption-quick-start-checklist.md)

6.  他のワークロードを Microsoft 365 または 365 Officeする計画を開始する

7.  Skype for Business ハイブリッドを確立し、Skype for Business および Lync サーバーの推奨されるアップグレード パスに従う  
    [Skype for Business オンプレミスから Teams にアップグレードする](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a>閉じるステートメント

Microsoft Teams は、すべての従業員、情報ワーカー、フロントライン ワーカーを 1 つのプラットフォームでまとめる組織の有効利用者になります。 今すぐ [開始](https://products.office.com/microsoft-teams/group-chat-software) できます。 最新のお知らせや毎月の製品更新プログラムについては、こちらから連絡 [を取り合います](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)。

また、世界中の企業が現在の COVID-19 の状況を管理する中で、Teams を組織内で最大限に活用するのに役立つ一連のコンテンツを作成しています。

  - [COVID-19 中](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)のお客様への取り組み

  - [2 週間: リモートワークについて学んだこと](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [オンライン会議とイベントを実施する](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [Teams により中小規模企業でのリモート作業をサポートする](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [ライブ イベントのデジタル変換: フロントラインからのボブ ベジェノの観測](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [Microsoft IT が社員のリモート作業を実現した 9 つの方法](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)

  - [リモートで作業し、安全を確保する ——CIOS のヒント](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [教師と学生がリモート学習に切り替えるのを支援する](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [Microsoft Teams でリモートで作業しながら生産性を維持する](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a>サポート サービスリファレンス

Teams は、完全に統合された Microsoft 365 または Office 365 エクスペリエンスをユーザーに提供するために、Exchange Online、SharePoint Online、OneDrive for Business、Microsoft 365 グループに依存します。 上記のように、Teams は、制限された機能でこれらのサービスを完全に展開することなく動作します。 Teams とその前提条件の詳細については [、「Teams](teams-overview.md)へようこそ」を参照してください。

上記の各サービスの詳細については、次のリンクに従ってください。

  - Exchange Online は、Teams の予定表機能やピアツーピア メッセージの保存に使用されます。 詳細については、「Exchange と [Teams の対話方法」を参照してください。](exchange-teams-interact.md)

> [!IMPORTANT]
> Teams と Exchange オンプレミスの相互運用では、「Exchange と Exchange Online 組織間の OAuth 認証を構成する」の説明に従って、新しい Exchange OAuth 認証プロトコルを [構成する必要があります](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)。

  - SharePoint はチャネルでのファイル共有に使用されます。/OneDrive for Business は 1 対 1 またはグループ チャットでのファイル共有に使用されます。 詳細については [、「SharePoint Online と OneDrive for Business](sharepoint-onedrive-interact.md)が Microsoft Teams と対話する方法」を参照してください。

  - [Microsoft 365 グループは](office-365-groups.md) 、チームおよびチャネルの作成/管理に使用されます。


## <a name="related-topics"></a>関連項目

[Microsoft Teams IT アーキテクチャとテレフォニー ソリューション ポスター](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[Skype for Business Server と Office 365 の間のハイブリッド接続を計画する](/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[Teams を使用してリモート ワーカーをサポートする](support-remote-work-with-teams.md)

[Microsoft 365 でリモートで作業する](https://aka.ms/remote-work)