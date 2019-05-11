---
title: ビジネス サーバー 2015 の Skype での HardwareVersions テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ca05582b-082c-4bab-9233-36fc9434dbca
description: HardwareVersions はテーブルをサポートします。 各レコードは、1 つのデバイスのハードウェアのバージョンに関する情報を格納します。
ms.openlocfilehash: 23da0f4a2f9ecbb230df8986dc39cc61db89e6b2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901137"
---
# <a name="hardwareversions-table-in-skype-for-business-server-2015"></a><span data-ttu-id="5baab-104">ビジネス サーバー 2015 の Skype での HardwareVersions テーブル</span><span class="sxs-lookup"><span data-stu-id="5baab-104">HardwareVersions table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="5baab-105">HardwareVersions はテーブルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="5baab-105">The HardwareVersions table is a supporting table.</span></span> <span data-ttu-id="5baab-106">各レコードは、1 つのデバイスのハードウェアのバージョンに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="5baab-106">Each record stores information about one device hardware version.</span></span>
  
|<span data-ttu-id="5baab-107">**列**</span><span class="sxs-lookup"><span data-stu-id="5baab-107">**Column**</span></span>|<span data-ttu-id="5baab-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="5baab-108">**Data Type**</span></span>|<span data-ttu-id="5baab-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="5baab-109">**Key/Index**</span></span>|<span data-ttu-id="5baab-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="5baab-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5baab-111">**バージョン Id**</span><span class="sxs-lookup"><span data-stu-id="5baab-111">**VersionId**</span></span> <br/> |<span data-ttu-id="5baab-112">int</span><span class="sxs-lookup"><span data-stu-id="5baab-112">int</span></span>  <br/> |<span data-ttu-id="5baab-113">Primary</span><span class="sxs-lookup"><span data-stu-id="5baab-113">Primary</span></span>  <br/> |<span data-ttu-id="5baab-114">このハードウェアのバージョンを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="5baab-114">Unique number identifying this hardware version.</span></span>  <br/> |
|<span data-ttu-id="5baab-115">**バージョン**</span><span class="sxs-lookup"><span data-stu-id="5baab-115">**Version**</span></span> <br/> |<span data-ttu-id="5baab-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="5baab-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="5baab-117">ハードウェアのバージョンです。</span><span class="sxs-lookup"><span data-stu-id="5baab-117">Hardware version.</span></span>  <br/> |
   

