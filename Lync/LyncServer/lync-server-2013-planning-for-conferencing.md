---
title: 'Lync Server 2013: 会議の計画'
description: 'Lync Server 2013: 会議の計画。'
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
ms.openlocfilehash: 28e71d185b7be8971c451351aac60dcaaf7eaeda
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567333"
---
# <a name="planning-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="d0fbf-103">Lync Server 2013 での会議の計画</span><span class="sxs-lookup"><span data-stu-id="d0fbf-103">Planning for conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0fbf-104">_**トピックの最終更新日:** 2013-01-29_</span><span class="sxs-lookup"><span data-stu-id="d0fbf-104">_**Topic Last Modified:** 2013-01-29_</span></span>

<span data-ttu-id="d0fbf-105">Lync Server 2013 には、会議機能の豊富なセットが用意されています。</span><span class="sxs-lookup"><span data-stu-id="d0fbf-105">Lync Server 2013 offers a rich set of conferencing capabilities:</span></span>

  - <span data-ttu-id="d0fbf-106">Web 会議には、ドキュメントのコラボレーション、アプリケーション共有、デスクトップ共有が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d0fbf-106">Web conferencing, which includes document collaboration, application sharing, and desktop sharing.</span></span> <span data-ttu-id="d0fbf-107">Lync Server 2013 は、Office Web Apps および Office Web Apps サーバーを使用して、PowerPoint プレゼンテーションの共有とレンダリングを処理します。</span><span class="sxs-lookup"><span data-stu-id="d0fbf-107">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="d0fbf-108">Office Web Apps サーバーのインストールと構成の詳細については、「 [Office Web Apps server および Lync Server 2013 との統合の構成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0fbf-108">For details about installing and configuring the Office Web Apps Server, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

  - <span data-ttu-id="d0fbf-109">音声ビデオ (A/V) 会議では、ユーザーがリアルタイムの電話会議またはビデオ会議を行うことが可能です。Microsoft Live Meeting サービスまたはサードパーティの音声ブリッジのような外部サービスを使用する必要もありません。</span><span class="sxs-lookup"><span data-stu-id="d0fbf-109">Audio/video (A/V) conferencing, which enables users to have real-time audio or video conferences without the need for external services such as the Microsoft Live Meeting service or a third-party audio bridge.</span></span>

  - <span data-ttu-id="d0fbf-110">ダイヤルイン会議は、ユーザーがサードパーティの電話会議プロバイダーを必要とせずに公衆交換電話網 (PSTN) 電話を使用して、Lync Server 2013 会議のオーディオ部分に参加できるようにします。</span><span class="sxs-lookup"><span data-stu-id="d0fbf-110">Dial-in conferencing, which allows users to join the audio portion of a Lync Server 2013 conference by using a public switched telephone network (PSTN) phone without requiring a third-party audio conferencing provider.</span></span>

  - <span data-ttu-id="d0fbf-111">インスタント メッセージング (IM) 会議では、単一の IM セッションで複数者間で通信できます。</span><span class="sxs-lookup"><span data-stu-id="d0fbf-111">Instant messaging (IM) conferencing, in which more than two parties communicate in a single IM session.</span></span> <span data-ttu-id="d0fbf-112">IM 会議の詳細については、「 [Lync Server 2013 でのフロントエンドサーバー、インスタントメッセージング、およびプレゼンスの計画](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0fbf-112">For details about IM conferencing, see [Planning for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

<span data-ttu-id="d0fbf-113">Lync Server 2013 は、スケジュールされた会議と即時会議の両方をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d0fbf-113">Lync Server 2013 supports both scheduled conferences and impromptu conferences.</span></span>

<span data-ttu-id="d0fbf-114">Lync Server 2013 のフロントエンドサーバーを展開する場合は、web 会議、音声ビデオ会議、およびダイヤルイン会議機能も展開するかどうかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="d0fbf-114">When you deploy Lync Server 2013, Front End Server, you can choose whether to also deploy the web conferencing, A/V conferencing, and dial-in conferencing capabilities.</span></span> <span data-ttu-id="d0fbf-115">IM 会議機能は、Lync Server 2013 フロントエンドサーバー上の IM 会話機能と共に常に自動的に展開されます。</span><span class="sxs-lookup"><span data-stu-id="d0fbf-115">IM conferencing capabilities are always automatically deployed along with IM conversation capabilities on Lync Server 2013 Front End Servers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d0fbf-116">Office Communicator 2007 R2 クライアント (Microsoft Office Outlook 用 Live Meeting コンソールまたは電話会議アドインを含む) を使用して開催された会議が展開に含まれている場合は、Lync Server 2013 に移行した後、次のような制限があります。</span><span class="sxs-lookup"><span data-stu-id="d0fbf-116">If your deployment includes meetings organized using Office Communicator 2007 R2 clients (including the Live Meeting console or Conferencing Add-in for Microsoft Office Outlook), the meetings will have the following limitations after they are migrated to Lync Server 2013:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="d0fbf-117">会議のユーザーは、ドキュメントのグループ作業、アプリケーション共有、およびデスクトップ共有などのデータコラボレーション機能を使用できません。</span><span class="sxs-lookup"><span data-stu-id="d0fbf-117">Users in the meeting will not be able to use data collaboration features, including document collaboration, application sharing, and desktop sharing.</span></span></P>
> <LI>
> <P><span data-ttu-id="d0fbf-118">Office Communicator 2007 R2 クライアントは Lync Server 2013 ではサポートされていないため、安定性の問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="d0fbf-118">Stability issues may arise since Office Communicator 2007 R2 clients are not supported with Lync Server 2013.</span></span></P></LI></UL><span data-ttu-id="d0fbf-119">これらの問題を回避するには、Office Communicator 2007 R2 クライアントを使用して開催されたすべての会議を、Lync 2010 用オンラインミーティングアドインまたは Lync 2013 オンラインミーティングアドインのいずれかを使用して、Outlook 2010 または Outlook 2013 を使用して再スケジュールします。</span><span class="sxs-lookup"><span data-stu-id="d0fbf-119">To avoid these issues, reschedule any meeting organized using Office Communicator 2007 R2 clients with Outlook 2010 or Outlook 2013 using either the Online Meeting Add-in for Lync 2010 or Online Meeting Add-in for Lync 2013.</span></span>



</div>

<span data-ttu-id="d0fbf-120">次のセクションでは、計画プロセス、コンポーネント、ハードウェアおよびソフトウェアの要件、および展開プロセスを含む、様々な種類の会議機能の展開に必要な項目について説明します。</span><span class="sxs-lookup"><span data-stu-id="d0fbf-120">The following sections describe what is required to deploy the various types of conferencing capabilities, including the planning process, components, hardware and software requirements, and the deployment process.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d0fbf-121">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d0fbf-121">In This Section</span></span>

  - [<span data-ttu-id="d0fbf-122">Lync Server 2013 での会議の概要</span><span class="sxs-lookup"><span data-stu-id="d0fbf-122">Overview of conferencing in Lync Server 2013</span></span>](lync-server-2013-overview-of-conferencing.md)

  - [<span data-ttu-id="d0fbf-123">Lync Server 2013 での会議の要件の定義</span><span class="sxs-lookup"><span data-stu-id="d0fbf-123">Defining your requirements for conferencing in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-conferencing.md)

  - [<span data-ttu-id="d0fbf-124">Lync Server 2013 の会議のコンポーネントとトポロジ</span><span class="sxs-lookup"><span data-stu-id="d0fbf-124">Components and topologies for conferencing in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-conferencing.md)

  - [<span data-ttu-id="d0fbf-125">Lync Server 2013 での会議の技術要件</span><span class="sxs-lookup"><span data-stu-id="d0fbf-125">Technical requirements for conferencing in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-conferencing.md)

  - [<span data-ttu-id="d0fbf-126">Lync Server 2013 での会議の展開チェックリスト</span><span class="sxs-lookup"><span data-stu-id="d0fbf-126">Deployment checklist for conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-conferencing.md)

  - [<span data-ttu-id="d0fbf-127">Lync Server 2013 での大規模会議のサポート</span><span class="sxs-lookup"><span data-stu-id="d0fbf-127">Support for large meetings in Lync Server 2013</span></span>](lync-server-2013-support-for-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

