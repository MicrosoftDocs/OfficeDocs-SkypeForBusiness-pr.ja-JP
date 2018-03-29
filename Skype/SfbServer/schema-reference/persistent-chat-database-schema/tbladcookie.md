---
title: tblADCookie
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
ms.openlocfilehash: bc2c0657caa66a0420bc493bf4b688a2a081db36
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="tbladcookie"></a><span data-ttu-id="7a1f2-103">tblADCookie</span><span class="sxs-lookup"><span data-stu-id="7a1f2-103">tblADCookie</span></span>
 
<span data-ttu-id="7a1f2-104">tblADCookie には、現在のライトウェイト ディレクトリ アクセス プロトコル (LDAP) 同期 cookie が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7a1f2-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>
  
<span data-ttu-id="7a1f2-105">**列**</span><span class="sxs-lookup"><span data-stu-id="7a1f2-105">**Columns**</span></span>

|<span data-ttu-id="7a1f2-106">**列**</span><span class="sxs-lookup"><span data-stu-id="7a1f2-106">**Column**</span></span>|<span data-ttu-id="7a1f2-107">**タイプ**</span><span class="sxs-lookup"><span data-stu-id="7a1f2-107">**Type**</span></span>|<span data-ttu-id="7a1f2-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="7a1f2-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7a1f2-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="7a1f2-109">prinGuid</span></span>  <br/> |<span data-ttu-id="7a1f2-110">GUID では、null でないです。</span><span class="sxs-lookup"><span data-stu-id="7a1f2-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="7a1f2-111">監視対象のドメインのプリンシパル GUID。</span><span class="sxs-lookup"><span data-stu-id="7a1f2-111">Principal GUID of the domain being monitored.</span></span>  <br/> |
|<span data-ttu-id="7a1f2-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="7a1f2-112">prinDCHost</span></span>  <br/> |<span data-ttu-id="7a1f2-113">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="7a1f2-113">nvarchar (255)</span></span>  <br/> |<span data-ttu-id="7a1f2-114">Active Directory ドメイン サービスの同期に使用される現在のドメイン コント ローラーの完全修飾ドメイン名 (FQDN) です。情報としての価値があります。</span><span class="sxs-lookup"><span data-stu-id="7a1f2-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span>  <br/> |
|<span data-ttu-id="7a1f2-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="7a1f2-115">adcContent</span></span>  <br/> |<span data-ttu-id="7a1f2-116">イメージ (バイナリ)</span><span class="sxs-lookup"><span data-stu-id="7a1f2-116">image (binary)</span></span>  <br/> |<span data-ttu-id="7a1f2-117">作業中のディレクトリ同期 cookie です。</span><span class="sxs-lookup"><span data-stu-id="7a1f2-117">Active Directory Sync cookie.</span></span>  <br/> |
|<span data-ttu-id="7a1f2-118">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="7a1f2-118">lastUpdated</span></span>  <br/> |<span data-ttu-id="7a1f2-119">datetime</span><span class="sxs-lookup"><span data-stu-id="7a1f2-119">datetime</span></span>  <br/> |<span data-ttu-id="7a1f2-120">行の更新日時とタイム ・ スタンプ。</span><span class="sxs-lookup"><span data-stu-id="7a1f2-120">Time stamp with the row update time.</span></span>  <br/> |
|<span data-ttu-id="7a1f2-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="7a1f2-121">lockedUntil</span></span>  <br/> |<span data-ttu-id="7a1f2-122">datetime</span><span class="sxs-lookup"><span data-stu-id="7a1f2-122">datetime</span></span>  <br/> |<span data-ttu-id="7a1f2-123">行がロックされ、変更されるまでの時間です。</span><span class="sxs-lookup"><span data-stu-id="7a1f2-123">Time until the row is locked for changes.</span></span> <span data-ttu-id="7a1f2-124">これは、チャット サービスの 1 つだけの時に、作業中のディレクトリ同期がいることを確認するソフトウェア インタロック メカニズムの一部です。</span><span class="sxs-lookup"><span data-stu-id="7a1f2-124">This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span>  <br/> |
   
<span data-ttu-id="7a1f2-125">**キー**</span><span class="sxs-lookup"><span data-stu-id="7a1f2-125">**Keys**</span></span>

|<span data-ttu-id="7a1f2-126">**列**</span><span class="sxs-lookup"><span data-stu-id="7a1f2-126">**Column(s)**</span></span>|<span data-ttu-id="7a1f2-127">**説明**</span><span class="sxs-lookup"><span data-stu-id="7a1f2-127">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7a1f2-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="7a1f2-128">prinGuid</span></span>  <br/> |<span data-ttu-id="7a1f2-129">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="7a1f2-129">Primary key.</span></span>  <br/> |
|<span data-ttu-id="7a1f2-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="7a1f2-130">prinGuid</span></span>  <br/> |<span data-ttu-id="7a1f2-131">Principal.prinGuid テーブル内の参照と外部キーです。</span><span class="sxs-lookup"><span data-stu-id="7a1f2-131">Foreign key with lookup in Principal.prinGuid table.</span></span>  <br/> |
   

