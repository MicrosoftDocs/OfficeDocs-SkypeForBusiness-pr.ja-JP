---
title: 'Lync Server 2013: 外部ユーザーアクセスの展開チェックリスト'
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
ms.openlocfilehash: 5010608f05f99d1d1830874a80b6f9f44fd25b38
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135894"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-external-user-access-in-lync-server-2013"></a>Lync Server 2013 での外部ユーザーアクセスの展開チェックリスト

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-02-04_

境界ネットワークを展開し、外部ユーザーのサポートを実装する前に、フロントエンドプールまたは Standard Edition サーバーを含む、Microsoft Lync Server 2013 の内部サーバーを展開しておく必要があります。 オプションのディレクターを内部ネットワークに展開することを計画している場合は、エッジサーバーを展開する前にも展開する必要があります。 ディレクターの展開プロセスの詳細については、「計画」のドキュメントの「 [Lync Server 2013 のディレクターのシナリオ](lync-server-2013-scenarios-for-the-director.md)」を参照してください。

Microsoft Lync Server 2013 には、内部サーバーとエッジサーバーの両方の計画と展開を容易にするためのツールが含まれています。 トポロジが完成したら、作成したトポロジ定義を運用環境に公開します。 これを行うためには、**Domain Admins** グループと **RTCUniversalServerAdmins** グループのメンバーである必要があります。

  - **Planning tool**   Office Communications Server 2007 R2 には、計画ツールとエッジ計画ツールが含まれており、これを使用してトポロジ設計をガイドすることができます。 Lync Server 2010 では、これら2つのツールは、計画されたユーザー数の収集、音声の要件、外部ユーザーアクセスの種類、フェデレーションオプションなどの追加機能を備えた単一の計画ツールに統合されました。 さらに、IP アドレス、ロードバランサーの種類、その他の境界ネットワークに関する考慮事項など、インフラストラクチャのネットワークパラメーターを計画することができます。

  - **トポロジビルダー**   Lync Server 2013 トポロジビルダーを使用して、トポロジとコンポーネントを定義できます。 トポロジビルダーは、Lync Server 2013 を実行しているサーバーを展開するために不可欠です。 トポロジビルダーは、組織内の Lync Server 2013 を実行しているすべてのサーバーを構成するために使用される中央管理ストアに結果を発行します。 トポロジビルダーを使用せずに、サーバーに Lync Server 2013 をインストールすることはできません。

トポロジビルダーを実行してエッジトポロジを定義するなど、計画プロセス中にエッジトポロジを設計した場合は、その結果を使用してエッジサーバーの展開を開始できます。 以前にエッジトポロジの作成を終了していない場合、または以前に指定した情報を変更する場合は、他の展開手順を続行する前に、トポロジビルダーの実行を終了する必要があります。 トポロジを構築する方法の詳細については、「 [Lync Server 2013 の外部ユーザーアクセスのシナリオ](lync-server-2013-scenarios-for-external-user-access.md)」を参照してください。

計画ツールとトポロジビルダーの詳細については、「計画」のドキュメントの「 [Lync Server 2013 の計画プロセスの開始](lync-server-2013-beginning-the-planning-process.md)」を参照してください。

次の表に、エッジ サーバーの展開プロセスの概要を示します。 外部ユーザーアクセスを展開する前に実行する必要のある計画の決定事項を確認するには、「 [Lync Server 2013 の外部ユーザーアクセスのシナリオ](lync-server-2013-scenarios-for-external-user-access.md)」を参照してください。

<div>


> [!WARNING]  
> 次の表には、新規展開に関する情報を掲載しています。 エッジサーバーを Lync Server 2010、Office Communications Server 2007 R2 または Office Communications Server の2007環境に展開している場合は、「 <A href="migration.md">Migration</A> The lync server 2013 への移行の詳細」を参照してください。 Office communications server 2007、Live Communications Server 2005、Live Communications Server 2003 を含む、Office Communications Server 2007 R2 より前のバージョンの移行はサポートされていません。



</div>

エッジ サーバーのパフォーマンスとセキュリティを向上させ、展開作業を円滑に行うことができるようにするため、次のベスト プラクティスに従って境界ネットワークとエッジ サーバーを展開します。

  - エッジサーバーの展開は、組織内の Lync Server 2013 の動作をテストおよび検証した後にのみ行います。

  - エッジ サーバーは、ドメインではなく、ワークグループに展開することをお勧めします。これにより、インストールが容易になり、Active Directory ドメイン サービス (AD DS) を境界ネットワークの外側に置くことができます。境界ネットワーク上に AD DS を配置すると、セキュリティ リスクが高くなる場合があります。

  - 全体が境界ネットワーク内にあるドメインへのエッジ サーバーの追加はサポートされていますが、お勧めしません。内部ドメインに属するエッジ サーバーは、インターネットは最も信頼性が低く、境界ネットワークはインターネットよりも信頼性が高く、内部ネットワークは最も信頼性が高いという信頼されたネットワークの境界の規則に違反します。内部ドメインのメンバーであるエッジ サーバーは自動的に最も信頼性の高いネットワークに属しますが、実際にはより信頼性の低いネットワーク (境界ネットワーク) に存在するからです。

<div>

## <a name="deployment-process-for-edge-servers"></a>エッジ サーバーの展開プロセス


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>フェーズ</th>
<th>手順</th>
<th>アクセス許可</th>
<th>ドキュメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>適切なエッジ トポロジの作成および適切なコンポーネントの決定。</p></td>
<td><ul>
<li><p>トポロジビルダーを実行して、エッジサーバーの設定を構成し、トポロジを作成および公開した後、Lync Server 管理シェルを使用してトポロジ構成ファイルをエクスポートします。</p></li>
</ul></td>
<td><p><strong>Domain admins</strong>グループおよび<strong>RTCUniversalServerAdmins</strong>または<strong>csadmins</strong>グループ</p>
<div>

> [!NOTE]  
> ローカル ユーザー グループのメンバーであるアカウントを使用してトポロジを定義することはできますが、トポロジを公開するには <STRONG>Domain Admins</STRONG> グループおよび <STRONG>RTCUniversalServerAdmins</STRONG> グループのメンバーであるアカウントが必要です。


</div></td>
<td><p>「展開」のドキュメントの「 <a href="lync-server-2013-building-an-edge-and-director-topology.md">Lync Server 2013 でのエッジおよびディレクターのトポロジの構築</a>」</p></td>
</tr>
<tr class="even">
<td><p>セットアップの準備。</p></td>
<td><ol>
<li><p>システムの前提条件が適合していることを確認します。</p></li>
<li><p>各エッジ サーバーの、内部とパブリック側の両方のネットワーク インターフェイスの IP アドレス (IPv4 および IPv6 (使用されている場合)) を構成します。</p></li>
<li><p>内部および外部の DNS レコード (IPv4 および IPv6 の場合はホスト A および AAAA) を構成します。これにはエッジ サーバーとして展開されるコンピューターでの DNS サフィックスの構成も含まれます。</p></li>
<li><p>(オプション) パブリック証明書を作成してインストールします。証明書の取得に必要な時間は、証明書を発行する証明機関 (CA) によって異なります。現時点でこのステップを実行しない場合は、エッジ サーバーのインストール時に実行する必要があります。証明書を取得してインストールしないと、エッジ サーバー サービスを開始できません。</p></li>
<li><p>展開が Windows Live、AOL、または Yahoo! ユーザーとの通信をサポートする場合は、パブリック IM 接続のサポートをプロビジョニングします。</p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P>2012年9月1日時点で、Microsoft Lync パブリック IM 接続ユーザーサブスクリプションライセンス ("PIC USL") は、新規購入時または契約の更新時に購入することができなくなりました。 アクティブなライセンスを持つお客様は、Yahoo! とのフェデレーションを続行できます。 メッセンジャーサービスが終了するまでの期間。 AOL および Yahoo! の2014年6月の寿命の終了日 が発表されました。 詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。</P>
> <LI>
> <P>PIC USL は、Lync Server または Office Communications Server が Yahoo! とのフェデレーションを行うために必要なユーザーごとの月ごとのサブスクリプションライセンスです。 Messenger. このサービスを提供するための Microsoft の機能は、Yahoo! からのサポートに応じて決定されました。これは、使用する基礎となる契約です。</P>
> <LI>
> <P>Lync は、組織間や世界中の個人と接続するための強力なツールです。 Windows Live Messenger とのフェデレーションでは、Lync Standard CAL を超えるユーザー/デバイスライセンスを追加する必要はありません。 Skype フェデレーションがこの一覧に追加され、Lync ユーザーが IM と音声を使用して数百人のユーザーにアクセスできるようになります。</P></LI></UL>


</div></li>
<li><p>展開で使用される場合は、Office Communications Server 2007、Office Communications Server 2007 R2、Lync Server 2010 パートナーに対する XMPP およびフェデレーションサポートのサポートを準備します。</p></li>
<li><p>ファイアウォールの構成。</p></li>
</ol></td>
<td><p>組織に合わせて設定</p></td>
<td><p>「展開」のドキュメントの「 <a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Lync Server 2013 の境界ネットワークへのサーバーのインストールの準備</a>」</p></td>
</tr>
<tr class="odd">
<td><p>リバース プロキシの設定。</p></td>
<td><ul>
<li><p>境界ネットワークでリバースプロキシ (Microsoft Forefront Threat Management Gateway 2010 または Microsoft Internet Security and 促進 (ISA) Server Service Pack 1) を設定し、必要なパブリック証明書を取得して構成します。リバースプロキシサーバー上の web 公開ルール。</p>
<p>モビリティの計画を行っており、フロントエンド プールまたは Standard Edition サーバーに Mobility Service を展開する場合は、Mobility Service 用のリバース プロキシを準備します。</p></li>
</ul></td>
<td><p><strong>Administrators</strong> グループまたはリバース プロキシの管理者</p></td>
<td><p>「展開」のドキュメントの「 <a href="lync-server-2013-setting-up-reverse-proxy-servers.md">Lync Server 2013 用のリバースプロキシサーバーの</a>セットアップ」</p></td>
</tr>
<tr class="even">
<td><p>ディレクターのセットアップ (オプション)。</p></td>
<td><ul>
<li><p>(オプション) 内部ネットワークにディレクターを 1 つ以上インストールして構成します。</p></li>
</ul></td>
<td><p><strong>Administrators</strong> グループ</p></td>
<td><p>「展開」のドキュメントの「 <a href="lync-server-2013-setting-up-the-director.md">Lync Server 2013 でのディレクターのセットアップ</a>」</p></td>
</tr>
<tr class="odd">
<td><p>エッジ サーバーの設定。</p></td>
<td><ol>
<li><p>必要なソフトウェアをインストールします。</p></li>
<li><p>エクスポートされたトポロジ構成ファイルを各エッジ サーバーにトランスポートします。</p></li>
<li><p>各エッジサーバーに Lync Server 2013 ソフトウェアをインストールします。</p></li>
<li><p>エッジ サーバーを構成します。</p></li>
<li><p>各エッジ サーバー用の証明書を要求してインストールします。</p></li>
<li><p>エッジ サーバー サービスを開始します。</p></li>
</ol></td>
<td><p><strong>Administrators</strong> グループ</p></td>
<td><p>「展開」のドキュメントの「 <a href="lync-server-2013-setting-up-edge-servers.md">Lync Server 2013 でのエッジサーバーのセットアップ</a>」</p></td>
</tr>
<tr class="even">
<td><p>外部ユーザー アクセスの展開の構成。</p></td>
<td><ol>
<li><p>Lync Server コントロールパネルを使用して、次の各機能のサポートを構成します (該当する場合)。</p>
<ul>
<li><p>メディア リレー</p></li>
<li><p>フェデレーション ルート</p></li>
<li><p>リモート ユーザー アクセス</p></li>
<li><p>Lync Server、Office Communications Server、Live Communications Server とのフェデレーション</p></li>
<li><p>パブリック IM 接続</p></li>
<li><p>XMPP フェデレーション</p></li>
<li><p>匿名ユーザー</p></li>
</ul></li>
<li><p>(必要に応じて) リモート ユーザー アクセス、フェデレーション、パブリック IM 接続、XMPP、および匿名ユーザー サポート用のユーザー アカウントを構成します。</p></li>
</ol></td>
<td><p><strong>RTCUniversalServerAdmins</strong> グループ、または <strong>CSAdministrator</strong> の役割に割り当てられているユーザー アカウント</p></td>
<td><p>「展開」のドキュメントの「 <a href="lync-server-2013-configuring-support-for-external-user-access.md">Lync Server 2013 での外部ユーザーアクセスのサポートの構成</a>」</p></td>
</tr>
<tr class="odd">
<td><p>エッジ サーバー構成の確認。</p></td>
<td><ol>
<li><p>内部サーバーからのサーバー接続および構成データのレプリケーションを確認します。</p></li>
<li><p>外部ユーザー (リモート ユーザー、フェデレーション ドメイン内のユーザー、パブリック IM ユーザー、および匿名ユーザーなど) が、必要に応じて展開に接続できることを確認します。</p></li>
<li><p>Lync Server リモート接続アナライザーを使用して構成と通信を確認する<a href="https://www.testocsconnectivity.com" class="uri">https://www.testocsconnectivity.com</a></p></li>
<li><p>構成および通信の問題のトラブルシューティングを行います。</p></li>
</ol></td>
<td><p>レプリケーションの確認の場合は、<strong>RTCUniversalServerAdmins</strong> グループ、または <strong>CSAdministrator</strong> の役割に割り当てられているユーザー アカウント</p>
<p>ユーザー接続の確認の場合は、サポートしている外部ユーザー アクセスの各種ユーザー</p>
<p>リモート ユーザー</p></td>
<td><p>「展開」のドキュメントの「 <a href="lync-server-2013-verifying-your-edge-deployment.md">Lync Server 2013 でのエッジ展開の確認</a>」</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

