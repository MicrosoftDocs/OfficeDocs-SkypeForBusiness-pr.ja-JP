---
title: 通話品質ダッシュボード (CQD) の建物マップを作成する
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: 通話品質ダッシュボード (CQD) でテナントのアップロードとデータの作成に使用できる建物マップを作成する方法について学習します。
ms.openlocfilehash: 890e5e9b394cf8b600e635014c90ebb9053a1e07
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "46584036"
---
# <a name="create-a-building-map-for-call-quality-dashboard-cqd"></a><span data-ttu-id="bf91d-103">通話品質ダッシュボード (CQD) の建物マップを作成する</span><span class="sxs-lookup"><span data-stu-id="bf91d-103">Create a building map for Call Quality Dashboard (CQD)</span></span>

<span data-ttu-id="bf91d-104">Microsoft Teamsまたは Skype for Business Online のデプロイでは、すべてのクライアントが外部です。</span><span class="sxs-lookup"><span data-stu-id="bf91d-104">In a Microsoft Teams or Skype for Business Online deployment, all clients are external.</span></span> <span data-ttu-id="bf91d-105">その結果、既定では、クライアントが社内ネットワークに接続されているかどうかに関係なく、すべてのクライアントが通話品質ダッシュボード (CQD) で外部として報告されます。</span><span class="sxs-lookup"><span data-stu-id="bf91d-105">As a result, by default, all clients are reported as outside in Call Quality Dashboard (CQD), regardless of whether the client is connected on an internal corporate network.</span></span>

<span data-ttu-id="bf91d-106">CQD を使用する場合は、エンドポイントの場所と、エンドポイントが管理できるネットワークに接続されたのか、管理できないネットワークに接続されたのかを把握する必要があります。これは、管理できるネットワークのみを改善できるという前提です。</span><span class="sxs-lookup"><span data-stu-id="bf91d-106">When you work with CQD, you need to know the location of an endpoint and whether it was connected to a network you can manage or a network you can't manage, the assumption being that you can only improve networks you can manage.</span></span> <span data-ttu-id="bf91d-107">サブネットをアップロードし、CQD に情報を構築することで、CQD を有効にして、エンドポイントが内部 (管理された) ネットワークに接続されたのか、外部 (管理されていない) ネットワークに接続されたのかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="bf91d-107">By uploading subnet and building information to CQD, you enable CQD to determine whether the endpoint was connected to an internal (managed) network or to an external (unmanaged) network.</span></span> <span data-ttu-id="bf91d-108">このため、組織の建物マップを作成し [、CQD にアップロードすることが重要です](CQD-upload-tenant-building-data.md)。</span><span class="sxs-lookup"><span data-stu-id="bf91d-108">That's why it's important to create a building map for your organization and [upload it to CQD](CQD-upload-tenant-building-data.md).</span></span>

## <a name="building-mapping-tools"></a><span data-ttu-id="bf91d-109">マッピング ツールの構築</span><span class="sxs-lookup"><span data-stu-id="bf91d-109">Building mapping tools</span></span>

<span data-ttu-id="bf91d-110">組織のサブネットをマップする方法は多数あります。</span><span class="sxs-lookup"><span data-stu-id="bf91d-110">There are many ways to map your organization's subnets.</span></span> <span data-ttu-id="bf91d-111">ヘルプが必要な場合は、このブログ投稿で説明されている CQDTools PowerShell モジュール [を使用できます](https://aka.ms/cqdtools)。</span><span class="sxs-lookup"><span data-stu-id="bf91d-111">If you need help, you can use the CQDTools PowerShell Module described in this [blog post](https://aka.ms/cqdtools).</span></span> <span data-ttu-id="bf91d-112">これらのツールは PowerShell に基づいており、Active Directory (AD) のサイトとサービスと Microsoft DHCP サービスを使用して、建物のファイルを事前に設定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="bf91d-112">These tools are based on PowerShell and use Active Directory (AD) Sites and Services and Microsoft DHCP services to help pre-populate your building file.</span></span> <span data-ttu-id="bf91d-113">これらのツールは、次のタスクに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="bf91d-113">These tools will help with the following tasks:</span></span>

1. <span data-ttu-id="bf91d-114">サイトADサービスにクエリを実行し、に含まれる情報に基づいて建物ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="bf91d-114">Query AD Sites and Services, and create a building file based on the information contained within.</span></span>
1. <span data-ttu-id="bf91d-115">Microsoft DHCP サーバーまたはサーバーにクエリを実行してサブネット情報を取得し、建物ファイルを自動的に作成します。</span><span class="sxs-lookup"><span data-stu-id="bf91d-115">Query a Microsoft DHCP server or servers to pull subnet information and automatically create a building file.</span></span>
1. <span data-ttu-id="bf91d-116">既存の建物ファイルを検証し、重複と重複をチェックします。</span><span class="sxs-lookup"><span data-stu-id="bf91d-116">Validate an existing building file, checking for duplicates and overlaps.</span></span>
1. <span data-ttu-id="bf91d-117">CQD で、未作成のサブネットを検索します。</span><span class="sxs-lookup"><span data-stu-id="bf91d-117">Find unmapped subnets in CQD.</span></span>

## <a name="related-topics"></a><span data-ttu-id="bf91d-118">関連トピック</span><span class="sxs-lookup"><span data-stu-id="bf91d-118">Related topics</span></span>

[<span data-ttu-id="bf91d-119">アップロードを作成し、CQD でデータを構築する</span><span class="sxs-lookup"><span data-stu-id="bf91d-119">Upload tenant and building data in CQD</span></span>](CQD-upload-tenant-building-data.md)