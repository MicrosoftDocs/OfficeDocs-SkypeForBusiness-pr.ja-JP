---
title: トポロジの公開での CMS の選択ページ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.PublishTopologySelectCmsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df447066-2840-431b-bc4e-acf8aa692d71
ROBOTS: NOINDEX, NOFOLLOW
description: トポロジビルダーを使用して構成したトポロジを公開します。 フロントエンドサーバーまたはフロントエンドプールが、中央管理ストアを保持する役割を持つことを示すリストから選択するように求められます。 この役割は、1つのフロントエンドサーバーまたはフロントエンドプールでいつでも保持できます。
ms.openlocfilehash: 9cecdc170934f7359597484e56299e2fe76499b9
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41701672"
---
# <a name="publish-topology-select-cms-page"></a><span data-ttu-id="5cdea-105">トポロジの公開での CMS の選択ページ</span><span class="sxs-lookup"><span data-stu-id="5cdea-105">Publish Topology Select CMS Page</span></span>
 
<span data-ttu-id="5cdea-106">トポロジビルダーを使用して構成したトポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="5cdea-106">You publish the topology that you have configured using Topology Builder.</span></span> <span data-ttu-id="5cdea-107">フロントエンドサーバーまたはフロントエンドプールが、中央管理ストアを保持する役割を持つことを示すリストから選択するように求められます。</span><span class="sxs-lookup"><span data-stu-id="5cdea-107">You are asked to select from a list which Front End Server or Front End pool will assume the role of holding the Central Management store.</span></span> <span data-ttu-id="5cdea-108">この役割は、1つのフロントエンドサーバーまたはフロントエンドプールでいつでも保持できます。</span><span class="sxs-lookup"><span data-stu-id="5cdea-108">Only one Front End Server or Front End pool can hold this role at any given time.</span></span> 
  
### <a name="about-the-central-management-server"></a><span data-ttu-id="5cdea-109">サーバーの全体管理サーバーについて</span><span class="sxs-lookup"><span data-stu-id="5cdea-109">About the Central Management Server</span></span>
<span data-ttu-id="5cdea-110">サーバーの全体管理サーバーは、1つのマスター/マルチレプリカシステムです。このシステムでは、データベースの読み取り/書き込みのコピーが、中央管理サーバーを含むフロントエンドサーバーによって保持されています。</span><span class="sxs-lookup"><span data-stu-id="5cdea-110">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="5cdea-111">トポロジ内の各コンピューターには、サーバーを含むフロントエンドサーバーを含む、セットアップ時にコンピューターにインストールされた、SQL Server データベースの中央管理ストアデータの読み取り専用コピーがあります (既定では、RTCLOCAL という名前が付いています)。デプロイメント.</span><span class="sxs-lookup"><span data-stu-id="5cdea-111">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="5cdea-112">ローカルデータベースは、すべてのコンピューターでサービスとして実行される Lync Server Replica Replicator エージェントを介して、レプリカの更新を受信します。</span><span class="sxs-lookup"><span data-stu-id="5cdea-112">The local database receives replica updates by way of the Lync Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="5cdea-113">サーバーの全体管理サーバー上の実際のデータベースの名前とローカルレプリカは XDS で、これらは xds と xds のファイルで構成されます。</span><span class="sxs-lookup"><span data-stu-id="5cdea-113">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="5cdea-114">Master データベースの場所は、Active Directory ドメインサービスのサービスコントロールポイント (SCP) によって参照されます。</span><span class="sxs-lookup"><span data-stu-id="5cdea-114">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="5cdea-115">一元管理サーバーを使用して Lync Server を管理および構成するすべてのツール SCP を使用して、中央管理ストアを検索します。</span><span class="sxs-lookup"><span data-stu-id="5cdea-115">All tools that use the Central Management Server to manage and configure Lync Server use the SCP to locate the Central Management store.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5cdea-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="5cdea-116">See also</span></span>

[<span data-ttu-id="5cdea-117">CsManagementServer の移動</span><span class="sxs-lookup"><span data-stu-id="5cdea-117">Move-CsManagementServer</span></span>](https://docs.microsoft.com/powershell/module/skype/move-csmanagementserver?view=skype-ps)
