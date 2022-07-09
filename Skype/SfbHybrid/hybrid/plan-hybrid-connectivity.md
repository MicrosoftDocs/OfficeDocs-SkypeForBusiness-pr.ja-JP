---
title: ハイブリッド接続|を計画するSkype for Business Serverと Teams
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
search.appverid: MET150
description: ハイブリッド モードを構成して、Skype for Business Serverと Teams 間のハイブリッド接続を実装Skype for Business計画します。
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: a73b14a3642a216ff9cbbe919b586979aabf6a81
ms.sourcegitcommit: 15ec17eff4ad4c962d00b8683513f9b269d82917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2022
ms.locfileid: "66695050"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-teams"></a>Skype for Business Serverと Teams 間のハイブリッド接続を計画する

> [!Important]
> Skype for Business Online は 2021 年から廃止されましたが、2019 年、Skype for Business Server 2015 年、Lync Server 2013 Skype for Business Serverオンプレミス製品は引き続きサポートされています。 さらに、Microsoft は、これらのオンプレミス製品と Microsoft Teams 間のハイブリッド環境をサポートしています。 これにより、これらのオンプレミス展開を使用する組織は、TeamsOnly にユーザーを移行できます。  最後に、Skype for Business Serverの Cloud Connector Edition はサポートされなくなりました。 オンプレミスの PSTN 接続を必要とするお客様は [、ダイレクト ルーティング](/MicrosoftTeams/direct-routing-landing-page)を使用する必要があります。


Skype for Business Serverまたは Lync Server 2013 と Teams 間のハイブリッド接続を計画する方法については、このトピックを参照してください。 ハイブリッド接続を設定することは、オンプレミス環境をクラウド内の Microsoft Teams のみの環境に移行する最初の手順です。

Skype for Business Serverのオンプレミス展開では、Skype for Businessのユーザーが Teams を使用することもできますが、オンプレミスのSkype for Business Server展開を使用するように構成されている限り、そのようなユーザーはすべての Teams 機能を使用できるわけではありません。 これらのユーザーはオンプレミスで "ホーム" と言われ、特定の Teams 機能は使用できませんが、これらのユーザーはオンプレミスに所属しています。たとえば、次のようになります。

- 他の組織のユーザーとユーザーの Teams クライアントを介したフェデレーション通話とチャットは利用できません
- ユーザーの Teams クライアントを介して、Skype for Business クライアントを使用する組織内の他のユーザーとの相互運用。
- PSTN 通話機能 (ユーザーに電話システム ライセンスが割り当てられている場合)。

Teams の完全な機能を得るには、これらのユーザーをオンプレミスからクラウドSkype for Business移動する必要があります。その時点でユーザーは TeamsOnly になります。 ユーザーをオンプレミスからクラウドに移動する操作は、ユーザーの共存モードを TeamsOnly に設定します。 ユーザーがクラウドと TeamsOnly に移動されると、すべての着信チャットと通話が Teams クライアントに送信されます (Teams のサイド バイ サイド使用法とは異なります)。  詳細については、Teams とSkype for Businessを[組み合わせて使用する組織の](/microsoftteams/migration-interop-guidance-for-teams-with-skype) [teams のSkype for Businessと移行および](/microsoftteams/coexistence-chat-calls-presence)相互運用性に関するガイダンスを参照してください。

クラウドでオンプレミスと TeamsOnly の間でユーザーを移動するには、ハイブリッド モードSkype for Business構成する必要があります。 さらに、オンプレミスのSkype for Businessデプロイを使用停止する前に、すべてのユーザーをオンプレミスからクラウドに移動します。   ハイブリッド接続を使用すると、自分のスケジュールとビジネス ニーズに基づいてユーザーをクラウドに移行させるよう選択できます。  ダイレクト ルーティングを使用すると、クラウドへの移行の間および移行の完了後も、オンプレミスの音声インフラストラクチャを活用することができます。

このトピックでは、既存のオンプレミスのSkype for Business Server展開と Teams 間のハイブリッド接続を構成するために必要なインフラストラクチャとシステムの要件について説明します。

このトピックを読み、ハイブリッド接続を構成する準備ができたら、「[Skype for Business Serverと Teams 間のハイブリッド接続を構成する](configure-hybrid-connectivity.md)」を参照してください。 構成トピックでは、オンプレミスの展開と Teams 間のハイブリッド接続を設定するための詳細なガイダンスが提供されます。


## <a name="implications-of-the-retirement-of-skype-for-business-online"></a>Skype for Business Online の廃止の影響
Skype for Business Online の廃止前と廃止後の両方で、オンプレミスのSkype for Business Serverに所属するユーザーは Teams を使用できますが、TeamsOnly にすることはできません。 (オンプレミスユーザーは既定でアイランド モードであり、TeamsOnly 以外のモードが割り当てられます)。 ユーザーは Teams の完全な利点、特にフェデレーション、PSTN サポート、およびすべての受信チャットと通話が TeamsOnly モードになると Teams に着信することを保証することのみを体験できます。 

Skype for Business Online の廃止は、Skype for Business Serverまたは Lync Server 2013 の既存のサポート ライフサイクルには影響しません。  ただし、Skype for Business Online の廃止は、既存のハイブリッド組織を含むオンプレミスのSkype for Business Serverまたは Lync Server 2013 を使用する組織で *、ユーザーがクラウドに移行し TeamsOnly になる***方法** の特定の側面に影響を与えます。 オンプレミスからクラウド (TeamsOnly など) に移行するための前提条件構成としてのハイブリッドの使用は変わりません。

Skype for Business Online が廃止される前は、ハイブリッド組織は次の 3 つの基本的な種類のユーザーで構成される可能性があります。 
- オンプレミス ユーザー (Teams を使用する場合と使用しない場合があるが、Teams のみモードではないユーザー) 
- TeamsOnly 以外の共存モードを持つオンライン ユーザー
- TeamsOnly ユーザー。

ただし、Skype for Business Online の廃止後、ハイブリッド組織は次の 2 つの基本的な種類のユーザーのみで構成できます。 
- オンプレミス ユーザー (TeamsOnly モードでは使用できないが、Teams を使用できるユーザーと使用しないユーザー)
- Teams のみユーザー。 

組織がSkype for Business Serverまたは Lync Server 2013 から Teams に移行するには、廃止前とまったく同じツールセットを使用してハイブリッドを設定し、構成 *する* 必要があります。 ユーザーをオンプレミスから TeamsOnly に移動する場合、スイッチ`Move-CsUser`を指定`-MoveToTeams`する必要はなくなりました。 以前は、このスイッチが指定されていない場合、ユーザーはオンプレミスSkype for Business Serverホームから Skype for Business Online に移行し、モードは変更されませんでした。 ただし、Skype Business Online が廃止されたため、ユーザーをオンプレミスからクラウド`Move-CsUser`に移動すると、スイッチが指定されているかどうか`-MoveToTeams`に関係なく、TeamsOnly モードが *自動的* に割り当てられ、会議がオンプレミスから Teams 会議に変換されます。 また、Lync Server 2013 を持つ組織は、スイッチを使用していなかった `MoveToTeams` ため、ユーザーをオンプレミスから TeamsOnly に直接移動できます。 

同様に、新しいユーザーがオンプレミスではなく Microsoft 365 で直接作成された場合、テナントのモードに関係なく、そのユーザーは自動的に Teams のみモードになります。 少なくとも 1 人のオンプレミス ユーザーを持つハイブリッド組織では、新しいユーザーをクラウド ユーザーにする場合でも、オンプレミス ユーザーが新しいユーザーにルーティングできるように、Microsoft 365 で直接ユーザーを作成するのではなく、オンプレミスの Active Directoryで *新しいユーザー* を作成 (その後 Microsoft 365 に同期) する必要があることに注意してください。 オンプレミス ディレクトリに作成した後、これらの新しいユーザーは、オンプレミスのSkype for Business展開 *で* sip を有効にし、必要に応じてクラウドに移動して TeamsOnly にする必要があります。 

共存モードは、Skype for Business Online の廃止後も引き続き存在します。 以前と同様に、オンプレミスにSkype for Business Serverアカウントを持つユーザーには、TeamsOnly を除く任意の共存モードを割り当てることができます。 ただし、退職後は、オンラインに所属するユーザーは TeamsOnly のみになります。 オンラインホームのユーザーに TeamsOnly 以外のモードを割り当てることはできなくなります。


> [!Important]
> TeamsOnly ではないSkype for Business Online に所属するユーザーを持つ既存のハイブリッド組織は、できるだけ早くこれらのユーザーを Teams のみモードにアップグレードすることに重点を置く必要があります。 TeamsOnly ではない Skype for Business *Online* に所属しているユーザーがまだ組織にある場合は、Microsoft が支援するアップグレードをスケジュールして、これらのユーザーを TeamsOnly に移行します。 **Microsoft Assisted のアップグレードは、Skype for Business Serverオンプレミスに所属しているユーザーには影響しません。** スケジュール通知は、オンラインでSkype for Business オンラインに所属するユーザーを持つハイブリッド顧客に事前に送信されます。TeamsOnly 以外のユーザーは Teams にアップグレードされます。

## <a name="about-shared-sip-address-space-functionality"></a>共有 SIP アドレス空間機能について

<a name="BKMK_Overview"> </a>

Skype for Business Serverと Teams のオンプレミス展開の間にハイブリッド接続を設定すると、一部のユーザーをオンプレミスに、一部のユーザーをオンラインでホームにすることができます。

この種類の構成は共有 SIP アドレス空間機能に依存しており、"分割ドメイン" とも呼ばれます。つまり、contoso.com などのドメインのユーザーは、次の図に示すように、オンプレミスと Teams のSkype for Business Serverを使用して分割されます。

![Skype for Business Hybrid接続 - 分割ドメイン。](../../sfbserver2019/media/plan-hybrid-connectivity-2019-1.png)

共有 SIP アドレス空間が構成されている場合:

- Azure Active Directory Connect は、オンプレミス ディレクトリを Microsoft 365 と同期するために使用されます。
- オンプレミスに所属するユーザーは、オンプレミスのSkype for Business サーバーと対話します。
- ホーム オンラインのユーザーは Teams とやり取りします。
- 両方の環境のユーザーは、相互に通信できます。
- オンプレミスの Active Directoryは権限があります。 すべてのユーザーを最初にオンプレミスの Active Directoryで作成し、次に Azure AD に同期する必要があります。 ユーザーをオンラインでホームする場合でも、最初にオンプレミス環境でユーザーを作成してから、ユーザーをオンラインに移動して、ユーザーがオンプレミス ユーザーによって検出可能であることを確認する必要があります。

ユーザーをオンラインに移動する前に、ユーザーに Teams ライセンスと Skype for Business Online (プラン 2) を割り当てる必要があります。 **Skype for Business Online ライセンスの割り当ては、Skype for Business Online の終了後も必要です。** ユーザーが電話会議や電話システムなどの追加のオンライン機能を利用する場合は、Microsoft 365 で適切なライセンスを割り当てる必要があります。

## <a name="hybrid-connectivity-infrastructure-requirements"></a>ハイブリッド接続インフラストラクチャの要件

<a name="BKMK_Infrastructure"> </a>

オンプレミス環境と Microsoft 365 通信サービスの間にハイブリッド接続を実装するには、次のインフラストラクチャ要件を満たす必要があります。

- サポートされているトポロジに展開される、Skype for Business Serverまたは Lync Server の単一のオンプレミス展開。 このトピックの [トポロジ要件](plan-hybrid-connectivity.md#BKMK_Topology) に関する記事を参照してください。

- Teams を使用する Microsoft 365 組織。
    > [!NOTE]
    > オンプレミスのデプロイでは、ハイブリッド構成に 1 つのテナントのみを使用できます。
    
- オンプレミス ディレクトリを Microsoft 365 と同期する Azure Active Directory Connect。 AADConnect サービス アカウントの詳細については、「[Azure AD Connect: アカウントとアクセス許可](/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions)」を参照してください。

- 管理ツールをSkype for Business Serverします。 これらは、ユーザーをオンプレミスからクラウドに移動するために必要です。 これらのツールは、オンプレミスの展開とインターネットの両方にアクセスできるサーバーにインストールする必要があります。
- オンライン管理ツール。 Teams 管理センターまたはWindows PowerShellを使用して Teams を管理できます。 PowerShell を使用して Teams を管理するには、Teams PowerShell モジュールをダウンロードしてインストールします。 (Skype for Business オンライン コネクタは廃止されました)。
- 共有 SIP アドレス空間を有効にする必要があり、ホスティング プロバイダーとして Microsoft 365 を使用するようにオンプレミス展開を構成する必要があります。 ハイブリッド接続を構成するために必要な手順の詳細については、「ハイブリッド接続の [構成」を](configure-hybrid-connectivity.md)参照してください。

ハイブリッド接続を構成した後、ユーザーを Teams に移動できます。 詳細については、「ユーザーを [オンプレミスから Teams に移動する](move-users-from-on-premises-to-teams.md)」を参照してください。

## <a name="server-version-requirements"></a>サーバーのバージョン要件

<a name="BKMK_Topology"> </a>

**Teams** とのハイブリッド用にデプロイを構成するには、次のサポートされているトポロジのいずれかが必要です。

- Skype for Business Server 2019 の展開には、Skype for Business Server 2019 を実行するすべてのサーバーが含まれています。
- Skype for Business Server 2015 の展開には、Skype for Business Server 2015 を実行するすべてのサーバーが含まれています。
- Lync Server 2013 を実行しているすべてのサーバーを含む Lync Server 2013 の展開。  ただし、ハイブリッド音声接続が必要な場合は、以下に示すように、混合バージョンのトポロジを使用する必要があります。
- 次に示すように、最大 2 つの異なるサーバー バージョンのデプロイ。
  - Skype for Business Server 2015 および Skype for Business Server 2019
  - Lync Server 2013 および Skype for Business Server 2019
  - Lync Server 2013 および Skype for Business Server 2015
- 2022 年 7 月 31 日の時点で、オンプレミスの展開とクラウドの間でユーザーを移動するには、次の最小バージョンのSkype for Business Serverまたは Lync Server を使用している必要があります。
</br>

|オンプレミス製品|必要な最小バージョン|必要な最小ビルド|
|---|---|---|
|Skype for Business Server 2019| CU6 |7.0.2046.385|
|Skype for Business Server 2015| CU12|6.0.9319.619|
|Lync Server 2013| 修正プログラム 7 を使用した CU10|5.0.8308.1182|

</br>

> [!NOTE] 
> Lync Server 2010 は Teams ではサポートされていません。


## <a name="multi-forest-support"></a>複数フォレストのサポート

<a name="BKMK_MultiForest"> </a>

Microsoft では、次の種類のマルチフォレスト ハイブリッド シナリオがサポートされています。

- **リソース フォレスト トポロジ** この種のトポロジでは、Skype for Business Server (リソース フォレスト) をホストする 1 つのフォレストと、リソース フォレスト内のSkype for Business Serverにアクセスするアカウント ID をホストする追加のフォレストが 1 つ以上存在します。 一般に、次の要件が満たされている場合、ユーザーは別のフォレストの Skype for Business 機能にアクセスできます。
  - ユーザーは、Skype for Business をホストするフォレストに適切に同期されます。 ハイブリッド構成では、これは、ユーザーを無効なユーザー オブジェクトとして同期する必要があることを意味します。
  - Skype for Business をホストするフォレストは、ユーザーを含むフォレストを信頼する必要があります。
    リソース フォレストハイブリッドシナリオの詳細については、「[ハイブリッド Skype for Business用のリソース フォレスト トポロジをデプロイする」を](configure-a-multi-forest-environment-for-hybrid.md)参照してください。

- **複数のフォレストでのSkype for Business Serverの複数のデプロイ。** この構成は、合併と買収のシナリオや、より複雑な企業の結果として発生する可能性があります。 1 つの Microsoft 365 組織のオンプレミスからクラウドへのすべてのユーザーの統合は、次の主要な要件が満たされていれば、複数のSkype for Business展開を持つ組織に対して実現できます。
  - 最大で 1 つの Microsoft 365 組織が関係している必要があります。 複数の組織を持つシナリオでの統合はサポートされていません。
  - いつでも、ハイブリッド モードにできるオンプレミスの Skype for Business フォレストは 1 つ (共有 SIP アドレス スペース) のみです。 他のすべてのオンプレミス Skype for Business フォレストは、完全にオンプレミスのままである必要があります (おそらく相互にフェデレーションされている)。 これらの他のオンプレミス組織は、必要に応じて AAD と同期し、2018 年 12 月時点で利用可能な [オンライン SIP ドメインを無効にする新機能](/powershell/module/skype/disable-csonlinesipdomain) を使用できることに注意してください。

    複数のフォレストにSkype for Businessを展開しているお客様は、分割ドメイン (共有 SIP アドレス空間) 機能を使用して、各Skype for Business フォレストを Microsoft 365 組織に完全に移行する必要があります。 フォレストの移行が完了したら、次のオンプレミスのSkype for Business展開を移行する前に、オンプレミスのデプロイでハイブリッドを無効にする必要があります。 さらに、クラウドに移行する前は、オンプレミスユーザーは、同じユーザーのオンプレミス ディレクトリに表されていないすべてのユーザーとフェデレーション状態のままです。 詳細については、「[Teams とSkype for Businessのクラウド統合](cloud-consolidation.md)」を参照してください。

## <a name="federation-requirements"></a>フェデレーションの要件

<a name="BKMK_Federation"> </a>

ハイブリッド モードSkype for Business構成する場合は、オンプレミス環境とオンライン環境が相互にフェデレーションできることを確認する必要があります。  既定では、オンライン環境はフェデレーションを開いています。オンプレミス環境では、多くの場合、既定でフェデレーションが閉じられています。  

ハイブリッドデプロイを正常に構成するには、次の要件を満たす必要があります。

- ドメイン一致は、オンプレミスの展開と Microsoft 365 組織で同じように構成する必要があります。 オンプレミスの展開でパートナー検出が有効になっている場合は、オンライン組織用にオープン フェデレーションを構成する必要があります。 パートナー検出が有効になっていない場合は、オンライン組織に対してクローズド フェデレーションを構成する必要があります。
- オンプレミス展開の [ブロックされたドメイン] の一覧は、オンライン テナントの [ブロックされたドメイン] の一覧と完全に一致している必要があります。
- オンプレミス展開の [許可されたドメイン] の一覧は、オンライン テナントの [許可されたドメイン] の一覧と完全に一致している必要があります。
- フェデレーションは、オンライン テナントの外部通信に対して有効にする必要があります。

## <a name="network-considerations"></a>ネットワークの考慮事項

次のセクションでは、次の点に関する考慮事項について説明します。

- DNS 設定
- ファイアウォールに関する考慮事項

### <a name="dns-settings-for-hybrid-deployments"></a>ハイブリッド展開の DNS 設定

<a name="BKMK_DNS"> </a>

ハイブリッド展開用の DNS レコードを作成する場合、すべての Skype for Business 外部 DNS レコードはオンプレミス インフラストラクチャを指す必要があります。 必要な DNS レコードの詳細については、[Skype for Business Serverの DNS 要件を](../../sfbserver/plan-your-deployment/network-requirements/dns.md)参照してください。

さらに、次の表に示す DNS 解決がオンプレミスの展開で機能することを確認する必要があります。 (オンプレミスのフェデレーションを既に構成している場合は、おそらく既にこれらを持っています)。

|DNS レコード  <br/> |以下で解決可能  <br/> |DNS 要件  <br/> |
|:-----|:-----|:-----|
|_sipfederationtls._tcp の DNS SRV レコード。\<sipdomain.com\> Access Edge 外部 IP に解決されるすべてのサポートされている SIP ドメインについて  <br/> |Edge サーバー  <br/> |ハイブリッド構成でフェデレーション通信を有効にします。 エッジ サーバーは、オンプレミスとオンラインの間で分割されている SIP ドメインのフェデレーション トラフィックをルーティングする場所を把握する必要があります。  <br/> ユーザー名と SRV レコード内のドメイン間で一致する厳密な DNS 名を使用する必要があります。  <br/> |
|エッジ Web 会議サービス FQDN の DNS A レコード(例: Web 会議エッジの外部 IP への解決 webcon.contoso.com)  <br/> |内部企業ネットワーク接続ユーザーのコンピューター  <br/> |オンライン ユーザーがオンプレミスのホストされた会議でコンテンツを表示または表示できるようにします。 コンテンツには、PowerPoint ファイル、ホワイトボード、投票、共有ノートが含まれます。  <br/> |

組織での DNS の構成方法によっては、これらのレコードに内部 DNS 解決を提供するために、対応する SIP ドメインの内部ホスト型 DNS ゾーンにこれらのレコードを追加する必要がある場合があります。

### <a name="firewall-considerations-for-hybrid-deployments"></a>ハイブリッド展開に関するファイアウォールに関する考慮事項

<a name="BKMK_Firewall"> </a>

ネットワーク上のコンピューターは、標準のインターネット DNS 参照を実行できる必要があります。これらのコンピューターが標準のインターネット サイトに接続できれば、ネットワークはこの要件を満たしています。

Microsoft Online Services データ センターの場所に応じて、ワイルドカード ドメイン名 (.outlook.com からの \*トラフィックなど) に基づいて接続を受け入れるようにネットワーク ファイアウォール デバイスを構成する必要もあります。 組織のファイアウォールでワイルドカード名の構成がサポートされていない場合は、許可する IP アドレス範囲と指定したポートを手動で決定する必要があります。

ポートとプロトコル要件の詳細を含む詳細については、 [Microsoft 365 の URL と IP アドレス範囲](/microsoft-365/enterprise/urls-and-ip-address-ranges)に関するページを参照してください。
