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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: ClientVersions テーブルは、データベースに記録されているセッションに参加しているさまざまなクライアントの種類とバージョンの一覧を格納するサポートテーブルです。 テーブル内の各レコードは、1つのクライアントバージョンを表します。
ms.openlocfilehash: c616f7d44d138732e96f2d71c7fdf0197c75ca5c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815405"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a><span data-ttu-id="824bf-104">Skype for Business Server 2015 の ClientVersions テーブル</span><span class="sxs-lookup"><span data-stu-id="824bf-104">ClientVersions table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="824bf-105">ClientVersions テーブルは、データベースに記録されているセッションに参加しているさまざまなクライアントの種類とバージョンの一覧を格納するサポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="824bf-105">The ClientVersions table is a supporting table that stores a list of the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="824bf-106">テーブル内の各レコードは、1つのクライアントバージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="824bf-106">Each record in the table represents one client version.</span></span>
  
|<span data-ttu-id="824bf-107">**列**</span><span class="sxs-lookup"><span data-stu-id="824bf-107">**Column**</span></span>|<span data-ttu-id="824bf-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="824bf-108">**Data Type**</span></span>|<span data-ttu-id="824bf-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="824bf-109">**Key/Index**</span></span>|<span data-ttu-id="824bf-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="824bf-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="824bf-111">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="824bf-111">**VersionId**</span></span> <br/> |<span data-ttu-id="824bf-112">**int**</span><span class="sxs-lookup"><span data-stu-id="824bf-112">**int**</span></span> <br/> |<span data-ttu-id="824bf-113">Primary</span><span class="sxs-lookup"><span data-stu-id="824bf-113">Primary</span></span>  <br/> |<span data-ttu-id="824bf-114">このクライアントの種類とバージョンを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="824bf-114">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="824bf-115">**バージョン**</span><span class="sxs-lookup"><span data-stu-id="824bf-115">**Version**</span></span> <br/> |<span data-ttu-id="824bf-116">**nvarchar(256)**</span><span class="sxs-lookup"><span data-stu-id="824bf-116">**nvarchar(256)**</span></span> <br/> ||<span data-ttu-id="824bf-117">バージョン名。</span><span class="sxs-lookup"><span data-stu-id="824bf-117">Version name.</span></span>  <br/> |
|<span data-ttu-id="824bf-118">**ClientType**</span><span class="sxs-lookup"><span data-stu-id="824bf-118">**ClientType**</span></span> <br/> |<span data-ttu-id="824bf-119">int</span><span class="sxs-lookup"><span data-stu-id="824bf-119">int</span></span>  <br/> ||<span data-ttu-id="824bf-120">セッションで使用するクライアントの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="824bf-120">Specifies the type of client used in the session.</span></span> <span data-ttu-id="824bf-121">詳細については、 [Useragentdef テーブル](useragentdef.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="824bf-121">See the [UserAgentDef table](useragentdef.md) for more information.</span></span> <br/> <span data-ttu-id="824bf-122">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="824bf-122">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

