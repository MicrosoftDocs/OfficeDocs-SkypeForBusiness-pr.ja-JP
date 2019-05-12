---
title: ビジネス サーバー 2015 の Skype での DeRegisterType テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: DeRegisterType テーブルは、可能性のあるユーザーの一覧を格納する静的なテーブルが 'クライアントの開始'、'登録の期限が切れて' 'クライアントが応答を停止して' などの種類を登録解除
ms.openlocfilehash: 958de5dd537f391ca75936ad86a84cb6fed0778d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901174"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="37b7a-103">ビジネス サーバー 2015 の Skype での DeRegisterType テーブル</span><span class="sxs-lookup"><span data-stu-id="37b7a-103">DeRegisterType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="37b7a-104">DeRegisterType テーブルは、可能性のあるユーザーの一覧を格納する静的なテーブルが 'クライアントの開始'、'登録の期限が切れて' 'クライアントが応答を停止して' などの種類を登録解除</span><span class="sxs-lookup"><span data-stu-id="37b7a-104">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as 'client initiated', 'registration expired', or 'client stopped responding.'</span></span>
  
|<span data-ttu-id="37b7a-105">**列**</span><span class="sxs-lookup"><span data-stu-id="37b7a-105">**Column**</span></span>|<span data-ttu-id="37b7a-106">**データ型**</span><span class="sxs-lookup"><span data-stu-id="37b7a-106">**Data Type**</span></span>|<span data-ttu-id="37b7a-107">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="37b7a-107">**Key/Index**</span></span>|<span data-ttu-id="37b7a-108">**詳細**</span><span class="sxs-lookup"><span data-stu-id="37b7a-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="37b7a-109">**DeRegisterTypeId**</span><span class="sxs-lookup"><span data-stu-id="37b7a-109">**DeRegisterTypeId**</span></span> <br/> |<span data-ttu-id="37b7a-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="37b7a-110">tinyint</span></span>  <br/> |<span data-ttu-id="37b7a-111">Primary</span><span class="sxs-lookup"><span data-stu-id="37b7a-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="37b7a-112">**DeRegisterReason**</span><span class="sxs-lookup"><span data-stu-id="37b7a-112">**DeRegisterReason**</span></span> <br/> |<span data-ttu-id="37b7a-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="37b7a-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="37b7a-114">使用可能な値:</span><span class="sxs-lookup"><span data-stu-id="37b7a-114">Allowed values:</span></span> <br/>  <span data-ttu-id="37b7a-115">0 - 不明</span><span class="sxs-lookup"><span data-stu-id="37b7a-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="37b7a-116">1--クライアント開始の登録解除します。</span><span class="sxs-lookup"><span data-stu-id="37b7a-116">1 -- Client Initiated Deregistration</span></span> <br/>  <span data-ttu-id="37b7a-117">2-登録の有効期限が切れてください。</span><span class="sxs-lookup"><span data-stu-id="37b7a-117">2 -- Registration Expired</span></span> <br/>  <span data-ttu-id="37b7a-118">3-クライアントがクラッシュしました。</span><span class="sxs-lookup"><span data-stu-id="37b7a-118">3 - Client crashed</span></span> <br/>  <span data-ttu-id="37b7a-119">4--ユーザー属性の変更</span><span class="sxs-lookup"><span data-stu-id="37b7a-119">4 -- User Attributes Changed</span></span> <br/>  <span data-ttu-id="37b7a-120">5-優先レジストラーの変更</span><span class="sxs-lookup"><span data-stu-id="37b7a-120">5 - Preferred Registrar Changed</span></span> <br/>  <span data-ttu-id="37b7a-121">サバイバル モードでの 6 - レガシ クライアント</span><span class="sxs-lookup"><span data-stu-id="37b7a-121">6 -- Legacy Client In Survival Mode</span></span> <br/> |
   

