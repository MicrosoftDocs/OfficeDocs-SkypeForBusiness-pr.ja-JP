---
title: トポロジの公開での CMS の選択ページ
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PublishTopologySelectCmsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df447066-2840-431b-bc4e-acf8aa692d71
ROBOTS: NOINDEX, NOFOLLOW
description: トポロジ ビルダーを使用して構成したトポロジを公開します。 中央管理ストアを保持する役割を担うフロント エンド サーバーまたはフロントエンド プールを一覧から選択する必要があります。 このロールを保持できるフロントエンド サーバーまたはフロントエンド プールは 1 つのみです。
ms.openlocfilehash: d4af4756dc42c54790ee1120b418eb5e6a349387
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822187"
---
# <a name="publish-topology-select-cms-page"></a><span data-ttu-id="9d87c-105">トポロジの公開での CMS の選択ページ</span><span class="sxs-lookup"><span data-stu-id="9d87c-105">Publish Topology Select CMS Page</span></span>
 
<span data-ttu-id="9d87c-106">トポロジ ビルダーを使用して構成したトポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="9d87c-106">You publish the topology that you have configured using Topology Builder.</span></span> <span data-ttu-id="9d87c-107">中央管理ストアを保持する役割を担うフロント エンド サーバーまたはフロントエンド プールを一覧から選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d87c-107">You are asked to select from a list which Front End Server or Front End pool will assume the role of holding the Central Management store.</span></span> <span data-ttu-id="9d87c-108">このロールを保持できるフロントエンド サーバーまたはフロントエンド プールは 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="9d87c-108">Only one Front End Server or Front End pool can hold this role at any given time.</span></span> 
  
### <a name="about-the-central-management-server"></a><span data-ttu-id="9d87c-109">中央管理サーバーについて</span><span class="sxs-lookup"><span data-stu-id="9d87c-109">About the Central Management Server</span></span>
<span data-ttu-id="9d87c-110">中央管理サーバーは単一のマスター/複数レプリカ システムで、データベースの読み取り/書き込みコピーは、中央管理サーバーを含むフロントエンド サーバーによって保持されます。</span><span class="sxs-lookup"><span data-stu-id="9d87c-110">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="9d87c-111">中央管理サーバーを含むフロントエンド サーバーを含むトポロジ内の各コンピューターには、セットアップおよび展開時に、コンピューターにインストールされた SQL Server データベース (既定では RTCLOCAL という名前) の中央管理ストア データの読み取り専用コピーがあります。</span><span class="sxs-lookup"><span data-stu-id="9d87c-111">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="9d87c-112">ローカル データベースは、すべてのコンピューターでサービスとして実行される Lync Server レプリカ レプリケーター エージェントを使用してレプリカの更新を受信します。</span><span class="sxs-lookup"><span data-stu-id="9d87c-112">The local database receives replica updates by way of the Lync Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="9d87c-113">中央管理サーバーとローカル レプリカ上の実際のデータベースの名前は、xds.mdf ファイルと xds.ldf ファイルで構成される XDS です。</span><span class="sxs-lookup"><span data-stu-id="9d87c-113">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="9d87c-114">マスター データベースの場所は、Active Directory ドメイン サービスのサービス コントロール ポイント (SCP) によって参照されます。</span><span class="sxs-lookup"><span data-stu-id="9d87c-114">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="9d87c-115">中央管理サーバーを使用して Lync Server を管理および構成するツールはすべて、SCP を使用して中央管理ストアを検索します。</span><span class="sxs-lookup"><span data-stu-id="9d87c-115">All tools that use the Central Management Server to manage and configure Lync Server use the SCP to locate the Central Management store.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9d87c-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="9d87c-116">See also</span></span>

[<span data-ttu-id="9d87c-117">Move-CsManagementServer</span><span class="sxs-lookup"><span data-stu-id="9d87c-117">Move-CsManagementServer</span></span>](https://docs.microsoft.com/powershell/module/skype/move-csmanagementserver?view=skype-ps)
