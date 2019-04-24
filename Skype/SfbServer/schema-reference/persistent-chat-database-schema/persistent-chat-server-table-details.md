---
title: 常設チャット サーバー テーブルの詳細
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c22d4a76-da50-49de-9038-e0ed7b8e1b58
description: 次のトピックでは、永続的なチャットのデータベース スキーマのテーブルの各列を説明します。
ms.openlocfilehash: 5ee15bfab456f2e2e5c1ea535a1b521f9544a352
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212671"
---
# <a name="persistent-chat-server-table-details"></a><span data-ttu-id="c42a2-103">常設チャット サーバー テーブルの詳細</span><span class="sxs-lookup"><span data-stu-id="c42a2-103">Persistent Chat Server table details</span></span>
 
<span data-ttu-id="c42a2-104">次のトピックでは、永続的なチャットのデータベース スキーマのテーブルの各列を説明します。</span><span class="sxs-lookup"><span data-stu-id="c42a2-104">The following topics detail the columns in each of the Persistent Chat database schema tables.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="c42a2-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c42a2-105">In this section</span></span>

- [<span data-ttu-id="c42a2-106">tblADCookie</span><span class="sxs-lookup"><span data-stu-id="c42a2-106">tblADCookie</span></span>](tbladcookie.md)
    
- [<span data-ttu-id="c42a2-107">tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="c42a2-107">tblPrincipalMemberDifference</span></span>](tblprincipalmemberdifference.md)
    
- [<span data-ttu-id="c42a2-108">tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="c42a2-108">tblADUpdates</span></span>](tbladupdates.md)
    
- [<span data-ttu-id="c42a2-109">tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="c42a2-109">tblPrincipalMembers</span></span>](tblprincipalmembers.md)
    
- [<span data-ttu-id="c42a2-110">tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="c42a2-110">tblPrincipalMeta</span></span>](tblprincipalmeta.md)
    
- [<span data-ttu-id="c42a2-111">tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="c42a2-111">tblSkippedAffiliations</span></span>](tblskippedaffiliations.md)
    
- [<span data-ttu-id="c42a2-112">tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="c42a2-112">tblPrincipalType</span></span>](tblprincipaltype.md)
    
- [<span data-ttu-id="c42a2-113">tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="c42a2-113">tblPrincipal</span></span>](tblprincipal.md)
    
- [<span data-ttu-id="c42a2-114">tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="c42a2-114">tblPrincipalAffiliations</span></span>](tblprincipalaffiliations.md)
    
- [<span data-ttu-id="c42a2-115">tblNode</span><span class="sxs-lookup"><span data-stu-id="c42a2-115">tblNode</span></span>](tblnode.md)
    
- [<span data-ttu-id="c42a2-116">tblRoleType</span><span class="sxs-lookup"><span data-stu-id="c42a2-116">tblRoleType</span></span>](tblroletype.md)
    
- [<span data-ttu-id="c42a2-117">tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="c42a2-117">tblScopePrincipal</span></span>](tblscopeprincipal.md)
    
- [<span data-ttu-id="c42a2-118">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="c42a2-118">tblPrincipalRole</span></span>](tblprincipalrole.md)
    
- [<span data-ttu-id="c42a2-119">tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="c42a2-119">tblSiopWhiteList</span></span>](tblsiopwhitelist.md)
    
- [<span data-ttu-id="c42a2-120">tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="c42a2-120">tblEnumAttribute</span></span>](tblenumattribute.md)
    
- [<span data-ttu-id="c42a2-121">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="c42a2-121">tblEnumValue</span></span>](tblenumvalue.md)
    
- [<span data-ttu-id="c42a2-122">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="c42a2-122">tblPrincipalInvites</span></span>](tblprincipalinvites.md)
    
- [<span data-ttu-id="c42a2-123">tblChat</span><span class="sxs-lookup"><span data-stu-id="c42a2-123">tblChat</span></span>](tblchat.md)
    
- [<span data-ttu-id="c42a2-124">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="c42a2-124">tblLastInviteId</span></span>](tbllastinviteid.md)
    
- [<span data-ttu-id="c42a2-125">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="c42a2-125">tblLastChatId</span></span>](tbllastchatid.md)
    
- [<span data-ttu-id="c42a2-126">tblPreference</span><span class="sxs-lookup"><span data-stu-id="c42a2-126">tblPreference</span></span>](tblpreference.md)
    
- [<span data-ttu-id="c42a2-127">tblFileToken</span><span class="sxs-lookup"><span data-stu-id="c42a2-127">tblFileToken</span></span>](tblfiletoken.md)
    
- [<span data-ttu-id="c42a2-128">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="c42a2-128">tblServerIdentity</span></span>](tblserveridentity.md)
    
- [<span data-ttu-id="c42a2-129">tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="c42a2-129">tblAdminLock</span></span>](tbladminlock.md)
    
- [<span data-ttu-id="c42a2-130">tblSystemRevision</span><span class="sxs-lookup"><span data-stu-id="c42a2-130">tblSystemRevision</span></span>](tblsystemrevision.md)
    
- [<span data-ttu-id="c42a2-131">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="c42a2-131">tblActivePeers</span></span>](tblactivepeers.md)
    
- [<span data-ttu-id="c42a2-132">tblConfig</span><span class="sxs-lookup"><span data-stu-id="c42a2-132">tblConfig</span></span>](tblconfig.md)
    
- [<span data-ttu-id="c42a2-133">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="c42a2-133">tblComplianceData</span></span>](tblcompliancedata.md)
    
- [<span data-ttu-id="c42a2-134">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="c42a2-134">tblComplianceFanout</span></span>](tblcompliancefanout.md)
    
- [<span data-ttu-id="c42a2-135">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="c42a2-135">tblComplianceParticipant</span></span>](tblcomplianceparticipant.md)
    
- [<span data-ttu-id="c42a2-136">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="c42a2-136">tblComplianceState</span></span>](tblcompliancestate.md)
    

