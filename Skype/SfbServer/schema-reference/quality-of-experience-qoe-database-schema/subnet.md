---
title: Subnet テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: サブネットの表はサポートテーブルです。 各レコードは、[ネットワーク構成] の設定で定義された1つのサブネットを表します。
ms.openlocfilehash: 9f36c5e334e92caa8bf4a81a682b7737e8999b3c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294636"
---
# <a name="subnet-table"></a><span data-ttu-id="3db6a-104">Subnet テーブル</span><span class="sxs-lookup"><span data-stu-id="3db6a-104">Subnet table</span></span>
 
<span data-ttu-id="3db6a-105">サブネットの表はサポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="3db6a-105">The Subnet table is a supporting table.</span></span> <span data-ttu-id="3db6a-106">各レコードは、[ネットワーク構成] の設定で定義された1つのサブネットを表します。</span><span class="sxs-lookup"><span data-stu-id="3db6a-106">Each record represents one subnet defined in network configuration setting.</span></span>
  
|<span data-ttu-id="3db6a-107">**列**</span><span class="sxs-lookup"><span data-stu-id="3db6a-107">**Column**</span></span>|<span data-ttu-id="3db6a-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="3db6a-108">**Data Type**</span></span>|<span data-ttu-id="3db6a-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="3db6a-109">**Key/Index**</span></span>|<span data-ttu-id="3db6a-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="3db6a-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3db6a-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="3db6a-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="3db6a-112">int</span><span class="sxs-lookup"><span data-stu-id="3db6a-112">int</span></span>  <br/> |<span data-ttu-id="3db6a-113">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="3db6a-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="3db6a-114">サブネットの IP の整数表現。</span><span class="sxs-lookup"><span data-stu-id="3db6a-114">Integer representation for the subnet IP.</span></span>  <br/> |
|<span data-ttu-id="3db6a-115">**ネット**</span><span class="sxs-lookup"><span data-stu-id="3db6a-115">**SubnetMask**</span></span> <br/> |<span data-ttu-id="3db6a-116">int</span><span class="sxs-lookup"><span data-stu-id="3db6a-116">int</span></span>  <br/> ||<span data-ttu-id="3db6a-117">サブネット マスク。</span><span class="sxs-lookup"><span data-stu-id="3db6a-117">Subnet mask.</span></span>  <br/> |
|<span data-ttu-id="3db6a-118">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="3db6a-118">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="3db6a-119">int</span><span class="sxs-lookup"><span data-stu-id="3db6a-119">int</span></span>  <br/> |<span data-ttu-id="3db6a-120">外部</span><span class="sxs-lookup"><span data-stu-id="3db6a-120">Foreign</span></span>  <br/> |<span data-ttu-id="3db6a-121">[Usersite テーブル](usersite.md)から参照されます。</span><span class="sxs-lookup"><span data-stu-id="3db6a-121">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="3db6a-122">**サブネットの説明**</span><span class="sxs-lookup"><span data-stu-id="3db6a-122">**SubnetDescription**</span></span> <br/> |<span data-ttu-id="3db6a-123">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="3db6a-123">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="3db6a-124">サブネットの説明。</span><span class="sxs-lookup"><span data-stu-id="3db6a-124">The description for the subnet.</span></span>  <br/> |
   

