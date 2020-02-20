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
ms.openlocfilehash: ca0fd8edb6e2939b82711392c53b0e5bef3e7740
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152937"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-conferencing-in-lync-server-2013"></a>Lync Server 2013 での会議の計画

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-01-29_

Lync Server 2013 には、会議機能の豊富なセットが用意されています。

  - Web 会議には、ドキュメントのコラボレーション、アプリケーション共有、デスクトップ共有が含まれます。 Lync Server 2013 は、Office Web Apps および Office Web Apps サーバーを使用して、PowerPoint プレゼンテーションの共有とレンダリングを処理します。 Office Web Apps サーバーのインストールと構成の詳細については、「 [Office Web Apps server および Lync Server 2013 との統合の構成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)」を参照してください。

  - 音声ビデオ (A/V) 会議では、ユーザーがリアルタイムの電話会議またはビデオ会議を行うことが可能です。Microsoft Live Meeting サービスまたはサードパーティの音声ブリッジのような外部サービスを使用する必要もありません。

  - ダイヤルイン会議は、ユーザーがサードパーティの電話会議プロバイダーを必要とせずに公衆交換電話網 (PSTN) 電話を使用して、Lync Server 2013 会議のオーディオ部分に参加できるようにします。

  - インスタント メッセージング (IM) 会議では、単一の IM セッションで複数者間で通信できます。 IM 会議の詳細については、「 [Lync Server 2013 でのフロントエンドサーバー、インスタントメッセージング、およびプレゼンスの計画](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md)」を参照してください。

Lync Server 2013 は、スケジュールされた会議と即時会議の両方をサポートしています。

Lync Server 2013 のフロントエンドサーバーを展開する場合は、web 会議、音声ビデオ会議、およびダイヤルイン会議機能も展開するかどうかを選択できます。 IM 会議機能は、Lync Server 2013 フロントエンドサーバー上の IM 会話機能と共に常に自動的に展開されます。

<div>


> [!NOTE]  
> 展開に Office Communicator 2007 R2 クライアント (Microsoft Office Outlook 用 Live Meeting コンソールまたは電話会議アドインを含む) を使用して開催された会議が含まれる場合、会議は Lync に移行された後、次の制限があります。サーバー 2013: 
> <UL>
> <LI>
> <P>会議のユーザーは、ドキュメントのグループ作業、アプリケーション共有、およびデスクトップ共有などのデータコラボレーション機能を使用できません。</P>
> <LI>
> <P>Office Communicator 2007 R2 クライアントは Lync Server 2013 ではサポートされていないため、安定性の問題が発生することがあります。</P></LI></UL>これらの問題を回避するには、Office Communicator 2007 R2 クライアントを使用して開催されたすべての会議を、Lync 2010 用オンラインミーティングアドインまたは Lync 2013 オンラインミーティングアドインのいずれかを使用して、Outlook 2010 または Outlook 2013 を使用して再スケジュールします。



</div>

次のセクションでは、計画プロセス、コンポーネント、ハードウェアおよびソフトウェアの要件、および展開プロセスを含む、様々な種類の会議機能の展開に必要な項目について説明します。

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 での会議の概要](lync-server-2013-overview-of-conferencing.md)

  - [Lync Server 2013 での会議の要件の定義](lync-server-2013-defining-your-requirements-for-conferencing.md)

  - [Lync Server 2013 の会議のコンポーネントとトポロジ](lync-server-2013-components-and-topologies-for-conferencing.md)

  - [Lync Server 2013 での会議の技術要件](lync-server-2013-technical-requirements-for-conferencing.md)

  - [Lync Server 2013 での会議の展開チェックリスト](lync-server-2013-deployment-checklist-for-conferencing.md)

  - [Lync Server 2013 での大規模会議のサポート](lync-server-2013-support-for-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

