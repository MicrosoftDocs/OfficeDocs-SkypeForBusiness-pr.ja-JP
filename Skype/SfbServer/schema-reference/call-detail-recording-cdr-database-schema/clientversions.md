---
title: Skype for Business Server 2015 の ClientVersions テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: ClientVersions テーブルは、データベースに記録されているセッションに参加しているさまざまなクライアントの種類とバージョンの一覧を格納するサポートテーブルです。 テーブル内の各レコードは、1つのクライアントバージョンを表します。
ms.openlocfilehash: b42bc79fb04ca4ce2ef88fb7c280db7bc281e23b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296512"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a><span data-ttu-id="cacc4-104">Skype for Business Server 2015 の ClientVersions テーブル</span><span class="sxs-lookup"><span data-stu-id="cacc4-104">ClientVersions table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="cacc4-105">ClientVersions テーブルは、データベースに記録されているセッションに参加しているさまざまなクライアントの種類とバージョンの一覧を格納するサポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="cacc4-105">The ClientVersions table is a supporting table that stores a list of the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="cacc4-106">テーブル内の各レコードは、1つのクライアントバージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="cacc4-106">Each record in the table represents one client version.</span></span>
  
|<span data-ttu-id="cacc4-107">**列**</span><span class="sxs-lookup"><span data-stu-id="cacc4-107">**Column**</span></span>|<span data-ttu-id="cacc4-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="cacc4-108">**Data Type**</span></span>|<span data-ttu-id="cacc4-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="cacc4-109">**Key/Index**</span></span>|<span data-ttu-id="cacc4-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="cacc4-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cacc4-111">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="cacc4-111">**VersionId**</span></span> <br/> |<span data-ttu-id="cacc4-112">**int**</span><span class="sxs-lookup"><span data-stu-id="cacc4-112">**int**</span></span> <br/> |<span data-ttu-id="cacc4-113">Primary</span><span class="sxs-lookup"><span data-stu-id="cacc4-113">Primary</span></span>  <br/> |<span data-ttu-id="cacc4-114">このクライアントの種類とバージョンを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="cacc4-114">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="cacc4-115">**バージョン**</span><span class="sxs-lookup"><span data-stu-id="cacc4-115">**Version**</span></span> <br/> |<span data-ttu-id="cacc4-116">**nvarchar(256)**</span><span class="sxs-lookup"><span data-stu-id="cacc4-116">**nvarchar(256)**</span></span> <br/> ||<span data-ttu-id="cacc4-117">バージョン名。</span><span class="sxs-lookup"><span data-stu-id="cacc4-117">Version name.</span></span>  <br/> |
|<span data-ttu-id="cacc4-118">**ClientType**</span><span class="sxs-lookup"><span data-stu-id="cacc4-118">**ClientType**</span></span> <br/> |<span data-ttu-id="cacc4-119">int</span><span class="sxs-lookup"><span data-stu-id="cacc4-119">int</span></span>  <br/> ||<span data-ttu-id="cacc4-120">セッションで使用するクライアントの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="cacc4-120">Specifies the type of client used in the session.</span></span> <span data-ttu-id="cacc4-121">詳細については、 [Useragentdef テーブル](useragentdef.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cacc4-121">See the [UserAgentDef table](useragentdef.md) for more information.</span></span> <br/> <span data-ttu-id="cacc4-122">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="cacc4-122">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

