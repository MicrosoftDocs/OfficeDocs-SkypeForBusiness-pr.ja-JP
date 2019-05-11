---
title: SIPResponseMetaData テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: SIPResponseMetaDataTable には、SIP 応答コードの分類とそのコードのそれぞれの定義の一覧が含まれています。 これらのコードは SIP デバイスに影響するイベントへの応答として生成され、SIP 通信セッションです。などの SIP デバイスが、要求を行ったが、その要求を尊重する、サーバーが拒否した場合に、403 応答コードが生成されます。
ms.openlocfilehash: edd1f4e60376b367f701864ff15d334c4d971e47
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930288"
---
# <a name="sipresponsemetadata-table"></a><span data-ttu-id="3338c-104">SIPResponseMetaData テーブル</span><span class="sxs-lookup"><span data-stu-id="3338c-104">SIPResponseMetaData table</span></span>
 
<span data-ttu-id="3338c-105">SIPResponseMetaDataTable には、SIP 応答コードの分類とそのコードのそれぞれの定義の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3338c-105">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes.</span></span> <span data-ttu-id="3338c-106">これらのコードは SIP デバイスに影響するイベントへの応答として生成され、SIP 通信セッションです。などの SIP デバイスが、要求を行ったが、その要求を尊重する、サーバーが拒否した場合に、403 応答コードが生成されます。</span><span class="sxs-lookup"><span data-stu-id="3338c-106">These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>
  
<span data-ttu-id="3338c-107">次の表は、ビジネス サーバー 2015 の Skype で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3338c-107">This table was introduced in Skype for Business Server 2015.</span></span>
  
|<span data-ttu-id="3338c-108">**列**</span><span class="sxs-lookup"><span data-stu-id="3338c-108">**Column**</span></span>|<span data-ttu-id="3338c-109">**データ型**</span><span class="sxs-lookup"><span data-stu-id="3338c-109">**Data Type**</span></span>|<span data-ttu-id="3338c-110">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="3338c-110">**Key/Index**</span></span>|<span data-ttu-id="3338c-111">**詳細**</span><span class="sxs-lookup"><span data-stu-id="3338c-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3338c-112">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="3338c-112">**ResponseCode**</span></span> <br/> |<span data-ttu-id="3338c-113">int</span><span class="sxs-lookup"><span data-stu-id="3338c-113">int</span></span>  <br/> |<span data-ttu-id="3338c-114">Primary</span><span class="sxs-lookup"><span data-stu-id="3338c-114">Primary</span></span>  <br/> |<span data-ttu-id="3338c-115">SIP 応答コードを表す数値を指定します。</span><span class="sxs-lookup"><span data-stu-id="3338c-115">Numeric value that represents the SIP response code.</span></span>  <br/> |
|<span data-ttu-id="3338c-116">**クラス**</span><span class="sxs-lookup"><span data-stu-id="3338c-116">**Class**</span></span> <br/> |<span data-ttu-id="3338c-117">int</span><span class="sxs-lookup"><span data-stu-id="3338c-117">int</span></span>  <br/> || <span data-ttu-id="3338c-118">応答コードの一般的な分類です。</span><span class="sxs-lookup"><span data-stu-id="3338c-118">General classification for the response code.</span></span> <span data-ttu-id="3338c-119">分類は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3338c-119">Classifications include:</span></span> <br/>  <span data-ttu-id="3338c-120">1-情報の応答</span><span class="sxs-lookup"><span data-stu-id="3338c-120">1 - Informational Responses</span></span> <br/>  <span data-ttu-id="3338c-121">2-正常に応答</span><span class="sxs-lookup"><span data-stu-id="3338c-121">2 - Successful Responses</span></span> <br/>  <span data-ttu-id="3338c-122">3-リダイレクト応答</span><span class="sxs-lookup"><span data-stu-id="3338c-122">3 - Redirection Responses</span></span> <br/>  <span data-ttu-id="3338c-123">4-クライアントのエラーへの応答</span><span class="sxs-lookup"><span data-stu-id="3338c-123">4 - Client Failure Responses</span></span> <br/>  <span data-ttu-id="3338c-124">5 - サーバー エラー応答</span><span class="sxs-lookup"><span data-stu-id="3338c-124">5 -- Server Failure Responses</span></span> <br/>  <span data-ttu-id="3338c-125">6-グローバル エラーの応答</span><span class="sxs-lookup"><span data-stu-id="3338c-125">6 - Global Failure Response</span></span> <br/> |
|<span data-ttu-id="3338c-126">**説明**</span><span class="sxs-lookup"><span data-stu-id="3338c-126">**Description**</span></span> <br/> |<span data-ttu-id="3338c-127">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="3338c-127">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="3338c-128">SIP 応答コードの説明です。</span><span class="sxs-lookup"><span data-stu-id="3338c-128">Description of the SIP response code.</span></span> <span data-ttu-id="3338c-129">たとえば、181 の応答コードには、次の説明があります。</span><span class="sxs-lookup"><span data-stu-id="3338c-129">For example, response code 181 has the following description:</span></span>  <br/> <span data-ttu-id="3338c-130">呼び出しが転送されます。</span><span class="sxs-lookup"><span data-stu-id="3338c-130">Call Is Being Forwarded</span></span>  <br/> |
   

