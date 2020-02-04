---
title: 'Lync Server 2013: Microsoft Lync 展開方法の決定'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deciding how to deploy Microsoft Lync
ms:assetid: 6ca677d3-745d-4935-8f05-19274a8bccf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204979(v=OCS.15)
ms:contentKeyID: 48184423
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aef6ac76b6c0e8a6fb3c0444ab219acf78119ecd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728557"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deciding-how-to-deploy-lync-server-2013"></a>Lync Server 2013 展開方法の決定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-03_

Lync を計画する場合、最初の主な決定は、Microsoft Lync: Lync Server 2013 を社内に展開する方法、またはクラウドの Microsoft Office 365 で Lync Online を展開する方法です。

  - **Lync Server 2013 オンプレミス**: lync のすべての機能セットが提供され、展開の構成、カスタマイズ、および操作に最適な柔軟性が提供されます。 すべてのサーバーがオンサイトにインストールされ、組織によって管理されます。 オンプレミスの展開では、Lync Server のさまざまな機能が提供されます。

  - **クラウドでの Lync Online**Lync Online は、Lync Server のビジネスクラス機能を犠牲にすることなく、クラウドベースのインスタントメッセージング、プレゼンス、会議のコストとアジリティの向上を希望する組織向けに設計されています。 Lync Online を使用すると、Microsoft は必要なサーバーインフラストラクチャを展開して管理し、継続的なメンテナンス、パッチ、アップグレードを処理します。 オンプレミスの展開で利用できる機能の一部は、Lync Online では利用できません。

どのような種類の展開を使用するかは、展開するワークロードと組織の地理的状態とビジネス状態によって異なります。

<div>

## <a name="lync-server"></a>Lync Server

オンプレミスの Lync Server 展開は、次のシナリオに適しています。

  - **完全なエンタープライズ音声機能**   PBX の代わりとして、または高度な通話機能を使用する完全なエンタープライズボイスソリューションを展開する予定がある場合は、オンプレミスの Lync Server を展開する必要があります。 オンプレミスは、PBX システムと trunks との直接接続、および応答グループやコールパークなどの高度な電話機能をサポートします。 現時点では、Lync Online はこれらの機能をサポートしていません。

  - **メディア品質コントロール**   通話受付制御 (CAC) 機能やサービス品質 (QoS) 機能など、さまざまな種類のメディア品質保証機能が必要な場合は、オンプレミスの展開が必要になります。

  - **常設チャット**   組織に常設チャットを展開する必要がある場合は、オンプレミスの展開を選択する必要があります。

  - **サードパーティのサーバーアプリケーション**   では、オンプレミスの展開のみが、Microsoft ユニファイドコミュニケーションマネージ API を使う信頼されたサードパーティアプリケーションと連携できます (ucma)。

  - **地域のサポート**   が必要な複数地域の企業、複数の国または地域のデータセンターがあり、各地域にサーバーを展開して管理する必要がある場合は、オンプレミスの展開をお勧めします。この種類の地域管理機能が提供されます。

  - ****   オンプレミスの Lync Server 展開でポリシー、レポート、アップグレードを管理することで、サーバーとクライアントのすべてのポリシー、監視およびその他のレポート、アップグレードのタイミングにアクセスできます。 Lync Online には、ポリシー設定とレポートのサブセットが用意されています。このウィンドウには、アップグレードを承認するための重要なウィンドウが含まれています。

</div>

<div>

## <a name="lync-online"></a>Lync Online

上に挙げた要因が自分にとって重要ではない場合は、[Lync Online] を選んで、展開と管理性をさらに向上させることができます。 Lync Online は、強力な IM、プレゼンス、会議機能のセットを提供します。また、組織内のユーザー間での音声通話とビデオ通話も可能になります。

</div>

</div>

<span> </span>

</div>

</div>

</div>

