---
title: tblADCookie
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie には、現在のライトウェイト ディレクトリ アクセス プロトコル (LDAP) 同期 cookie が含まれています。
ms.openlocfilehash: 3e7eeeeae6623bbbb308f4e05c4ab8a4b9a7be50
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213159"
---
# <a name="tbladcookie"></a><span data-ttu-id="a48c1-103">tblADCookie</span><span class="sxs-lookup"><span data-stu-id="a48c1-103">tblADCookie</span></span>
 
<span data-ttu-id="a48c1-104">tblADCookie には、現在のライトウェイト ディレクトリ アクセス プロトコル (LDAP) 同期 cookie が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a48c1-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>
  
<span data-ttu-id="a48c1-105">**列**</span><span class="sxs-lookup"><span data-stu-id="a48c1-105">**Columns**</span></span>

|<span data-ttu-id="a48c1-106">**列**</span><span class="sxs-lookup"><span data-stu-id="a48c1-106">**Column**</span></span>|<span data-ttu-id="a48c1-107">**型**</span><span class="sxs-lookup"><span data-stu-id="a48c1-107">**Type**</span></span>|<span data-ttu-id="a48c1-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="a48c1-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a48c1-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="a48c1-109">prinGuid</span></span>  <br/> |<span data-ttu-id="a48c1-110">GUID では、null でないです。</span><span class="sxs-lookup"><span data-stu-id="a48c1-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="a48c1-111">監視対象のドメインのプリンシパル GUID。</span><span class="sxs-lookup"><span data-stu-id="a48c1-111">Principal GUID of the domain being monitored.</span></span>  <br/> |
|<span data-ttu-id="a48c1-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="a48c1-112">prinDCHost</span></span>  <br/> |<span data-ttu-id="a48c1-113">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="a48c1-113">nvarchar (255)</span></span>  <br/> |<span data-ttu-id="a48c1-114">Active Directory ドメイン サービスの同期に使用される現在のドメイン コント ローラーの完全修飾ドメイン名 (FQDN) です。情報としての価値があります。</span><span class="sxs-lookup"><span data-stu-id="a48c1-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span>  <br/> |
|<span data-ttu-id="a48c1-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="a48c1-115">adcContent</span></span>  <br/> |<span data-ttu-id="a48c1-116">イメージ (バイナリ)</span><span class="sxs-lookup"><span data-stu-id="a48c1-116">image (binary)</span></span>  <br/> |<span data-ttu-id="a48c1-117">作業中のディレクトリ同期 cookie です。</span><span class="sxs-lookup"><span data-stu-id="a48c1-117">Active Directory Sync cookie.</span></span>  <br/> |
|<span data-ttu-id="a48c1-118">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="a48c1-118">lastUpdated</span></span>  <br/> |<span data-ttu-id="a48c1-119">datetime</span><span class="sxs-lookup"><span data-stu-id="a48c1-119">datetime</span></span>  <br/> |<span data-ttu-id="a48c1-120">行の更新日時とタイム ・ スタンプ。</span><span class="sxs-lookup"><span data-stu-id="a48c1-120">Time stamp with the row update time.</span></span>  <br/> |
|<span data-ttu-id="a48c1-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="a48c1-121">lockedUntil</span></span>  <br/> |<span data-ttu-id="a48c1-122">datetime</span><span class="sxs-lookup"><span data-stu-id="a48c1-122">datetime</span></span>  <br/> |<span data-ttu-id="a48c1-123">行がロックされ、変更されるまでの時間です。</span><span class="sxs-lookup"><span data-stu-id="a48c1-123">Time until the row is locked for changes.</span></span> <span data-ttu-id="a48c1-124">これは、チャット サービスの 1 つだけの時に、作業中のディレクトリ同期がいることを確認するソフトウェア インタロック メカニズムの一部です。</span><span class="sxs-lookup"><span data-stu-id="a48c1-124">This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span>  <br/> |
   
<span data-ttu-id="a48c1-125">**キー**</span><span class="sxs-lookup"><span data-stu-id="a48c1-125">**Keys**</span></span>

|<span data-ttu-id="a48c1-126">**列**</span><span class="sxs-lookup"><span data-stu-id="a48c1-126">**Column(s)**</span></span>|<span data-ttu-id="a48c1-127">**説明**</span><span class="sxs-lookup"><span data-stu-id="a48c1-127">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a48c1-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="a48c1-128">prinGuid</span></span>  <br/> |<span data-ttu-id="a48c1-129">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="a48c1-129">Primary key.</span></span>  <br/> |
|<span data-ttu-id="a48c1-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="a48c1-130">prinGuid</span></span>  <br/> |<span data-ttu-id="a48c1-131">Principal.prinGuid テーブル内の参照と外部キーです。</span><span class="sxs-lookup"><span data-stu-id="a48c1-131">Foreign key with lookup in Principal.prinGuid table.</span></span>  <br/> |
   

