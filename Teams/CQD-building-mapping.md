---
title: 通話品質ダッシュボード (CQD) 用の建物マップを作成する
ms.author: lolaj
author: LolaJacobsen
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
description: 通話品質ダッシュボード (CQD) でテナントと建物のデータをアップロードするために使用できる構築マップを作成する方法について説明します。
ms.openlocfilehash: 18e88c2de64d2d63589a3cd2ebddbc9643fe4522
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086100"
---
# <a name="create-a-building-map-for-call-quality-dashboard-cqd"></a><span data-ttu-id="a7b27-103">通話品質ダッシュボード (CQD) 用の建物マップを作成する</span><span class="sxs-lookup"><span data-stu-id="a7b27-103">Create a building map for Call Quality Dashboard (CQD)</span></span>

<span data-ttu-id="a7b27-104">Microsoft Teams または Skype for Business Online の展開では、すべてのクライアントが外部になります。</span><span class="sxs-lookup"><span data-stu-id="a7b27-104">In a Microsoft Teams or Skype for Business Online deployment, all clients are external.</span></span> <span data-ttu-id="a7b27-105">この結果、既定では、クライアントが社内の企業ネットワークに接続されているかどうかに関係なく、すべてのクライアントが通話品質ダッシュボード (CQD) の外部として報告されます。</span><span class="sxs-lookup"><span data-stu-id="a7b27-105">As a result, by default, all clients are reported as outside in Call Quality Dashboard (CQD), regardless of whether the client is connected on an internal corporate network.</span></span>

<span data-ttu-id="a7b27-106">CQD を使用する場合は、エンドポイントの場所と、管理できないネットワークに接続されていたかどうかを把握しておく必要があります。そのためには、管理可能なネットワークのみを対象としていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="a7b27-106">When you work with CQD, you need to know the location of an endpoint and whether it was connected to a network you can manage or a network you can't manage, the assumption being that you can only improve networks you can manage.</span></span> <span data-ttu-id="a7b27-107">サブネットと建物の情報を CQD にアップロードすることによって、CQD は、エンドポイントが内部 (管理された) ネットワークに接続されているのか、外部の (管理されている) ネットワークに接続されているのかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="a7b27-107">By uploading subnet and building information to CQD, you enable CQD to determine whether the endpoint was connected to an internal (managed) network or to an external (unmanaged) network.</span></span> <span data-ttu-id="a7b27-108">そのため、組織の構築地図を作成し、 [CQD にアップロード](CQD-upload-tenant-building-data.md)することが重要です。</span><span class="sxs-lookup"><span data-stu-id="a7b27-108">That's why it's important to create a building map for your organization and [upload it to CQD](CQD-upload-tenant-building-data.md).</span></span>

## <a name="building-mapping-tools"></a><span data-ttu-id="a7b27-109">作成マッピングツール</span><span class="sxs-lookup"><span data-stu-id="a7b27-109">Building mapping tools</span></span>

<span data-ttu-id="a7b27-110">組織のサブネットをマッピングするには、さまざまな方法があります。</span><span class="sxs-lookup"><span data-stu-id="a7b27-110">There are many ways to map your organization's subnets.</span></span> <span data-ttu-id="a7b27-111">ヘルプが必要な場合は、この[ブログ投稿](https://aka.ms/cqdtools)で説明されている CQDTools PowerShell モジュールを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="a7b27-111">If you need help, you can use the CQDTools PowerShell Module described in this [blog post](https://aka.ms/cqdtools).</span></span> <span data-ttu-id="a7b27-112">これらのツールは、PowerShell に基づいており、Active Directory (AD) のサイトとサービス、および Microsoft DHCP サービスを使用して、作成したファイルを事前に作成するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a7b27-112">These tools are based on PowerShell and use Active Directory (AD) Sites and Services and Microsoft DHCP services to help pre-populate your building file.</span></span> <span data-ttu-id="a7b27-113">これらのツールは、次のタスクを実行するときに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a7b27-113">These tools will help with the following tasks:</span></span>

1. <span data-ttu-id="a7b27-114">広告サイトとサービスを照会し、その中に含まれている情報に基づいて建物ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="a7b27-114">Query AD Sites and Services, and create a building file based on the information contained within.</span></span>
1. <span data-ttu-id="a7b27-115">Microsoft DHCP サーバーまたはサーバーに照会して、サブネット情報を取得し、建物ファイルを自動的に作成します。</span><span class="sxs-lookup"><span data-stu-id="a7b27-115">Query a Microsoft DHCP server or servers to pull subnet information and automatically create a building file.</span></span>
1. <span data-ttu-id="a7b27-116">重複しているかどうかを確認し、既存の建物ファイルを検証します。</span><span class="sxs-lookup"><span data-stu-id="a7b27-116">Validate an existing building file, checking for duplicates and overlaps.</span></span>
1. <span data-ttu-id="a7b27-117">CQD でマッピングされていないサブネットを検索します。</span><span class="sxs-lookup"><span data-stu-id="a7b27-117">Find unmapped subnets in CQD.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a7b27-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="a7b27-118">Related topics</span></span>

[<span data-ttu-id="a7b27-119">CQD でテナントと建物データをアップロードする</span><span class="sxs-lookup"><span data-stu-id="a7b27-119">Upload tenant and building data in CQD</span></span>](CQD-upload-tenant-building-data.md)