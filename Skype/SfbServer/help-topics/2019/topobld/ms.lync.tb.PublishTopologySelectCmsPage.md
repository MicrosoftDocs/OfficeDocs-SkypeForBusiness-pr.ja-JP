---
title: トポロジの公開での CMS の選択ページ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PublishTopologySelectCmsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df447066-2840-431b-bc4e-acf8aa692d71
ROBOTS: NOINDEX, NOFOLLOW
description: トポロジ ビルダーを使用して構成したトポロジを公開します。 フロント エンド サーバーまたはフロント エンド プールは、中央管理ストアを保持しているの役割を仮定したリストから選択するように求められます。 フロント エンド サーバーまたはフロント エンド プールを 1 つだけでは、任意の時点で、この役割を保持できます。
ms.openlocfilehash: e649629650bfa1fe168698984e3e8b0aaa5d2df4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33888759"
---
# <a name="publish-topology-select-cms-page"></a><span data-ttu-id="02794-105">トポロジの公開での CMS の選択ページ</span><span class="sxs-lookup"><span data-stu-id="02794-105">Publish Topology Select CMS Page</span></span>
 
<span data-ttu-id="02794-106">トポロジ ビルダーを使用して構成したトポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="02794-106">You publish the topology that you have configured using Topology Builder.</span></span> <span data-ttu-id="02794-107">フロント エンド サーバーまたはフロント エンド プールは、中央管理ストアを保持しているの役割を仮定したリストから選択するように求められます。</span><span class="sxs-lookup"><span data-stu-id="02794-107">You are asked to select from a list which Front End Server or Front End pool will assume the role of holding the Central Management store.</span></span> <span data-ttu-id="02794-108">フロント エンド サーバーまたはフロント エンド プールを 1 つだけでは、任意の時点で、この役割を保持できます。</span><span class="sxs-lookup"><span data-stu-id="02794-108">Only one Front End Server or Front End pool can hold this role at any given time.</span></span> 
  
### <a name="about-the-central-management-server"></a><span data-ttu-id="02794-109">サーバーの全体管理サーバーについて</span><span class="sxs-lookup"><span data-stu-id="02794-109">About the Central Management Server</span></span>
<span data-ttu-id="02794-110">サーバーの全体管理サーバーは、マスターまたは複数の単一のレプリカのシステムでは、中央管理サーバーが含まれるフロント エンド サーバーでデータベースの読み取り/書き込みコピーを保持する場所。</span><span class="sxs-lookup"><span data-stu-id="02794-110">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="02794-111">中央の管理サーバーを含むフロント エンド サーバーを含め、トポロジ内の各コンピューターには、中央管理ストア内のデータのセットアップ中にコンピューターにインストールされている SQL Server データベース (既定では RTCLOCAL という名前) の読み取り専用コピーし、展開します。</span><span class="sxs-lookup"><span data-stu-id="02794-111">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="02794-112">ローカル データベースは、すべてのコンピューターでサービスとして実行される Lync Server レプリカ レプリケーター エージェントを使用してレプリカの更新を受信します。</span><span class="sxs-lookup"><span data-stu-id="02794-112">The local database receives replica updates by way of the Lync Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="02794-113">中央管理サーバーとローカルのレプリカには、実際のデータベースの名前は、XDS で、xds.mdf および xds.ldf ファイルの構成です。</span><span class="sxs-lookup"><span data-stu-id="02794-113">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="02794-114">Master データベースの場所は、Active Directory ドメイン サービスでサービス コントロール ポイント (SCP) によって参照されます。</span><span class="sxs-lookup"><span data-stu-id="02794-114">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="02794-115">中央管理サーバーを使用して管理し、Lync Server を構成するすべてのツールでは、SCP を使用して、中央管理ストアを探します。</span><span class="sxs-lookup"><span data-stu-id="02794-115">All tools that use the Central Management Server to manage and configure Lync Server use the SCP to locate the Central Management store.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="02794-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="02794-116">See also</span></span>

[<span data-ttu-id="02794-117">移動 CsManagementServer</span><span class="sxs-lookup"><span data-stu-id="02794-117">Move-CsManagementServer</span></span>](https://docs.microsoft.com/powershell/module/skype/move-csmanagementserver?view=skype-ps)
