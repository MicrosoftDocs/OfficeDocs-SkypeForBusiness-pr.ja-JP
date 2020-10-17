---
title: Lync Server 2013 の概要
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
ms.openlocfilehash: f2878f47fcace98bbd9e156f24c2b87e85faf728
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525234"
---
# <a name="introduction-to-lync-server-2013"></a>Lync Server 2013 の概要

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-10-07_

Lync Server 2013 とそのクライアントソフトウェア (Lync 2013 など) により、ユーザーは新しい方法で接続し、物理的な場所に関係なく接続を維持することができます。 Lync および Lync Server は、ユーザーが1つのクライアントインターフェイスで通信し、統一されたプラットフォームとして展開され、単一の管理インフラストラクチャを通じて管理するさまざまな方法を統合しています。

この表と以下のセクションでは、Lync Server がユーザーに提供する主な機能セット ( *ワークロード*) について説明します。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>ワークロード</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IM とプレゼンス</p></td>
<td><p>インスタント メッセージング (IM) とプレゼンスにより、ユーザーは効率的かつ効果的に相手を見つけて連絡できます。</p>
<p>IM は、会話履歴を備えるインスタント メッセージング プラットフォームを提供し、MSN/Windows Live、Yahoo!、AOL、Google Talk などパブリック IM ネットワーク ユーザーとのパブリック IM 接続をサポートします。</p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P>2012年9月1日時点で、Microsoft Lync パブリック IM 接続ユーザーサブスクリプションライセンス ("PIC USL") は、新規購入時または契約の更新時に購入することができなくなりました。 アクティブなライセンスを持つお客様は、Yahoo! とのフェデレーションを続行できます。 メッセンジャーサービスが終了するまでの期間。 AOL および Yahoo! の2014年6月の寿命の終了日 が発表されました。 詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。</P>
> <LI>
> <P>PIC USL は、Lync Server または Office Communications Server が Yahoo! とのフェデレーションを行うために必要なユーザーごとの月ごとのサブスクリプションライセンスです。 Messenger. このサービスを提供するための Microsoft の機能は、Yahoo! からのサポートに応じて決定されました。これは、使用する基礎となる契約です。</P>
> <LI>
> <P>Lync は、組織間や世界中の個人と接続するための強力なツールです。 Windows Live Messenger とのフェデレーションでは、Lync Standard CAL を超えるユーザー/デバイスライセンスを追加する必要はありません。 Skype フェデレーションがこの一覧に追加され、Lync ユーザーが IM と音声を使用して数百人のユーザーにアクセスできるようになります。</P></LI></UL>


</div>
<p>プレゼンスは、ユーザーの個人的な空き時間や通話応答の意思を、[<strong>連絡可能</strong>] や [<strong>取り込み中</strong>] などの共通のステータス、さらには [<strong>一時退席中</strong>] や [<strong>応答しない</strong>] といったさらに詳細なステータスを使って明確にし、表示します。この豊富なプレゼンス情報により、他のユーザーは効果的な連絡方法をすばやく選択できます。</p></td>
</tr>
<tr class="even">
<td><p>会議</p></td>
<td><p>Lync Server は、スケジュールされた会議と即時の会議の両方について、IM 会議、電話会議、web 会議、ビデオ会議、およびアプリケーション共有のサポートを備えています。 これらの会議の全種類が 1 つのクライアントでサポートされます。 Lync Server は、電話会議の音声部分に公衆交換電話網 (PSTN) 電話のユーザーが参加できるように、ダイヤルイン会議もサポートします。</p>
<p>会議はリアル タイムでシームレスに変更および拡大できます。たとえば、1 つの会議を数人のユーザー間のインスタント メッセージのみで開始し、デスクトップ共有を使用するより参加者の多い大規模な音声会議へと、会話の流れを遮ることなくすばやく簡単に切り替えることができます。</p></td>
</tr>
<tr class="odd">
<td><p>エンタープライズ VoIP</p></td>
<td><p><em>エンタープライズ voip</em> は、Lync Server でのボイスオーバー Ip (VoIP) サービスです。 従来の構内交換機 (PBX) システムを強化または置き換える音声オプションを提供します。 IP PBX のすべてのテレフォニー機能に加え、エンタープライズ VoIP は豊富なプレゼンス、IM、共同作業、および会議と統合されています。 通話応答、保留、再開、着信転送、通話転送、リモート転送などの機能が直接サポートされ、また、個人用短縮ダイヤル キーは連絡先リストに置き換えられ、自動インターコムは IM に置き換えられます。</p>
<p>エンタープライズ VoIP は、通話受付管理 (CAC) による高い可用性、ブランチ オフィスの存続性、およびデータ復元性の拡張オプションをサポートします。</p></td>
</tr>
<tr class="even">
<td><p>リモート ユーザーのサポート</p></td>
<td><p><em>エッジ</em>サーバーと呼ばれるサーバーを展開してリモートユーザーに接続を提供することにより、組織のファイアウォールの外側にいるユーザーに Lync Server の完全な機能を提供できます。 これらのリモートユーザーは、Lync 2013 がインストールされたパーソナルコンピューター、電話、または web インターフェイスを使用して、会議に接続できます。</p>
<p>エッジ サーバーを展開すると、パートナーやベンダー組織とのフェデレーション<em></em>も有効にできます。フェデレーション関係によって、ユーザーは連絡先リストにフェデレーション ユーザーを追加したり、フェデレーション ユーザーとプレゼンス情報やインスタント メッセージを交換したり、音声通話やビデオ通話、会議にフェデレーション ユーザーを招待したりできます。</p></td>
</tr>
<tr class="odd">
<td><p>モバイル クライアントのサポート</p></td>
<td><p>さらに、Lync Server mobility services では、サポートされている Apple iOS、Android、Windows Phone、または Nokia のモバイルデバイスを使用して Lync 機能にアクセスしたり、インスタントメッセージの送受信、連絡先の表示、プレゼンスの表示などのアクティビティを実行したりできます。 また、クリックして会議に参加、勤務先から通話、同一番号接続、ボイス メール、不在着信など、モバイル デバイスでいくつかのエンタープライズ VoIP 機能がサポートされます。 バックグラウンドで実行されるアプリケーションをサポートしないモバイル デバイス用にプッシュ通知もサポートされます。</p></td>
</tr>
<tr class="even">
<td><p>他の製品との統合</p></td>
<td><p>Lync Server は他のいくつかの製品と統合され、ユーザーと管理者にさらに利点を提供します。</p>
<p>会議ツールは Outlook に統合されており、開催者は1回のクリックで会議のスケジュールを設定したり、即時会議を開始したり、出席者が簡単に参加できるようにすることができます。</p>
<p>プレゼンス情報は、Outlook と SharePoint に統合されています。</p>
<p>Exchange ユニファイド メッセージング (UM) では、いくつかの統合機能を提供します。 ユーザーは、Lync Server 内に新しいボイスメールがあるかどうかを確認できます。 Outlook メッセージ内の再生ボタンをクリックして音声ボイス メールを聞いたり、通知メッセージ内でボイス メールのトランスクリプションを表示したりできます。</p>
<p>さらに、Exchange 2013 で Lync Server 2013 を実行すると、統合連絡先ストアのようないくつかの新機能が有効になります。これには、両方の製品のクライアントがアクセスできるようにすることも、2013 Exchange の管理データベースに格納されている連絡先の高解像度の写真を使用することもできます。</p></td>
</tr>
<tr class="odd">
<td><p>簡単な展開</p></td>
<td><p>サーバーとクライアントの計画と展開に役立つように、Lync Server ではトポロジビルダーが提供されています。</p>
<p>トポロジビルダーは、Lync Server のインストールコンポーネントです。 トポロジビルダーを使用して、計画したトポロジを作成、調整、および発行します。 また、サーバーのインストールを開始する前にトポロジを検証します。 個々のサーバーに Lync Server をインストールすると、インストールプログラムによってサーバーがトポロジ内に配置されたとおりに展開されます。</p></td>
</tr>
<tr class="even">
<td><p>簡単な管理</p></td>
<td><p>Lync Server を展開した後、次のような強力で合理的な管理ツールが提供されます。</p>
<ul>
<li><p>構成の集中管理。変更を集中管理して展開全体にすばやくレプリケートできます。</p></li>
<li><p>Lync Server コントロールパネル。管理者向けの web ベースのグラフィカルユーザーインターフェイスです。 この web ベースの UI を使用すると、Lync Server 管理者は、自分のコンピューターに特別な管理ソフトウェアがインストールされていなくても、企業ネットワーク上のあらゆる場所からシステムを管理できます。</p></li>
<li><p>Lync Server 管理シェルコマンドライン管理ツール。これは、Windows PowerShell コマンドラインインターフェイスに基づいています。 製品のすべての側面を管理するための豊富なコマンドセットを提供し、Lync Server 管理者が使い慣れたツールを使用して繰り返しタスクを自動化できるようにします。</p></li>
</ul></td>
</tr>
</tbody>
</table>


IM およびプレゼンスの機能はすべての Lync Server 展開に自動的にインストールされますが、会議、エンタープライズ Voip、リモートユーザーアクセスを展開するかどうかを選択して、展開を組織のニーズに合わせて調整することができます。

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 の IM およびプレゼンス](lync-server-2013-im-and-presence.md)

  - [Lync Server 2013 の会議](lync-server-2013-conferencing.md)

  - [Lync Server 2013 のエンタープライズ Voip](lync-server-2013-enterprise-voice.md)

  - [Lync Server 2013 を使用したスケーラビリティ](lync-server-2013-scalability.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

