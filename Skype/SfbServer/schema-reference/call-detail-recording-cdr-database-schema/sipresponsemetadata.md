---
title: SIPResponseMetaData テーブル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: SIPResponseMetaDataTable には、SIP 応答コードと、各コードの分類と定義の一覧が含まれます。これらのコードは SIP デバイスおよび SIP 通信セッションに影響を与えるイベントへの応答して生成されます。たとえば、応答コード 403 は、SIP デバイスが要求を行い、サーバーがその要求の実行を拒否したときに生成されます。
ms.openlocfilehash: 3d6714e9c5b5c154d19381fad33821b02ec8a73e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809927"
---
# <a name="sipresponsemetadata-table"></a><span data-ttu-id="c9d26-104">SIPResponseMetaData テーブル</span><span class="sxs-lookup"><span data-stu-id="c9d26-104">SIPResponseMetaData table</span></span>
 
<span data-ttu-id="c9d26-p102">SIPResponseMetaDataTable には、SIP 応答コードと、各コードの分類と定義の一覧が含まれます。これらのコードは SIP デバイスおよび SIP 通信セッションに影響を与えるイベントへの応答して生成されます。たとえば、応答コード 403 は、SIP デバイスが要求を行い、サーバーがその要求の実行を拒否したときに生成されます。</span><span class="sxs-lookup"><span data-stu-id="c9d26-p102">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes. These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>
  
<span data-ttu-id="c9d26-107">この表は、Skype for Business Server 2015 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c9d26-107">This table was introduced in Skype for Business Server 2015.</span></span>
  
|<span data-ttu-id="c9d26-108">**列**</span><span class="sxs-lookup"><span data-stu-id="c9d26-108">**Column**</span></span>|<span data-ttu-id="c9d26-109">**データ型**</span><span class="sxs-lookup"><span data-stu-id="c9d26-109">**Data Type**</span></span>|<span data-ttu-id="c9d26-110">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="c9d26-110">**Key/Index**</span></span>|<span data-ttu-id="c9d26-111">**詳細**</span><span class="sxs-lookup"><span data-stu-id="c9d26-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c9d26-112">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="c9d26-112">**ResponseCode**</span></span> <br/> |<span data-ttu-id="c9d26-113">int</span><span class="sxs-lookup"><span data-stu-id="c9d26-113">int</span></span>  <br/> |<span data-ttu-id="c9d26-114">Primary</span><span class="sxs-lookup"><span data-stu-id="c9d26-114">Primary</span></span>  <br/> |<span data-ttu-id="c9d26-115">SIP 応答コードを表す数値。</span><span class="sxs-lookup"><span data-stu-id="c9d26-115">Numeric value that represents the SIP response code.</span></span>  <br/> |
|<span data-ttu-id="c9d26-116">**Class**</span><span class="sxs-lookup"><span data-stu-id="c9d26-116">**Class**</span></span> <br/> |<span data-ttu-id="c9d26-117">int</span><span class="sxs-lookup"><span data-stu-id="c9d26-117">int</span></span>  <br/> || <span data-ttu-id="c9d26-p103">応答コードの一般的な分類。以下の分類があります。</span><span class="sxs-lookup"><span data-stu-id="c9d26-p103">General classification for the response code. Classifications include:</span></span> <br/>  <span data-ttu-id="c9d26-120">1 - 情報応答</span><span class="sxs-lookup"><span data-stu-id="c9d26-120">1 - Informational Responses</span></span> <br/>  <span data-ttu-id="c9d26-121">2 - 成功した応答</span><span class="sxs-lookup"><span data-stu-id="c9d26-121">2 - Successful Responses</span></span> <br/>  <span data-ttu-id="c9d26-122">3 - リダイレクト応答</span><span class="sxs-lookup"><span data-stu-id="c9d26-122">3 - Redirection Responses</span></span> <br/>  <span data-ttu-id="c9d26-123">4 - クライアント エラー応答</span><span class="sxs-lookup"><span data-stu-id="c9d26-123">4 - Client Failure Responses</span></span> <br/>  <span data-ttu-id="c9d26-124">5 -- サーバー障害応答</span><span class="sxs-lookup"><span data-stu-id="c9d26-124">5 -- Server Failure Responses</span></span> <br/>  <span data-ttu-id="c9d26-125">6 - グローバル エラー応答</span><span class="sxs-lookup"><span data-stu-id="c9d26-125">6 - Global Failure Response</span></span> <br/> |
|<span data-ttu-id="c9d26-126">**説明**</span><span class="sxs-lookup"><span data-stu-id="c9d26-126">**Description**</span></span> <br/> |<span data-ttu-id="c9d26-127">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c9d26-127">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="c9d26-p104">SIP 応答コードの説明。たとえば、コード 181 には以下の説明があります。</span><span class="sxs-lookup"><span data-stu-id="c9d26-p104">Description of the SIP response code. For example, response code 181 has the following description:</span></span>  <br/> <span data-ttu-id="c9d26-130">Call Is Being Forwarded (呼び出しを転送中)</span><span class="sxs-lookup"><span data-stu-id="c9d26-130">Call Is Being Forwarded</span></span>  <br/> |
   

