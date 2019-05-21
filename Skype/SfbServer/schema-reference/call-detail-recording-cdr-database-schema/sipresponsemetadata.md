---
title: SIPResponseMetaData テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: SIPResponseMetaDataTable には、SIP 応答コードの一覧と、各コードの分類と定義が含まれています。 これらのコードは、SIP デバイスと SIP コミュニケーションセッションに影響を与えるイベントに対応して生成されます。たとえば、応答コード403は、SIP デバイスが要求を行ったときに、サーバーがその要求を受け入れることを拒否したときに生成されます。
ms.openlocfilehash: eecd8397315b93ebce9e5fad973f1274a6eb763a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295791"
---
# <a name="sipresponsemetadata-table"></a><span data-ttu-id="7745a-104">SIPResponseMetaData テーブル</span><span class="sxs-lookup"><span data-stu-id="7745a-104">SIPResponseMetaData table</span></span>
 
<span data-ttu-id="7745a-105">SIPResponseMetaDataTable には、SIP 応答コードの一覧と、各コードの分類と定義が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7745a-105">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes.</span></span> <span data-ttu-id="7745a-106">これらのコードは、SIP デバイスと SIP コミュニケーションセッションに影響を与えるイベントに対応して生成されます。たとえば、応答コード403は、SIP デバイスが要求を行ったときに、サーバーがその要求を受け入れることを拒否したときに生成されます。</span><span class="sxs-lookup"><span data-stu-id="7745a-106">These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>
  
<span data-ttu-id="7745a-107">この表は、Skype for Business Server 2015 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="7745a-107">This table was introduced in Skype for Business Server 2015.</span></span>
  
|<span data-ttu-id="7745a-108">**列**</span><span class="sxs-lookup"><span data-stu-id="7745a-108">**Column**</span></span>|<span data-ttu-id="7745a-109">**データ型**</span><span class="sxs-lookup"><span data-stu-id="7745a-109">**Data Type**</span></span>|<span data-ttu-id="7745a-110">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="7745a-110">**Key/Index**</span></span>|<span data-ttu-id="7745a-111">**詳細**</span><span class="sxs-lookup"><span data-stu-id="7745a-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7745a-112">**返信**</span><span class="sxs-lookup"><span data-stu-id="7745a-112">**ResponseCode**</span></span> <br/> |<span data-ttu-id="7745a-113">int</span><span class="sxs-lookup"><span data-stu-id="7745a-113">int</span></span>  <br/> |<span data-ttu-id="7745a-114">Primary</span><span class="sxs-lookup"><span data-stu-id="7745a-114">Primary</span></span>  <br/> |<span data-ttu-id="7745a-115">SIP 応答コードを表す数値。</span><span class="sxs-lookup"><span data-stu-id="7745a-115">Numeric value that represents the SIP response code.</span></span>  <br/> |
|<span data-ttu-id="7745a-116">**クラス**</span><span class="sxs-lookup"><span data-stu-id="7745a-116">**Class**</span></span> <br/> |<span data-ttu-id="7745a-117">int</span><span class="sxs-lookup"><span data-stu-id="7745a-117">int</span></span>  <br/> || <span data-ttu-id="7745a-118">応答コードの一般的な分類。</span><span class="sxs-lookup"><span data-stu-id="7745a-118">General classification for the response code.</span></span> <span data-ttu-id="7745a-119">分類には以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7745a-119">Classifications include:</span></span> <br/>  <span data-ttu-id="7745a-120">1-情報の返信</span><span class="sxs-lookup"><span data-stu-id="7745a-120">1 - Informational Responses</span></span> <br/>  <span data-ttu-id="7745a-121">2-成功応答</span><span class="sxs-lookup"><span data-stu-id="7745a-121">2 - Successful Responses</span></span> <br/>  <span data-ttu-id="7745a-122">3-リダイレクション応答</span><span class="sxs-lookup"><span data-stu-id="7745a-122">3 - Redirection Responses</span></span> <br/>  <span data-ttu-id="7745a-123">4-クライアントの失敗応答</span><span class="sxs-lookup"><span data-stu-id="7745a-123">4 - Client Failure Responses</span></span> <br/>  <span data-ttu-id="7745a-124">5--サーバー障害への応答</span><span class="sxs-lookup"><span data-stu-id="7745a-124">5 -- Server Failure Responses</span></span> <br/>  <span data-ttu-id="7745a-125">6-グローバルなエラー応答</span><span class="sxs-lookup"><span data-stu-id="7745a-125">6 - Global Failure Response</span></span> <br/> |
|<span data-ttu-id="7745a-126">**説明**</span><span class="sxs-lookup"><span data-stu-id="7745a-126">**Description**</span></span> <br/> |<span data-ttu-id="7745a-127">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7745a-127">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="7745a-128">SIP 応答コードの説明。</span><span class="sxs-lookup"><span data-stu-id="7745a-128">Description of the SIP response code.</span></span> <span data-ttu-id="7745a-129">たとえば、応答コード181には次の説明があります。</span><span class="sxs-lookup"><span data-stu-id="7745a-129">For example, response code 181 has the following description:</span></span>  <br/> <span data-ttu-id="7745a-130">通話が転送されています</span><span class="sxs-lookup"><span data-stu-id="7745a-130">Call Is Being Forwarded</span></span>  <br/> |
   

