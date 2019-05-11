---
title: tblPrincipalMemberDifference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference には、グループ メンバーシップの変更 (追加し、削除メンバー) を Active Directory ドメイン サービスの同期の後の手順でまだ処理されていないが含まれています。
ms.openlocfilehash: 4445bc6a4b83053d7d9244fc20d0a7a8cbd01b26
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33902237"
---
# <a name="tblprincipalmemberdifference"></a><span data-ttu-id="41d77-103">tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="41d77-103">tblPrincipalMemberDifference</span></span>
 
<span data-ttu-id="41d77-104">tblPrincipalMemberDifference には、グループ メンバーシップの変更 (追加し、削除メンバー) を Active Directory ドメイン サービスの同期の後の手順でまだ処理されていないが含まれています。</span><span class="sxs-lookup"><span data-stu-id="41d77-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>
  
<span data-ttu-id="41d77-105">**列**</span><span class="sxs-lookup"><span data-stu-id="41d77-105">**Columns**</span></span>

|<span data-ttu-id="41d77-106">**列**</span><span class="sxs-lookup"><span data-stu-id="41d77-106">**Column**</span></span>|<span data-ttu-id="41d77-107">**型**</span><span class="sxs-lookup"><span data-stu-id="41d77-107">**Type**</span></span>|<span data-ttu-id="41d77-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="41d77-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="41d77-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="41d77-109">prinGuid</span></span>  <br/> |<span data-ttu-id="41d77-110">GUID では、null でないです。</span><span class="sxs-lookup"><span data-stu-id="41d77-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="41d77-111">変更するグループのプリンシパル GUID。</span><span class="sxs-lookup"><span data-stu-id="41d77-111">Principal GUID of the group that changed.</span></span>  <br/> |
|<span data-ttu-id="41d77-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="41d77-112">memberADPath</span></span>  <br/> |<span data-ttu-id="41d77-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="41d77-113">nvarchar (256)</span></span>  <br/> |<span data-ttu-id="41d77-114">メンバーの識別名です。</span><span class="sxs-lookup"><span data-stu-id="41d77-114">Distinguished name of the member.</span></span>  <br/> |
|<span data-ttu-id="41d77-115">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="41d77-115">memberRemoved</span></span>  <br/> |<span data-ttu-id="41d77-116">ビットの null でないです。</span><span class="sxs-lookup"><span data-stu-id="41d77-116">bit, not null</span></span>  <br/> |<span data-ttu-id="41d77-117">メンバーを追加した場合は false。</span><span class="sxs-lookup"><span data-stu-id="41d77-117">False if the member was added.</span></span> <span data-ttu-id="41d77-118">True を設定すると、メンバーが削除されました。</span><span class="sxs-lookup"><span data-stu-id="41d77-118">True if the member was removed.</span></span>  <br/> |
   
<span data-ttu-id="41d77-119">**キー**</span><span class="sxs-lookup"><span data-stu-id="41d77-119">**Key**</span></span>

|<span data-ttu-id="41d77-120">**列**</span><span class="sxs-lookup"><span data-stu-id="41d77-120">**Column**</span></span>|<span data-ttu-id="41d77-121">**説明**</span><span class="sxs-lookup"><span data-stu-id="41d77-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="41d77-122">\<prinGuid、memberADPath\></span><span class="sxs-lookup"><span data-stu-id="41d77-122">\<prinGuid, memberADPath\></span></span>  <br/> |<span data-ttu-id="41d77-123">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="41d77-123">Primary key.</span></span>  <br/> |
   

