---
title: 'Lync Server 2013: Microsoft Lync の展開方法の決定'
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
ms.openlocfilehash: fdd7deb87eef28e3b439f290f6da5a90d2fe50dc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187370"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deciding-how-to-deploy-lync-server-2013"></a>Lync Server 2013 の展開方法を決定する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-03_

Lync を計画する場合、最初の主要な決定は、Microsoft Lync: Lync Server 2013 をオンプレミスとして展開する方法、またはクラウド内の Microsoft Office 365 で Lync Online を展開する方法です。

  - **Lync Server 2013 オンプレミス**: これにより、lync のすべての機能セットが提供され、展開の構成、カスタマイズ、および運用を極めて柔軟に行うことができます。 すべてのサーバーはオンサイトでインストールされ、組織によって保守されます。 オンプレミスの展開では、Lync Server のすべての機能が提供されます。

  - **クラウド内の Lync Online**Lync Online は、Lync Server のビジネスクラス機能を犠牲にせずに、クラウドベースのインスタントメッセージング、プレゼンス、および会議のコストとアジリティのメリットを必要とする組織向けに設計されています。 Lync Online では、Microsoft によって必要なサーバーインフラストラクチャが展開および維持され、継続的なメンテナンス、パッチ、およびアップグレードが処理されます。 オンプレミスの展開で使用できる一部の機能は、Lync Online では使用できません。

どちらの種類の展開が最も適しているかは、展開する負荷と、組織の地理的状況およびビジネスの状況によって異なります。

<div>

## <a name="lync-server"></a>Lync Server

内部設置型の Lync Server 展開は、次のようなシナリオに最適です。

  - **完全なエンタープライズ voip 機能**   完全なエンタープライズ voip ソリューションを展開して PBX を交換したり、高度な通話機能を使用したりする場合は、オンプレミスの Lync Server の展開が必要です。 オンプレミスは、PBX システムとトランクとの直接接続、および応答グループやコールパークなどの高度な電話機能をサポートします。 Lync Online は現在これらの機能をサポートしていません。

  - **メディア品質管理**   通話受付管理 (CAC) 機能やサービスの品質 (QoS) 機能などのメディア品質保証機能の全範囲が必要な場合は、オンプレミスの展開が必要になります。

  - **常設チャット**   組織の常設チャットを展開する必要がある場合は、オンプレミスの展開を選択する必要があります。

  - **サードパーティのサーバーアプリケーション**   社内展開のみが、Microsoft ユニファイドコミュニケーションマネージ API (ucma) を使用する、信頼されたサードパーティアプリケーションと連携することができます。

  - **地域のサポート**   を必要とする多国籍/複数地域の企業複数の国または地域にデータセンターがあり、地域ベースでサーバーを展開および管理する必要がある場合は、この種の地域管理機能を提供するため、オンプレミスの展開が最適です。

  - ****   オンプレミスの Lync Server 展開を使用して、ポリシー、レポート、およびアップグレードを完全に制御することにより、サーバーとクライアントのポリシーの完全なセット、監視やその他のレポート、アップグレードのタイミングにアクセスできるようになります。 Lync Online では、ポリシー設定とレポートのサブセットが提供されており、アップグレードを受け入れるために非常に限定的なウィンドウが提供されます。

</div>

<div>

## <a name="lync-online"></a>Lync Online

上記のどの要素も重要でない場合は、より展開が簡単で管理しやすい Lync Online を選択できます。 Lync Online は、堅牢な IM、プレゼンス、会議機能セットを提供し、組織内のユーザー間で IP 経由で音声およびビデオ通話を行うこともできます。

</div>

</div>

<span> </span>

</div>

</div>

</div>

