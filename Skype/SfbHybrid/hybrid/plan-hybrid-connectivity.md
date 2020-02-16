---
title: ハイブリッド接続を計画する |Skype for Business Server 2019 Office 365 の統合
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
description: Skype for Business Server と Skype for business Online または Teams 間でハイブリッド接続を実装するための計画に関する考慮事項。
ms.openlocfilehash: 1a1513b307c6f55f6b403a0d5db85ac14d1f7a6f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043379"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-office-365"></a>Skype for Business Server と Office 365 の間のハイブリッド接続を計画する

## <a name="overview"></a>概要

このトピックでは、Skype for Business Server と Teams または Skype for Business Online 間のハイブリッド接続を計画する方法について説明します。 オンプレミス環境をクラウドに移動するための最初のステップは、ハイブリッド接続のセットアップです。

オンプレミスの Skype for Business ユーザーが Teams も並行して使用している場合、これらのユーザーは、Teams クライアントから Skype for Business ユーザーと相互運用することも、Teams クライアントからフェデレーション組織内のユーザーと通信することもできません。 Teams でこの機能を使用できるようにするには、これらのユーザーを Skype for Business オンプレミスからクラウドに移動する必要があります。このためには、Skype for Business ハイブリッド モードを構成する必要があります。 さらに、最適な結果を得るために、これらのユーザーは Teams Only モードにする必要があります。これにより、すべてのユーザーの着信呼び出しとチャットがユーザーの Teams クライアントに配置されます。

また、オンプレミスの Skype for Business 展開を停止する前に、ハイブリッド接続をセットアップして、すべてのユーザーをクラウドに移行する必要があります。  ハイブリッド接続を使用すると、自分のスケジュールとビジネス ニーズに基づいてユーザーをクラウドに移行させるよう選択できます。 ダイレクト ルーティングを使用すると、クラウドへの移行の間および移行の完了後も、オンプレミスの音声インフラストラクチャを活用することができます。

このトピックでは、既存のオンプレミスの Skype for Business Server の展開と Teams または Skype for Business Online との間でハイブリッド接続を構成するために必要なインフラストラクチャとシステム要件について説明します。

このトピックを読み、ハイブリッド接続を構成する準備ができたら、「 [configure hybrid connectivity Between Skype For Business Server And Office 365](configure-hybrid-connectivity.md)」を参照してください。 構成に関するトピックでは、オンプレミスの展開と Teams または Skype for Business Online 間でハイブリッド接続をセットアップするための手順について説明します。

## <a name="about-shared-sip-address-space-functionality"></a>共有 SIP アドレススペース機能について

<a name="BKMK_Overview"> </a>

 ハイブリッド接続が Skype for business Server と Teams または Skype for Business Online の社内展開との間で設定されている場合、一部のユーザーをオンプレミスに所属させることができます。また、一部のユーザーはオンラインに所属しています。

この種類の構成は、共有 SIP アドレススペース機能に依存します。また、contoso.com などのドメインのユーザーが、社内の Skype for Business Server と Teams または Skype for business を使用して分割される場合もあります。次の図に示すように、オンラインにします。

![SfB ハイブリッド接続-分割ドメイン](../../sfbserver2019/media/plan-hybrid-connectivity-2019-1.png)

共有 SIP アドレススペースが構成されている場合:

- Azure Active Directory Connect は、オンプレミスディレクトリと Office 365 を同期するために使用されます。
- オンプレミスに所属するユーザーは、オンプレミスの Skype for Business サーバーと対話します。
- オンラインに所属しているユーザーは、Skype for Business Online または Teams サービスと対話することができます。
- 両方の環境のユーザーは相互に通信できます。
- オンプレミスの Active Directory は、権限があります。 最初にすべてのユーザーをオンプレミスの Active Directory に作成してから、Azure AD に同期する必要があります。 ユーザーがオンラインになることを意図している場合でも、ユーザーをオンプレミス環境で作成し、ユーザーをオンラインに移動して、ユーザーがオンプレミスのユーザーによって検出可能になるようにする必要があります。

ユーザーをオンラインで移動できるようにするには、ユーザーに Skype for Business Online (Plan 2) ライセンスが割り当てられている必要があります。 ユーザーが Teams を使用する場合は、ユーザーに Teams のライセンスが割り当てられている必要があります (また、Skype for Business ライセンスが有効なままになっている必要があります)。 ユーザーが電話会議や電話システムなどの他のオンライン機能を利用する場合は、Office 365 で適切なライセンスを割り当てる必要があります。

## <a name="infrastructure-requirements"></a>インフラストラクチャの要件

<a name="BKMK_Infrastructure"> </a>

オンプレミス環境と Office 365 コミュニケーションサービスとの間にハイブリッド接続を実装するには、次のインフラストラクチャ要件を満たす必要があります。

- サポートされているトポロジに展開されている Skype for Business Server または Lync Server の単一のオンプレミス展開。 このトピックの「[トポロジ要件](plan-hybrid-connectivity.md#BKMK_Topology)」を参照してください。
- Skype for Business Online が有効になっている Microsoft Office 365 テナント。
    > [!NOTE]
    > オンプレミス展開のハイブリッド構成では、1つのテナントのみを使用できます。
- オンプレミスのディレクトリを Office 365 と同期するには、Azure Active Directory Connect を使用します。 詳細については、「 [AZURE AD Connect: Accounts and permissions](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions)」を参照してください。
- Skype for Business Server の管理ツール。  これらは、オンプレミスからクラウドにユーザーを移動するために必要です。 これらのツールは、オンプレミスの展開とインターネットにアクセスできるサーバーにインストールする必要があります。
- オンライン管理ツール。  Teams 管理センターまたは Windows PowerShell を使用して、Teams と Skype for Business Online を管理することができます。 PowerShell を使用して Teams または Skype for Business Online のいずれかを管理するには、Skype for Business Online コネクタをダウンロードしてインストールします。
- 共有 SIP アドレススペースが有効になっており、オンプレミス展開が Office 365 をホスティングプロバイダーとして使用するように構成されている必要があります。 ハイブリッド接続を構成するために必要な手順の詳細については、「 [configure hybrid connectivity](configure-hybrid-connectivity.md)」を参照してください。

ハイブリッド接続を構成した後、ユーザーを Teams または Skype for business Online に移動することができます。 詳細については、「[オンプレミスから Teams へのユーザーの移動](move-users-from-on-premises-to-teams.md)」および「[オンプレミスから Skype for business Online へのユーザーの移動](move-users-from-on-premises-to-skype-for-business-online.md)」を参照してください。

## <a name="server-version-requirements"></a>サーバーバージョンの要件

<a name="BKMK_Topology"> </a>

**Teams または Skype For Business Online**とのハイブリッドの展開を構成するには、次のサポートされているトポロジのいずれかを使用する必要があります。

- Skype for business Server 2019 を Skype for business Server 2019 を実行しているすべてのサーバーと共に展開します。
- Skype for business Server 2015 を Skype for business Server 2015 を実行しているすべてのサーバーと共に展開します。
- Lync server 2013 を実行して2013いるすべてのサーバーでの Lync Server の展開。  ただし、ハイブリッド音声接続が必要な場合は、以下に示すように、混合バージョントポロジを使用する必要があります。
- 次のリストに示すように、最大2つの異なるサーバーバージョンを持つ展開。
  - Skype for Business Server 2015 と Skype for business Server 2019
  - Lync Server 2013 および Skype for Business Server 2019
  - Lync Server 2013 および Skype for Business Server 2015

*任意のトポロジでハイブリッド音声が必要な場合*は、フェデレーションエッジとして指定されているエッジサーバーと、SIP フェデレーションに関連付けられているプールの両方が、Skype for business 2015 以降を実行している必要があります。 ユーザーは Lync 2013 プールが存在する場合は、そのままにしておくことができます。 詳細については、「 [Plan Phone System WITH PSTN Connectivity In Skype For Business Server](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)」を参照してください。

Lync Server 2010 を含む次のトポロジは、インスタントメッセージングおよび会議用の**Skype For Business Online でサポートされて**います。  **Lync Server 2010 を含むトポロジは、ハイブリッド音声または Teams ではサポートされていません**。

- 異種 Lync Server 2010 と Skype for Business Server 2015 の展開
- Lync Server 2010 と Lync Server 2013 の混在した展開
- Lync server 2010 の展開は、最新の累積的な更新プログラムを適用して Lync Server 2010 を実行しているすべてのサーバーに適用されます。

フェデレーションエッジサーバーおよびフェデレーションエッジサーバーの次ホップサーバーは、最新の累積更新プログラムを使用して Lync Server 2010 を実行している必要があります。 Skype for Business Server 2015 または Lync Server 2013 の管理ツールは、少なくとも1つのサーバーまたは管理ワークステーションにインストールする必要があります。

## <a name="multi-forest-support"></a>複数フォレストのサポート

<a name="BKMK_MultiForest"> </a>

Microsoft では、次の種類の複数フォレストハイブリッドシナリオをサポートしています。

- **リソースフォレストのトポロジ。** この種類のトポロジでは、Skype for Business Server (リソースフォレスト) をホストするフォレストが1つあり、アカウント id をホストする1つまたは複数の追加フォレストがあります。これにより、リソースフォレスト内の Skype for Business サーバーにアクセスできます。 一般に、次の要件が満たされている場合、ユーザーは別のフォレストの Skype for Business 機能にアクセスできます。
  - ユーザーは、Skype for Business をホストするフォレストに適切に同期されます。 ハイブリッド構成では、ユーザーが無効なユーザーオブジェクトとして同期されている必要があります。
  - Skype for Business をホストするフォレストは、ユーザーを含むフォレストを信頼する必要があります。
    リソースフォレストのハイブリッドシナリオの詳細については、「 [Deploy a resource forest topology for Hybrid Skype For business](configure-a-multi-forest-environment-for-hybrid.md)」を参照してください。
- **複数のフォレストで Skype for Business Server を複数配置している。** この構成は、合併および買収のシナリオや、より複雑な企業のために発生する可能性があります。  次の主要な要件が満たされている場合は、複数の Skype for Business 展開がある組織では、オンプレミスのすべてのユーザーを1つの Office 365 テナント内のクラウドに統合することができます。

  - 関係する Office 365 テナントは 1 つでなければなりません。 複数の Office 365 テナントが関係するシナリオでの統合はサポートされていません。
  - 任意の時点で、オンプレミスの Skype for Business フォレストは1つだけ、ハイブリッドモード (共有 SIP アドレススペース) にすることができます。 その他のすべてのオンプレミス Skype for Business フォレストは、完全にオンプレミスのままにしておく必要があります (また、互いにフェデレーションが可能な場合があります)。 これらの他のオンプレミス組織は、必要な場合には 2018 年 12 月以降使用可能になっているオンライン SIP ドメインを無効にする新しい機能を使用して、AAD と同期[できます](https://docs.microsoft.com/powershell/module/skype/disable-csonlinesipdomain)。

    複数のフォレストに Skype for Business を展開しているお客様は、分割ドメイン (共有 SIP アドレススペース) 機能を使用して、各 Skype for Business フォレストを個別に Office 365 テナントに完全に移行する必要があります。その後、オンプレミス展開では、次のオンプレミスの Skype for Business 展開を移行する前に、に移動します。 さらに、クラウドに移行する前に、オンプレミスのユーザーは、同じユーザーのオンプレミスのディレクトリに表示されていないすべてのユーザーと共にフェデレーション状態のままになります。 詳細については、「 [Teams と Skype for business のクラウド統合](cloud-consolidation.md)」を参照してください。

## <a name="federation-requirements"></a>フェデレーション要件

<a name="BKMK_Federation"> </a>

ハイブリッドを構成する場合は、オンプレミスの環境とオンライン環境が相互にフェデレーションできるようにする必要があります。  オンライン環境では、既定でフェデレーションが開かれています。多くの場合、オンプレミスの環境では、フェデレーションが既定で閉じられています。  

ハイブリッド展開を正しく構成するには、次の要件を満たす必要があります。

- オンプレミス展開と Office 365 テナントでは、ドメインの一致が同じように構成されている必要があります。 オンプレミス展開でパートナー検出が有効になっている場合は、オンラインテナントに対してオープンフェデレーションを構成する必要があります。 パートナー検出が有効になっていない場合は、オンラインテナント用に閉じられたフェデレーションを構成する必要があります。
- オンプレミス展開の禁止ドメインリストは、オンラインテナントの禁止ドメインリストと正確に一致する必要があります。
- オンプレミス展開の許可ドメインリストは、オンラインテナントの許可されたドメインリストと正確に一致している必要があります。
- オンラインテナントの外部通信に対してフェデレーションを有効にする必要があります。

## <a name="network-considerations"></a>ネットワークの考慮事項

次のセクションでは、の考慮事項について説明します。

- DNS 設定
- ファイアウォールに関する考慮事項

### <a name="dns-settings"></a>DNS 設定

<a name="BKMK_DNS"> </a>

ハイブリッド展開用の DNS レコードを作成する場合、すべての Skype for Business の外部 DNS レコードは、オンプレミスのインフラストラクチャをポイントする必要があります。 必要な DNS レコードの詳細については、「 [Skype For Business Server の dns 要件](../../sfbserver/plan-your-deployment/network-requirements/dns.md)」を参照してください。

また、次の表に記載されている DNS 解決がオンプレミス展開でも動作することを確認する必要があります。 (既にオンプレミスのフェデレーションを構成している場合は、既にこれらが用意されている可能性があります)。

|DNS レコード  <br/> |解決方法  <br/> |DNS 要件  <br/> |
|:-----|:-----|:-----|
|_Sipfederationtls _tcp の DNS SRV レコード。\<エッジ\>の外部 IP へのアクセスを解決するための、サポートされているすべての SIP ドメインの sipdomain.com  <br/> |エッジサーバー  <br/> |ハイブリッド構成でフェデレーション通信を有効にします。 エッジサーバーは、オンプレミスとオンラインの間で分割されている SIP ドメインのフェデレーショントラフィックをルーティングする場所を知っている必要があります。  <br/> ユーザー名と SRV レコードのドメイン間で厳密な DNS 名の一致を使用する必要があります。  <br/> |
|エッジ Web 会議サービス FQDN 用の DNS A レコード (webcon.contoso.com、Web 会議エッジ外部 IP への解決など)  <br/> |内部の企業ネットワークに接続されたユーザーのコンピューター  <br/> |オンラインユーザーがオンプレミスでホストされている会議のコンテンツを表示または表示できるようにします。 コンテンツには、PowerPoint ファイル、ホワイトボード、投票、および共有メモが含まれます。  <br/> |

組織での DNS の構成方法によっては、これらのレコードを対応する SIP ドメインの内部ホスト DNS ゾーンに追加して、これらのレコードに対する内部 DNS 解決を提供する必要がある場合があります。

### <a name="firewall-considerations"></a>ファイアウォールに関する考慮事項

<a name="BKMK_Firewall"> </a>

ネットワーク上のコンピューターは、標準のインターネット DNS 参照を実行できる必要があります。これらのコンピューターが標準のインターネット サイトに接続できれば、ネットワークはこの要件を満たしています。

Microsoft Online Services データセンターの場所によっては、ネットワークファイアウォールデバイスが、ワイルドカードドメイン名 (たとえば、outlook.com から\*のすべてのトラフィック) に基づいて接続を受け入れるように構成する必要もあります。 組織のファイアウォールがワイルドカード名の構成をサポートしていない場合は、許可する IP アドレスの範囲と指定されたポートを手動で決定する必要があります。

ポートとプロトコルの要件に関する詳細を含む詳細については、「 [Office 365 の url と IP アドレスの範囲](https://go.microsoft.com/fwlink/p/?LinkId=252942)」を参照してください。
