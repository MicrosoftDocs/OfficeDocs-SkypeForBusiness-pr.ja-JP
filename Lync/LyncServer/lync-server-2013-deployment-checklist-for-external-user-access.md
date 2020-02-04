---
title: 'Lync Server 2013: 外部ユーザー アクセスの展開チェックリスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for external user access
ms:assetid: 3f55f502-88a0-4315-8783-45a32a0b78ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425910(v=OCS.15)
ms:contentKeyID: 48183947
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ad2ad90ab43402babdd10478e1d86cac2a38ddf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762725"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-external-user-access-in-lync-server-2013"></a>Lync Server 2013 の外部ユーザー アクセスの展開チェックリスト

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-02-04_

境界ネットワークを展開して外部ユーザーのサポートを実装する前に、フロントエンドプールまたは Standard Edition サーバーを含む Microsoft Lync Server 2013 内部サーバーを既に展開しておく必要があります。 内部ネットワークにオプションのディレクターを展開する予定がある場合は、エッジサーバーを展開する前に展開する必要があります。 ディレクター展開プロセスの詳細については、計画ドキュメントの「 [Lync Server 2013 のディレクターのシナリオ](lync-server-2013-scenarios-for-the-director.md)」を参照してください。

Microsoft Lync Server 2013 には、内部サーバーとエッジサーバーの両方の計画と展開を容易にするためのツールが含まれています。 トポロジが完了したら、生成されたトポロジ定義を運用環境に公開します。 これを行うには、 **Domain Admins**グループと**RTCUniversalServerAdmins**グループのメンバーである必要があります。

  - **計画ツール**   Office Communications Server 2007 R2 には計画ツールとエッジ計画ツールが含まれており、これを使ってトポロジの設計をガイドすることができます。 Lync Server 2010 では、これら2つのツールが1つの計画ツールとしてまとめられており、計画されたユーザー数の収集、音声要件、外部ユーザーアクセスの種類、フェデレーションオプションなどの追加の機能が備わっています。 さらに、IP アドレス、ロードバランサーの種類、その他の境界ネットワークに関する考慮事項など、インフラストラクチャのネットワークパラメーターを計画することもできます。

  - **トポロジビルダー**   Lync Server 2013 トポロジビルダーを使用すると、トポロジとコンポーネントを定義できます。 トポロジビルダーは、Lync Server 2013 を実行しているサーバーの展開に不可欠です。 トポロジビルダーは、組織内の Lync Server 2013 を実行しているすべてのサーバーを構成するために使用される中央管理ストアに結果を発行します。 サーバーには、トポロジビルダーを使わずに Lync Server 2013 をインストールすることはできません。

計画プロセスで edge トポロジを設計して、edge トポロジを定義したトポロジビルダーを実行している場合は、これらの結果を使用してエッジサーバーの展開を開始できます。 以前にエッジトポロジの作成を完了していない場合、または以前に指定した情報を変更したい場合は、他の展開手順に進む前に、トポロジビルダーの実行を完了する必要があります。 トポロジの構築方法の詳細については、「 [Lync Server 2013 での外部ユーザーアクセスのシナリオ](lync-server-2013-scenarios-for-external-user-access.md)」を参照してください。

計画ツールとトポロジビルダーの詳細については、計画ドキュメントの「 [Lync Server 2013 の計画プロセスの開始](lync-server-2013-beginning-the-planning-process.md)」を参照してください。

次の表では、エッジサーバーの展開プロセスの概要を示します。 外部ユーザーアクセスを展開する前に行う必要がある計画決定を確認するには、「 [Lync Server 2013 での外部ユーザーアクセスのシナリオ](lync-server-2013-scenarios-for-external-user-access.md)」を参照してください。

<div>


> [!WARNING]  
> 次の表の情報は、新しい展開に焦点を当てています。 Lync Server 2010、Office Communications Server 2007 R2、または Office Communications Server 2007 環境でエッジサーバーを展開している場合は、「<A href="migration.md">移行</A>」で「lync server 2013 への移行に関する詳細」を参照してください。 Office communications server 2007、Live Communications Server 2005、Live Communications Server 2003 など、Office Communications Server 2007 R2 より前のバージョンでは、移行はサポートされていません。



</div>

エッジサーバーのパフォーマンスとセキュリティを強化し、展開を容易にするために、境界ネットワークとエッジサーバーを展開するときに、次のベストプラクティスを適用します。

  - エッジサーバーを展開するのは、組織内の Lync Server 2013 のテストと検証が完了した後のみです。

  - エッジサーバーは、ドメインではなくワークグループに展開することをお勧めします。 これにより、インストールが簡単になり、境界ネットワークから Active Directory ドメインサービス (AD DS) が維持されます。 境界ネットワークで広告 DS を検索すると、重大なセキュリティリスクをもたらす可能性があります。

  - 境界ネットワーク内の完全なドメインにエッジサーバーに参加することはサポートされますが、お勧めしません。 内部ドメインの一部としてのエッジサーバーが、信頼できるネットワーク境界に違反していて、インターネットが最も信頼できない、境界ネットワークがインターネットよりも信頼されていて、内部ネットワークが最も信頼されている。 ドメインのメンバーとしてのエッジサーバーは、最も信頼されたネットワークの一部になりますが、信頼度の低いネットワーク (境界) に存在します。

<div>

## <a name="deployment-process-for-edge-servers"></a>エッジサーバーの展開プロセス


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>段階</th>
<th>ステップ</th>
<th>アクセス許可</th>
<th>ドキュメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>適切なエッジトポロジを作成し、適切なコンポーネントを決定します。</p></td>
<td><ul>
<li><p>トポロジビルダーを実行して、エッジサーバーの設定を構成し、トポロジを作成および公開してから、Lync Server 管理シェルを使用してトポロジ構成ファイルをエクスポートします。</p></li>
</ul></td>
<td><p><strong>Domain Admins</strong>グループおよび<strong>RTCUniversalServerAdmins</strong>または<strong>csadmins</strong>グループ</p>
<div>

> [!NOTE]  
> [ローカルユーザー] グループのメンバーであるアカウントを使用してトポロジを定義できますが、トポロジを公開するには、 <STRONG>Domain Admins</STRONG>グループと<STRONG>RTCUniversalServerAdmins</STRONG>グループのメンバーであるアカウントが必要です。


</div></td>
<td><p>展開ドキュメントの<a href="lync-server-2013-building-an-edge-and-director-topology.md">Lync Server 2013 でエッジとディレクターのトポロジを構築する</a></p></td>
</tr>
<tr class="even">
<td><p>セットアップの準備をします。</p></td>
<td><ol>
<li><p>システムの前提条件が満たされていることを確認します。</p></li>
<li><p>各エッジサーバー上の内部および一般向けのネットワークインターフェイスの両方に対して、IP アドレス (IPv4 および IPv6 を使用している場合) を構成します。</p></li>
<li><p>エッジサーバーとして展開するコンピューター上の DNS サフィックスを構成するなど、内部と外部の DNS レコード (IPv4 および IPv6 の場合は host A と AAAA) を構成します。</p></li>
<li><p>省略公開証明書を作成してインストールします。 証明書を取得するために必要な時間は、証明書が発行される証明機関 (CA) によって異なります。 この手順をこの時点で実行しない場合は、Edge Server のインストール中に実行する必要があります。 エッジサーバーのサービスは、証明書が取得されてインストールされるまで開始できません。</p></li>
<li><p>展開が Windows Live、AOL、または Yahoo! との通信をサポートする場合は、パブリック IM 接続のサポートを提供します。 ユーザー.</p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P>2012年9月1日以降、Microsoft Lync パブリック IM 接続ユーザーサブスクリプションライセンス ("PIC USL") は、新規または更新契約の購入に使用できなくなりました。 アクティブなライセンスを持っているお客様は、Yahoo! とのフェデレーションを継続できます。 サービスが終了するまでの Messenger。 AOL および Yahoo! の2014年6月の終了日 が発表されました。 詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。</P>
> <LI>
> <P>PIC USL は、Lync Server または Office Communications Server が Yahoo! とのフェデレーションを行うために必要な1か月あたりのユーザーごとのサブスクリプションライセンスです。 Messenger. このサービスを提供するための Microsoft の機能は、Yahoo! からのサポートによって決定されたものであり、その基となる契約は "巻停止" となります。</P>
> <LI>
> <P>Lync は、組織間、および世界各地の個人と接続するための強力なツールです。 Windows Live Messenger とのフェデレーションには、Lync 標準 CAL 以外の追加のユーザー/デバイスライセンスは必要ありません。 Skype federation はこのリストに追加されます。 Lync ユーザーは、IM と音声を使用して、数百人の何百万ものユーザーに連絡できます。</P></LI></UL>


</div></li>
<li><p>展開で使用される場合は、Office Communications Server 2007、Office Communications Server 2007 R2、Lync Server 2010 パートナー向けの XMPP およびフェデレーションサポートのサポートを提供します。</p></li>
<li><p>ファイアウォールを構成します。</p></li>
</ol></td>
<td><p>組織に応じて</p></td>
<td><p>展開ドキュメントで<a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Lync Server 2013 用の境界ネットワークにサーバーをインストールするための準備</a></p></td>
</tr>
<tr class="odd">
<td><p>リバースプロキシをセットアップします。</p></td>
<td><ul>
<li><p>境界ネットワークに、(Microsoft Forefront Threat Management Gateway 2010 または Microsoft インターネットセキュリティとアクセラレータ (ISA) サーバーの場合) リバースプロキシをセットアップして、必要なパブリック証明書を取得して構成します。リバースプロキシサーバー上の web 公開ルール。</p>
<p>モビリティを計画していて、フロントエンドプールまたは Standard Edition サーバーにモビリティサービスを展開している場合は、モビリティサービスのリバースプロキシを準備します。</p></li>
</ul></td>
<td><p><strong>管理者</strong>グループまたはリバースプロキシ管理者</p></td>
<td><p>展開ドキュメントの<a href="lync-server-2013-setting-up-reverse-proxy-servers.md">Lync Server 2013 用にリバースプロキシサーバー</a>をセットアップする</p></td>
</tr>
<tr class="even">
<td><p>ディレクターを設定する (省略可能)。</p></td>
<td><ul>
<li><p>省略内部ネットワークに1つ以上のディレクターをインストールして構成します。</p></li>
</ul></td>
<td><p><strong>管理者</strong>グループ</p></td>
<td><p>展開ドキュメントの<a href="lync-server-2013-setting-up-the-director.md">Lync Server 2013 でのディレクターの</a>セットアップ</p></td>
</tr>
<tr class="odd">
<td><p>エッジサーバーをセットアップします。</p></td>
<td><ol>
<li><p>必須ソフトウェアをインストールします。</p></li>
<li><p>エクスポートされたトポロジ構成ファイルを各エッジサーバーに転送します。</p></li>
<li><p>各エッジサーバーに Lync Server 2013 ソフトウェアをインストールします。</p></li>
<li><p>エッジサーバーを構成します。</p></li>
<li><p>各エッジサーバーに対して証明書を要求およびインストールします。</p></li>
<li><p>Edge Server サービスを開始します。</p></li>
</ol></td>
<td><p><strong>管理者</strong>グループ</p></td>
<td><p>展開ドキュメントの<a href="lync-server-2013-setting-up-edge-servers.md">Lync Server 2013 での Edge サーバーの</a>セットアップ</p></td>
</tr>
<tr class="even">
<td><p>外部ユーザーアクセスの展開を構成します。</p></td>
<td><ol>
<li><p>Lync Server コントロールパネルを使用して、次の各機能のサポートを構成します (該当する場合)。</p>
<ul>
<li><p>メディアリレー</p></li>
<li><p>フェデレーションルート</p></li>
<li><p>リモートユーザーアクセス</p></li>
<li><p>Lync Server、Office Communications Server、Live Communications Server とのフェデレーション</p></li>
<li><p>パブリック IM 接続</p></li>
<li><p>XMPP フェデレーション</p></li>
<li><p>匿名ユーザー</p></li>
</ul></li>
<li><p>リモートユーザーアクセス、フェデレーション、パブリック IM 接続、XMPP、匿名ユーザーのサポート (該当する場合) のユーザーアカウントを構成する</p></li>
</ol></td>
<td><p><strong>Csadministrator</strong>ロールに割り当てられている<strong>RTCUniversalServerAdmins</strong>グループまたはユーザーアカウント</p></td>
<td><p>展開ドキュメントの<a href="lync-server-2013-configuring-support-for-external-user-access.md">Lync Server 2013 で外部ユーザーアクセスのサポートを構成する</a></p></td>
</tr>
<tr class="odd">
<td><p>エッジサーバーの構成を確認します。</p></td>
<td><ol>
<li><p>サーバーの接続と、内部サーバーからの構成データのレプリケーションを確認します。</p></li>
<li><p>展開に応じて、リモートユーザー、フェデレーションドメインのユーザー、パブリック IM ユーザー、匿名ユーザーなどの外部ユーザーが接続できることを確認します。</p></li>
<li><p>Lync Server Remote Connectivity Analyzer を使用して構成と通信を確認する<a href="https://www.testocsconnectivity.com" class="uri">https://www.testocsconnectivity.com</a></p></li>
<li><p>構成と通信に関する問題のトラブルシューティング</p></li>
</ol></td>
<td><p><strong>RTCUniversalServerAdmins</strong> 、または<strong>csadministrator</strong>の役割に割り当てられているユーザーアカウントを確認するには</p>
<p>ユーザー接続を確認するために、サポートする外部ユーザーアクセスの各種類のユーザー</p>
<p>リモートユーザー</p></td>
<td><p>展開ドキュメントの<a href="lync-server-2013-verifying-your-edge-deployment.md">Lync Server 2013 での edge の展開を確認</a>する</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

