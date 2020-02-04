---
title: 'Lync Server 2013: 会議の計画'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for conferencing
ms:assetid: 983a272a-e1b3-4d70-8f84-836b092fe526
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398781(v=OCS.15)
ms:contentKeyID: 48184937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53b7813a197dd7cc3116540c605d7efbdb22a04b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725437"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-conferencing-in-lync-server-2013"></a>Lync Server 2013 での会議の計画

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-01-29_

Lync Server 2013 には、次のような豊富な会議機能が用意されています。

  - Web 会議。ドキュメントのグループ作業、アプリの共有、デスクトップ共有が含まれます。 Lync Server 2013 は、PowerPoint プレゼンテーションの共有とレンダリングを処理するために、Office Web Apps と Office Web Apps サーバーを使用します。 Office Web Apps サーバーのインストールと構成の詳細については、「 [Office Web Apps サーバーおよび Lync server 2013 との統合を構成する](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)」を参照してください。

  - 音声/ビデオ (A/V) 会議: Microsoft Live Meeting サービスやサードパーティのオーディオブリッジなどの外部サービスを必要とせずに、リアルタイムの音声通話またはビデオ会議を行うことができます。

  - ダイヤルイン会議: ユーザーは、サードパーティの電話会議プロバイダーを必要とせずに、公衆交換電話網 (PSTN) 電話を使って、Lync Server 2013 会議のオーディオ部分に参加することができます。

  - インスタントメッセージング (IM) 会議: 3 人以上の当事者が単一の IM セッションで通信します。 IM 会議の詳細については、「 [Lync Server 2013 でのフロントエンドサーバー、インスタントメッセージング、およびプレゼンスの計画](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md)」を参照してください。

Lync Server 2013 は、スケジュールされた会議と一時的会議の両方をサポートしています。

Lync Server 2013、フロントエンドサーバーを展開するときに、web 会議、A/V 会議、ダイヤルイン会議機能も展開するかどうかを選ぶことができます。 IM 会議機能は、Lync Server 2013 フロントエンドサーバーの IM 会話機能と共に、常に自動的に展開されます。

<div>


> [!NOTE]  
> 展開に Office Communicator 2007 R2 クライアント (Microsoft Office Outlook 用 Live Meeting 本体または電話会議アドインを含む) を使って開催された会議が含まれている場合、会議は Lync に移行した後に次の制限があります。サーバー 2013: 
> <UL>
> <LI>
> <P>会議に参加しているユーザーは、ドキュメントのグループ作業、アプリケーション共有、デスクトップ共有などのデータコラボレーション機能を使用できなくなります。</P>
> <LI>
> <P>Office Communicator 2007 R2 クライアントが Lync Server 2013 でサポートされていないため、安定性の問題が発生する場合があります。</P></LI></UL>これらの問題を回避するには、lync 2010 用のオンライン会議アドインまたは Lync 2013 用オンライン会議アドインのいずれかを使用して、Office Communicator 2007 R2 2013 2010 クライアントを使用して開催される会議を再スケジュールします。



</div>

以下のセクションでは、計画プロセス、コンポーネント、ハードウェアとソフトウェアの要件、展開プロセスなど、さまざまな種類の会議機能を展開するために必要なものについて説明します。

<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 での会議の概要](lync-server-2013-overview-of-conferencing.md)

  - [Lync Server 2013 での会議の要件の定義](lync-server-2013-defining-your-requirements-for-conferencing.md)

  - [Lync Server 2013 の会議のコンポーネントおよびトポロジ](lync-server-2013-components-and-topologies-for-conferencing.md)

  - [Lync Server 2013 の会議の技術要件](lync-server-2013-technical-requirements-for-conferencing.md)

  - [Lync Server 2013 の会議の展開チェックリスト](lync-server-2013-deployment-checklist-for-conferencing.md)

  - [Lync Server 2013 での大規模会議のサポート](lync-server-2013-support-for-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

