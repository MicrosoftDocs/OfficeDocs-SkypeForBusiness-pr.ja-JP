---
title: ハイブリッド接続の計画|Skype for Business Server 2019 および Microsoft 365 または Office 365 統合
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Skype for Business ハイブリッド モードを構成して、Skype for Business Server と Teams または Skype for Business Online 間のハイブリッド接続を実装する計画。
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: 1a43243f4b5ce827a7c688c1aad1983466aa6ca7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110263"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-microsoft-365-or-office-365"></a>Skype for Business Server と Microsoft 365 または Office 365 の間のハイブリッド接続を計画する

Skype for Business Server と Teams または Skype for Business Online 間のハイブリッド接続を計画する方法については、このトピックを参照してください。 オンプレミス環境をクラウドに移動するための最初のステップは、ハイブリッド接続のセットアップです。

オンプレミスの Skype for Business ユーザーが Teams も並行して使用している場合、これらのユーザーは、Teams クライアントから Skype for Business ユーザーと相互運用することも、Teams クライアントからフェデレーション組織内のユーザーと通信することもできません。 Teams でこの機能を使用できるようにするには、これらのユーザーを Skype for Business オンプレミスからクラウドに移動する必要があります。このためには、Skype for Business ハイブリッド モードを構成する必要があります。 さらに、最適なエクスペリエンスを得る場合、これらのユーザーは Teams Only モードに設定する必要があります。これにより、ユーザーのすべての着信呼び出しとチャットがユーザーの Teams クライアントに送信されます。

また、オンプレミスの Skype for Business 展開を停止する前に、ハイブリッド接続をセットアップして、すべてのユーザーをクラウドに移行する必要があります。  ハイブリッド接続を使用すると、自分のスケジュールとビジネス ニーズに基づいてユーザーをクラウドに移行させるよう選択できます。 ダイレクト ルーティングを使用すると、クラウドへの移行の間および移行の完了後も、オンプレミスの音声インフラストラクチャを活用することができます。

このトピックでは、既存のオンプレミスの Skype for Business Server 展開と Teams または Skype for Business Online 間のハイブリッド接続を構成するために必要なインフラストラクチャとシステム要件について説明します。

このトピックを読んでハイブリッド接続を構成する準備ができたら、「Configure hybrid connectivity between Skype for Business Server と Microsoft 365 または microsoft 365 または Office [365」](configure-hybrid-connectivity.md)を参照してください。 構成のトピックでは、オンプレミス展開と Teams または Skype for Business Online 間のハイブリッド接続をセットアップする手順を示します。

> [!Important]
> Skype for Business Online は 2021 年 7 月 31 日に廃止され、その後サービスにアクセスできなくなりました。  さらに、Skype for Business Server または Cloud Connector Edition と Skype for Business Online を介したオンプレミス環境間の PSTN 接続はサポートされなくなりました。  直接ルーティングを使用してオンプレミスのテレフォニー ネットワークを Teams に接続する方法 [について説明します](/MicrosoftTeams/direct-routing-landing-page)。

## <a name="about-shared-sip-address-space-functionality"></a>共有 SIP アドレス空間の機能について

<a name="BKMK_Overview"> </a>

 Skype for Business Server と Teams または Skype for Business Online のオンプレミス展開の間にハイブリッド接続を設定すると、一部のユーザーをオンプレミスに配置し、一部のユーザーをオンラインでホームに設定できます。

この種類の構成は、共有 SIP アドレス空間の機能に依存し、次の図に示すように、contoso.com などのドメインのユーザーを意味する "分割ドメイン" と呼ばれる場合があります。

![Skype for Business Hybrid connectivity - スプリット ドメイン](../../sfbserver2019/media/plan-hybrid-connectivity-2019-1.png)

共有 SIP アドレス空間が構成されている場合:

- Azure Active Directory Connect を使用して、オンプレミス ディレクトリを Microsoft 365 または Office 365 と同期します。
- オンプレミスのユーザーは、オンプレミスの Skype for Business サーバーとやり取りします。
- オンラインに参加しているユーザーは、Skype for Business Online または Teams サービスとやり取りできます。
- 両方の環境のユーザーが相互に通信できます。
- オンプレミスの Active Directory は権限があります。 すべてのユーザーは、最初にオンプレミスの Active Directory に作成し、Azure サーバーに同期AD。 ユーザーをオンラインで使用する場合でも、最初にユーザーをオンプレミス環境で作成し、そのユーザーをオンラインに移動して、ユーザーがオンプレミスのユーザーが検出可能なユーザーを確認する必要があります。

ユーザーをオンラインに移動するには、Skype for Business Online (プラン 2) ライセンスを割り当てる必要があります。 ユーザーが Teams を使用する場合、ユーザーには Teams ライセンスも割り当てる必要があります (Skype for Business ライセンスは有効なままにする必要があります)。 ユーザーが電話会議や電話システムなどの追加のオンライン機能を利用する場合は、Microsoft 365 または Office 365 で適切なライセンスを割り当てる必要があります。

## <a name="hybrid-connectivity-infrastructure-requirements"></a>ハイブリッド接続インフラストラクチャの要件

<a name="BKMK_Infrastructure"> </a>

オンプレミス環境と Microsoft 365 または Office 365 通信サービス間のハイブリッド接続を実装するには、次のインフラストラクチャ要件を満たす必要があります。

- サポートされているトポロジに展開される Skype for Business Server または Lync Server の単一のオンプレミス展開。 この [トピックの「トポロジ要件](plan-hybrid-connectivity.md#BKMK_Topology) 」を参照してください。

- Skype for Business Online が有効になっている microsoft 365 Office 365 組織。
    > [!NOTE]
    > オンプレミス展開では、ハイブリッド構成に使用できるテナントは 1 つのみです。
    
- Azure Active Directory Connect を使用して、オンプレミス ディレクトリを Microsoft 365 または Office 365 と同期します。 詳細については [、「Azure AD接続: アカウントとアクセス許可」を参照してください](/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions)。

- Skype for Business Server 管理ツール。 これらは、ユーザーをオンプレミスからクラウドに移動するために必要です。 これらのツールは、オンプレミス展開とインターネットの両方にアクセスできるサーバーにインストールする必要があります。
- オンライン管理ツール。 Teams 管理センターまたは管理者を使用して、Teams Windows PowerShell Skype for Business Online を管理できます。 PowerShell を使用して Teams または Skype for Business Online を管理するには、Skype for Business Online Connector をダウンロードしてインストールします。
- 共有 SIP アドレス空間を有効にし、Microsoft 365 または Office 365 をホスティング プロバイダーとして使用するようにオンプレミス展開を構成する必要があります。 ハイブリッド接続を構成するために必要な手順の詳細については [、「Configure hybrid connectivity」を参照してください](configure-hybrid-connectivity.md)。

ハイブリッド接続を構成した後、ユーザーを Teams または Skype for Business Online に移動できます。 詳細については、「ユーザーをオンプレミスから Teams に移動する」および「 [オンプレミス](move-users-from-on-premises-to-teams.md) から Skype for Business Online にユーザーを [移動する」を参照してください](move-users-from-on-premises-to-skype-for-business-online.md)。

## <a name="server-version-requirements"></a>サーバーのバージョン要件

<a name="BKMK_Topology"> </a>

Teams または **Skype for Business Online** を使用してハイブリッドの展開を構成するには、次のサポートされているトポロジのいずれかを使用する必要があります。

- Skype for Business Server 2019 の展開には、Skype for Business Server 2019 を実行するすべてのサーバーが含まれています。
- Skype for Business Server 2015 の展開には、Skype for Business Server 2015 を実行するすべてのサーバーが含まれています。
- Lync Server 2013 を実行しているすべてのサーバーを含む Lync Server 2013 展開。  ただし、ハイブリッド音声接続が必要な場合は、以下に示す混合バージョンのトポロジを使用する必要があります。
- 以下に示す最大 2 つの異なるサーバー バージョンを持つ展開。
  - Skype for Business Server 2015 および Skype for Business Server 2019
  - Lync Server 2013 および Skype for Business Server 2019
  - Lync Server 2013 および Skype for Business Server 2015

*任意のトポロジ* でハイブリッド音声が必要な場合は、フェデレーション エッジとして指定されているエッジ サーバーと SIP フェデレーションに関連付けられているプールの両方が、Skype for Business 2015 以降を実行している必要があります。 Lync 2013 プールが存在する場合、ユーザーは Lync 2013 プールに残ります。 詳細については、「Skype for Business Server で PSTN 接続を使用して電話システムを計画 [する」を参照してください](../../SfbServer/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity.md)。

**Lync Server 2010** を含む次のトポロジは、インスタント メッセージングと会議のために Skype for Business Online でサポートされています。 Lync Server **2010** を含むトポロジは、ハイブリッド音声や Teams ではサポートされていません。

- Lync Server 2010 と Skype for Business Server 2015 の混在展開
- Lync Server 2010 と Lync Server 2013 の混在展開
- Lync Server 2010 を実行しているすべてのサーバーが最新の累積的な更新プログラムを備える Lync Server 2010 展開。

フェデレーション エッジ サーバーからのフェデレーション エッジ サーバーと次ホップ サーバーは、最新の累積的な更新プログラムを使用して Lync Server 2010 を実行している必要があります。 Skype for Business Server 2015 または Lync Server 2013 管理ツールは、少なくとも 1 つのサーバーまたは管理ワークステーションにインストールする必要があります。

## <a name="multi-forest-support"></a>複数フォレストのサポート

<a name="BKMK_MultiForest"> </a>

Microsoft では、次の種類のマルチフォレスト ハイブリッド シナリオがサポートされています。

- **リソース フォレスト トポロジ。** この種類のトポロジでは、Skype for Business Server (リソース フォレスト) をホストする 1 つのフォレストと、リソース フォレスト内の Skype for Business Server にアクセスするアカウント ID をホストする 1 つ以上のフォレストがあります。 一般に、次の要件が満たされている場合、ユーザーは別のフォレストの Skype for Business 機能にアクセスできます。
  - ユーザーは、Skype for Business をホストするフォレストに適切に同期されます。 ハイブリッド構成では、ユーザーは無効なユーザー オブジェクトとして同期する必要があります。
  - Skype for Business をホストするフォレストは、ユーザーを含むフォレストを信頼する必要があります。
    リソース フォレスト ハイブリッド シナリオの詳細については [、「Deploy a resource forest topology for hybrid Skype for Business」を参照してください](configure-a-multi-forest-environment-for-hybrid.md)。

- **複数のフォレストで Skype for Business Server を複数配置している。** この構成は、合併および買収のシナリオ、およびより複雑な企業の結果として発生する可能性があります。 次の重要な要件が満たされている場合、複数の Skype for Business 展開を持つ組織では、オンプレミスからクラウドへのすべてのユーザーの統合を 1 つの Microsoft 365 または Office 365 組織で実現できます。
  - Microsoft 365 または 365 組織Office 1 つが必要です。 複数の組織とのシナリオでの統合はサポートされていません。
  - 任意の時点で、ハイブリッド モード (共有 SIP アドレス空間) で使用できるオンプレミスの Skype for Business フォレストは 1 つのみです。 他のすべてのオンプレミスの Skype for Business フォレストは、完全にオンプレミスのままである必要があります (おそらく、互いにフェデレーションされている可能性があります)。 これらの他のオンプレミス組織は、2018 年 12 月現在利用可能なオンライン [SIP](/powershell/module/skype/disable-csonlinesipdomain) ドメインを無効にする新しい機能を必要に応じて AAD に同期できます。

    複数のフォレストに Skype for Business を展開しているお客様は、次のオンプレミス Skype for Business 展開を移行する前に、分割ドメイン (共有 SIP アドレス空間) 機能を使用して各 Skype for Business フォレストを Microsoft 365 または Office 365 組織に完全に移行してから、オンプレミス展開とのハイブリッドを無効にする必要があります。 さらに、クラウドに移行する前に、オンプレミスのユーザーは、同じユーザーのオンプレミス ディレクトリに表示されないユーザーとフェデレーション状態のままです。 詳細については、「Teams と Skype for Business の [クラウド統合」を参照してください](cloud-consolidation.md)。

## <a name="federation-requirements"></a>フェデレーション要件

<a name="BKMK_Federation"> </a>

Skype for Business ハイブリッド モードを構成する場合は、オンプレミス環境とオンライン環境が互いにフェデレーションできる必要があります。  オンライン環境には、既定で開いているフェデレーションがあります。多くの場合、オンプレミス環境は既定でフェデレーションを閉じています。  

ハイブリッド展開を正常に構成するには、次の要件を満たす必要があります。

- ドメイン一致は、オンプレミス展開と Microsoft 365 または 365 組織で同Officeする必要があります。 オンプレミス展開でパートナーの検出が有効になっている場合は、オンライン組織用にオープン フェデレーションを構成する必要があります。 パートナーの検出が有効になっていない場合は、オンライン組織に対して閉じたフェデレーションを構成する必要があります。
- オンプレミス展開の [ブロックされたドメイン] リストは、オンライン テナントの [ブロックされたドメイン] リストと完全に一致している必要があります。
- オンプレミス展開の [許可されたドメイン] リストは、オンライン テナントの [許可されたドメイン] リストと完全に一致している必要があります。
- フェデレーションは、オンライン テナントの外部通信に対して有効にする必要があります。

## <a name="network-considerations"></a>ネットワークの考慮事項

以下のセクションでは、以下の考慮事項について説明します。

- DNS 設定
- ファイアウォールに関する考慮事項

### <a name="dns-settings-for-hybrid-deployments"></a>ハイブリッド展開の DNS 設定

<a name="BKMK_DNS"> </a>

ハイブリッド展開用に DNS レコードを作成する場合は、すべての Skype for Business 外部 DNS レコードがオンプレミス インフラストラクチャを指している必要があります。 必要な DNS レコードの詳細については、「Skype for Business Server の DNS 要件 [」を参照してください](../../sfbserver/plan-your-deployment/network-requirements/dns.md)。

さらに、次の表に示す DNS 解決がオンプレミス展開で動作するようにする必要があります。 (オンプレミスのフェデレーションを既に構成している場合は、既にこれらを持っている可能性が高い)。

|DNS レコード  <br/> |で解決可能  <br/> |DNS 要件  <br/> |
|:-----|:-----|:-----|
|_sipfederationtls._tcp の DNS SRV レコード。\<sipdomain.com\> Access Edge 外部 IP への解決をサポートしているすべての SIP ドメインの場合  <br/> |エッジ サーバー  <br/> |ハイブリッド構成でフェデレーション通信を有効にする。 エッジ サーバーは、オンプレミスとオンラインの間で分割された SIP ドメインのフェデレーション トラフィックをルーティングする場所を知る必要があります。  <br/> ユーザー名と SRV レコードのドメイン間で厳密な DNS 名一致を使用する必要があります。  <br/> |
|DNS エッジ Web 会議サービス FQDN のレコード (たとえば、web 会議エッジ webcon.contoso.com 外部 IP への解決など)  <br/> |社内ネットワーク接続ユーザーのコンピューター  <br/> |オンライン ユーザーがオンプレミスのホストされた会議でコンテンツを表示または表示できます。 コンテンツには、PowerPoint ファイル、ホワイトボード、ポーリング、共有メモが含まれます。  <br/> |

組織での DNS の構成方法によっては、これらのレコードに内部 DNS 解決を提供するために、対応する SIP ドメインの内部ホスト DNS ゾーンにこれらのレコードを追加する必要がある場合があります。

### <a name="firewall-considerations-for-hybrid-deployments"></a>ハイブリッド展開のファイアウォールに関する考慮事項

<a name="BKMK_Firewall"> </a>

ネットワーク上のコンピューターは、標準のインターネット DNS 参照を実行できる必要があります。これらのコンピューターが標準のインターネット サイトに接続できれば、ネットワークはこの要件を満たしています。

Microsoft Online Services データ センターの場所に応じて、ワイルドカード ドメイン名 (.outlook.com からのトラフィックなど) に基づいて接続を受け入れるネットワーク ファイアウォール \* デバイスも構成する必要があります。 組織のファイアウォールがワイルドカード名の構成をサポートしていない場合は、許可する IP アドレス範囲と指定したポートを手動で決定する必要があります。

ポートとプロトコル要件の詳細を含む詳細については [、「Microsoft 365」および「Office 365 URL](/microsoft-365/enterprise/urls-and-ip-address-ranges)と IP アドレス範囲」を参照してください。