---
title: Skype for Business Server 2015 の Gateways テーブル
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
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: Gateways テーブルはサポート テーブルです。 各レコードには、データベース内にレコードがある公衆交換電話網 (PSTN) 通話に関係する 1 つのゲートウェイに関する情報が格納されます。
ms.openlocfilehash: e945e5464093eb0eb58965fa1ef8a734ea0afa75
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821587"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a><span data-ttu-id="7e66a-104">Skype for Business Server 2015 の Gateways テーブル</span><span class="sxs-lookup"><span data-stu-id="7e66a-104">Gateways table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="7e66a-105">Gateways テーブルはサポート テーブルです。</span><span class="sxs-lookup"><span data-stu-id="7e66a-105">The Gateways table is a supporting table.</span></span> <span data-ttu-id="7e66a-106">各レコードには、データベース内にレコードがある公衆交換電話網 (PSTN) 通話に関係する 1 つのゲートウェイに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="7e66a-106">Each record stores information about one gateway that is involved in public switched telephone network (PSTN) calls that have records in the database.</span></span>
  
|<span data-ttu-id="7e66a-107">**列**</span><span class="sxs-lookup"><span data-stu-id="7e66a-107">**Column**</span></span>|<span data-ttu-id="7e66a-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="7e66a-108">**Data Type**</span></span>|<span data-ttu-id="7e66a-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="7e66a-109">**Key/Index**</span></span>|<span data-ttu-id="7e66a-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="7e66a-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7e66a-111">**GatewayId**</span><span class="sxs-lookup"><span data-stu-id="7e66a-111">**GatewayId**</span></span> <br/> |<span data-ttu-id="7e66a-112">int</span><span class="sxs-lookup"><span data-stu-id="7e66a-112">int</span></span>  <br/> |<span data-ttu-id="7e66a-113">Primary</span><span class="sxs-lookup"><span data-stu-id="7e66a-113">Primary</span></span>  <br/> |<span data-ttu-id="7e66a-114">このゲートウェイを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="7e66a-114">Unique number identifying this gateway.</span></span>  <br/> |
|<span data-ttu-id="7e66a-115">**ゲートウェイ**</span><span class="sxs-lookup"><span data-stu-id="7e66a-115">**Gateway**</span></span> <br/> |<span data-ttu-id="7e66a-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7e66a-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="7e66a-117">ゲートウェイ名。</span><span class="sxs-lookup"><span data-stu-id="7e66a-117">Gateway name.</span></span>  <br/> |
   

