---
title: 'Lync Server 2013: 一般的な会議の概念'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Common conferencing concepts
ms:assetid: a21d4987-1c0a-44c8-8a39-9c17ffb57f3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688158(v=OCS.15)
ms:contentKeyID: 49733762
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 546e350dc78883ac56623a23f9153d5bdfd4a1d8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045719"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="common-conferencing-concepts-in-lync-server-2013"></a>Lync Server 2013 での一般的な会議の概念

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-19_

すべての種類の会議に共通する概念がいくつかあります。 これらについては、以下のセクションで説明します。

<div>

## <a name="policies-and-bandwidth-management"></a>ポリシーと帯域幅管理

Lync Server 2013 を使用すると、管理者はユーザーが整理できる会議の種類に関するポリシーを設定できます。 これにより、組織のポリシーを適用し、帯域幅の使用状況を制御することができます。 さまざまな種類の会議ポリシーを定義して、個々のユーザーやユーザーのグループに割り当てることができます。 ピアツーピア会話を制御するポリシーを設定することもできます。 会議ポリシーの設定の詳細については、「操作」のドキュメントの「 [Lync Server 2013 の会議ポリシー](lync-server-2013-conferencing-policies.md) 」を参照してください。 帯域幅管理の詳細については、「lync server [2013 での通話受付管理の概要](lync-server-2013-overview-of-call-admission-control.md)」および「 [lync server 2013 でのビデオ帯域幅の構成](lync-server-2013-configuring-video-bandwidth.md)」を参照してください。

</div>

<div>

## <a name="archiving-and-compliance-features"></a>アーカイブとコンプライアンスの機能

Lync Server 2013 には、組織が法令遵守規制に従う必要がある場合に使用できる機能が用意されています。 アーカイブ機能を使用して、会議に提示されたコンテンツや、インスタントメッセージング (IM) の会話や IM 会議の内容をアーカイブすることもできます。 詳細については、「計画」のドキュメントの「 [planning For アーカイビング In Lync Server 2013](lync-server-2013-planning-for-archiving.md) 」を参照してください。 常設チャットサーバーのコンプライアンス機能を使用して、長期間にわたって保持されるマルチパーティのトピックベースの会話をアーカイブすることができます。 詳細については、「計画」のドキュメントの「 [Lync server 2013 での常設チャットサーバーの計画](lync-server-2013-planning-for-persistent-chat-server.md)」を参照してください。

</div>

<div>

## <a name="monitoring-feature"></a>監視機能

監視サーバー機能は、通話詳細レコード (Cdr) をキャプチャできます。これを使用して、どのユーザーが Lync Server 2013 を使用している他のユーザーにどのようなユーザーを伝えるかを追跡できます。 監視の展開と構成の詳細については、「 [Lync Server 2013 での監視の展開](lync-server-2013-deploying-monitoring.md)」を参照してください。

</div>

<div>

## <a name="enabling-external-participation-in-conferences"></a>会議への外部参加を有効にする

招待されたときに外部ユーザーが会議に参加できるようにすることで、Lync Server 2013 会議への投資のメリットを大幅に向上させることができます。 外部ユーザーには次のユーザーが含まれます。

  - **リモートユーザー**   ファイアウォールの外側で作業していて、ラップトップやその他の Lync Server 2013 デバイスを使用している場合は、組織のユーザーを所有します。

  - ****   Lync Server 2013 を実行しているユーザーと共同で作業する企業のフェデレーションユーザー。 こちら側のユーザーがこれらのユーザーに容易にコンタクトできるようにするには、これらの企業とフェデレーション関係を作成する必要があります。

  - **匿名ユーザー**   ユーザーが特定の会議に参加することを明示的に招待されている他の外部ユーザー。 自社の会議開催者は、会議への電子メールの招待状を外部ユーザーに送信できます。 電子メールには、外部ユーザーがクリックして会議に参加できるリンクがあります。

これらのシナリオのいずれかまたはすべてを有効にするには、Lync server 2013 の展開と外部ユーザーとの間でセキュリティで保護された通信を有効にするためにエッジサーバーを展開する必要があります。 エッジサーバーを使用する Lync Server 2013 ソリューションは、仮想プライベートネットワーク (VPN) などの他のソリューションよりも高品質のメディアを提供します。 詳細については、「 [Lync Server 2013 での外部ユーザーアクセスの計画](lync-server-2013-planning-for-external-user-access.md)」を参照してください。

また、エッジサーバーを展開するかどうかにかかわらず、ユーザーが標準の PSTN 電話からダイヤルインしてオンプレミスの音声会議に参加できるようにすることができます。 これは、Lync Server 2013 ダイヤルイン会議を展開することによって実現されます。

</div>

<div>

## <a name="compatibility-among-meeting-types-and-client-versions"></a>ミーティングの種類およびクライアント バージョン間の互換性

Lync Server 2013 を以前のバージョンの Office Communications Server とそのクライアントと相互運用するには、次の点に注意する必要があります。

  - Lync Server 2013 を使用しているユーザーは、Live Meeting 会議をスケジュールしたり、この種類の移行された会議を変更したりすることはできません。

  - Lync Server 2013 を使用しているユーザーが、Office Communications Server 2007 R2 を実行しているサーバーでホストされている Live Meeting 会議に出席する必要がある場合、これらの会議に参加するには、そのコンピューターに Live Meeting クライアント (Lync Server 2013 に加えて) がインストールされている必要があります。

  - Live Meeting 会議が Lync Server 2013 に移行されると、会議コンテンツは移行されません。 その内容が必要な場合は、再びアップロードする必要があります。

</div>

</div>

<span> </span>

</div>

</div>

</div>

