---
title: tblPrincipalMemberDifference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference には、後の Active Directory ドメインサービスの同期手順でまだ処理されていないグループメンバーシップの変更 (メンバーの追加と削除) が含まれています。
ms.openlocfilehash: 18d0f3f5c8700db0bb81470f5ee90851e8d277ad
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295301"
---
# <a name="tblprincipalmemberdifference"></a><span data-ttu-id="1f632-103">tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="1f632-103">tblPrincipalMemberDifference</span></span>
 
<span data-ttu-id="1f632-104">tblPrincipalMemberDifference には、後の Active Directory ドメインサービスの同期手順でまだ処理されていないグループメンバーシップの変更 (メンバーの追加と削除) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1f632-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>
  
<span data-ttu-id="1f632-105">**行**</span><span class="sxs-lookup"><span data-stu-id="1f632-105">**Columns**</span></span>

|<span data-ttu-id="1f632-106">**列**</span><span class="sxs-lookup"><span data-stu-id="1f632-106">**Column**</span></span>|<span data-ttu-id="1f632-107">**型**</span><span class="sxs-lookup"><span data-stu-id="1f632-107">**Type**</span></span>|<span data-ttu-id="1f632-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="1f632-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1f632-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="1f632-109">prinGuid</span></span>  <br/> |<span data-ttu-id="1f632-110">GUID、null ではない</span><span class="sxs-lookup"><span data-stu-id="1f632-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="1f632-111">変更されたグループのプリンシパル GUID。</span><span class="sxs-lookup"><span data-stu-id="1f632-111">Principal GUID of the group that changed.</span></span>  <br/> |
|<span data-ttu-id="1f632-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="1f632-112">memberADPath</span></span>  <br/> |<span data-ttu-id="1f632-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1f632-113">nvarchar (256)</span></span>  <br/> |<span data-ttu-id="1f632-114">メンバーの識別名。</span><span class="sxs-lookup"><span data-stu-id="1f632-114">Distinguished name of the member.</span></span>  <br/> |
|<span data-ttu-id="1f632-115">メンバーの削除</span><span class="sxs-lookup"><span data-stu-id="1f632-115">memberRemoved</span></span>  <br/> |<span data-ttu-id="1f632-116">ビット、null ではない</span><span class="sxs-lookup"><span data-stu-id="1f632-116">bit, not null</span></span>  <br/> |<span data-ttu-id="1f632-117">メンバーが追加された場合は False。</span><span class="sxs-lookup"><span data-stu-id="1f632-117">False if the member was added.</span></span> <span data-ttu-id="1f632-118">メンバーが削除された場合は True です。</span><span class="sxs-lookup"><span data-stu-id="1f632-118">True if the member was removed.</span></span>  <br/> |
   
<span data-ttu-id="1f632-119">**キー**</span><span class="sxs-lookup"><span data-stu-id="1f632-119">**Key**</span></span>

|<span data-ttu-id="1f632-120">**列**</span><span class="sxs-lookup"><span data-stu-id="1f632-120">**Column**</span></span>|<span data-ttu-id="1f632-121">**説明**</span><span class="sxs-lookup"><span data-stu-id="1f632-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1f632-122">\<prinGuid、memberADPath\></span><span class="sxs-lookup"><span data-stu-id="1f632-122">\<prinGuid, memberADPath\></span></span>  <br/> |<span data-ttu-id="1f632-123">主キー。</span><span class="sxs-lookup"><span data-stu-id="1f632-123">Primary key.</span></span>  <br/> |
   

