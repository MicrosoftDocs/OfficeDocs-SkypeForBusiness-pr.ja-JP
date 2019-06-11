---
title: 'Lync Server 2013: フロントエンド サーバー、インスタント メッセージングおよびプレゼンスの特徴と機能'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Features and functionality of Front End Servers, instant messaging, and presence
ms:assetid: 05b29536-dcd7-49b5-934a-2ebf20ddc45c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398109(v=OCS.15)
ms:contentKeyID: 48183294
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 739825eed3c8a3ba8239849e0c17c449180a2d95
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833157"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="features-and-functionality-of-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a>Lync Server 2013 のフロントエンド サーバー、インスタント メッセージングおよびプレゼンスの特徴と機能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-03-17_

フロントエンドサーバーは、ほとんどの Lync Server 機能を提供します。 次の2つのエディションがあります。 Lync Server Enterprise Edition は、主に大規模な組織向けに設計されています。また、主に小規模の組織向けに設計されています。これは、より小さいハードウェアの investement を必要とします。高可用性が必要です。 どちらのエディションも、IM、プレゼンス、会議、エンタープライズ Voip などのすべての Lync Server ワークロードをサポートしています。

インスタント メッセージング (IM) を使用すると、ユーザーは各自のコンピューターでテキスト ベースのメッセージを使用して、リアルタイムで相互通信を行うことができます。 2 パーティとマルチパーティの両方の IM セッションがサポートされています。 2 パーティの IM 会話の参加者は、3 番目の参加者をいつでも会話に追加できます。 この際には、会議機能をサポートするように会話ウィンドウが変更されます。

<div>


> [!IMPORTANT]
> Lync と Communicator クライアントが1対1の通信に関わる場合、ピアツーピアと呼ばれることがよくあります。 技術的には、2つのクライアントは1つの会話と1つの会話の間でやり取りされ、中央にはインスタントメッセージング multipoint コントロールユニット (IMMCU) が含まれます。 IMMCU は、フロントエンドサーバーのコンポーネントです。 必要な通信ワークフローに IMMCU を配置すると、フロントエンドサーバーが有効になっている通話の詳細の記録とその他の機能を使用できます。 通信は、クライアント上の動的ソースポートからフロントエンドサーバーポート TLS/TCP/5061 に送信されます (推奨トランスポート層セキュリティを使用していることを前提としています)。 設計上、ピアツーピア通信 (およびマルチパーティの IM) は、Lync Server と IMMCU がアクティブで利用可能な場合にのみ可能です。



</div>

*プレゼンス*は、ネットワーク上の他の状態に関する情報をユーザーに提供します。 ユーザーのプレゼンス状態からは、他のユーザーがそのユーザーに連絡してもよいかどうかや、連絡する場合にインスタント メッセージング、電話、メールのどれを使用するかを判断するのに役立つ情報が得られます。 プレゼンスにより、可能な場合にはすぐにやりとりできますが、他にも、ユーザーが会議中であるかどうかや、外出のために応答できない状況なのかに関する情報も提供されます。 このプレゼンス状態は、Microsoft Outlook メッセージングおよびコラボレーションクライアント、Microsoft SharePoint テクノロジ、Microsoft Word、Microsoft Excel スプレッドシートなど、Lync およびその他のプレゼンスに対応しているアプリケーションのプレゼンスアイコンとして表示されます。プログラム. プレゼンス アイコンからは、そのユーザーの現在の状態と、連絡してもよいかどうかを判別できます。

</div>

<span> </span>

</div>

</div>

</div>

