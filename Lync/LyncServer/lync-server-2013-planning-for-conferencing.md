---
title: 'Lync Server 2013: 会議の計画'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for conferencing
ms:assetid: 983a272a-e1b3-4d70-8f84-836b092fe526
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398781(v=OCS.15)
ms:contentKeyID: 48184937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2aff3eef21ca150f4ad6fc9bb2358c2ac81680fd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824821"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="69b90-102">Lync Server 2013 での会議の計画</span><span class="sxs-lookup"><span data-stu-id="69b90-102">Planning for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69b90-103">_**最終更新日:** 2013-01-29_</span><span class="sxs-lookup"><span data-stu-id="69b90-103">_**Topic Last Modified:** 2013-01-29_</span></span>

<span data-ttu-id="69b90-104">Lync Server 2013 には、次のような豊富な会議機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="69b90-104">Lync Server 2013 offers a rich set of conferencing capabilities:</span></span>

  - <span data-ttu-id="69b90-105">Web 会議。ドキュメントのグループ作業、アプリの共有、デスクトップ共有が含まれます。</span><span class="sxs-lookup"><span data-stu-id="69b90-105">Web conferencing, which includes document collaboration, application sharing, and desktop sharing.</span></span> <span data-ttu-id="69b90-106">Lync Server 2013 は、PowerPoint プレゼンテーションの共有とレンダリングを処理するために、Office Web Apps と Office Web Apps サーバーを使用します。</span><span class="sxs-lookup"><span data-stu-id="69b90-106">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="69b90-107">Office Web Apps サーバーのインストールと構成の詳細については、「 [Office Web Apps サーバーおよび Lync server 2013 との統合を構成する](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69b90-107">For details about installing and configuring the Office Web Apps Server, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

  - <span data-ttu-id="69b90-108">音声/ビデオ (A/V) 会議: Microsoft Live Meeting サービスやサードパーティのオーディオブリッジなどの外部サービスを必要とせずに、リアルタイムの音声通話またはビデオ会議を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="69b90-108">Audio/video (A/V) conferencing, which enables users to have real-time audio or video conferences without the need for external services such as the Microsoft Live Meeting service or a third-party audio bridge.</span></span>

  - <span data-ttu-id="69b90-109">ダイヤルイン会議: ユーザーは、サードパーティの電話会議プロバイダーを必要とせずに、公衆交換電話網 (PSTN) 電話を使って、Lync Server 2013 会議のオーディオ部分に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="69b90-109">Dial-in conferencing, which allows users to join the audio portion of a Lync Server 2013 conference by using a public switched telephone network (PSTN) phone without requiring a third-party audio conferencing provider.</span></span>

  - <span data-ttu-id="69b90-110">インスタントメッセージング (IM) 会議: 3 人以上の当事者が単一の IM セッションで通信します。</span><span class="sxs-lookup"><span data-stu-id="69b90-110">Instant messaging (IM) conferencing, in which more than two parties communicate in a single IM session.</span></span> <span data-ttu-id="69b90-111">IM 会議の詳細については、「 [Lync Server 2013 でのフロントエンドサーバー、インスタントメッセージング、およびプレゼンスの計画](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69b90-111">For details about IM conferencing, see [Planning for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

<span data-ttu-id="69b90-112">Lync Server 2013 は、スケジュールされた会議と一時的会議の両方をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="69b90-112">Lync Server 2013 supports both scheduled conferences and impromptu conferences.</span></span>

<span data-ttu-id="69b90-113">Lync Server 2013、フロントエンドサーバーを展開するときに、web 会議、A/V 会議、ダイヤルイン会議機能も展開するかどうかを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="69b90-113">When you deploy Lync Server 2013, Front End Server, you can choose whether to also deploy the web conferencing, A/V conferencing, and dial-in conferencing capabilities.</span></span> <span data-ttu-id="69b90-114">IM 会議機能は、Lync Server 2013 フロントエンドサーバーの IM 会話機能と共に、常に自動的に展開されます。</span><span class="sxs-lookup"><span data-stu-id="69b90-114">IM conferencing capabilities are always automatically deployed along with IM conversation capabilities on Lync Server 2013 Front End Servers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="69b90-115">展開に Office Communicator 2007 R2 クライアント (Microsoft Office Outlook 用 Live Meeting 本体または電話会議アドインを含む) を使って開催された会議が含まれている場合、会議は Lync に移行した後に次の制限があります。サーバー 2013:</span><span class="sxs-lookup"><span data-stu-id="69b90-115">If your deployment includes meetings organized using Office Communicator 2007 R2 clients (including the Live Meeting console or Conferencing Add-in for Microsoft Office Outlook), the meetings will have the following limitations after they are migrated to Lync Server 2013:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="69b90-116">会議に参加しているユーザーは、ドキュメントのグループ作業、アプリケーション共有、デスクトップ共有などのデータコラボレーション機能を使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="69b90-116">Users in the meeting will not be able to use data collaboration features, including document collaboration, application sharing, and desktop sharing.</span></span></P>
> <LI>
> <P><span data-ttu-id="69b90-117">Office Communicator 2007 R2 クライアントが Lync Server 2013 でサポートされていないため、安定性の問題が発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="69b90-117">Stability issues may arise since Office Communicator 2007 R2 clients are not supported with Lync Server 2013.</span></span></P></LI></UL><span data-ttu-id="69b90-118">これらの問題を回避するには、lync 2010 用のオンライン会議アドインまたは Lync 2013 用オンライン会議アドインのいずれかを使用して、Office Communicator 2007 R2 2013 2010 クライアントを使用して開催される会議を再スケジュールします。</span><span class="sxs-lookup"><span data-stu-id="69b90-118">To avoid these issues, reschedule any meeting organized using Office Communicator 2007 R2 clients with Outlook 2010 or Outlook 2013 using either the Online Meeting Add-in for Lync 2010 or Online Meeting Add-in for Lync 2013.</span></span>



</div>

<span data-ttu-id="69b90-119">以下のセクションでは、計画プロセス、コンポーネント、ハードウェアとソフトウェアの要件、展開プロセスなど、さまざまな種類の会議機能を展開するために必要なものについて説明します。</span><span class="sxs-lookup"><span data-stu-id="69b90-119">The following sections describe what is required to deploy the various types of conferencing capabilities, including the planning process, components, hardware and software requirements, and the deployment process.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="69b90-120">このセクション中</span><span class="sxs-lookup"><span data-stu-id="69b90-120">In This Section</span></span>

  - [<span data-ttu-id="69b90-121">Lync Server 2013 での会議の概要</span><span class="sxs-lookup"><span data-stu-id="69b90-121">Overview of conferencing in Lync Server 2013</span></span>](lync-server-2013-overview-of-conferencing.md)

  - [<span data-ttu-id="69b90-122">Lync Server 2013 での会議の要件の定義</span><span class="sxs-lookup"><span data-stu-id="69b90-122">Defining your requirements for conferencing in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-conferencing.md)

  - [<span data-ttu-id="69b90-123">Lync Server 2013 の会議のコンポーネントおよびトポロジ</span><span class="sxs-lookup"><span data-stu-id="69b90-123">Components and topologies for conferencing in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-conferencing.md)

  - [<span data-ttu-id="69b90-124">Lync Server 2013 の会議の技術要件</span><span class="sxs-lookup"><span data-stu-id="69b90-124">Technical requirements for conferencing in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-conferencing.md)

  - [<span data-ttu-id="69b90-125">Lync Server 2013 の会議の展開チェックリスト</span><span class="sxs-lookup"><span data-stu-id="69b90-125">Deployment checklist for conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-conferencing.md)

  - [<span data-ttu-id="69b90-126">Lync Server 2013 での大規模会議のサポート</span><span class="sxs-lookup"><span data-stu-id="69b90-126">Support for large meetings in Lync Server 2013</span></span>](lync-server-2013-support-for-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

