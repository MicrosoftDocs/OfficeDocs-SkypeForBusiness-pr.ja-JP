---
title: 'Lync Server 2013: フロントエンドサーバー、インスタントメッセージング、およびプレゼンスの特徴と機能'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Features and functionality of Front End Servers, instant messaging, and presence
ms:assetid: 05b29536-dcd7-49b5-934a-2ebf20ddc45c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398109(v=OCS.15)
ms:contentKeyID: 48183294
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8e25a74dcffe76f16b12a8c80f8ad8f980370dc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041036"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="features-and-functionality-of-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a>Lync Server 2013 のフロントエンドサーバー、インスタントメッセージング、およびプレゼンスの特徴と機能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-03-17_

フロントエンドサーバーは、ほとんどの Lync Server 機能を提供します。 次の2つのエディションがあります。 Lync Server Enterprise Edition は、主に大規模な組織向けに設計されており、主に小規模の組織向けに設計されており、小規模のハードウェア investement を必要とします。高可用性が必要です。 両方のエディションは、IM、プレゼンス、会議、エンタープライズ Voip などのすべての Lync Server ワークロードをサポートしています。

インスタント メッセージング (IM) を使用すると、ユーザーは各自のコンピューターでテキスト ベースのメッセージを使用して、リアルタイムで相互通信を行うことができます。 2 パーティとマルチパーティの両方の IM セッションがサポートされています。 2 パーティの IM 会話の参加者は、3 番目の参加者をいつでも会話に追加できます。 この際には、会議機能をサポートするように会話ウィンドウが変更されます。

<div>


> [!IMPORTANT]
> 1対1の通信に関係する Lync および Communicator クライアントは、ピアツーピアと呼ばれることがよくあります。 技術的には、2つのクライアントは1つの会話に、インスタントメッセージング multipoint control unit (IMMCU) を中央に持つ1つの会話と通信します。 IMMCU はフロントエンドサーバーのコンポーネントです。 必要な通信ワークフローに IMMCU を配置すると、フロントエンドサーバーが有効になっている通話詳細記録およびその他の機能を使用できるようになります。 クライアント上の動的送信元ポートからフロントエンドサーバーポート TLS/TCP/5061 への通信です (推奨トランスポート層セキュリティを使用していることを前提としています)。 設計上、Lync Server と IMMCU がアクティブで利用可能な場合にのみ、ピアツーピア通信 (およびマルチパーティ IM) を使用できます。



</div>

プレゼンス** は、ネットワーク上の他のユーザーの状態に関する情報をユーザーに提供します。 ユーザーのプレゼンス状態からは、他のユーザーがそのユーザーに連絡してもよいかどうかや、連絡する場合にインスタント メッセージング、電話、および電子メールのどれを使用するかを判断するのに役立つ情報を得ることができます。 プレゼンスにより、可能な場合は即時に通信しやすくなりますが、ユーザーが会議中であるかどうかや、外出のために応答できない状況なのかに関する情報も提供されます。 このプレゼンス状態は、Lync などのプレゼンスアイコンとして表示されます。これには、Microsoft Outlook メッセージングおよびコラボレーションクライアント、Microsoft SharePoint テクノロジ、microsoft Word、microsoft Excel スプレッドシートなどのその他のプレゼンスを認識するアプリケーションがあります。ソフトウェア. プレゼンス アイコンからは、そのユーザーの現在の状態と、連絡してもよいかどうかを判別できます。

</div>

<span> </span>

</div>

</div>

</div>

