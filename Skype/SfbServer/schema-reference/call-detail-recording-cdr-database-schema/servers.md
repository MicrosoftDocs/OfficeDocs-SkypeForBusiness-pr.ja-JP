---
title: Servers テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1535e676-a647-4606-bc56-e8bfde5ca823
description: サーバーのテーブルは、さまざまなサーバーに関する情報を格納するサポート テーブルです。 テーブル内の各レコードは、1 つのサーバーを表します。
ms.openlocfilehash: dca15b704badb5d2348f1380ea4752a629c05fae
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930554"
---
# <a name="servers-table"></a><span data-ttu-id="1b929-104">Servers テーブル</span><span class="sxs-lookup"><span data-stu-id="1b929-104">Servers table</span></span>
 
<span data-ttu-id="1b929-105">サーバーのテーブルは、さまざまなサーバーに関する情報を格納するサポート テーブルです。</span><span class="sxs-lookup"><span data-stu-id="1b929-105">The Servers table is a supporting table that stores information about the various servers.</span></span> <span data-ttu-id="1b929-106">テーブル内の各レコードは、1 つのサーバーを表します。</span><span class="sxs-lookup"><span data-stu-id="1b929-106">Each record in the table represents one server.</span></span>
  
|<span data-ttu-id="1b929-107">**列**</span><span class="sxs-lookup"><span data-stu-id="1b929-107">**Column**</span></span>|<span data-ttu-id="1b929-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="1b929-108">**Data Type**</span></span>|<span data-ttu-id="1b929-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="1b929-109">**Key/Index**</span></span>|<span data-ttu-id="1b929-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="1b929-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1b929-111">**ServerId**</span><span class="sxs-lookup"><span data-stu-id="1b929-111">**ServerId**</span></span> <br/> |<span data-ttu-id="1b929-112">int</span><span class="sxs-lookup"><span data-stu-id="1b929-112">int</span></span>  <br/> |<span data-ttu-id="1b929-113">Primary</span><span class="sxs-lookup"><span data-stu-id="1b929-113">Primary</span></span>  <br/> |<span data-ttu-id="1b929-114">このサーバーを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="1b929-114">Unique number identifying this server.</span></span>  <br/> |
|<span data-ttu-id="1b929-115">**ServerFQDN**</span><span class="sxs-lookup"><span data-stu-id="1b929-115">**ServerFQDN**</span></span> <br/> |<span data-ttu-id="1b929-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1b929-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="1b929-117">サーバーの FQDN です。</span><span class="sxs-lookup"><span data-stu-id="1b929-117">Server FQDN.</span></span>  <br/> |
   

