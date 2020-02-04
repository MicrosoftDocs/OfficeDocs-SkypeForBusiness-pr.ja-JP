---
title: 'Lync Server 2013: 概要'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Introduction to Lync Server
ms:assetid: 99dd6b65-e591-421f-852b-ee9fe9588998
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398795(v=OCS.15)
ms:contentKeyID: 48184885
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8879bd2f3638df17215b7b8f0ee4a12c751277f8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725667"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="introduction-to-lync-server-2013"></a>Lync Server 2013 の概要

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-10-07_

Lync Server 2013 と、Lync 2013 などのクライアントソフトウェアを使用すると、ユーザーは新しい方法で接続し、物理的な場所に関係なく接続を維持することができます。 Lync と Lync Server は、単一のクライアントインターフェイスでコミュニケーションを行い、統一されたプラットフォームとして展開し、単一の管理インフラストラクチャで管理するさまざまな方法を提供します。

この表と次のセクションでは、Lync Server でユーザーに提供される主な機能セットまたは*ワークロード*について説明します。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>よる</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IM とプレゼンス</p></td>
<td><p>インスタントメッセージング (IM) とプレゼンスを使用すると、ユーザーは簡単かつ効率的に相互に検索してコミュニケーションを行うことができます。</p>
<p>IM は、会話履歴を含むインスタントメッセージングプラットフォームであり、MSN、Windows Live、Yahoo!、AOL、Google Talk などのパブリック IM ネットワークのユーザーとのパブリック IM 接続をサポートします。</p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P>2012年9月1日以降、Microsoft Lync パブリック IM 接続ユーザーサブスクリプションライセンス ("PIC USL") は、新規または更新契約の購入に使用できなくなりました。 アクティブなライセンスを持っているお客様は、Yahoo! とのフェデレーションを継続できます。 サービスが終了するまでの Messenger。 AOL および Yahoo! の2014年6月の終了日 が発表されました。 詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。</P>
> <LI>
> <P>PIC USL は、Lync Server または Office Communications Server が Yahoo! とのフェデレーションを行うために必要な1か月あたりのユーザーごとのサブスクリプションライセンスです。 Messenger. このサービスを提供するための Microsoft の機能は、Yahoo! からのサポートによって決定されたものであり、その基となる契約は "巻停止" となります。</P>
> <LI>
> <P>Lync は、組織間、および世界各地の個人と接続するための強力なツールです。 Windows Live Messenger とのフェデレーションには、Lync 標準 CAL 以外の追加のユーザー/デバイスライセンスは必要ありません。 Skype federation はこのリストに追加されます。 Lync ユーザーは、IM と音声を使用して、数百人の何百万ものユーザーに連絡できます。</P></LI></UL>


</div>
<p>[プレゼンス] は、ユーザーの個人の空き時間情報を設定して表示します。また、<strong>利用可能</strong>か<strong>取り込み中</strong>かなどの一般的な状態を使用することに加えて、適切な状態を使用する<strong>こと</strong>で、問題が発生した場合には、良好な状態になります。 <strong></strong> この豊富なプレゼンス情報を使うと、他のユーザーがすぐに連絡を選択できるようになります。</p></td>
</tr>
<tr class="even">
<td><p>会議</p></td>
<td><p>Lync Server には、スケジュールされた会議と一時的会議の両方について、IM 会議、電話会議、web 会議、ビデオ会議、およびアプリケーション共有がサポートされています。 これらすべての種類の会議は、1つのクライアントでサポートされています。 Lync Server は、ダイヤルイン会議もサポートしているため、公衆交換電話網 (PSTN) の電話機のユーザーは、会議のオーディオ部分に参加することができます。</p>
<p>会議はリアルタイムでシームレスに変更され、増加する可能性があります。 たとえば、1人の会議を、少数のユーザー間でインスタントメッセージとして開始したり、デスクトップ共有を使用して音声会議に参加したり、会話フローを中断することなく、すばやく簡単に会話を始めたりすることができます。</p></td>
</tr>
<tr class="odd">
<td><p>エンタープライズ VoIP</p></td>
<td><p>[<em>エンタープライズボイス</em>] は、Lync Server での Voip (Voice Over Internet Protocol) サービスです。 従来の構内交換 (PBX) システムを拡張または交換するためのボイスオプションを提供します。 エンタープライズボイスは、IP PBX の完全なテレフォニー機能に加えて、リッチプレゼンス、IM、共同作業、会議に統合されています。 通話の応答、保留、再開、転送、転送、転送すればなどの機能は直接サポートされますが、パーソナライズされた短縮ダイヤルキーは連絡先リストに置き換えられ、自動機能付きインターコムは IM に置き換えられます。</p>
<p>エンタープライズボイスは、通話受付制御 (CAC)、支店の office survivability、およびデータの復元の拡張オプションを通じて高可用性をサポートします。</p></td>
</tr>
<tr class="even">
<td><p>リモートユーザー向けのサポート</p></td>
<td><p>このようなリモートユーザーへの接続を提供するために、サーバーを<em>エッジサーバー</em>として展開することで、現在組織外のユーザーに対して Lync Server の完全な機能を提供することができます。 これらのリモートユーザーは、Lync 2013 がインストールされているパーソナルコンピューター、電話、または web インターフェイスを使用して、会議に接続できます。</p>
<p>エッジサーバーを展開すると、パートナー組織やベンダー組織と<em>フェデレーション</em>を行うことができます。 フェデレーション関係により、ユーザーはフェデレーションされたユーザーを連絡先リストに配置し、プレゼンス情報やインスタントメッセージをこれらのユーザーとやり取りして、音声通話、ビデオ通話、会議に招待することができます。</p></td>
</tr>
<tr class="odd">
<td><p>モバイルクライアントのサポート</p></td>
<td><p>さらに、Lync Server mobility services を使用すると、サポートされている Apple iOS、Android、Windows Phone、Nokia モバイルデバイスを使って Lync 機能にアクセスしたり、インスタントメッセージの送受信、連絡先の表示などの操作を実行したりすることができます。プレゼンスを表示します。 さらに、モバイルデバイスでは、クリックして電話会議に参加したり、勤務先の電話による通話、ボイスメール、不在着信など、一部のエンタープライズ音声機能をサポートしたりします。 プッシュ通知は、バックグラウンドで実行されているアプリケーションをサポートしていないモバイルデバイスでもサポートされます。</p></td>
</tr>
<tr class="even">
<td><p>他の製品との統合</p></td>
<td><p>Lync Server は、他のいくつかの製品と統合され、ユーザーと管理者にとってさらに利点をもたらします。</p>
<p>会議ツールは Outlook に統合されているため、開催者は1回のクリックで会議のスケジュールを設定したり、一時的な会議を開始したりできます。これにより、出席者が簡単に参加できるようになります。</p>
<p>プレゼンス情報は Outlook と SharePoint に統合されています。</p>
<p>Exchange ユニファイドメッセージング (UM) には、複数の統合機能が用意されています。 ユーザーは、Lync Server 内に新しいボイスメールがあるかどうかを確認できます。 Outlook メッセージの再生ボタンをクリックすると、音声のボイスメールを聞くことができます。また、通知メッセージのボイスメールの議事録を表示することもできます。</p>
<p>さらに、Exchange 2013 で Lync Server 2013 を実行すると、両方の製品のクライアントからアクセスできる統合連絡先ストア、および Exchange 2013 データベースに保存されている連絡先の高解像度写真など、いくつかの新機能が有効になります。</p></td>
</tr>
<tr class="odd">
<td><p>簡単な展開</p></td>
<td><p>サーバーとクライアントを計画して展開するために、Lync Server によってトポロジビルダーが提供されます。</p>
<p>トポロジビルダーは、Lync Server のインストールコンポーネントです。 トポロジビルダーを使用して、計画されたトポロジを作成、調整、公開します。 また、サーバーのインストールを開始する前にトポロジを検証することもできます。 個々のサーバーに Lync Server をインストールすると、インストールプログラムによって、トポロジで指示されたとおりにサーバーが展開されます。</p></td>
</tr>
<tr class="even">
<td><p>簡単な管理</p></td>
<td><p>Lync Server を展開すると、次のような強力で合理化された管理ツールが提供されます。</p>
<ul>
<li><p>一元的な構成管理: 変更を一元的に管理し、展開全体に迅速に複製することができます。</p></li>
<li><p>Lync Server コントロールパネル。管理者向けの web ベースのグラフィカルユーザーインターフェイスです。 この web ベースの UI を使用すると、Lync Server 管理者は、専用の管理ソフトウェアがコンピューターにインストールされていなくても、企業ネットワーク上の任意の場所からシステムを管理することができます。</p></li>
<li><p>Lync Server 管理シェルコマンドライン管理ツール。これは、Windows PowerShell コマンドラインインターフェイスに基づいています。 製品のすべての要素を管理するための豊富なコマンドセットを提供します。また、Lync Server の管理者が、使い慣れたツールを使用して繰り返し行うタスクを自動化することができます。</p></li>
</ul></td>
</tr>
</tbody>
</table>


IM とプレゼンス機能は、すべての Lync Server 展開に自動的にインストールされますが、会議、エンタープライズ Voip、リモートユーザーアクセスを展開して、組織のニーズに合わせて展開するかどうかを選ぶことができます。

<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 IM とプレゼンス](lync-server-2013-im-and-presence.md)

  - [Lync Server 2013 電話会議](lync-server-2013-conferencing.md)

  - [Lync Server 2013 のエンタープライズ VoIP](lync-server-2013-enterprise-voice.md)

  - [Lync Server 2013 のスケーラビリティ](lync-server-2013-scalability.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

