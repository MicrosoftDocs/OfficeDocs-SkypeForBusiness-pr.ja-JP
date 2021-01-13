---
title: tblADCookie
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie には、現在のライトウェイト ディレクトリ アクセス プロトコル (LDAP) 同期 Cookie が格納されます。
ms.openlocfilehash: 78a477399da811e674bb5a4493e61100acdd4782
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814757"
---
# <a name="tbladcookie"></a><span data-ttu-id="7e7ef-103">tblADCookie</span><span class="sxs-lookup"><span data-stu-id="7e7ef-103">tblADCookie</span></span>
 
<span data-ttu-id="7e7ef-104">tblADCookie には、現在のライトウェイト ディレクトリ アクセス プロトコル (LDAP) 同期 Cookie が格納されます。</span><span class="sxs-lookup"><span data-stu-id="7e7ef-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>
  
<span data-ttu-id="7e7ef-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="7e7ef-105">**Columns**</span></span>

|<span data-ttu-id="7e7ef-106">**列**</span><span class="sxs-lookup"><span data-stu-id="7e7ef-106">**Column**</span></span>|<span data-ttu-id="7e7ef-107">**型**</span><span class="sxs-lookup"><span data-stu-id="7e7ef-107">**Type**</span></span>|<span data-ttu-id="7e7ef-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="7e7ef-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7e7ef-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="7e7ef-109">prinGuid</span></span>  <br/> |<span data-ttu-id="7e7ef-110">NULL でない GUID</span><span class="sxs-lookup"><span data-stu-id="7e7ef-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="7e7ef-111">監視対象のドメインのプリンシパル GUID。</span><span class="sxs-lookup"><span data-stu-id="7e7ef-111">Principal GUID of the domain being monitored.</span></span>  <br/> |
|<span data-ttu-id="7e7ef-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="7e7ef-112">prinDCHost</span></span>  <br/> |<span data-ttu-id="7e7ef-113">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="7e7ef-113">nvarchar (255)</span></span>  <br/> |<span data-ttu-id="7e7ef-114">Active Directory ドメイン サービス同期に使用されている現在のドメイン コントローラーの完全修飾ドメイン名 (FQDN)。情報的な値を持つ。</span><span class="sxs-lookup"><span data-stu-id="7e7ef-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span>  <br/> |
|<span data-ttu-id="7e7ef-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="7e7ef-115">adcContent</span></span>  <br/> |<span data-ttu-id="7e7ef-116">image (バイナリ)</span><span class="sxs-lookup"><span data-stu-id="7e7ef-116">image (binary)</span></span>  <br/> |<span data-ttu-id="7e7ef-117">Active Directory の同期 Cookie。</span><span class="sxs-lookup"><span data-stu-id="7e7ef-117">Active Directory Sync cookie.</span></span>  <br/> |
|<span data-ttu-id="7e7ef-118">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="7e7ef-118">lastUpdated</span></span>  <br/> |<span data-ttu-id="7e7ef-119">日付型</span><span class="sxs-lookup"><span data-stu-id="7e7ef-119">datetime</span></span>  <br/> |<span data-ttu-id="7e7ef-120">行更新時刻でのタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="7e7ef-120">Time stamp with the row update time.</span></span>  <br/> |
|<span data-ttu-id="7e7ef-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="7e7ef-121">lockedUntil</span></span>  <br/> |<span data-ttu-id="7e7ef-122">日付型</span><span class="sxs-lookup"><span data-stu-id="7e7ef-122">datetime</span></span>  <br/> |<span data-ttu-id="7e7ef-p101">行が変更のためにロックされるまでの時間。これは、一度に 1 つのチャット サービスのみが Active Directory 同期を行うことを保証するソフトウェア インタロック メカニズムの一部です。</span><span class="sxs-lookup"><span data-stu-id="7e7ef-p101">Time until the row is locked for changes. This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span>  <br/> |
   
<span data-ttu-id="7e7ef-125">**Keys**</span><span class="sxs-lookup"><span data-stu-id="7e7ef-125">**Keys**</span></span>

|<span data-ttu-id="7e7ef-126">**Column(s)**</span><span class="sxs-lookup"><span data-stu-id="7e7ef-126">**Column(s)**</span></span>|<span data-ttu-id="7e7ef-127">**説明**</span><span class="sxs-lookup"><span data-stu-id="7e7ef-127">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7e7ef-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="7e7ef-128">prinGuid</span></span>  <br/> |<span data-ttu-id="7e7ef-129">主キー。</span><span class="sxs-lookup"><span data-stu-id="7e7ef-129">Primary key.</span></span>  <br/> |
|<span data-ttu-id="7e7ef-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="7e7ef-130">prinGuid</span></span>  <br/> |<span data-ttu-id="7e7ef-131">Principal.prinGuid テーブル内の参照による外部キー。</span><span class="sxs-lookup"><span data-stu-id="7e7ef-131">Foreign key with lookup in Principal.prinGuid table.</span></span>  <br/> |
   

