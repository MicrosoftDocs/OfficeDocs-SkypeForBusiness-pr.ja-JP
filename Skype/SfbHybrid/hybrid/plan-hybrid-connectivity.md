---
title: ハイブリッド接続の計画|Skype for Business ServerとTeams
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: ハイブリッド モードを構成して、Skype for Business ServerとTeamsのハイブリッド接続Skype for Business計画します。
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: ede3c000bf46cc5b3e1e2a181da2adc6dda93855
ms.sourcegitcommit: 5f19df90443810e027085f8b38d22218e4123a16
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2021
ms.locfileid: "59482401"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-teams"></a>ハイブリッド接続を計画して、Skype for Business ServerとTeams

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

このトピックでは、ハイブリッド接続を計画する方法について説明します。Skype for Business ServerとTeams。 オンプレミス環境をクラウドに移動するための最初のステップは、ハイブリッド接続のセットアップです。

オンプレミスの Skype for Business ユーザーが Teams も並行して使用している場合、これらのユーザーは、Teams クライアントから Skype for Business ユーザーと相互運用することも、Teams クライアントからフェデレーション組織内のユーザーと通信することもできません。 Teams でこの機能を使用できるようにするには、これらのユーザーを Skype for Business オンプレミスからクラウドに移動する必要があります。このためには、Skype for Business ハイブリッド モードを構成する必要があります。 さらに、最適なエクスペリエンスを得る場合、これらのユーザーは Teams のみモードにする必要があります。これにより、ユーザーのすべての着信呼び出しとチャットがユーザーの Teams クライアントに送信されます。

また、オンプレミスの Skype for Business 展開を停止する前に、ハイブリッド接続をセットアップして、すべてのユーザーをクラウドに移行する必要があります。  ハイブリッド接続を使用すると、自分のスケジュールとビジネス ニーズに基づいてユーザーをクラウドに移行させるよう選択できます。 ダイレクト ルーティングを使用すると、クラウドへの移行の間および移行の完了後も、オンプレミスの音声インフラストラクチャを活用することができます。

このトピックでは、既存のオンプレミスの展開と展開の間でハイブリッド接続を構成するために必要なインフラストラクチャとSkype for Business ServerについてTeams。

このトピックを読んでハイブリッド接続を構成する準備ができたら、「ハイブリッド接続を構成する」を参照Skype for Business Server[と](configure-hybrid-connectivity.md)Teams。 構成に関するトピックでは、オンプレミス展開とハイブリッド 接続のセットアップに関する詳細なガイダンスをTeams。

> [!Important]
> Skype for Businessオンラインは 2021 年 7 月 31 日に廃止され、使用できなくなりました。 さらに、オンプレミス環境間の PSTN 接続は、Skype for Business Server または Cloud Connector Edition と Skype for Business Online の間でサポートされなくなりました。  直接ルーティングを使用してオンプレミスのテレフォニー ネットワークをネットワークにTeams[する方法について説明します](/MicrosoftTeams/direct-routing-landing-page)。

## <a name="implications-of-the-retirement-of-skype-for-business-online"></a>オンラインの退職のSkype for Business
Skype for Business Online の退職前と退職後の両方で、Skype for Business Server オンプレミスのユーザーは Teams を使用できますが、TeamsOnly にすることはできません。 (既定では、ユーザーはアイランド モードです)。 ユーザーは、TeamsOnly モードでTeams、特定のフェデレーションと PSTN サポートの利点を完全に体験できます。 

オンラインのSkype for Businessは、Lync Server 2013 または Lync Server 2013 の既存のサポート ライフサイクルSkype for Business Server影響しません。  ただし、Skype for Business Online の退職は、既存のハイブリッド組織を含むオンプレミスの Skype for Business Server または Lync Server 2013 を使用しているお客様がクラウドに移行する方法の特定の側面に影響を与えました。 引退後に変更されていないのは、ハイブリッドをオンプレミスからクラウドに移行する手段として使用する方法は変わらないという意味です。

ハイブリッド組織は、Skype for Businessの使用を中止する前に、次の 3 つの基本的な種類のユーザーで構成される可能性があります。 
- オンプレミス ユーザー (ユーザーがユーザーを使用する場合と使用しない場合Teams、ユーザーのみTeamsモードではありません) 
- TeamsOnly 以外の共存モードを持つオンライン ユーザー
- TeamsOnly ユーザー。

ただし、Skype for BusinessがSkype for Business、ハイブリッド組織は次の 2 つの基本的な種類のユーザーで構成できます。 
- オンプレミスのユーザー (Who TeamsOnly モードではなく、Teamsを使用する場合と使用しない場合があります)
- Teamsユーザーのみ。 

組織が Skype for Business Server または Lync Server 2013 から Teams に移行するには、引き続き同じツールセットを使用してハイブリッドをセットアップおよび構成する必要があります。引き続き、退職前とまったく同じです。 変更されたのは、ユーザーをオンプレミスから Teams に移動するときに、ユーザーをオンプレミスから `-MoveToTeams` TeamsOnly に直接移動するスイッチを指定する必要がなくなりました `Move-CsUser` 。 以前は、このスイッチが指定されていない場合、ユーザーは Skype for Business Server オンプレミスのホームから Skype for Business Online に移行し、モードは変更されません。 退職の結果、ユーザーをオンプレミスからクラウドに移動すると、ユーザーは自動的に TeamsOnly モードに割り当て、オンプレミスからの会議は、スイッチが実際に指定されたかどうかに関係なく、スイッチが指定された場合と同様に、自動的に Teams 会議に変換されます。 `Move-CsUser` `-MoveToTeams` (これには、切り替え前の Lync Server 2013 からの移行が含 `MoveToTeams` まれます)。 

同様に、新しいユーザーがオンプレミスではなく Microsoft 365 で直接作成された場合、そのユーザーはテナントのモードに関係なく自動的に Teams のみモードになります。 ハイブリッド組織では、オンプレミスのユーザーが新しいユーザーにルーティングできるよう、Microsoft 365 でユーザーを直接作成するのではなく、オンプレミスの Active Directory で新しいユーザーを作成し (Microsoft 365 に同期する) 必要があります。

オンラインの使用を取り除く後も、Skype for Businessモードが存在します。 以前と同様に、オンプレミスにSkype for Business Serverアカウントを持つユーザーには、TeamsOnly を除くすべての共存モードを割り当てることができます。 ただし、退職後、オンラインに住むユーザーは TeamsOnly にしか使用できません (オンライン ユーザーが任意のモードSkype for Business現在とは対照的です)。  

> [!Important]
> - teamsOnly ではない Skype for Business Online にユーザーが参加している既存のハイブリッド組織では、できるだけ早くこれらのユーザーを Teams のみモードにアップグレードする必要があります。 組織に TeamsOnly ではない Skype for Business Online にユーザーがまだ所属している場合は、これらのユーザーを TeamsOnly に移行する Microsoft 支援アップグレードをスケジュールできます。 これは、オンプレミスのユーザーにSkype for Business Server影響を与える可能性はありません。 スケジュール通知は、これらのオンラインの TeamsOnly 以外のユーザーが Teams にアップグレードされる前に、Skype for Business Online にユーザーが参加しているハイブリッド顧客に事前に送信されます。
> - すぐに、TeamsOnly 以外のモードをオンラインのユーザーに割り当てなくなりました。

## <a name="about-shared-sip-address-space-functionality"></a>共有 SIP アドレス空間の機能について

<a name="BKMK_Overview"> </a>

 Skype for Business Server と Teams のオンプレミス展開の間にハイブリッド接続を設定すると、一部のユーザーをオンプレミスに配置し、一部のユーザーをオンラインでホームに設定できます。

この種類の構成は、共有 SIP アドレス空間の機能に依存し、次の図に示すように、contoso.com などのドメインのユーザーは、Skype for Business Server と Teams を使用する間で分割される場合があります。

![Skype for Business Hybrid接続 - 分割ドメイン。](../../sfbserver2019/media/plan-hybrid-connectivity-2019-1.png)

共有 SIP アドレス空間が構成されている場合:

- Azure Active Directory Connectを使用して、オンプレミス ディレクトリとディレクトリを同期Microsoft 365。
- オンプレミスのユーザーは、オンプレミスのサーバーとSkype for Businessします。
- オンラインに登録されているユーザーは、Teams と対話し、2021 年 7 月 31 日まで Skype for Business Online を共同存在モードに基づいて操作できます。
- 両方の環境のユーザーが相互に通信できます。
- オンプレミスの Active Directory は権限があります。 すべてのユーザーは、最初にオンプレミスの Active Directory に作成し、Azure サーバーに同期AD。 ユーザーをオンラインで使用する場合でも、最初にユーザーをオンプレミス環境で作成し、そのユーザーをオンラインに移動して、ユーザーがオンプレミスのユーザーが検出可能なユーザーを確認する必要があります。

ユーザーをオンラインに移動する前に、ユーザーにオンライン (プラン 2) とTeamsライセンスSkype for Business割り当てる必要があります。 **オンライン ライセンスのSkype for Businessは、オンラインの使用を取り除Skype for Businessです。** ユーザーが電話会議や 電話システム などの追加のオンライン機能を利用する場合は、Microsoft 365 で適切なライセンスを割り当てる必要があります。

## <a name="hybrid-connectivity-infrastructure-requirements"></a>ハイブリッド接続インフラストラクチャの要件

<a name="BKMK_Infrastructure"> </a>

オンプレミス環境と通信サービス間のハイブリッド接続をMicrosoft 365するには、次のインフラストラクチャ要件を満たす必要があります。

- サポートされているトポロジに展開Skype for Business Server Lync Server の単一のオンプレミス展開。 この [トピックの「トポロジ要件](plan-hybrid-connectivity.md#BKMK_Topology) 」を参照してください。

- ユーザー Microsoft 365を持つ組織Teams。
    > [!NOTE]
    > オンプレミス展開では、ハイブリッド構成に使用できるテナントは 1 つのみです。
    
- Azure Active Directory Connectオンプレミス ディレクトリと同期する方法をMicrosoft 365。 詳細については、「Azure AD Connect: アカウントとアクセス許可[」を参照してください](/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions)。

- Skype for Business Server管理ツール。 これらは、ユーザーをオンプレミスからクラウドに移動するために必要です。 これらのツールは、オンプレミス展開とインターネットの両方にアクセスできるサーバーにインストールする必要があります。
- オンライン管理ツール。 管理センターまたは管理センター Teams使用して、Windows PowerShell管理Teams。 PowerShell を使用してサーバーを管理するにはTeams PowerShell モジュールをダウンロードしてTeamsインストールします。 (オンライン Skype for Businessが廃止されました)。
- 共有 SIP アドレス空間を有効にする必要があります。また、オンプレミス展開は、ホスト プロバイダーとしてMicrosoft 365構成する必要があります。 ハイブリッド接続を構成するために必要な手順の詳細については [、「Configure hybrid connectivity」を参照してください](configure-hybrid-connectivity.md)。

ハイブリッド接続を構成した後、ユーザーを別のユーザーにTeams。 詳細については、「ユーザーを[オンプレミスからユーザーに移動する」を参照Teams。](move-users-from-on-premises-to-teams.md)

## <a name="server-version-requirements"></a>サーバーのバージョン要件

<a name="BKMK_Topology"> </a>

ハイブリッドの展開を構成するには、Teamsサポートされているトポロジのいずれかを使用する必要があります。 

- Skype for Business Server 2019 の展開には、Skype for Business Server 2019 を実行するすべてのサーバーが含まれています。
- Skype for Business Server 2015 の展開には、Skype for Business Server 2015 を実行するすべてのサーバーが含まれています。
- Lync Server 2013 を実行しているすべてのサーバーを含む Lync Server 2013 展開。  ただし、ハイブリッド音声接続が必要な場合は、以下に示す混合バージョンのトポロジを使用する必要があります。
- 以下に示す最大 2 つの異なるサーバー バージョンを持つ展開。
  - Skype for Business Server 2015 および Skype for Business Server 2019
  - Lync Server 2013 および Skype for Business Server 2019
  - Lync Server 2013 および Skype for Business Server 2015

*任意* のトポロジでハイブリッド音声が必要な場合は、フェデレーション エッジとして指定されているエッジ サーバーと、SIP フェデレーションに関連付けられているプールの両方が Skype for Business 2015 以降で実行されている必要があります。 Lync 2013 プールが存在する場合、ユーザーは Lync 2013 プールに残ります。 詳細については、「音声ソリューションを [計画する」を参照してください](/MicrosoftTeams/cloud-voice-landing-page)。

> [!NOTE]
> Lync Server 2010 は、このアプリケーションではTeams。

## <a name="multi-forest-support"></a>複数フォレストのサポート

<a name="BKMK_MultiForest"> </a>

Microsoft では、次の種類のマルチフォレスト ハイブリッド シナリオがサポートされています。

- **リソース フォレスト トポロジ。** この種類のトポロジでは、Skype for Business Server (リソース フォレスト) をホストする 1 つのフォレストと、リソース フォレスト内の Skype for Business Server にアクセスするアカウント ID をホストする 1 つ以上のフォレストがあります。 一般に、ユーザーは、次Skype for Business満たされている場合、別のフォレストの機能にアクセスできます。
  - ユーザーは、ユーザーをホストするフォレストに適切に同期Skype for Business。 ハイブリッド構成では、ユーザーは無効なユーザー オブジェクトとして同期する必要があります。
  - ホストするフォレスト Skype for Business、ユーザーを含むフォレストを信頼する必要があります。
    リソース フォレスト ハイブリッド シナリオの詳細については、「ハイブリッド フォレストのリソース フォレスト トポロジを展開する」を参照[Skype for Business。](configure-a-multi-forest-environment-for-hybrid.md)

- **複数のフォレストにSkype for Business Server展開。** この構成は、合併および買収のシナリオ、およびより複雑な企業の結果として発生する可能性があります。 次の重要な要件が満たされている場合、複数の Microsoft 365 Skype for Business 展開を持つ組織では、オンプレミスからクラウドへのすべてのユーザーの統合を実現できます。
  - 関連する組織には、少なくとも 1 Microsoft 365必要があります。 複数の組織とのシナリオでの統合はサポートされていません。
  - 任意の時点で、ハイブリッド モード (共有 SIP アドレスSkype for Business 1 つのオンプレミス フォレストのみを使用できます。 その他のすべてのオンプレミス Skype for Businessフォレストは、完全にオンプレミスに残る必要があります (おそらく、互いにフェデレーションされている可能性があります)。 これらの他のオンプレミス組織は、2018 年 12 月現在利用可能なオンライン [SIP](/powershell/module/skype/disable-csonlinesipdomain) ドメインを無効にする新しい機能を必要に応じて AAD に同期できます。

    複数のフォレストに Skype for Business を展開しているお客様は、分割ドメイン (共有 SIP アドレス空間) 機能を使用して、Skype for Business フォレストごとに個別に Microsoft 365 組織に完全に移行する必要があります。 フォレストの移行が完了したら、次のオンプレミス展開を移行する前に、オンプレミス展開とのハイブリッドを無効にするSkype for Businessがあります。 さらに、クラウドに移行する前に、オンプレミスのユーザーは、同じユーザーのオンプレミス ディレクトリに表示されないユーザーとフェデレーション状態のままです。 詳細については、「クラウド統合[for Teams」を参照](cloud-consolidation.md)Skype for Business。

## <a name="federation-requirements"></a>フェデレーション要件

<a name="BKMK_Federation"> </a>

ハイブリッド モードSkype for Business構成する場合は、オンプレミス環境とオンライン環境が互いにフェデレーションできる必要があります。  オンライン環境には、既定で開いているフェデレーションがあります。多くの場合、オンプレミス環境は既定でフェデレーションを閉じています。  

ハイブリッド展開を正常に構成するには、次の要件を満たす必要があります。

- ドメインの一致は、オンプレミスの展開と組織で同じ構成Microsoft 365があります。 オンプレミス展開でパートナーの検出が有効になっている場合は、オンライン組織用にオープン フェデレーションを構成する必要があります。 パートナーの検出が有効になっていない場合は、オンライン組織に対して閉じたフェデレーションを構成する必要があります。
- オンプレミス展開の [ブロックされたドメイン] リストは、オンライン テナントの [ブロックされたドメイン] リストと完全に一致している必要があります。
- オンプレミス展開の [許可されたドメイン] リストは、オンライン テナントの [許可されたドメイン] リストと完全に一致している必要があります。
- フェデレーションは、オンライン テナントの外部通信に対して有効にする必要があります。

## <a name="network-considerations"></a>ネットワークの考慮事項

以下のセクションでは、以下の考慮事項について説明します。

- DNS 設定
- ファイアウォールに関する考慮事項

### <a name="dns-settings-for-hybrid-deployments"></a>ハイブリッド展開の DNS 設定

<a name="BKMK_DNS"> </a>

ハイブリッド展開用に DNS レコードを作成する場合は、Skype for Business DNS レコードがオンプレミス インフラストラクチャを指している必要があります。 必要な DNS レコードの詳細については、「DNS の要件」を参照[Skype for Business Server。](../../sfbserver/plan-your-deployment/network-requirements/dns.md)

さらに、次の表に示す DNS 解決がオンプレミス展開で動作するようにする必要があります。 (オンプレミスのフェデレーションを既に構成している場合は、既にこれらを持っている可能性が高い)。

|DNS レコード  <br/> |で解決可能  <br/> |DNS 要件  <br/> |
|:-----|:-----|:-----|
|_sipfederationtls._tcp の DNS SRV レコード。\<sipdomain.com\> Access Edge 外部 IP への解決をサポートしているすべての SIP ドメインの場合  <br/> |エッジ サーバー  <br/> |ハイブリッド構成でフェデレーション通信を有効にする。 エッジ サーバーは、オンプレミスとオンラインの間で分割された SIP ドメインのフェデレーション トラフィックをルーティングする場所を知る必要があります。  <br/> ユーザー名と SRV レコードのドメイン間で厳密な DNS 名一致を使用する必要があります。  <br/> |
|DNS エッジ Web 会議サービス FQDN のレコード (たとえば、web 会議エッジ webcon.contoso.com 外部 IP への解決など)  <br/> |社内ネットワーク接続ユーザーのコンピューター  <br/> |オンライン ユーザーがオンプレミスのホストされた会議でコンテンツを表示または表示できます。 コンテンツには、PowerPoint、ホワイトボード、ポーリング、共有メモが含まれます。  <br/> |

組織での DNS の構成方法によっては、これらのレコードに内部 DNS 解決を提供するために、対応する SIP ドメインの内部ホスト DNS ゾーンにこれらのレコードを追加する必要がある場合があります。

### <a name="firewall-considerations-for-hybrid-deployments"></a>ハイブリッド展開のファイアウォールに関する考慮事項

<a name="BKMK_Firewall"> </a>

ネットワーク上のコンピューターは、標準のインターネット DNS 参照を実行できる必要があります。これらのコンピューターが標準のインターネット サイトに接続できれば、ネットワークはこの要件を満たしています。

Microsoft Online Services データ センターの場所に応じて、ワイルドカード ドメイン名 (.outlook.com からのトラフィックなど) に基づいて接続を受け入れるネットワーク ファイアウォール \* デバイスも構成する必要があります。 組織のファイアウォールがワイルドカード名の構成をサポートしていない場合は、許可する IP アドレス範囲と指定したポートを手動で決定する必要があります。

ポートおよびプロトコル要件の詳細を含む詳細については、「URL と IP アドレスMicrosoft 365[を参照してください](/microsoft-365/enterprise/urls-and-ip-address-ranges)。
