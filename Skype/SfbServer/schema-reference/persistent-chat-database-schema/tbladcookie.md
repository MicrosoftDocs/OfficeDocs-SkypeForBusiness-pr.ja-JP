---
title: tblADCookie
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
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie には、現在のライトウェイトディレクトリアクセスプロトコル (LDAP) 同期 cookie が含まれています。
ms.openlocfilehash: c9a4c666a5fe4a76ecb3685f60f1208ec3ea88ed
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814705"
---
# <a name="tbladcookie"></a><span data-ttu-id="6c362-103">tblADCookie</span><span class="sxs-lookup"><span data-stu-id="6c362-103">tblADCookie</span></span>
 
<span data-ttu-id="6c362-104">tblADCookie には、現在のライトウェイトディレクトリアクセスプロトコル (LDAP) 同期 cookie が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6c362-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>
  
<span data-ttu-id="6c362-105">**行**</span><span class="sxs-lookup"><span data-stu-id="6c362-105">**Columns**</span></span>

|<span data-ttu-id="6c362-106">**列**</span><span class="sxs-lookup"><span data-stu-id="6c362-106">**Column**</span></span>|<span data-ttu-id="6c362-107">**種類**</span><span class="sxs-lookup"><span data-stu-id="6c362-107">**Type**</span></span>|<span data-ttu-id="6c362-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="6c362-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6c362-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="6c362-109">prinGuid</span></span>  <br/> |<span data-ttu-id="6c362-110">GUID、null ではない</span><span class="sxs-lookup"><span data-stu-id="6c362-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="6c362-111">監視されているドメインのプリンシパル GUID。</span><span class="sxs-lookup"><span data-stu-id="6c362-111">Principal GUID of the domain being monitored.</span></span>  <br/> |
|<span data-ttu-id="6c362-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="6c362-112">prinDCHost</span></span>  <br/> |<span data-ttu-id="6c362-113">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="6c362-113">nvarchar (255)</span></span>  <br/> |<span data-ttu-id="6c362-114">Active Directory ドメインサービスの同期に使用される、現在のドメインコントローラーの完全修飾ドメイン名 (FQDN) です。情報があります。</span><span class="sxs-lookup"><span data-stu-id="6c362-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span>  <br/> |
|<span data-ttu-id="6c362-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="6c362-115">adcContent</span></span>  <br/> |<span data-ttu-id="6c362-116">image (バイナリ)</span><span class="sxs-lookup"><span data-stu-id="6c362-116">image (binary)</span></span>  <br/> |<span data-ttu-id="6c362-117">Active Directory 同期 cookie。</span><span class="sxs-lookup"><span data-stu-id="6c362-117">Active Directory Sync cookie.</span></span>  <br/> |
|<span data-ttu-id="6c362-118">最終更新日</span><span class="sxs-lookup"><span data-stu-id="6c362-118">lastUpdated</span></span>  <br/> |<span data-ttu-id="6c362-119">datetime</span><span class="sxs-lookup"><span data-stu-id="6c362-119">datetime</span></span>  <br/> |<span data-ttu-id="6c362-120">行の更新時刻を含むタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="6c362-120">Time stamp with the row update time.</span></span>  <br/> |
|<span data-ttu-id="6c362-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="6c362-121">lockedUntil</span></span>  <br/> |<span data-ttu-id="6c362-122">datetime</span><span class="sxs-lookup"><span data-stu-id="6c362-122">datetime</span></span>  <br/> |<span data-ttu-id="6c362-123">変更のために行がロックされるまでの時間です。</span><span class="sxs-lookup"><span data-stu-id="6c362-123">Time until the row is locked for changes.</span></span> <span data-ttu-id="6c362-124">これは、チャットサービスの1つだけが同時に Active Directory の同期を行うことができるようにするソフトウェアの連結メカニズムの一部です。</span><span class="sxs-lookup"><span data-stu-id="6c362-124">This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span>  <br/> |
   
<span data-ttu-id="6c362-125">**機能**</span><span class="sxs-lookup"><span data-stu-id="6c362-125">**Keys**</span></span>

|<span data-ttu-id="6c362-126">**列**</span><span class="sxs-lookup"><span data-stu-id="6c362-126">**Column(s)**</span></span>|<span data-ttu-id="6c362-127">**説明**</span><span class="sxs-lookup"><span data-stu-id="6c362-127">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6c362-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="6c362-128">prinGuid</span></span>  <br/> |<span data-ttu-id="6c362-129">主キー。</span><span class="sxs-lookup"><span data-stu-id="6c362-129">Primary key.</span></span>  <br/> |
|<span data-ttu-id="6c362-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="6c362-130">prinGuid</span></span>  <br/> |<span data-ttu-id="6c362-131">プリンシパルで参照される外部キー (prinGuid テーブル)。</span><span class="sxs-lookup"><span data-stu-id="6c362-131">Foreign key with lookup in Principal.prinGuid table.</span></span>  <br/> |
   

