---
title: ビジネス サーバー 2015 の Skype での ClientVersions テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: ClientVersions テーブルは、さまざまな種類のクライアントのリストを格納するサポート テーブルと、データベースに記録されているセッションに参加したバージョンです。 テーブル内の各レコードは、1 つのクライアント バージョンを表します。
ms.openlocfilehash: df80e907359297c9cdb518562fdeea54d31a2a47
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898530"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a><span data-ttu-id="5385a-104">ビジネス サーバー 2015 の Skype での ClientVersions テーブル</span><span class="sxs-lookup"><span data-stu-id="5385a-104">ClientVersions table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="5385a-105">ClientVersions テーブルは、さまざまな種類のクライアントのリストを格納するサポート テーブルと、データベースに記録されているセッションに参加したバージョンです。</span><span class="sxs-lookup"><span data-stu-id="5385a-105">The ClientVersions table is a supporting table that stores a list of the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="5385a-106">テーブル内の各レコードは、1 つのクライアント バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="5385a-106">Each record in the table represents one client version.</span></span>
  
|<span data-ttu-id="5385a-107">**列**</span><span class="sxs-lookup"><span data-stu-id="5385a-107">**Column**</span></span>|<span data-ttu-id="5385a-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="5385a-108">**Data Type**</span></span>|<span data-ttu-id="5385a-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="5385a-109">**Key/Index**</span></span>|<span data-ttu-id="5385a-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="5385a-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5385a-111">**バージョン Id**</span><span class="sxs-lookup"><span data-stu-id="5385a-111">**VersionId**</span></span> <br/> |<span data-ttu-id="5385a-112">**int**</span><span class="sxs-lookup"><span data-stu-id="5385a-112">**int**</span></span> <br/> |<span data-ttu-id="5385a-113">Primary</span><span class="sxs-lookup"><span data-stu-id="5385a-113">Primary</span></span>  <br/> |<span data-ttu-id="5385a-114">このクライアントの種類とバージョンを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="5385a-114">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="5385a-115">**バージョン**</span><span class="sxs-lookup"><span data-stu-id="5385a-115">**Version**</span></span> <br/> |<span data-ttu-id="5385a-116">**nvarchar(256)**</span><span class="sxs-lookup"><span data-stu-id="5385a-116">**nvarchar(256)**</span></span> <br/> ||<span data-ttu-id="5385a-117">バージョン名です。</span><span class="sxs-lookup"><span data-stu-id="5385a-117">Version name.</span></span>  <br/> |
|<span data-ttu-id="5385a-118">**顧客タイプ**</span><span class="sxs-lookup"><span data-stu-id="5385a-118">**ClientType**</span></span> <br/> |<span data-ttu-id="5385a-119">int</span><span class="sxs-lookup"><span data-stu-id="5385a-119">int</span></span>  <br/> ||<span data-ttu-id="5385a-120">セッションで使用されているクライアントの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="5385a-120">Specifies the type of client used in the session.</span></span> <span data-ttu-id="5385a-121">詳細については、 [UserAgentDef テーブル](useragentdef.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5385a-121">See the [UserAgentDef table](useragentdef.md) for more information.</span></span> <br/> <span data-ttu-id="5385a-122">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5385a-122">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

