---
title: 'Lync Server 2013: 電話会議の Location-Based ルーティング'
description: 'Lync Server 2013: 電話会議の Location-Based ルーティング。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location-Based Routing for conferencing
ms:assetid: e1acb1ba-0ed2-4abf-8a7b-1ca3049e95e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362849(v=OCS.15)
ms:contentKeyID: 56335087
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 979c835e03bbf87c9a9bf86b030cb9a8f4e138e0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554853"
---
# <a name="location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="85dc8-103">Lync Server 2013 での会議の Location-Based ルーティング</span><span class="sxs-lookup"><span data-stu-id="85dc8-103">Location-Based Routing for conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85dc8-104">_**トピックの最終更新日:** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="85dc8-104">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="85dc8-105">Location-Based ルーティングを使用すると、通話の当事者の場所に基づいて VoIP エンドポイントと PSTN エンドポイント間の通話のルーティングを制限することができます。</span><span class="sxs-lookup"><span data-stu-id="85dc8-105">Location-Based Routing makes it possible to restrict the routing of calls between VoIP endpoints and PSTN endpoints based on the location of the parties in the call.</span></span> <span data-ttu-id="85dc8-106">Lync Server 2013 の累積的な更新プログラム2では、Location-Based のルーティングルールを Lync 会議 (会議など) に適用して、PSTN の有料電話を回避できます。</span><span class="sxs-lookup"><span data-stu-id="85dc8-106">With Cumulative Update 2 of Lync Server 2013, Location-Based Routing rules can be enforced on Lync meetings (i.e. conferences) to prevent PSTN toll bypass.</span></span> <span data-ttu-id="85dc8-107">アプリケーションはアクティブな会議を監視し、参加しているユーザーの場所に基づいて Location-Based ルーティング制限を適用します。</span><span class="sxs-lookup"><span data-stu-id="85dc8-107">The application monitors an active conference and enforces Location-Based Routing restrictions based on the location of users participating.</span></span> <span data-ttu-id="85dc8-108">また Location-Based ルーティング会議アプリケーションでは、PSTN エンドポイントを使用する提案転送に Location-Based ルーティング制限を適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="85dc8-108">The Location-Based Routing Conferencing application additionally enables the enforcement of Location-Based Routing restrictions to consultative transfers involving PSTN endpoints.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="85dc8-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="85dc8-109">In This Section</span></span>

  - [<span data-ttu-id="85dc8-110">Lync Server 2013 での会議の Location-Based ルーティングの概要</span><span class="sxs-lookup"><span data-stu-id="85dc8-110">Overview of Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-overview-of-location-based-routing-for-conferencing.md)

  - [<span data-ttu-id="85dc8-111">Lync Server 2013 での場所に基づくルーティングおよびコンサルティング呼び出しの転送</span><span class="sxs-lookup"><span data-stu-id="85dc8-111">Location-Based Routing and consultative call transfers in Lync Server 2013</span></span>](lync-server-2013-location-based-routing-and-consultative-call-transfers.md)

  - [<span data-ttu-id="85dc8-112">Lync Server 2013 での会議の Location-Based ルーティングの要件</span><span class="sxs-lookup"><span data-stu-id="85dc8-112">Requirements for Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-requirements-for-location-based-routing-for-conferencing.md)

  - [<span data-ttu-id="85dc8-113">Lync Server 2013 での会議の Location-Based ルーティングの構成</span><span class="sxs-lookup"><span data-stu-id="85dc8-113">Configuration of Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-configuration-of-location-based-routing-for-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

