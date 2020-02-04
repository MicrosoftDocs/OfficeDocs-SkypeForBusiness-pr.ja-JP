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
ms.openlocfilehash: 91d21526cfcd6d2c78cd67660136e8f7600d1841
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742777"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="common-conferencing-concepts-in-lync-server-2013"></a>Lync Server 2013 での一般的な会議の概念

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-19_

いくつかの概念は、すべての種類の会議に共通しています。 これらについては、次のセクションで説明します。

<div>

## <a name="policies-and-bandwidth-management"></a>ポリシーと帯域幅の管理

Lync Server 2013 を使用すると、管理者は、ユーザーが整理できる会議の種類に対してポリシーを設定できます。 これにより、組織のポリシーを適用し、帯域幅の使用を制御することができます。 さまざまな会議のポリシーを定義し、個々のユーザーやユーザーのグループに割り当てることができます。 また、ピアツーピア会話を制御するポリシーを設定することもできます。 会議ポリシーの設定の詳細については、操作のドキュメントの「 [Lync Server 2013 の会議ポリシー](lync-server-2013-conferencing-policies.md) 」を参照してください。 帯域幅管理の詳細については、「 [Lync server 2013 での通話受付制御の概要](lync-server-2013-overview-of-call-admission-control.md)」および「 [lync server 2013 でのビデオの帯域幅の構成](lync-server-2013-configuring-video-bandwidth.md)」を参照してください。

</div>

<div>

## <a name="archiving-and-compliance-features"></a>アーカイブとコンプライアンスの機能

Lync Server 2013 には、組織が法令遵守規則に従う必要がある場合に使用できる機能が用意されています。 アーカイブ機能を使用して、会議に表示されたコンテンツをアーカイブしたり、インスタントメッセージング (IM) の会話や IM 会議のコンテンツをアーカイブすることができます。 詳細については、計画ドキュメントの「 [Lync Server 2013 でのアーカイブの計画](lync-server-2013-planning-for-archiving.md)」を参照してください。 常設チャットサーバーのコンプライアンス機能を使用して、時間の経過と共に保持されるマルチパーティのトピックベースの会話をアーカイブすることができます。 詳細については、計画ドキュメントの「 [Lync server 2013 での常設チャットサーバーの計画](lync-server-2013-planning-for-persistent-chat-server.md)」を参照してください。

</div>

<div>

## <a name="monitoring-feature"></a>監視機能

監視サーバー機能は、通話の詳細レコード (CDRs) を取得できます。この機能を使って、Lync Server 2013 を使っている他のユーザーとどのユーザーを話すかを追跡できます。 監視の展開と構成の詳細については、「 [Lync Server 2013 での監視の展開](lync-server-2013-deploying-monitoring.md)」を参照してください。

</div>

<div>

## <a name="enabling-external-participation-in-conferences"></a>会議での外部参加を有効にする

招待された場合は、外部ユーザーが会議に参加できるようにすることで、Lync Server 2013 会議での投資の利点を大幅に高めることができます。 外部ユーザーには次のユーザーが含まれます。

  - **リモートユーザー**   は、ファイアウォール外で作業していて、ノート pc やその他の Lync Server 2013 デバイスを使用している場合に、組織の独自のユーザーを管理します。

  - ****   Lync Server 2013 を実行している企業の会社からフェデレーションされたユーザー。 自社ユーザーがこうしたユーザーに容易にコンタクトできるようにするには、これらの企業とフェデレーション関係を作成する必要があります。

  - **匿名ユーザー**   ユーザーが特定の会議に参加することを明示的に招待されている他の外部ユーザー。 会社の会議の開催者は、会議の招待メールを外部ユーザーに送信することができます。 このメールには、外部ユーザーがクリックして会議に参加するためのリンクが含まれています。

これらのシナリオのいずれか、またはすべてを有効にするには、microsoft の Lync Server 2013 の展開と外部ユーザーとの間でセキュリティで保護された通信を有効にするためにエッジサーバーを展開する必要があります。 エッジサーバーを使用する Lync Server 2013 ソリューションは、仮想プライベートネットワーク (VPN) などの他のソリューションよりも高品質のメディアを提供します。 詳細については、「 [Lync Server 2013 での外部ユーザーアクセスの計画](lync-server-2013-planning-for-external-user-access.md)」を参照してください。

さらに、エッジサーバーを展開するかどうかにかかわらず、ユーザーが標準の PSTN 電話からダイヤルインしてオンプレミスの音声会議に参加できるようにすることができます。 これは、Lync Server 2013 ダイヤルイン会議を展開することによって実現されます。

</div>

<div>

## <a name="compatibility-among-meeting-types-and-client-versions"></a>会議の種類とクライアントバージョン間の互換性

Lync Server 2013 を以前のバージョンの Office Communications Server とそのクライアントと相互運用できるようにするには、次の問題を認識しておく必要があります。

  - Lync Server 2013 を使用しているユーザーは、Live Meeting 会議をスケジュールしたり、この種類の移行した会議を変更したりすることはできません。

  - Office Communications Server 2007 R2 を実行しているサーバーでホストされている Live Meeting 会議に参加する必要がある Lync Server 2013 を使っているユーザーは、これらの会議に参加するために、Live Meeting クライアントを (Lync Server 2013 に加えて) コンピューターにインストールしておく必要があります。

  - Live Meeting 会議が Lync Server 2013 に移行されると、会議コンテンツが移行されません。 このコンテンツが必要な場合は、もう一度アップロードする必要があります。

</div>

</div>

<span> </span>

</div>

</div>

</div>

