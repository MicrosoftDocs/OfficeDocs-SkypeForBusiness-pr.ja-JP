---
title: ビジネス サーバー 2015 の Skype でゲートウェイ テーブル
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: ゲートウェイはテーブルをサポートします。 各レコードは、データベースにレコードがある公衆交換電話網 (PSTN) の呼び出しが関係している 1 つのゲートウェイに関する情報を格納します。
ms.openlocfilehash: e9592b227e8ccff6829748230abd3e8ddb8edb75
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a><span data-ttu-id="2a469-104">ビジネス サーバー 2015 の Skype でゲートウェイ テーブル</span><span class="sxs-lookup"><span data-stu-id="2a469-104">Gateways table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="2a469-105">ゲートウェイはテーブルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="2a469-105">The Gateways table is a supporting table.</span></span> <span data-ttu-id="2a469-106">各レコードは、データベースにレコードがある公衆交換電話網 (PSTN) の呼び出しが関係している 1 つのゲートウェイに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="2a469-106">Each record stores information about one gateway that is involved in public switched telephone network (PSTN) calls that have records in the database.</span></span>
  
|<span data-ttu-id="2a469-107">**列**</span><span class="sxs-lookup"><span data-stu-id="2a469-107">**Column**</span></span>|<span data-ttu-id="2a469-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="2a469-108">**Data Type**</span></span>|<span data-ttu-id="2a469-109">**キーまたはインデックス**</span><span class="sxs-lookup"><span data-stu-id="2a469-109">**Key/Index**</span></span>|<span data-ttu-id="2a469-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="2a469-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2a469-111">**GatewayId**</span><span class="sxs-lookup"><span data-stu-id="2a469-111">**GatewayId**</span></span> <br/> |<span data-ttu-id="2a469-112">int</span><span class="sxs-lookup"><span data-stu-id="2a469-112">int</span></span>  <br/> |<span data-ttu-id="2a469-113">Primary</span><span class="sxs-lookup"><span data-stu-id="2a469-113">Primary</span></span>  <br/> |<span data-ttu-id="2a469-114">このゲートウェイを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="2a469-114">Unique number identifying this gateway.</span></span>  <br/> |
|<span data-ttu-id="2a469-115">**ゲートウェイ**</span><span class="sxs-lookup"><span data-stu-id="2a469-115">**Gateway**</span></span> <br/> |<span data-ttu-id="2a469-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2a469-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="2a469-117">ゲートウェイの名前。</span><span class="sxs-lookup"><span data-stu-id="2a469-117">Gateway name.</span></span>  <br/> |
   

