---
title: 'Lync Server 2013: モビリティの技術要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for mobility
ms:assetid: 831be681-4de0-4e42-b04f-8879ca4dcd23
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690030(v=OCS.15)
ms:contentKeyID: 48184679
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8df94773a551ee503ac435af8f31d0104dc38aa
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536144"
---
# <a name="technical-requirements-for-mobility-in-lync-server-2013"></a>Lync Server 2013 でのモビリティの技術要件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-07-24_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

モバイル ユーザーは、特別な計画を必要とするさまざまなモバイル アプリケーション シナリオに直面します。 たとえば、ユーザーが3G ネットワーク経由で接続することによってモバイルアプリケーションの使用を開始して、職場に到着したときに会社の Wi-Fi ネットワークに切り替えた後、建物を離れたときに3G に戻ることがあります。 このようなネットワークの移行をサポートし、一貫したユーザー エクスペリエンスを確保するように、環境を計画する必要があります。 このセクションでは、モバイルアプリケーションとモビリティリソースの自動検出をサポートするために必要なインフラストラクチャ要件について説明します。

<div>


> [!NOTE]  
> モバイルアプリケーションは他の Lync Server 2013 サービスに接続することもできますが、すべてのモバイルアプリケーション web 要求を同じ外部 web 完全修飾ドメイン名 (FQDN) に送信するための要件は、Lync Server 2013 Mobility Service にのみ適用されます。 その他のモビリティサービスでは、この構成は必要ありません。



</div>

ハードウェアロードバランサーの cookie アフィニティの要件は大幅に減少しており、Lync Server 2013 で配信された Lync Mobile を使用している場合は、伝送制御プロトコル (TCP) の類似性を代用します。 Cookie の類似性を使用することはできますが、web サービスで不要になったことはありません。

<div>


> [!IMPORTANT]  
> すべての Mobility Service トラフィックは、発信元の場所に関係なく、リバースプロキシを経由します (内部または外部)。 単一のリバースプロキシまたはリバースプロキシのファームの場合、またはリバースプロキシ機能を提供するデバイスの場合、内部トラフィックがインターフェイスを介して egressing され、同じインターフェイス上ですぐに受信しようとすると、問題が発生することがあります。 これは、多くの場合、TCP パケットスプーフィングまたはスプーフィングのみというセキュリティ規則違反につながります。 モビリティーを機能させるには、<EM>ヘアピン</EM>(パケットまたは一連のパケットの出口と即時入力) を許可する必要があります。 この問題を解決する方法の1つは、ファイアウォールとは別のリバースプロキシを使用することです (スプーフィング防止ルールは、セキュリティ上の理由から、必ずファイアウォールで常に適用する必要があります)。 ヘアピンは、ファイアウォールの外部インターフェイスではなく、リバースプロキシの外部インターフェイスで発生する可能性があります。 ファイアウォールでスプーフィングを検出し、リバースプロキシでルールを緩和して、モビリティに必要なヘアピンを許可します。<BR>可能であれば、ドメインネームシステム (DNS) ホストまたは CNAME レコードを使用して、ヘアピンの動作 (ファイアウォールではない) のリバースプロキシを定義します。



</div>

Lync Server 2013 は、Lync 2010 Mobile および Lync 2013 モバイルクライアントの mobility service をサポートしています。 両方のクライアントは、Lync Server 2013 の自動検出サービスを使用して、そのモビリティエントリポイントを見つけますが、使用する mobility service は異なります。 Lync 2010 Mobile は *Mcx*と呼ばれる Mobility Service を使用します。これは、lync Server 2010 用の累積的な更新プログラム (11 月 11 2011 日) で導入されました。 Lync 2013 mobile クライアントは、mobility service プロバイダーとして統合コミュニケーション Web API または *Ucwa*を使用します。

<div>

## <a name="internal-and-external-dns-configuration"></a>内部および外部 DNS の構成

Mobility Service Mcx (Lync Server 2010:11 月 2011) および UCWA (Lync Server 2013 の累積的な更新プログラムで導入されました。 2 2013 月2日) は同じ方法で DNS を使用します。

自動検出を使用する場合、モバイルデバイスは、DNS を使用してリソースを検索します。 DNS 参照中に、内部 DNS レコード (lyncdiscoverinternal) に関連付けられている FQDN への接続が最初に試行され \<internal domain name\> ます。 内部 DNS レコードを使用して接続を確立できない場合は、外部 DNS レコード (lyncdiscover) を使用して接続が試行され \<sipdomain\> ます。 ネットワークの内部にあるモバイル デバイスは内部自動検出サービス URL に接続し、ネットワークの外部にあるモバイル デバイスは自動検出サービスの外部 URL に接続します。 外部自動検出要求はリバースプロキシを経由します。 Lync Server 2013 自動検出サービスは、Mobility Service (Mcx および UCWA) Url を含む、ユーザーのホームプールのすべての Web サービス Url を返します。 ただし、Mobility Service の内部 URL と Mobility Service の外部 URL は共に Web サービスの外部 FQDN に関連付けられます。 したがって、モバイルデバイスがネットワークの内部と外部のどちらにあるかに関係なく、デバイスは常に、リバースプロキシを介して外部で Lync Server 2013 Mobility Service に接続します。

<div>


> [!NOTE]  
> 展開には、内部および外部での複数の異なる名前空間を含めることができることを理解しておくことが重要です。 SIP ドメイン名は、内部展開ドメイン名とは異なる場合があります。 たとえば、自分の SIP ドメインは <STRONG>contoso.com</STRONG>の場合もありますが、内部展開は <STRONG>contoso.net</STRONG>の場合があります。 Lync Server にログインするユーザーは、 <STRONG>john@contoso.com</STRONG>などの SIP ドメイン名を使用します。 (トポロジビルダーで <STRONG>外部 web サービス</STRONG>として定義されている) 外部 web サービスにアドレス指定する場合、ドメイン名と SIP ドメイン名は、DNS での定義に従って一貫性が保たれます。 内部 web サービス (トポロジビルダーで <STRONG>内部 web サービス</STRONG>として定義されている) に対処する場合、内部 web サービスの既定の名前は、フロントエンドサーバー、フロントエンドプール、ディレクター、またはディレクタープールの FQDN になります。 [内部 web サービス名] を無効にすることもできます。 内部 web サービスの場合は、(SIP ドメイン名ではなく) 内部ドメイン名を使用し、上書きされた名前を反映する DNS ホスト A (または IPv6 の場合は AAAA) レコードを定義する必要があります。 たとえば、既定の内部 web サービスの FQDN は <STRONG>pool01.contoso.net</STRONG>の場合があります。 オーバーライドされた内部 web サービスの FQDN は <STRONG>webpool.contoso.net</STRONG>の場合があります。 この方法で web サービスを定義することにより、サービスの内部および外部の局所性と、それらを使用しているユーザーの局所性を確保することができます。<BR>ただし、トポロジビルダーでは web サービスが定義されており、結果の web サービス名、証明書を検証する証明書、およびそれを定義する DNS レコードが一貫している限り、内部 web サービスを任意のドメイン名 (SIP ドメイン名を含む) で定義することができます。 最終的には、IP アドレスに対する名前の解決は、DNS ホストレコードと一貫した名前空間によって決まります。<BR>このトピックと例の目的のために、内部ドメイン名を使用してトポロジと DNS 定義を示します。



</div>

次の図は、内部および外部の DNS 構成を使用する場合の、Mobility Service および自動検出サービスのモバイルアプリケーション web 要求のフローを示しています。

**自動検出を使用したモビリティサービスフロー**

![cdb96424-96f2-4abf-88d7-1d32d1010ffd](images/Hh690030.cdb96424-96f2-4abf-88d7-1d32d1010ffd(OCS.15).jpg "cdb96424-96f2-4abf-88d7-1d32d1010ffd")

<div>


> [!NOTE]  
> この図は、一般的な web サービスを示しています。 Mobility という名前の仮想ディレクトリは、Mobility services Mcx および/または UCWA を示しています。 Lync Server 2013 の累積的な更新プログラム (2013 年2月) を適用していない場合は、内部および外部の Web サービスで仮想ディレクトリ Ucwa が定義されていないことがあります。 仮想ディレクトリの自動検出があり、仮想ディレクトリに Mcx がある場合があります。<BR>展開したモビリティサービステクノロジに関係なく、自動検出とサービスの検出は同じように機能します。



</div>

社内ネットワークの内側と外側からのモバイル ユーザーをサポートするには、内部と外部の Web FQDN について、いくつかの前提条件が満たされる必要があります。また、実装するように選択した機能に応じて、他の要件を満たすことが必要になる場合もあります。

  - 自動検出のための新しい DNS、CNAME または A (host、if IPv6、AAAA) レコード。

  - 新しいファイアウォールルール。 Wi-Fi ネットワーク経由でプッシュ通知をサポートする場合。

  - 内部サーバー証明書およびリバースプロキシ証明書のサブジェクトの別名 (自動検出用)。

  - フロントエンドサーバーのハードウェアロードバランサーの構成変更ソースの類似性。

Mobility Service および自動検出サービスをサポートするためには、トポロジが次の要件を満たしている必要があります。

  - フロントエンドプールの内部 web FQDN は、フロントエンドプールの外部 web FQDN とは別のものにする必要があります。

  - 内部 Web FQDN は、社内ネットワークにのみ解決し、社内ネットワークの内側からのみアクセスできる必要があります。

  - 外部 web FQDN は、インターネットからのみ解決し、インターネットからアクセスできるようにする必要があります。

  - 社内ネットワークの内側にいるユーザーの場合、Mobility Service の URL は、外部 Web FQDN にアドレス指定される必要があります。この要件は Mobility Service 向けであり、この URL にのみ適用されます。

  - 企業ネットワークの外部にいるユーザーの場合、要求はフロントエンドプールまたはディレクターの外部 web FQDN に送られる必要があります。

自動検出をサポートする場合、SIP ドメインごとに以下の DNS レコードを作成する必要があります。

  - 組織のネットワーク内から接続するモバイルユーザーをサポートするための内部 DNS レコード。

  - インターネットから接続するモバイルユーザーをサポートするための外部 (パブリック) DNS レコード。

内部の自動検出 URL は、ネットワークの外部からアドレス指定できません。 外部自動検出 URL は、ネットワーク内からアドレス指定できません。 ただし、外部 URL に対してこの要件を満たしていない場合は、常に内部 URL が最初に試行されるので、モバイルクライアントの機能に影響を与えることはありません。

DNS レコードは、CNAME レコードまたは A (IPv6、AAAA の場合は host) レコードのいずれかにすることができます。

<div>


> [!NOTE]  
> モバイル デバイスのクライアントでは、異なるドメインからの複数の SSL (Secure Sockets Layer) 証明書がサポートされません。 つまり、HTTPS では、異なるドメインへの CNAME のリダイレクトがサポートされません。 たとえば、director.contoso.net のアドレスにリダイレクトされる lyncdiscover.contoso.com の DNS CNAME レコードは、HTTPS ではサポートされません。 このようなトポロジでは、CNAME のリダイレクトが HTTP で解決されるように、モバイル デバイスのクライアントは、最初の要求に対して HTTP を使用する必要があります。 その後、以降の要求については HTTPS を使用します。 このシナリオをサポートするには、ポート 80 (HTTP) の Web 公開ルールを使用して、リバース プロキシを構成する必要があります。 詳細については、「 <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Lync Server 2013 でモビリティのリバースプロキシを構成</A>する」の「ポート80の web 公開ルールを作成するには」を参照してください。<BR>HTTPS では、同じドメインへの CNAME のリダイレクトはサポートされます。 この例では、宛先ドメインの証明書が元のドメインを対象としています。



</div>

シナリオに必要な DNS レコードの詳細については、「 [dns の概要-Lync Server 2013 での自動検出](lync-server-2013-dns-summary-autodiscover.md)」を参照してください。

</div>

<div>

## <a name="port-and-firewall-requirements"></a>ポートとファイアウォールの要件

また、プッシュ通知をサポートし、Apple モバイル デバイスで Wi-Fi ネットワーク経由のプッシュ通知を受信する場合、社内の Wi-Fi ネットワークのポート 5223 も開く必要があります。 ポート 5223 は、送信 TCP ポートであり、Apple Push Notification Service (APNS) で使用されます。 モバイルデバイスが接続を開始します。 詳細については、「」を参照してください [http://support.apple.com/kb/TS1629](http://support.apple.com/kb/ts1629) 。

<div>


> [!WARNING]  
> Lync 2013 Mobile クライアントを使用している Apple デバイスでは、プッシュ通知は必要ありません。



</div>

ユーザーが存続可能ブランチアプライアンス (SBA) に所属している場合は、次のポートが必要です。

  - Ucの Ipexternallisteningport にはポート5088が必要です

  - Ucは、ポート5089を必要とします。

自動検出のポートとプロトコルの要件の詳細とガイダンスについては、「 [port summary-Lync Server 2013 での自動検出](lync-server-2013-port-summary-autodiscover.md)」を参照してください。

</div>

<div>

## <a name="certificate-requirements"></a>証明書の要件

Lync モバイル クライアントに対して自動検出をサポートする場合、証明書のサブジェクトの別名リストを変更し、モバイル クライアントからのセキュリティで保護された接続をサポートする必要があります。 自動検出サービスを実行するフロントエンドサーバーとディレクターごとに、新しい証明書を要求および割り当て、このセクションで説明するサブジェクトの別名エントリを追加する必要があります。 この方法として、リバース プロキシ用の証明書のサブジェクトの別名リストも変更することをお勧めします。 組織内のすべての SIP ドメインに対してサブジェクトの別名エントリを追加する必要があります。

通常、内部の証明機関を使用した証明書の再発行は簡単なプロセスですが、サブジェクトの複数の別名エントリを、リバース プロキシで使用されるパブリック証明書に追加するには、高い費用がかかる可能性があります。 多くの SIP ドメインがある場合 (サブジェクトの別名を追加する処理が非常に高価になります)、初期の自動検出サービス要求を、HTTPS を使用してポート 443 (既定の構成) で送信する代わりに、HTTP を使用してポート 80 で送信するようにリバース プロキシを構成できます。 その後、要求はディレクターまたはフロントエンドプールのポート8080にリダイレクトされます。 初期の自動検出サービス要求をポート 80 で発行すると、要求で HTTPS ではなく HTTP が使用されるため、リバース プロキシの証明書を変更する必要はありません。 この方法はサポートされていますが、お勧めしません。

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a>インターネット インフォメーション サービス (IIS) の要件

モバイル用に IIS 7.5、IIS 8.0、または IIS 8.5 を使用することをお勧めします。 Mobility Service installer は、パフォーマンスを向上させるために ASP.NET にフラグを設定します。 IIS 7.5 が既定でインストールされる Windows Server 2008 R2、IIS 8.0 は windows Server 2012 にインストールされ、IIS 8.5 は Windows Server 2012 R2 にインストールされます。 Mobility Service インストーラーは、ASP.NET の設定を自動的に変更します。

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a>ハードウェア ロード バランサーの要件

フロントエンドプールをサポートするロードバランサー機器で、Web サービストラフィック用の外部 Web サービス仮想 Ip (Vip) をソース用に構成する必要があります。 ソースアフィニティを使用すると、1つのクライアントからの複数の接続が、セッション状態を維持するために1台のサーバーに送信されるようになります。 アフィニティ要件の詳細については、「 [Lync Server 2013 の負荷分散の要件](lync-server-2013-load-balancing-requirements.md)」を参照してください。

内部 Wi-Fi ネットワーク上でのみ Lync mobile クライアントをサポートする場合は、「外部 Web サービスの Vip」に記載されているように、ソースに対して内部 Web サービス VIP を構成する必要があります。 このような状況では、 \_ ハードウェアロードバランサーの内部 Web サービス vip に対して、source addr (または TCP) アフィニティを使用する必要があります。 詳細については、「 [Lync Server 2013 の負荷分散の要件](lync-server-2013-load-balancing-requirements.md)」を参照してください。

</div>

<div>

## <a name="reverse-proxy-requirements"></a>リバース プロキシの要件

Lync mobile クライアントの自動検出をサポートしている場合は、現在の公開ルールを次のように更新する必要があります。

  - リバースプロキシ証明書のサブジェクトの別名の一覧を更新し、最初の自動検出サービス要求に HTTPS を使用する場合は、lyncdiscover の web 公開ルールを更新する必要が \<sipdomain\> あります。 通常、これはフロントエンドプールの外部 Web サービス URL の公開ルールと組み合わせて使用されます。

  - リバースプロキシ証明書のサブジェクトの別名リストを更新する必要がないように、最初の自動検出サービス要求に HTTP を使用する場合は、ポート HTTP/TCP 80 用の新しい web 公開ルールを作成する必要があります (まだ存在しない場合)。 HTTP/TCP 80 のルールが既に存在する場合は、そのルールを更新して lyncdiscover を含めることができます。\<sipdomain\> 値.

</div>

</div>

<span> </span>

</div>

</div>

</div>

