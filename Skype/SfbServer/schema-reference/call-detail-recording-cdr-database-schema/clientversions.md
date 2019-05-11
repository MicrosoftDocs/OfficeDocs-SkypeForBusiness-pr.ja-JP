---
title: ビジネス サーバー 2015 の Skype での ClientVersions テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: ClientVersions テーブルは、さまざまな種類のクライアントのリストを格納するサポート テーブルと、データベースに記録されているセッションに参加したバージョンです。 テーブル内の各レコードは、1 つのクライアント バージョンを表します。
ms.openlocfilehash: 86711c89baf374576ee53c64a67688cde10103cc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901444"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a><span data-ttu-id="ca0aa-104">ビジネス サーバー 2015 の Skype での ClientVersions テーブル</span><span class="sxs-lookup"><span data-stu-id="ca0aa-104">ClientVersions table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ca0aa-105">ClientVersions テーブルは、さまざまな種類のクライアントのリストを格納するサポート テーブルと、データベースに記録されているセッションに参加したバージョンです。</span><span class="sxs-lookup"><span data-stu-id="ca0aa-105">The ClientVersions table is a supporting table that stores a list of the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="ca0aa-106">テーブル内の各レコードは、1 つのクライアント バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="ca0aa-106">Each record in the table represents one client version.</span></span>
  
|<span data-ttu-id="ca0aa-107">**列**</span><span class="sxs-lookup"><span data-stu-id="ca0aa-107">**Column**</span></span>|<span data-ttu-id="ca0aa-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="ca0aa-108">**Data Type**</span></span>|<span data-ttu-id="ca0aa-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="ca0aa-109">**Key/Index**</span></span>|<span data-ttu-id="ca0aa-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="ca0aa-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ca0aa-111">**バージョン Id**</span><span class="sxs-lookup"><span data-stu-id="ca0aa-111">**VersionId**</span></span> <br/> |<span data-ttu-id="ca0aa-112">**int**</span><span class="sxs-lookup"><span data-stu-id="ca0aa-112">**int**</span></span> <br/> |<span data-ttu-id="ca0aa-113">Primary</span><span class="sxs-lookup"><span data-stu-id="ca0aa-113">Primary</span></span>  <br/> |<span data-ttu-id="ca0aa-114">このクライアントの種類とバージョンを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="ca0aa-114">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="ca0aa-115">**バージョン**</span><span class="sxs-lookup"><span data-stu-id="ca0aa-115">**Version**</span></span> <br/> |<span data-ttu-id="ca0aa-116">**nvarchar(256)**</span><span class="sxs-lookup"><span data-stu-id="ca0aa-116">**nvarchar(256)**</span></span> <br/> ||<span data-ttu-id="ca0aa-117">バージョン名です。</span><span class="sxs-lookup"><span data-stu-id="ca0aa-117">Version name.</span></span>  <br/> |
|<span data-ttu-id="ca0aa-118">**顧客タイプ**</span><span class="sxs-lookup"><span data-stu-id="ca0aa-118">**ClientType**</span></span> <br/> |<span data-ttu-id="ca0aa-119">int</span><span class="sxs-lookup"><span data-stu-id="ca0aa-119">int</span></span>  <br/> ||<span data-ttu-id="ca0aa-120">セッションで使用されているクライアントの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="ca0aa-120">Specifies the type of client used in the session.</span></span> <span data-ttu-id="ca0aa-121">詳細については、 [UserAgentDef テーブル](useragentdef.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca0aa-121">See the [UserAgentDef table](useragentdef.md) for more information.</span></span> <br/> <span data-ttu-id="ca0aa-122">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ca0aa-122">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

