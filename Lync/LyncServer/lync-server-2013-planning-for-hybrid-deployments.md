---
title: 'Lync Server 2013: ハイブリッド展開の計画'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for hybrid deployments
ms:assetid: f8b3d240-bc2e-42c9-acf8-d532d641a14c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205403(v=OCS.15)
ms:contentKeyID: 48185910
ms.date: 05/25/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54888a96d33dc3d9195256483f41719031847744
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780326"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013-hybrid-deployments"></a>Lync Server 2013 ハイブリッド展開の計画

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2016-05-25_

ハイブリッド展開の計画では、ユーザーとネットワークインフラストラクチャの次の要件を考慮する必要があります。

<div>

## <a name="infrastructure-requirements"></a>インフラストラクチャの要件

ハイブリッド展開を実装して展開するには、環境内に次のものが構成されている必要があります。

  - Skype for Business Online が有効になっている Microsoft Office 365 組織。 オンプレミス展開でハイブリッド構成に使用できるのは1つのテナントのみであることに注意してください。

  - サポートされているトポロジに展開されている Skype for Business Server または Lync Server の単一のオンプレミス展開 (インフラストラクチャ)。 「トポロジ要件」を参照してください。
    
    ハイブリッド用の Lync Server 2013 または Lync Server 2010 の展開の構成の詳細については、「 [Lync server 2013 ハイブリッド展開の構成](lync-server-2013-configuring-hybrid-deployments.md)」を参照してください。

  - Skype for Business Server 2015 管理ツール。 Lync server 2013 または Lync Server 2010 を使用している場合は、Lync Server 2013 管理ツールを使用できます。

  - Office 365 でシングルサインオンをサポートし、ユーザーがオンプレミスの場合と同じログイン資格情報を使用して Office にサインインできるようにするには、Azure Active Directory (AAD) Connect のパスワード同期機能を使用できます。 Active Directory フェデレーションサービス (AD FS) を使用して、Office 365 でシングルサインオンを行うこともできます。
    
    詳しくは「[オンプレミスの ID を Azure Active Directory と統合する](https://go.microsoft.com/fwlink/p/?linkid=619754)」をご覧ください。

  - 1つのディレクトリ同期ソリューションを使用して、オンプレミスとオンラインの Active Directory オブジェクトを同期させます。 ディレクトリ同期の詳細については、「[ディレクトリ統合ツール](https://go.microsoft.com/fwlink/p/?linkid=530320)」を参照してください。

</div>

<div>

## <a name="lync-client-support"></a>Lync クライアントのサポート

Lync クライアントでサポートされている機能と、オンプレミスおよびオンライン環境で使用できる機能にはいくつかの違いがあります。 組織内のユーザーをホームにする場所を決定する前に、Lync Server のさまざまな構成のクライアントサポートを表示できます。 Lync ハイブリッド展開では、以下のクライアントが Skype for Business Online でサポートされています。

  - Lync 2010

  - Lync 2013

  - Lync Windows ストアアプリ

  - Lync Web App

  - Lync Mobile

  - Lync for Mac 2011

  - Lync Room System

  - Lync Basic 2013

クライアントサポートの詳細については、以下のトピックを参照してください。

  - [Lync Online のクライアント](https://go.microsoft.com/fwlink/?linkid=281902)

  - [Lync Server 2013 のクライアントの比較表](lync-server-2013-desktop-client-comparison-tables.md)

  - [Lync Server 2013 のモバイルクライアントの比較表](lync-server-2013-mobile-client-comparison-tables.md)

</div>

<span id="BKMK_Topology"></span>

<div>

## <a name="topology-requirements"></a>トポロジ要件

Skype for Business Online でハイブリッド展開を構成するには、次のサポートされているトポロジのいずれかを使用する必要があります。

  - Skype for business Server 2015 を Skype for business Server 2015 を実行しているすべてのサーバーと共に展開します。

  - Lync server 2013 を実行して2013いるすべてのサーバーでの Lync Server の展開。

  - Lync server 2010 の展開は、最新の累積的な更新プログラムを適用して Lync Server 2010 を実行しているすべてのサーバーに適用されます。
    
      - フェデレーションエッジサーバーおよびフェデレーションエッジサーバーの次ホップサーバーは、最新の累積更新プログラムを使用して Lync Server 2010 を実行している必要があります。
    
      - Skype for Business Server 2015 または Lync Server 2013 の管理ツールは、少なくとも1つのサーバーまたは管理ワークステーションにインストールする必要があります。

  - Skype for Business Server 2015 を実行している少なくとも1つのサイトに、次のサーバーの役割を持つ Lync Server 2013 と Skype for Business 2015 Server の混在した展開。
    
      - 少なくとも1つのエンタープライズプールまたは Standard Edition サーバー
    
      - SIP フェデレーションに関連付けられたディレクタープール (存在する場合)
    
      - SIP フェデレーションに関連付けられているエッジプール

  - Skype for Business Server 2015 を実行している少なくとも1つのサイトに、次のサーバーの役割を持つ Lync Server 2010 と Skype for Business 2015 Server の混在した展開。
    
      - 少なくとも1つのエンタープライズプールまたは Standard Edition サーバー
    
      - SIP フェデレーションに関連付けられたディレクタープール (存在する場合)
    
      - サイトの SIP フェデレーションに関連付けられているエッジプール

  - 少なくとも1つのサイトで lync Server 2013 を実行しているサーバーの役割が混在する Lync Server 2010 および Lync Server 2013 の混在:
    
      - サイト内の少なくとも1つのエンタープライズプールまたは Standard Edition サーバー
    
      - SIP フェデレーションに関連付けられたディレクタープール (サイトに存在する場合)
    
      - サイトの SIP フェデレーションに関連付けられているエッジプール

<div>


> [!IMPORTANT]  
> オンプレミスと UNRESOLVED_TOKEN_VAL (skypeforbusiness) 間のユーザー移動を含む、すべてのユーザー管理は、管理ツールの最新バージョンを使用して実行する必要があります。 管理ツールは、既存のオンプレミス展開およびインターネットへの接続アクセス権を持つ別のサーバーにインストールする必要があります。 オンプレミス展開から UNRESOLVED_TOKEN_VAL (skype16_online) にユーザーを移動するための<A href="https://docs.microsoft.com/powershell/module/skype/Move-CsUser">移動ユーザー</A>コマンドレットは、オンプレミス展開に接続された管理ツールから実行する必要があります。



</div>

サポートされるトポロジの詳細については、「 [Lync server 2013 のサポートされるトポロジ](lync-server-2013-supported-topologies.md)」および「[エンタープライズハイブリッド展開用の Lync Server 2013 Reference トポロジ](https://go.microsoft.com/fwlink/p/?linkid=398709)」を参照してください。

ハイブリッド展開のトラブルシューティングと、PowerShell を Lync Online に接続する方法については、「 [Lync online: Lync PowerShell」および「ハイブリッドトラブルシューティング](https://go.microsoft.com/fwlink/p/?linkid=306718)」を参照してください。

</div>

<div>

## <a name="requirements-for-federation-allowedblocked-lists"></a>フェデレーション許可/ブロックリストの要件

許可されるドメインの一覧には、パートナーエッジの完全修飾ドメイン名 (FQDN) が構成されているドメインが含まれています。 これらは、*許可されたパートナーサーバー*または*直接フェデレーションパートナー*と呼ばれることがあります。 オンプレミス展開では、*パートナー検出*と*許可されたパートナードメインリスト*と呼ばれる、オープンフェデレーションと閉じられたフェデレーションの違いについて理解しておく必要があります。

ハイブリッド展開を正しく構成するには、次の要件を満たす必要があります。

  - オンプレミス展開と Office 365 組織に対して同じドメイン一致を構成する必要があります。 オンプレミス展開でパートナー検出が有効になっている場合は、オンラインテナントに対してオープンフェデレーションを構成する必要があります。 パートナー検出が有効になっていない場合は、オンラインテナント用に閉じられたフェデレーションを構成する必要があります。

  - オンプレミス展開の禁止ドメインリストは、オンラインテナントの禁止ドメインリストと正確に一致する必要があります。

  - オンプレミス展開の許可ドメインリストは、オンラインテナントの許可されたドメインリストと正確に一致している必要があります。

  - オンラインテナントの外部通信に対してフェデレーションを有効にする必要があります。これは、Lync Online コントロールパネルを使用して構成されます。

</div>

<div>

## <a name="dns-settings"></a>DNS 設定

ハイブリッド展開用の DNS レコードを作成する場合は、すべての Lync 外部 DNS レコードがオンプレミスのインフラストラクチャをポイントする必要があります。 必要な DNS レコードの詳細については、「 [Lync Server 2013 のドメインネームシステム (DNS) の要件](lync-server-2013-domain-name-system-dns-requirements.md)」を参照してください。

さらに、次の表に記載されている DNS 解決がオンプレミスの展開でも動作することを確認する必要があります。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>DNS レコード</p></td>
<td><p>解決方法</p></td>
<td><p>DNS 要件</p></td>
</tr>
<tr class="even">
<td><p>_Sipfederationtls _tcp の DNS SRV レコード。&lt;エッジ&gt;の外部 IP へのアクセスを解決するための、サポートされているすべての SIP ドメインの sipdomain.com</p></td>
<td><p>エッジサーバー</p></td>
<td><p>ハイブリッド構成でフェデレーション通信を有効にします。 エッジサーバーは、オンプレミスとオンラインの間で分割されている SIP ドメインのフェデレーショントラフィックをルーティングする場所を知っている必要があります。</p></td>
</tr>
<tr class="odd">
<td><p>エッジ Web 会議サービス FQDN 用の DNS A レコード (webcon.contoso.com、Web 会議エッジ外部 IP への解決など)</p></td>
<td><p>内部の企業ネットワークに接続されたユーザーのコンピューター</p></td>
<td><p>オンラインユーザーがオンプレミスでホストされている会議のコンテンツを表示または表示できるようにします。 コンテンツには、PowerPoint ファイル、ホワイトボード、投票、および共有メモが含まれます。</p></td>
</tr>
</tbody>
</table>


組織での DNS の構成方法によっては、これらのレコードを対応する SIP ドメインの内部ホスト DNS ゾーンに追加して、これらのレコードに対する内部 DNS 解決を提供する必要がある場合があります。

</div>

<div>

## <a name="firewall-considerations"></a>ファイアウォールの考慮

ネットワーク上のコンピューターは、標準のインターネット DNS 参照を実行できる必要があります。これらのコンピューターが標準のインターネット サイトに接続できれば、ネットワークはこの要件を満たしています。

Microsoft Online Services データセンターの場所によっては、ネットワークファイアウォールデバイスが、ワイルドカードドメイン名 (たとえば、outlook.com から\*のすべてのトラフィック) に基づいて接続を受け入れるように構成する必要もあります。 組織のファイアウォールがワイルドカードを使用した名前の構成方法をサポートしない場合は、許可する IP アドレスの範囲や特定のポートを手動で決める必要があります。

ヘルプトピック「 [Office 365 の url と IP アドレスの範囲](https://go.microsoft.com/fwlink/p/?linkid=252942)」を参照してください。

</div>

<span id="b"></span>

<div>

## <a name="port-and-protocol-requirements"></a>ポートとプロトコルの要件

内部 Lync Server 2013 の通信のポート要件に加えて、次のポートも構成する必要があります。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>プロトコル/ポート</th>
<th>アプリケーション</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TCP 443</p></td>
<td><p>受信を開く</p>
<ul>
<li><p>Active Directory フェデレーション サービス (フェデレーション サーバーの役割)</p>
<p>詳細については、「 <a href="https://go.microsoft.com/fwlink/p/?linkid=281899">AD FS の役割サービスについ</a>て」を参照してください。</p></li>
<li><p>Active Directory フェデレーション サービス (プロキシ サーバーの役割)</p></li>
<li><p>Microsoft Online Services ポータル</p></li>
<li><p>ポータル サイト</p></li>
<li><p>Outlook Web App</p></li>
<li><p>Lync クライアント (オンプレミスの Lync Server から Lync Online への通信)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>TCP 80 および 443</p></td>
<td><p>受信を開く</p>
<ul>
<li><p>Microsoft Online Services ディレクトリ同期ツール</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>TCP 5061</p></td>
<td><p>エッジサーバーで受信/送信を開く</p></td>
</tr>
<tr class="even">
<td><p>PSOM/TLS 443</p></td>
<td><p>データ共有セッションの受信/送信を開く</p></td>
</tr>
<tr class="odd">
<td><p>STUN/TCP 443</p></td>
<td><p>音声、ビデオ、アプリケーション共有セッションで受信/送信を開く</p></td>
</tr>
<tr class="even">
<td><p>STUN/UDP 3478</p></td>
<td><p>音声およびビデオセッションの受信/送信を開く</p></td>
</tr>
<tr class="odd">
<td><p>RTP/TCP 50000-59999</p></td>
<td><p>オーディオおよびビデオセッションの送信を開く</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-accounts-and-data"></a>ユーザー アカウントおよびデータ

Lync Server 2013 ハイブリッド展開では、Lync Online のホームにするすべてのユーザーが、Active Directory ドメインサービスでユーザーアカウントが作成されるように、最初に社内展開で作成する必要があります。 その後、ユーザーを Skype for Business Online に移動して、ユーザーの連絡先リストを移動することができます。

Lync オンプレミスと Lync Online の展開との間で AD FS および Dirsync を使用してユーザーアカウントを同期する場合は、ユーザーが Lync Online に移動されていない場合でも、組織内のすべての Lync ユーザーの AD アカウントをオンプレミスとオンラインの Lync 展開の間で同期する必要があります。 すべてのユーザーを同期しない場合は、組織内のオンプレミスのユーザーとオンラインユーザーとの間の通信が期待どおりに機能しないことがあります。

<div>


> [!IMPORTANT]  
> ユーザーがオンラインポータルの Office 365 を使用して作成されている場合、ユーザーアカウントは社内 Active Directory と同期されず、ユーザーはオンプレミスの Active Directory に存在しません。 既に Lync Online でユーザーを作成していて、オンプレミスの Lync Server でハイブリッドを構成する場合は、「lync <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">online から Lync online 2013 へのユーザーの移行</A>」を参照してください。



</div>

ハイブリッド展開を計画する場合は、次のユーザー関連の問題も考慮する必要があります。

  - **ユーザーの連絡先**   Lync Online ユーザーの連絡先の制限は250です。 その番号を超える連絡先は、アカウントが Lync Online に移動されたときにユーザーの連絡先リストから削除されます。

  - **インスタントメッセージングとプレゼンス**   ユーザーの連絡先リスト、グループ、アクセス制御リスト (acl) は、ユーザーアカウントと共に移行されます。

  - **会議データ、会議コンテンツ、および予約済み会議**   このコンテンツは、ユーザーアカウントと共に移行されません。 ユーザーは、アカウントが Lync Online に移行された後で会議を予約し直す必要があります。

</div>

<div>

## <a name="user-policies-and-features"></a>ユーザー ポリシと機能

  - Lync Server 2013 ハイブリッド環境では、ユーザーは、オンプレミスまたはオンラインのいずれかで、インスタントメッセージング、音声、および会議を有効にすることができますが、両方を同時に有効にすることはできません。

  - **Lync クライアント**   ユーザーによっては、lync Online に移行する際に新しいクライアントバージョンが必要になる場合があります。 Office Communications Server 2007 R2 の場合、Lync Online に移行する前に、ユーザーを Lync Server 2013 プールに移動する必要があります。
    
    クライアントサポートの詳細については、「 [Lync Online のクライアント](https://go.microsoft.com/fwlink/p/?linkid=281902)」および「[サポートされている lync クライアントとネットワークポートの構成](https://go.microsoft.com/fwlink/p/?linkid=281901)」を参照してください。

  - **オンプレミスのポリシーと構成 (非ユーザー)**   のオンラインおよびオンプレミスのポリシーには、個別の構成が必要です。 両方に適用されるグローバル ポリシーを設定することはできません。

</div>

</div>

<span> </span>

</div>

</div>

</div>

