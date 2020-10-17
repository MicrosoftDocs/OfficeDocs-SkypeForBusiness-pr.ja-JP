---
title: 'Lync Server 2013: 常設チャットサーバーのテーブルの詳細'
description: 'Lync Server 2013: 常設チャットサーバーテーブルの詳細。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Persistent Chat Server table details
ms:assetid: c22d4a76-da50-49de-9038-e0ed7b8e1b58
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615034(v=OCS.15)
ms:contentKeyID: 48185323
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a27feaaccf861d537127f06920cf903be5ae000
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545133"
---
# <a name="persistent-chat-server-table-details-in-lync-server-2013"></a><span data-ttu-id="9fac6-103">Lync Server 2013 の常設チャットサーバーテーブルの詳細</span><span class="sxs-lookup"><span data-stu-id="9fac6-103">Persistent Chat Server table details in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9fac6-104">_**トピックの最終更新日:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="9fac6-104">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="9fac6-105">次のトピックでは、各常設チャットデータベーススキーマテーブルの列について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="9fac6-105">The following topics detail the columns in each of the Persistent Chat database schema tables.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9fac6-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="9fac6-106">In This Section</span></span>

  - [<span data-ttu-id="9fac6-107">Lync Server 2013 の tblADCookie</span><span class="sxs-lookup"><span data-stu-id="9fac6-107">tblADCookie in Lync Server 2013</span></span>](lync-server-2013-tbladcookie.md)

  - [<span data-ttu-id="9fac6-108">Lync Server 2013 の tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="9fac6-108">tblPrincipalMemberDifference in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmemberdifference.md)

  - [<span data-ttu-id="9fac6-109">Lync Server 2013 の tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="9fac6-109">tblADUpdates in Lync Server 2013</span></span>](lync-server-2013-tbladupdates.md)

  - [<span data-ttu-id="9fac6-110">Lync Server 2013 の tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="9fac6-110">tblPrincipalMembers in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmembers.md)

  - [<span data-ttu-id="9fac6-111">Lync Server 2013 の tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="9fac6-111">tblPrincipalMeta in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmeta.md)

  - [<span data-ttu-id="9fac6-112">Lync Server 2013 の tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="9fac6-112">tblSkippedAffiliations in Lync Server 2013</span></span>](lync-server-2013-tblskippedaffiliations.md)

  - [<span data-ttu-id="9fac6-113">Lync Server 2013 の tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="9fac6-113">tblPrincipalType in Lync Server 2013</span></span>](lync-server-2013-tblprincipaltype.md)

  - [<span data-ttu-id="9fac6-114">Lync Server 2013 の tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="9fac6-114">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)

  - [<span data-ttu-id="9fac6-115">Lync Server 2013 の tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="9fac6-115">tblPrincipalAffiliations in Lync Server 2013</span></span>](lync-server-2013-tblprincipalaffiliations.md)

  - [<span data-ttu-id="9fac6-116">Lync Server 2013 の tblNode</span><span class="sxs-lookup"><span data-stu-id="9fac6-116">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)

  - [<span data-ttu-id="9fac6-117">Lync Server 2013 の tblRoleType</span><span class="sxs-lookup"><span data-stu-id="9fac6-117">tblRoleType in Lync Server 2013</span></span>](lync-server-2013-tblroletype.md)

  - [<span data-ttu-id="9fac6-118">Lync Server 2013 の tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="9fac6-118">tblScopePrincipal in Lync Server 2013</span></span>](lync-server-2013-tblscopeprincipal.md)

  - [<span data-ttu-id="9fac6-119">Lync Server 2013 のに tblprincipalrole</span><span class="sxs-lookup"><span data-stu-id="9fac6-119">tblPrincipalRole in Lync Server 2013</span></span>](lync-server-2013-tblprincipalrole.md)

  - [<span data-ttu-id="9fac6-120">Lync Server 2013 の tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="9fac6-120">tblSiopWhiteList in Lync Server 2013</span></span>](lync-server-2013-tblsiopwhitelist.md)

  - [<span data-ttu-id="9fac6-121">Lync Server 2013 の tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="9fac6-121">tblEnumAttribute in Lync Server 2013</span></span>](lync-server-2013-tblenumattribute.md)

  - [<span data-ttu-id="9fac6-122">Lync Server 2013 の tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="9fac6-122">tblEnumValue in Lync Server 2013</span></span>](lync-server-2013-tblenumvalue.md)

  - [<span data-ttu-id="9fac6-123">Lync Server 2013 のそして tblprincipalinvites</span><span class="sxs-lookup"><span data-stu-id="9fac6-123">tblPrincipalInvites in Lync Server 2013</span></span>](lync-server-2013-tblprincipalinvites.md)

  - [<span data-ttu-id="9fac6-124">Lync Server 2013 の tblChat</span><span class="sxs-lookup"><span data-stu-id="9fac6-124">tblChat in Lync Server 2013</span></span>](lync-server-2013-tblchat.md)

  - [<span data-ttu-id="9fac6-125">Lync Server 2013 の tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="9fac6-125">tblLastInviteId in Lync Server 2013</span></span>](lync-server-2013-tbllastinviteid.md)

  - [<span data-ttu-id="9fac6-126">Lync Server 2013 の tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="9fac6-126">tblLastChatId in Lync Server 2013</span></span>](lync-server-2013-tbllastchatid.md)

  - [<span data-ttu-id="9fac6-127">Lync Server 2013 の tblPreference</span><span class="sxs-lookup"><span data-stu-id="9fac6-127">tblPreference in Lync Server 2013</span></span>](lync-server-2013-tblpreference.md)

  - [<span data-ttu-id="9fac6-128">Lync Server 2013 の tblFileToken</span><span class="sxs-lookup"><span data-stu-id="9fac6-128">tblFileToken in Lync Server 2013</span></span>](lync-server-2013-tblfiletoken.md)

  - [<span data-ttu-id="9fac6-129">Lync Server 2013 の tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="9fac6-129">tblServerIdentity in Lync Server 2013</span></span>](lync-server-2013-tblserveridentity.md)

  - [<span data-ttu-id="9fac6-130">Lync Server 2013 の tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="9fac6-130">tblAdminLock in Lync Server 2013</span></span>](lync-server-2013-tbladminlock.md)

  - [<span data-ttu-id="9fac6-131">Lync Server 2013 の tblSystemRevision</span><span class="sxs-lookup"><span data-stu-id="9fac6-131">tblSystemRevision in Lync Server 2013</span></span>](lync-server-2013-tblsystemrevision.md)

  - [<span data-ttu-id="9fac6-132">Lync Server 2013 の tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="9fac6-132">tblActivePeers in Lync Server 2013</span></span>](lync-server-2013-tblactivepeers.md)

  - [<span data-ttu-id="9fac6-133">Lync Server 2013 の tblConfig</span><span class="sxs-lookup"><span data-stu-id="9fac6-133">tblConfig in Lync Server 2013</span></span>](lync-server-2013-tblconfig.md)

  - [<span data-ttu-id="9fac6-134">Lync Server 2013 の tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="9fac6-134">tblComplianceData in Lync Server 2013</span></span>](lync-server-2013-tblcompliancedata.md)

  - [<span data-ttu-id="9fac6-135">Lync Server 2013 の tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="9fac6-135">tblComplianceFanout in Lync Server 2013</span></span>](lync-server-2013-tblcompliancefanout.md)

  - [<span data-ttu-id="9fac6-136">Lync Server 2013 の tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="9fac6-136">tblComplianceParticipant in Lync Server 2013</span></span>](lync-server-2013-tblcomplianceparticipant.md)

  - [<span data-ttu-id="9fac6-137">Lync Server 2013 の tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="9fac6-137">tblComplianceState in Lync Server 2013</span></span>](lync-server-2013-tblcompliancestate.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

