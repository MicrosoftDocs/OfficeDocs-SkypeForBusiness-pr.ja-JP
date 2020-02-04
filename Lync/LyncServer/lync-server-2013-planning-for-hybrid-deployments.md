---
title: 'Lync Server 2013: ハイブリッド展開を計画する'
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
ms.openlocfilehash: e0902150170d51aa590afc8b3d02c887968a2031
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41751977"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013-hybrid-deployments"></a>Lync Server 2013 ハイブリッド展開の計画

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2016-05-25_

ハイブリッド展開を計画する場合は、ユーザーとネットワークインフラストラクチャについて、次の要件を考慮する必要があります。

<div>

## <a name="infrastructure-requirements"></a>インフラストラクチャの要件

ハイブリッド展開を実装して展開するには、環境内で次のように構成されている必要があります。

  - Skype for Business Online が有効になっている Microsoft Office 365 テナント オンプレミスの展開でハイブリッド構成に使用できるテナントは1つだけであることに注意してください。

  - サポートされているトポロジ内に展開された、Skype for Business Server または Lync Server の単一のオンプレミス展開 (インフラストラクチャ)。 「トポロジの要件」をご覧ください。
    
    ハイブリッド用の Lync Server 2013 または Lync Server 2010 の展開を構成する方法については、「 [Lync server 2013 ハイブリッド展開を構成する](lync-server-2013-configuring-hybrid-deployments.md)」を参照してください。

  - Skype for Business Server 2015 管理ツール。 Lync Server 2013 または Lync Server 2010 を使用している場合は、Lync Server 2013 管理ツールを使用できます。

  - Office 365 を使ったシングルサインオンをサポートして、ユーザーがオンプレミスとして Office にサインインするときに同じログイン資格情報を使用できるようにするには、Azure Active Directory (AAD) Connect のパスワード同期機能を使用できます。 また、Office 365 でのシングル サインオンに Active Directory フェデレーション サービス (AD FS) を使用することもできます。
    
    詳細については、「[オンプレミス id と Azure Active Directory の統合](http://go.microsoft.com/fwlink/p/?linkid=619754)」を参照してください。

  - オンプレミスとオンラインの Active Directory オブジェクトの同期を維持するための単一のディレクトリ同期ソリューション。 ディレクトリ同期の詳細については、「[ディレクトリ統合ツール](http://go.microsoft.com/fwlink/p/?linkid=530320)」を参照してください。

</div>

<div>

## <a name="lync-client-support"></a>Lync クライアントのサポート

Lync クライアントでサポートされる機能、およびオンプレミスとオンラインの環境で利用できる機能にはいくつかの違いがあります。 組織内のホームユーザーを決定する前に、Lync Server のさまざまな構成のクライアントサポートを表示できます。 Lync ハイブリッド展開では、次のクライアントが Skype for Business Online でサポートされています。

  - Lync 2010

  - Lync 2013

  - Lync Windows ストア アプリ

  - Lync Web App

  - Lync Mobile

  - Lync for Mac 2011

  - Lync Room System

  - Lync Basic 2013

クライアントのサポートの詳細については、次のトピックを参照してください。

  - [Lync Online のクライアント](http://go.microsoft.com/fwlink/?linkid=281902)

  - [Lync Server 2013 のクライアントの比較表](lync-server-2013-desktop-client-comparison-tables.md)

  - [Lync Server 2013 のモバイル クライアントの比較表](lync-server-2013-mobile-client-comparison-tables.md)

</div>

<span id="BKMK_Topology"></span>

<div>

## <a name="topology-requirements"></a>トポロジ要件

Skype for Business Online とのハイブリッド展開を構成するには、次のサポートされているトポロジのいずれかを使用する必要があります。

  - Skype for business server 2015 を実行しているすべてのサーバーでの Skype for Business Server 2015 の展開。

  - Lync server 2013 を実行しているすべてのサーバーでの Lync Server 2013 の展開。

  - Lync server 2010 の展開で、Lync Server 2010 を実行しているすべてのサーバーと最新の累積更新プログラムが適用されています。
    
      - フェデレーションエッジサーバーのフェデレーションエッジサーバーと次ホップサーバーでは、最新の累積更新プログラムを使用して、Lync Server 2010 を実行している必要があります。
    
      - Skype for Business Server 2015 または Lync Server 2013 の管理ツールは、少なくとも1つのサーバーまたは管理ワークステーションにインストールする必要があります。

  - Lync Server 2013 と Skype for Business Server 2015 の混在: Skype for Business Server 2015 を実行している少なくとも1つのサイトに次のサーバーロールが含まれています。
    
      - 少なくとも 1 台のエンタープライズ プールまたは Standard Edition サーバー 
    
      - SIP フェデレーションに関連づけられたディレクター プール (もしあれば)
    
      - SIP フェデレーションに関連づけられたエッジ プール (もしあれば)

  - Lync Server 2010 と Skype for Business Server 2015 の混在: Skype for Business Server 2015 を実行している少なくとも1つのサイトに次のサーバーの役割が含まれています。
    
      - 少なくとも 1 台のエンタープライズ プールまたは Standard Edition サーバー 
    
      - SIP フェデレーションに関連づけられたディレクター プール (もしあれば)
    
      - サイトの SIP フェデレーションに関連づけられたエッジ プール

  - Lync server 2013 を実行している少なくとも1つのサイトに次のサーバーロールが含まれている、混在する Lync Server 2010 と Lync Server 2013 の展開:
    
      - サイトの少なくとも 1 台のエンタープライズ プールまたは Standard Edition サーバー
    
      - SIP フェデレーションに関連づけられたディレクター プール (もしサイトにあれば)
    
      - サイトの SIP フェデレーションに関連づけられたエッジ プール

<div>


> [!IMPORTANT]  
> オンプレミスと UNRESOLVED_TOKEN_VAL (skypeforbusiness) の間のユーザー移動を含むすべてのユーザー管理は、最新バージョンの管理ツールを使用して行う必要があります。 管理ツールは、既存のオンプレミスの展開とインターネットへの接続にアクセスできる個別のサーバーにインストールする必要があります。 オンプレミスの展開から UNRESOLVED_TOKEN_VAL (skype16_online) にユーザーを移動するための<A href="https://docs.microsoft.com/powershell/module/skype/Move-CsUser">移動ユーザー</A>コマンドレットは、オンプレミスの展開に接続された管理ツールから実行される必要があります。



</div>

サポートされるトポロジの詳細については、「 [Lync server 2013 でサポートされるトポロジ](lync-server-2013-supported-topologies.md)」および「[エンタープライズハイブリッド展開の Lync Server 2013 リファレンストポロジ](http://go.microsoft.com/fwlink/p/?linkid=398709)」を参照してください。

ハイブリッド展開と Lync Online への PowerShell の接続のトラブルシューティングについては、「 [Lync Online: Lync PowerShell とハイブリッドトラブルシューティング](http://go.microsoft.com/fwlink/p/?linkid=306718)」を参照してください。

</div>

<div>

## <a name="requirements-for-federation-allowedblocked-lists"></a>フェデレーション許可/禁止リストの要件

許可ドメインの一覧には、パートナー エッジの完全修飾ドメイン名 (FQDN) が構成されているドメインが含まれます。これらは*許可パートナー サーバー*または*ダイレクト フェデレーション パートナー*と呼ばれることもあります。オープン フェデレーションとクローズド フェデレーションの違いをよく理解しておくことが必要です。オンプレミス展開ではこれらはそれぞれ*パートナーの検出*および*許可パートナー ドメインの一覧*と呼ばれます。

ハイブリッド展開を正しく構成するには、次の必要条件を満たす必要があります。

  - オンプレミス展開と Office 365 テナントでドメイン マッチングの構成を同一にする必要があります。オンプレミス展開でパートナーの検出が有効になっている場合、オンライン テナントではオープン フェデレーションを有効にする必要があります。パートナーの検出が無効になっている場合、オンライン テナントではクローズド フェデレーションを構成する必要があります。

  - オンプレミス展開における禁止ドメインの一覧はオンライン テナントの禁止ドメインの一覧と正確に一致する必要があります。

  - オンプレミス展開における許可ドメインの一覧はオンライン テナントの許可ドメインの一覧と正確に一致する必要があります。

  - オンラインテナントの外部通信では、フェデレーションを有効にする必要があります。これは、Lync Online のコントロールパネルを使用して構成されます。

</div>

<div>

## <a name="dns-settings"></a>DNS 設定

ハイブリッド展開用の DNS レコードを作成するときには、すべての Lync 外部 DNS レコードがオンプレミスインフラストラクチャを指すようにする必要があります。 必要な DNS レコードの詳細については、「 [Lync Server 2013 のドメインネームシステム (DNS) 要件](lync-server-2013-domain-name-system-dns-requirements.md)」を参照してください。

さらに、次の表で説明している DNS 解決が使用しているオンプレミス展開で機能することを確認する必要があります。


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
<td><p>_Tcp _sipfederationtls の DNS SRV レコード。&lt;サポート&gt;されているすべての SIP ドメインで、アクセスエッジの外部 IP へのアクセスを解決する sipdomain.com</p></td>
<td><p>エッジ サーバー</p></td>
<td><p>ハイブリッド展開でフェデレーション通信を有効にする。オンプレミスとオンラインで分割される SIP ドメイン用のフェデレーション トラフィックのルートをエッジ サーバーで認識している必要があります。</p></td>
</tr>
<tr class="odd">
<td><p>エッジ Web 会議サービス FQDN の DNS A レコード、たとえば、webcon.contoso.com は Web 会議のエッジ外部 IP に解決される</p></td>
<td><p>ユーザーのコンピューターが接続している会社内ネットワーク</p></td>
<td><p>オンライン ユーザーを有効にして、オンプレミスのホストされた会議でのコンテンツを提供または表示する。コンテンツには、PowerPoint ファイル、ホワイトボード、投票、および共有メモがあります。</p></td>
</tr>
</tbody>
</table>


所属する組織での DNS の構成方法によっては、内部 DNS 解決をこれらのレコードに適用するために、対応する SIP ドメインに対して組織内でホストする DNS ゾーンにこれらのレコードを追加する必要があります。

</div>

<div>

## <a name="firewall-considerations"></a>ファイアウォールに関する考慮事項

ネットワーク上のコンピューターは、標準のインターネット DNS 参照を実行できる必要があります。これらのコンピューターが標準のインターネット サイトに接続できれば、ネットワークはこの要件を満たしています。

Microsoft Online Services データセンターの場所によっては、ネットワークファイアウォールデバイスで、ワイルドカードドメイン名 (たとえば、outlook.com から\*のすべてのトラフィック) に基づいて接続を受け入れるように構成する必要もあります。 組織のファイアウォールがワイルドカードを使用した名前の構成方法をサポートしない場合は、許可する IP アドレスの範囲および特定のポートを手動で決める必要があります。

ヘルプトピック「 [Office 365 の url と IP アドレスの範囲](http://go.microsoft.com/fwlink/p/?linkid=252942)」を参照してください。

</div>

<span id="b"></span>

<div>

## <a name="port-and-protocol-requirements"></a>ポートとプロトコルの要件

Lync Server 2013 では、内部通信のポート要件のほかに、次のポートを構成する必要もあります。


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
<td><p>TCP 443</p></td>
<td><p>受信を開く</p>
<ul>
<li><p>Active Directory フェデレーションサービス (フェデレーションサーバーの役割)</p>
<p>詳細については、「 <a href="http://go.microsoft.com/fwlink/p/?linkid=281899">AD FS の役割サービスについ</a>て」を参照してください。</p></li>
<li><p>Active Directory フェデレーションサービス (プロキシサーバーの役割)</p></li>
<li><p>Microsoft Online Services ポータル</p></li>
<li><p>会社のポータル</p></li>
<li><p>Outlook Web App</p></li>
<li><p>Lync クライアント (オンプレミスの Lync Server から Lync Online への通信)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>TCP 80 および443</p></td>
<td><p>受信を開く</p>
<ul>
<li><p>Microsoft Online Services ディレクトリ同期ツール</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>TCP 5061</p></td>
<td><p>エッジサーバーで受信/送信を開く</p></td>
</tr>
<tr class="even">
<td><p>PSOM/TLS 443</p></td>
<td><p>データ共有セッションで受信/送信を開く</p></td>
</tr>
<tr class="odd">
<td><p>STUN/TCP 443</p></td>
<td><p>オーディオ、ビデオ、アプリケーション共有セッションで受信/送信を開く</p></td>
</tr>
<tr class="even">
<td><p>STUN/UDP 3478</p></td>
<td><p>音声およびビデオセッションで受信/送信を開く</p></td>
</tr>
<tr class="odd">
<td><p>RTP/TCP 50000-59999</p></td>
<td><p>音声およびビデオセッションで送信を開く</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-accounts-and-data"></a>ユーザーアカウントとデータ

Lync Server 2013 ハイブリッド展開では、Lync Online でホームにするすべてのユーザーは、まずオンプレミスの展開でそのユーザーアカウントが作成されるようにする必要があります。 その後、ユーザーを Skype for Business Online に移動します。これにより、ユーザーの連絡先リストが移動します。

Lync のオンプレミスと Lync Online の展開との間で、AD FS と Dirsync を使用してユーザーアカウントを同期する場合は、組織内のすべての Lync ユーザーの AD アカウントを、オンプレミスとオンラインの Lync の展開の間で、ユーザーも同期する必要があります。Lync Online に移動されません。 すべてのユーザーを同期しない場合、組織のオンプレミス展開のユーザーとオンライン ユーザーとの間の通信が正常に動作しない可能性があります。

<div>


> [!IMPORTANT]  
> ユーザーが Office 365 のオンラインポータルを使って作成されている場合、ユーザーアカウントはオンプレミスの Active Directory と同期されず、ユーザーはオンプレミスの Active Directory に存在しません。 Lync Online で既にユーザーを作成していて、オンプレミスの Lync サーバーとハイブリッドに構成する場合は、「lync <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Online から Lync server 2013 の lync にユーザーを移行</A>する」を参照してください。



</div>

また、ハイブリッド展開を計画する場合は、次のユーザー関連の問題も考慮する必要があります。

  - **ユーザーの連絡先**   Lync Online ユーザーの連絡先の制限は250です。 その数を超えた連絡先は、アカウントが Lync Online に移動されるときにユーザーの連絡先リストから削除されます。

  - **インスタントメッセージとプレゼンス**   のユーザーの連絡先リスト、グループ、アクセス制御リスト (acl) は、ユーザーアカウントを使用して移行されます。

  - **会議データ、会議コンテンツ、スケジュール**   された会議このコンテンツは、ユーザーアカウントで移行されません。 ユーザーは、アカウントが Lync Online に移行された後で会議を予約し直す必要があります。

</div>

<div>

## <a name="user-policies-and-features"></a>ユーザーポリシーと機能

  - Lync Server 2013 ハイブリッド環境では、インスタントメッセージング、音声、会議のオンプレミスまたはオンラインでの使用を有効にすることはできますが、両方を同時に有効にすることはできません。

  - **Lync クライアント**   一部のユーザーは、lync Online に移行するときに、新しいクライアントバージョンを必要とする場合があります。 Office Communications Server 2007 R2 の場合、Lync Online に移行する前に、ユーザーを Lync Server 2013 プールに移動する必要があります。
    
    クライアントのサポートの詳細については、「 [Lync Online のクライアント](http://go.microsoft.com/fwlink/p/?linkid=281902)」および「[サポートされている lync クライアントとネットワークポートの構成](http://go.microsoft.com/fwlink/p/?linkid=281901)」を参照してください。

  - **オンプレミスのポリシーと構成 (非ユーザー)**   のオンラインおよびオンプレミスのポリシーには、個別の構成が必要です。 両方に適用されるグローバル ポリシーを設定することはできません。

</div>

</div>

<span> </span>

</div>

</div>

</div>

