---
title: Lync Server 2013 のサーバーの役割
description: Lync Server 2013 のサーバーの役割。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server roles
ms:assetid: 7137fc06-fca2-4e5f-9db5-10c7c29a788c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398536(v=OCS.15)
ms:contentKeyID: 48184456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ee4636e602e5bfb8ce6eacdccb3d190f5728d1c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580193"
---
# <a name="server-roles-in-lync-server-2013"></a>Lync Server 2013 のサーバーの役割

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-10-07_

Lync Server を実行している各サーバーは、1つ以上の *サーバーの役割*を実行します。 サーバーの役割とは、そのサーバーによって提供される、定義済みの Lync Server の機能のセットのことです。 ネットワークで使用できるサーバーの役割をすべて展開する必要はありません。 必要な機能が含まれているサーバーの役割のみをインストールします。

Lync Server のサーバーの役割をよく理解していない場合でも、計画ツールを使用して、必要な機能に基づいて展開する必要があるサーバーの最適なソリューションにすることができます。 ここでは、サーバーの役割の概要とその役割が提供する一般的な機能について説明します。

  - Standard Edition サーバー

  - フロントエンド サーバーおよびバック エンド サーバー

  - エッジ サーバー

  - 仲介サーバー

  - ディレクター

  - 常設チャット フロントエンド サーバー

  - 常設チャット ストア (常設チャット バックエンド サーバー)

  - 常設チャット コンプライアンス ストア (常設チャット コンプライアンス バックエンド サーバー)

多くのサーバーの役割では、すべてが同じサーバーの役割を実行する複数のサーバーのプール** を展開して、スケーラビリティと高可用性を実現できます。 プール内の各サーバーは同じサーバーの役割を実行する必要があります。 Lync Server のほとんどの種類のプールでは、プール内のさまざまなサーバー間のトラフィックを分散するためにロードバランサーを展開する必要があります。 Lync Server は、ドメインネームシステム (DNS) 負荷分散とロードバランサー機器の両方をサポートしています。

<div>

## <a name="standard-edition-server"></a>Standard Edition サーバー

Standard Edition サーバーは、小規模な組織や、大規模な組織のパイロット プロジェクトを対象としています。 これにより、必要なデータベースを含む Lync Server の多くの機能を1台のサーバーで実行できるようになります。 これにより、Lync Server の機能を低コストで利用できるようになりますが、実際の高可用性ソリューションは提供されません。

Standard Edition サーバーでは、インスタントメッセージング (IM)、プレゼンス、会議、エンタープライズ Voip を使用して、すべてを1台のサーバー上で実行することができます。

高可用性ソリューションの場合は、Lync Server Enterprise Edition を使用します。

</div>

<div>

## <a name="front-end-server-and-back-end-server"></a>フロントエンド サーバーおよびバック エンド サーバー

Lync Server Enterprise Edition では、フロントエンドサーバーがコアサーバーの役割で、多くの基本的な Lync Server の機能を実行します。 フロントエンドサーバーは、バックエンドサーバーと共に、Lync Server Enterprise Edition の展開に必要な唯一のサーバーの役割です。

フロントエンド プール** は、まったく同じように構成されたフロントエンド サーバーのセットです。これらは連携して共通のユーザー グループにサービスを提供します。同じ役割を実行している複数のサーバーのプールでは、スケーラビリティとフェールオーバー機能を提供します。

フロントエンド サーバーには次の機能があります。

  - ユーザーの認証および登録

  - プレゼンス情報および連絡先カードの交換

  - アドレス帳サービスおよび配布リスト展開

  - IM 機能 (マルチパーティ IM 会議など)

  - Web 会議、PSTN ダイヤルイン会議、および音声ビデオ会議 (展開されている場合)。

  - Lync Server に含まれているアプリケーション (会議アテンダント、応答グループアプリケーションなど)、およびサードパーティアプリケーションの両方のアプリケーションホスティング

  - オプションで、使用状況の情報を詳細な通話の記録 (CDR) や通話エラー記録 (CER) の形式で収集するための監視。 この情報には、エンタープライズ Voip 通話と音声ビデオ会議の両方について、ネットワークを通過するメディアの品質 (オーディオおよびビデオ) に関する指標が提供されます。

  - Web スケジューラーや Join Launcher など、Web ベースのタスクをサポートするための Web コンポーネント。

  - オプションで、コンプライアンス上の理由で IM 通信および会議の内容をアーカイブするアーカイブ機能。 詳細については、「計画」のドキュメントの「 [planning For アーカイビング In Lync Server 2013](lync-server-2013-planning-for-archiving.md) 」を参照してください。
    
    Lync Server 2010 および以前のバージョンでは、監視とアーカイブはフロントエンドサーバーに併置されていない個別のサーバーの役割でした。

  - オプションで、常設チャットが有効になっている場合は、チャット ルーム管理用の常設チャット Web サービス、およびファイルのアップロード/ダウンロード用の常設チャット Web サービス。

フロントエンド プールは、ユーザーおよび会議データ用のプライマリ ストアでもあります。各ユーザーに関する情報は、プール内の 3 つのフロントエンド サーバーにレプリケートされ、バックエンド サーバーにバックアップされます。

また、展開内の1つのフロントエンドプールでも *中央管理サーバー*が実行されます。これは、基本的な構成データを管理し、Lync Server を実行しているすべてのサーバーに展開します。 中央管理サーバーは、Lync Server 管理シェルおよびファイル転送機能も提供します。

バックエンドサーバーは、フロントエンドプールのデータベースサービスを提供する Microsoft SQL Server を実行しているデータベースサーバーです。 バックエンド サーバーは、プールのユーザーおよび会議データのバックアップ ストアとして機能し、応答グループ データベースなどの他のデータベースのプライマリ ストアになります。 バックエンドサーバーは1つしか使用できませんが、SQL Server ミラーリングを使用するソリューションはフェールオーバーに推奨されます。 バックエンドサーバーは、どの Lync Server ソフトウェアも実行しません。

<div>


> [!IMPORTANT]  
> Lync Server データベースを他のデータベースと併置することはお勧めしません。 併置すると、可用性とパフォーマンスに影響することがあります。



</div>

バックエンド サーバーのデータベースには、プレゼンス情報、ユーザーの連絡先リスト、会議データ (現在のすべての会議の状態に関する固定データなど)、および会議のスケジュール データなどの情報が格納されています。

</div>

<div>

## <a name="edge-server"></a>エッジ サーバー

エッジ サーバーを使用すると、ユーザーは組織のファイアウォールの外側にいるユーザーと通信や共同作業を行うことができます。 これらの外部ユーザーには、現在、オフサイトで作業している組織の独自のユーザー、フェデレーションパートナー組織のユーザー、および Lync Server 展開でホストされている会議に参加するよう招待された外部ユーザーを含めることができます。 エッジサーバーでは、Windows Live、AOL、Yahoo、Google Talk を含むパブリック IM 接続サービスへの接続も可能になり \! ます。

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

エッジ サーバーを展開すると、モバイル デバイスで Lync 機能をサポートするモビリティ サービスも有効になります。 ユーザーは、サポートされる Apple iOS、Android、Windows Phone、または Nokia のモバイル デバイスを使用して、インスタント メッセージの送受信、連絡先の表示、プレゼンスの表示などのアクティビティを実行できます。 また、クリックして会議に参加、勤務先から通話、同一番号接続、ボイス メール、不在着信など、モバイル デバイスでいくつかのエンタープライズ VoIP 機能がサポートされます。 モビリティ機能では、バックグラウンドで実行されているアプリケーションをサポートしないモバイル デバイス用のプッシュ通知** もサポートされます。 プッシュ通知は、モバイル アプリケーションが非アクティブなときに発生したイベントについてモバイル デバイスに送信される通知です。

エッジ サーバーには、完全に統合された XMPP (eXtensible Messaging and Presence Protocol) プロキシと、フロントエンド サーバーに含まれる XMPP ゲートウェイも含まれます。 これらの XMPP コンポーネントを構成して、Lync Server 2013 ユーザーがインスタントメッセージングとプレゼンスの XMPP ベースのパートナー (Google Talk など) から連絡先を追加できるようにすることができます。

詳細については、「計画」のドキュメントの「 [planning for external user access In Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) 」を参照してください。

</div>

<div>

## <a name="mediation-server"></a>仲介サーバー

仲介サーバーは、エンタープライズ Voip およびダイヤルイン会議を実装するために必要なコンポーネントです。 仲介サーバーは、内部の Lync Server インフラストラクチャと公衆交換電話網 (PSTN) ゲートウェイ、IP-PBX、またはセッション開始プロトコル (SIP) トランク間のメディアを変換します。 フロントエンド サーバーと同じサーバーに配置されている、またはスタンドアロンの仲介サーバー プールに分離されている仲介サーバーを実行できます。

詳細については、「計画」のドキュメントの「 [Lync server 2013 の仲介サーバーコンポーネント](lync-server-2013-mediation-server-component.md) 」を参照してください。

</div>

<div>

## <a name="director"></a>ディレクター

ディレクターは、Lync Server ユーザー要求を認証できますが、ユーザーアカウントをホームにしたり、プレゼンスや会議サービスを提供したりすることはありません。 ディレクターは、外部ユーザー アクセスが有効になっている展開でセキュリティを強化するのに非常に役立ちます。 内部サーバーに要求を送信する前にディレクターで認証を実行できます。 サービス拒否攻撃が発生した場合、攻撃はディレクターによって終了され、フロントエンド サーバーには到達しません。 詳細については、「計画」のドキュメントの「 [Lync Server 2013 のディレクターのシナリオ](lync-server-2013-scenarios-for-the-director.md) 」を参照してください。

</div>

<div>

## <a name="persistent-chat-server-roles"></a>常設チャットサーバーの役割

常設チャットでは、ユーザーがトピックに基づく長時間のマルチパーティ会話に参加できます。常設チャット フロントエンド サーバーは、常設チャット サービスを実行します。常設チャット バックエンド サーバーでは、チャット履歴データと、カテゴリおよびチャット ルームに関する情報が格納されます。オプションの常設チャット コンプライアンス バックエンド サーバーでは、コンプライアンスの目的でチャットの内容とコンプライアンス イベントを格納できます。

Lync Server Standard Edition を実行しているサーバーは、同じサーバー上に併置された常設チャットも実行できます。 常設チャットフロントエンドサーバーを Enterprise Edition フロントエンドサーバーと併置することはできません。

詳細については、「 [Lync server 2013 での常設チャットサーバーの計画](lync-server-2013-planning-for-persistent-chat-server.md)」を参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 の仲介サーバーコンポーネント](lync-server-2013-mediation-server-component.md)  


[Lync Server 2013 でのアーカイブの計画](lync-server-2013-planning-for-archiving.md)  
[Lync Server 2013 での外部ユーザーアクセスの計画](lync-server-2013-planning-for-external-user-access.md)  
[Lync Server 2013 のディレクターのシナリオ](lync-server-2013-scenarios-for-the-director.md)  
[Lync Server 2013 での常設チャットサーバーの計画](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

