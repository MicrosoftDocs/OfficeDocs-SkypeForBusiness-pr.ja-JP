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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference には、後の Active Directory ドメインサービスの同期手順でまだ処理されていないグループメンバーシップの変更 (メンバーの追加と削除) が含まれています。
ms.openlocfilehash: c7e965658c9e351a7a2d079921b7abe8166b48ad
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814075"
---
# <a name="tblprincipalmemberdifference"></a><span data-ttu-id="3da64-103">tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="3da64-103">tblPrincipalMemberDifference</span></span>
 
<span data-ttu-id="3da64-104">tblPrincipalMemberDifference には、後の Active Directory ドメインサービスの同期手順でまだ処理されていないグループメンバーシップの変更 (メンバーの追加と削除) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3da64-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>
  
<span data-ttu-id="3da64-105">**行**</span><span class="sxs-lookup"><span data-stu-id="3da64-105">**Columns**</span></span>

|<span data-ttu-id="3da64-106">**列**</span><span class="sxs-lookup"><span data-stu-id="3da64-106">**Column**</span></span>|<span data-ttu-id="3da64-107">**種類**</span><span class="sxs-lookup"><span data-stu-id="3da64-107">**Type**</span></span>|<span data-ttu-id="3da64-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="3da64-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3da64-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="3da64-109">prinGuid</span></span>  <br/> |<span data-ttu-id="3da64-110">GUID、null ではない</span><span class="sxs-lookup"><span data-stu-id="3da64-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="3da64-111">変更されたグループのプリンシパル GUID。</span><span class="sxs-lookup"><span data-stu-id="3da64-111">Principal GUID of the group that changed.</span></span>  <br/> |
|<span data-ttu-id="3da64-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="3da64-112">memberADPath</span></span>  <br/> |<span data-ttu-id="3da64-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3da64-113">nvarchar (256)</span></span>  <br/> |<span data-ttu-id="3da64-114">メンバーの識別名。</span><span class="sxs-lookup"><span data-stu-id="3da64-114">Distinguished name of the member.</span></span>  <br/> |
|<span data-ttu-id="3da64-115">メンバーの削除</span><span class="sxs-lookup"><span data-stu-id="3da64-115">memberRemoved</span></span>  <br/> |<span data-ttu-id="3da64-116">ビット、null ではない</span><span class="sxs-lookup"><span data-stu-id="3da64-116">bit, not null</span></span>  <br/> |<span data-ttu-id="3da64-117">メンバーが追加された場合は False。</span><span class="sxs-lookup"><span data-stu-id="3da64-117">False if the member was added.</span></span> <span data-ttu-id="3da64-118">メンバーが削除された場合は True です。</span><span class="sxs-lookup"><span data-stu-id="3da64-118">True if the member was removed.</span></span>  <br/> |
   
<span data-ttu-id="3da64-119">**Key**</span><span class="sxs-lookup"><span data-stu-id="3da64-119">**Key**</span></span>

|<span data-ttu-id="3da64-120">**列**</span><span class="sxs-lookup"><span data-stu-id="3da64-120">**Column**</span></span>|<span data-ttu-id="3da64-121">**説明**</span><span class="sxs-lookup"><span data-stu-id="3da64-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3da64-122">\<prinGuid、memberADPath\></span><span class="sxs-lookup"><span data-stu-id="3da64-122">\<prinGuid, memberADPath\></span></span>  <br/> |<span data-ttu-id="3da64-123">主キー。</span><span class="sxs-lookup"><span data-stu-id="3da64-123">Primary key.</span></span>  <br/> |
   

