---
title: 'Lync Server 2013: Enhanced 9-1-1 の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Enhanced 9-1-1
ms:assetid: 5967de00-c8b9-4923-86da-6ad3369a4cad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398390(v=OCS.15)
ms:contentKeyID: 48184205
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0ef94e3de028f66684972fa6a3c95d4e63c35b5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840371"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-enhanced-9-1-1-in-lync-server-2013"></a><span data-ttu-id="f816c-102">Lync Server 2013 での Enhanced 9-1-1 の構成</span><span class="sxs-lookup"><span data-stu-id="f816c-102">Configure Enhanced 9-1-1 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f816c-103">_**最終更新日:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="f816c-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="f816c-p101">拡張 9-1-1 (E9-1-1) は、発信者の電話番号を正式な住所または主要道路住所に関連付ける緊急通知機能です。緊急応答機関 (PSAP) はこの情報を使用して、支援を必要とする発信者に緊急サービスをすぐに派遣できます。</span><span class="sxs-lookup"><span data-stu-id="f816c-p101">Enhanced 9-1-1 (E9-1-1) is an emergency notification feature that associates the calling party’s telephone number with a civic or a street address. Using this information, the Public Safety Answering Point (PSAP) can immediately dispatch emergency services to the caller in distress.</span></span>

<span data-ttu-id="f816c-106">E9-1-1 をサポートするには、Lync Server 2013 で、場所とクライアントを正しく関連付け、緊急通話を最も近い PSAP にルーティングするためにこの情報が使用されるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f816c-106">To support E9-1-1, Lync Server 2013 must be able to correctly associate a location with a client and to make sure that this information is used to route the emergency call to the nearest PSAP.</span></span>

<span data-ttu-id="f816c-107">E9 の展開の計画について詳しくは、「 [Lync Server 2013 の緊急サービスの計画 (E9-1)](lync-server-2013-planning-for-emergency-services-e9-1-1.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f816c-107">For details about planning for an E9-1-1 deployment, see [Planning for emergency services (E9-1-1) in Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f816c-108">Lync Server 2013 は、米国内の E9-1-1 のみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="f816c-108">Lync Server 2013 only supports E9-1-1 within the United States.</span></span> <span data-ttu-id="f816c-109">E9 を展開するには、認定された E9 サービスプロバイダーへの SIP 接続を構成するか、公衆交換電話 (PSTN) ベースの E9 サービスプロバイダーに緊急対応の場所識別番号 (ELIN) ゲートウェイを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f816c-109">To deploy E9-1-1, you need to configure a SIP connection to a qualified E9-1-1 service provider, or deploy an emergency location identification number (ELIN) gateway to a public switched telephone (PSTN)-based E9-1-1 service provider.</span></span> <span data-ttu-id="f816c-110">詳細については、「<A href="lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md">拡張 9-1-1 (E9)」および「Lync server 2013 の仲介サーバー</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f816c-110">For details, see <A href="lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md">Enhanced 9-1-1 (E9-1-1) and Mediation Server in Lync Server 2013</A>.</span></span> <span data-ttu-id="f816c-111">トランク接続の構成の詳細については、「 <A href="lync-server-2013-configure-a-trunk-with-media-bypass.md">Lync Server 2013 でメディアバイパスを使用してトランクを構成</A>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f816c-111">For details about configuring trunk connections, see <A href="lync-server-2013-configure-a-trunk-with-media-bypass.md">Configure a trunk with media bypass in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f816c-112">このセクション中</span><span class="sxs-lookup"><span data-stu-id="f816c-112">In This Section</span></span>

  - [<span data-ttu-id="f816c-113">Lync Server 2013 での E9 音声ルートの構成</span><span class="sxs-lookup"><span data-stu-id="f816c-113">Configure an E9-1-1 voice route in Lync Server 2013</span></span>](lync-server-2013-configure-an-e9-1-1-voice-route.md)

  - [<span data-ttu-id="f816c-114">Lync Server 2013 で位置情報のポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="f816c-114">Create location policies in Lync Server 2013</span></span>](lync-server-2013-create-location-policies.md)

  - [<span data-ttu-id="f816c-115">Lync Server 2013 で E9-1 のサイト情報を構成する</span><span class="sxs-lookup"><span data-stu-id="f816c-115">Configure site information for E9-1-1 in Lync Server 2013</span></span>](lync-server-2013-configure-site-information-for-e9-1-1.md)

  - [<span data-ttu-id="f816c-116">Configure the location database in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f816c-116">Configure the location database in Lync Server 2013</span></span>](lync-server-2013-configure-the-location-database.md)

  - [<span data-ttu-id="f816c-117">Lync Server 2013 の advanced E9-1-1 の機能を構成する</span><span class="sxs-lookup"><span data-stu-id="f816c-117">Configure advanced E9-1-1 features in Lync Server 2013</span></span>](lync-server-2013-configure-advanced-e9-1-1-features.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

