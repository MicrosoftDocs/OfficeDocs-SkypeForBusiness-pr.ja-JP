---
title: 'Lync Server 2013: 会議の場所に基づくルーティング'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Location-Based Routing for conferencing
ms:assetid: e1acb1ba-0ed2-4abf-8a7b-1ca3049e95e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362849(v=OCS.15)
ms:contentKeyID: 56335087
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ee4c8f996315ede0fd0f7ccd789a73cad25c4f3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832936"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="1289c-102">Lync Server 2013 での会議の位置情報に基づくルーティング</span><span class="sxs-lookup"><span data-stu-id="1289c-102">Location-Based Routing for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1289c-103">_**最終更新日:** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="1289c-103">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="1289c-104">位置情報に基づくルーティングを使用すると、通話中の当事者の位置に基づいて、VoIP エンドポイントと PSTN エンドポイント間での通話のルーティングを制限することができます。</span><span class="sxs-lookup"><span data-stu-id="1289c-104">Location-Based Routing makes it possible to restrict the routing of calls between VoIP endpoints and PSTN endpoints based on the location of the parties in the call.</span></span> <span data-ttu-id="1289c-105">Lync Server 2013 の累積的な更新プログラム2を使用すると、場所に基づくルーティングルールを Lync 会議 (会議など) に適用して、PSTN の有料電話のバイパスを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="1289c-105">With Cumulative Update 2 of Lync Server 2013, Location-Based Routing rules can be enforced on Lync meetings (i.e. conferences) to prevent PSTN toll bypass.</span></span> <span data-ttu-id="1289c-106">アプリケーションは、参加しているユーザーの場所に基づいて、アクティブな会議を監視し、位置に基づくルーティング制限を適用します。</span><span class="sxs-lookup"><span data-stu-id="1289c-106">The application monitors an active conference and enforces Location-Based Routing restrictions based on the location of users participating.</span></span> <span data-ttu-id="1289c-107">位置に基づくルーティング会議アプリケーションでは、PSTN エンドポイントを含む提案型転送への位置情報に基づくルーティング制限の適用を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="1289c-107">The Location-Based Routing Conferencing application additionally enables the enforcement of Location-Based Routing restrictions to consultative transfers involving PSTN endpoints.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1289c-108">このセクション中</span><span class="sxs-lookup"><span data-stu-id="1289c-108">In This Section</span></span>

  - [<span data-ttu-id="1289c-109">Lync Server 2013 での会議の位置情報に基づくルーティングの概要</span><span class="sxs-lookup"><span data-stu-id="1289c-109">Overview of Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-overview-of-location-based-routing-for-conferencing.md)

  - [<span data-ttu-id="1289c-110">Lync Server 2013 での位置情報に基づくルーティングとコンサルティングによる通話転送</span><span class="sxs-lookup"><span data-stu-id="1289c-110">Location-Based Routing and consultative call transfers in Lync Server 2013</span></span>](lync-server-2013-location-based-routing-and-consultative-call-transfers.md)

  - [<span data-ttu-id="1289c-111">Lync Server 2013 での会議の位置情報に基づくルーティングの要件</span><span class="sxs-lookup"><span data-stu-id="1289c-111">Requirements for Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-requirements-for-location-based-routing-for-conferencing.md)

  - [<span data-ttu-id="1289c-112">Lync Server 2013 での会議のための場所に基づくルーティングの構成</span><span class="sxs-lookup"><span data-stu-id="1289c-112">Configuration of Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-configuration-of-location-based-routing-for-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

