---
title: tblPrincipalMemberDifference
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference には、グループ メンバーシップの変更 (追加し、削除メンバー) を Active Directory ドメイン サービスの同期の後の手順でまだ処理されていないが含まれています。
ms.openlocfilehash: 603c8345f2adc2ba7d5eb04835218fd3e83d8ed4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalmemberdifference"></a><span data-ttu-id="b61e3-103">tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="b61e3-103">tblPrincipalMemberDifference</span></span>
 
<span data-ttu-id="b61e3-104">tblPrincipalMemberDifference には、グループ メンバーシップの変更 (追加し、削除メンバー) を Active Directory ドメイン サービスの同期の後の手順でまだ処理されていないが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b61e3-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>
  
<span data-ttu-id="b61e3-105">**列**</span><span class="sxs-lookup"><span data-stu-id="b61e3-105">**Columns**</span></span>

|<span data-ttu-id="b61e3-106">**列**</span><span class="sxs-lookup"><span data-stu-id="b61e3-106">**Column**</span></span>|<span data-ttu-id="b61e3-107">**タイプ**</span><span class="sxs-lookup"><span data-stu-id="b61e3-107">**Type**</span></span>|<span data-ttu-id="b61e3-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="b61e3-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b61e3-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="b61e3-109">prinGuid</span></span>  <br/> |<span data-ttu-id="b61e3-110">GUID では、null でないです。</span><span class="sxs-lookup"><span data-stu-id="b61e3-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="b61e3-111">変更するグループのプリンシパル GUID。</span><span class="sxs-lookup"><span data-stu-id="b61e3-111">Principal GUID of the group that changed.</span></span>  <br/> |
|<span data-ttu-id="b61e3-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="b61e3-112">memberADPath</span></span>  <br/> |<span data-ttu-id="b61e3-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b61e3-113">nvarchar (256)</span></span>  <br/> |<span data-ttu-id="b61e3-114">メンバーの識別名です。</span><span class="sxs-lookup"><span data-stu-id="b61e3-114">Distinguished name of the member.</span></span>  <br/> |
|<span data-ttu-id="b61e3-115">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="b61e3-115">memberRemoved</span></span>  <br/> |<span data-ttu-id="b61e3-116">ビットの null でないです。</span><span class="sxs-lookup"><span data-stu-id="b61e3-116">bit, not null</span></span>  <br/> |<span data-ttu-id="b61e3-117">メンバーを追加した場合は false。</span><span class="sxs-lookup"><span data-stu-id="b61e3-117">False if the member was added.</span></span> <span data-ttu-id="b61e3-118">True を設定すると、メンバーが削除されました。</span><span class="sxs-lookup"><span data-stu-id="b61e3-118">True if the member was removed.</span></span>  <br/> |
   
<span data-ttu-id="b61e3-119">**キー**</span><span class="sxs-lookup"><span data-stu-id="b61e3-119">**Key**</span></span>

|<span data-ttu-id="b61e3-120">**列**</span><span class="sxs-lookup"><span data-stu-id="b61e3-120">**Column**</span></span>|<span data-ttu-id="b61e3-121">**説明**</span><span class="sxs-lookup"><span data-stu-id="b61e3-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b61e3-122">\<prinGuid、memberADPath\></span><span class="sxs-lookup"><span data-stu-id="b61e3-122">\<prinGuid, memberADPath\></span></span>  <br/> |<span data-ttu-id="b61e3-123">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="b61e3-123">Primary key.</span></span>  <br/> |
   

