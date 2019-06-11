---
title: 'Lync Server 2013: 常設チャット サーバー テーブルの詳細'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Persistent Chat Server table details
ms:assetid: c22d4a76-da50-49de-9038-e0ed7b8e1b58
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615034(v=OCS.15)
ms:contentKeyID: 48185323
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 81f23e3ea5642341248be304612d71f12148865c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825185"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="persistent-chat-server-table-details-in-lync-server-2013"></a><span data-ttu-id="4a961-102">Lync Server 2013 の常設チャット サーバー テーブルの詳細</span><span class="sxs-lookup"><span data-stu-id="4a961-102">Persistent Chat Server table details in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a961-103">_**最終更新日:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="4a961-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="4a961-104">次のトピックでは、常設チャットデータベースの各スキーマテーブルの列について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="4a961-104">The following topics detail the columns in each of the Persistent Chat database schema tables.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4a961-105">このセクション中</span><span class="sxs-lookup"><span data-stu-id="4a961-105">In This Section</span></span>

  - [<span data-ttu-id="4a961-106">Lync Server 2013 の tblADCookie</span><span class="sxs-lookup"><span data-stu-id="4a961-106">tblADCookie in Lync Server 2013</span></span>](lync-server-2013-tbladcookie.md)

  - [<span data-ttu-id="4a961-107">Lync Server 2013 の tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="4a961-107">tblPrincipalMemberDifference in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmemberdifference.md)

  - [<span data-ttu-id="4a961-108">Lync Server 2013 の tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="4a961-108">tblADUpdates in Lync Server 2013</span></span>](lync-server-2013-tbladupdates.md)

  - [<span data-ttu-id="4a961-109">Lync Server 2013 の tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="4a961-109">tblPrincipalMembers in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmembers.md)

  - [<span data-ttu-id="4a961-110">Lync Server 2013 の tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="4a961-110">tblPrincipalMeta in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmeta.md)

  - [<span data-ttu-id="4a961-111">Lync Server 2013 の tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="4a961-111">tblSkippedAffiliations in Lync Server 2013</span></span>](lync-server-2013-tblskippedaffiliations.md)

  - [<span data-ttu-id="4a961-112">Lync Server 2013 の tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="4a961-112">tblPrincipalType in Lync Server 2013</span></span>](lync-server-2013-tblprincipaltype.md)

  - [<span data-ttu-id="4a961-113">Lync Server 2013 の tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="4a961-113">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)

  - [<span data-ttu-id="4a961-114">Lync Server 2013 の tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="4a961-114">tblPrincipalAffiliations in Lync Server 2013</span></span>](lync-server-2013-tblprincipalaffiliations.md)

  - [<span data-ttu-id="4a961-115">Lync Server 2013 の tblNode</span><span class="sxs-lookup"><span data-stu-id="4a961-115">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)

  - [<span data-ttu-id="4a961-116">Lync Server 2013 の tblRoleType</span><span class="sxs-lookup"><span data-stu-id="4a961-116">tblRoleType in Lync Server 2013</span></span>](lync-server-2013-tblroletype.md)

  - [<span data-ttu-id="4a961-117">Lync Server 2013 の tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="4a961-117">tblScopePrincipal in Lync Server 2013</span></span>](lync-server-2013-tblscopeprincipal.md)

  - [<span data-ttu-id="4a961-118">Lync Server 2013 の tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="4a961-118">tblPrincipalRole in Lync Server 2013</span></span>](lync-server-2013-tblprincipalrole.md)

  - [<span data-ttu-id="4a961-119">Lync Server 2013 の tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="4a961-119">tblSiopWhiteList in Lync Server 2013</span></span>](lync-server-2013-tblsiopwhitelist.md)

  - [<span data-ttu-id="4a961-120">Lync Server 2013 の tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="4a961-120">tblEnumAttribute in Lync Server 2013</span></span>](lync-server-2013-tblenumattribute.md)

  - [<span data-ttu-id="4a961-121">Lync Server 2013 の tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="4a961-121">tblEnumValue in Lync Server 2013</span></span>](lync-server-2013-tblenumvalue.md)

  - [<span data-ttu-id="4a961-122">Lync Server 2013 の tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="4a961-122">tblPrincipalInvites in Lync Server 2013</span></span>](lync-server-2013-tblprincipalinvites.md)

  - [<span data-ttu-id="4a961-123">Lync Server 2013 の tblChat</span><span class="sxs-lookup"><span data-stu-id="4a961-123">tblChat in Lync Server 2013</span></span>](lync-server-2013-tblchat.md)

  - [<span data-ttu-id="4a961-124">Lync Server 2013 の tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="4a961-124">tblLastInviteId in Lync Server 2013</span></span>](lync-server-2013-tbllastinviteid.md)

  - [<span data-ttu-id="4a961-125">Lync Server 2013 の tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="4a961-125">tblLastChatId in Lync Server 2013</span></span>](lync-server-2013-tbllastchatid.md)

  - [<span data-ttu-id="4a961-126">Lync Server 2013 の tblPreference</span><span class="sxs-lookup"><span data-stu-id="4a961-126">tblPreference in Lync Server 2013</span></span>](lync-server-2013-tblpreference.md)

  - [<span data-ttu-id="4a961-127">Lync Server 2013 の tblFileToken</span><span class="sxs-lookup"><span data-stu-id="4a961-127">tblFileToken in Lync Server 2013</span></span>](lync-server-2013-tblfiletoken.md)

  - [<span data-ttu-id="4a961-128">Lync Server 2013 の tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="4a961-128">tblServerIdentity in Lync Server 2013</span></span>](lync-server-2013-tblserveridentity.md)

  - [<span data-ttu-id="4a961-129">Lync Server 2013 の tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="4a961-129">tblAdminLock in Lync Server 2013</span></span>](lync-server-2013-tbladminlock.md)

  - [<span data-ttu-id="4a961-130">Lync Server 2013 の tblSystemRevision</span><span class="sxs-lookup"><span data-stu-id="4a961-130">tblSystemRevision in Lync Server 2013</span></span>](lync-server-2013-tblsystemrevision.md)

  - [<span data-ttu-id="4a961-131">Lync Server 2013 の tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="4a961-131">tblActivePeers in Lync Server 2013</span></span>](lync-server-2013-tblactivepeers.md)

  - [<span data-ttu-id="4a961-132">Lync Server 2013 の tblConfig</span><span class="sxs-lookup"><span data-stu-id="4a961-132">tblConfig in Lync Server 2013</span></span>](lync-server-2013-tblconfig.md)

  - [<span data-ttu-id="4a961-133">Lync Server 2013 の tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="4a961-133">tblComplianceData in Lync Server 2013</span></span>](lync-server-2013-tblcompliancedata.md)

  - [<span data-ttu-id="4a961-134">Lync Server 2013 内の tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="4a961-134">tblComplianceFanout in Lync Server 2013</span></span>](lync-server-2013-tblcompliancefanout.md)

  - [<span data-ttu-id="4a961-135">Lync Server 2013 内の tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="4a961-135">tblComplianceParticipant in Lync Server 2013</span></span>](lync-server-2013-tblcomplianceparticipant.md)

  - [<span data-ttu-id="4a961-136">Lync Server 2013 の tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="4a961-136">tblComplianceState in Lync Server 2013</span></span>](lync-server-2013-tblcompliancestate.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

