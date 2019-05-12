---
title: tblADCookie
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie には、現在のライトウェイト ディレクトリ アクセス プロトコル (LDAP) 同期 cookie が含まれています。
ms.openlocfilehash: d990d02e73be9a4d6178037a314e36add448ad40
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929946"
---
# <a name="tbladcookie"></a><span data-ttu-id="3fbd9-103">tblADCookie</span><span class="sxs-lookup"><span data-stu-id="3fbd9-103">tblADCookie</span></span>
 
<span data-ttu-id="3fbd9-104">tblADCookie には、現在のライトウェイト ディレクトリ アクセス プロトコル (LDAP) 同期 cookie が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3fbd9-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>
  
<span data-ttu-id="3fbd9-105">**列**</span><span class="sxs-lookup"><span data-stu-id="3fbd9-105">**Columns**</span></span>

|<span data-ttu-id="3fbd9-106">**列**</span><span class="sxs-lookup"><span data-stu-id="3fbd9-106">**Column**</span></span>|<span data-ttu-id="3fbd9-107">**型**</span><span class="sxs-lookup"><span data-stu-id="3fbd9-107">**Type**</span></span>|<span data-ttu-id="3fbd9-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="3fbd9-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3fbd9-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="3fbd9-109">prinGuid</span></span>  <br/> |<span data-ttu-id="3fbd9-110">GUID では、null でないです。</span><span class="sxs-lookup"><span data-stu-id="3fbd9-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="3fbd9-111">監視対象のドメインのプリンシパル GUID。</span><span class="sxs-lookup"><span data-stu-id="3fbd9-111">Principal GUID of the domain being monitored.</span></span>  <br/> |
|<span data-ttu-id="3fbd9-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="3fbd9-112">prinDCHost</span></span>  <br/> |<span data-ttu-id="3fbd9-113">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="3fbd9-113">nvarchar (255)</span></span>  <br/> |<span data-ttu-id="3fbd9-114">Active Directory ドメイン サービスの同期に使用される現在のドメイン コント ローラーの完全修飾ドメイン名 (FQDN) です。情報としての価値があります。</span><span class="sxs-lookup"><span data-stu-id="3fbd9-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span>  <br/> |
|<span data-ttu-id="3fbd9-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="3fbd9-115">adcContent</span></span>  <br/> |<span data-ttu-id="3fbd9-116">イメージ (バイナリ)</span><span class="sxs-lookup"><span data-stu-id="3fbd9-116">image (binary)</span></span>  <br/> |<span data-ttu-id="3fbd9-117">作業中のディレクトリ同期 cookie です。</span><span class="sxs-lookup"><span data-stu-id="3fbd9-117">Active Directory Sync cookie.</span></span>  <br/> |
|<span data-ttu-id="3fbd9-118">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="3fbd9-118">lastUpdated</span></span>  <br/> |<span data-ttu-id="3fbd9-119">datetime</span><span class="sxs-lookup"><span data-stu-id="3fbd9-119">datetime</span></span>  <br/> |<span data-ttu-id="3fbd9-120">行の更新日時とタイム ・ スタンプ。</span><span class="sxs-lookup"><span data-stu-id="3fbd9-120">Time stamp with the row update time.</span></span>  <br/> |
|<span data-ttu-id="3fbd9-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="3fbd9-121">lockedUntil</span></span>  <br/> |<span data-ttu-id="3fbd9-122">datetime</span><span class="sxs-lookup"><span data-stu-id="3fbd9-122">datetime</span></span>  <br/> |<span data-ttu-id="3fbd9-123">行がロックされ、変更されるまでの時間です。</span><span class="sxs-lookup"><span data-stu-id="3fbd9-123">Time until the row is locked for changes.</span></span> <span data-ttu-id="3fbd9-124">これは、チャット サービスの 1 つだけの時に、作業中のディレクトリ同期がいることを確認するソフトウェア インタロック メカニズムの一部です。</span><span class="sxs-lookup"><span data-stu-id="3fbd9-124">This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span>  <br/> |
   
<span data-ttu-id="3fbd9-125">**キー**</span><span class="sxs-lookup"><span data-stu-id="3fbd9-125">**Keys**</span></span>

|<span data-ttu-id="3fbd9-126">**列**</span><span class="sxs-lookup"><span data-stu-id="3fbd9-126">**Column(s)**</span></span>|<span data-ttu-id="3fbd9-127">**説明**</span><span class="sxs-lookup"><span data-stu-id="3fbd9-127">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3fbd9-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="3fbd9-128">prinGuid</span></span>  <br/> |<span data-ttu-id="3fbd9-129">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="3fbd9-129">Primary key.</span></span>  <br/> |
|<span data-ttu-id="3fbd9-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="3fbd9-130">prinGuid</span></span>  <br/> |<span data-ttu-id="3fbd9-131">Principal.prinGuid テーブル内の参照と外部キーです。</span><span class="sxs-lookup"><span data-stu-id="3fbd9-131">Foreign key with lookup in Principal.prinGuid table.</span></span>  <br/> |
   

