---
title: フェーズ8の従来のプールの廃止
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: httpsfix
description: 次のトピックでは、DNS エントリの更新、コンテンツ管理サーバーの移動、プールの廃止、および従来の展開からのサーバーとプールの非アクティブ化と削除に関するガイダンスを示します。 このセクションに記載されているすべての手順を行う必要はありません。 ドキュメントを読み、使用する使用停止手順を確認します。
ms.openlocfilehash: 4110e45b2790204e96205dd9552e14fa9c359446
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34273876"
---
# <a name="phase-8-decommission-legacy-pools"></a><span data-ttu-id="124e8-105">フェーズ 8: レガシ プールの使用停止</span><span class="sxs-lookup"><span data-stu-id="124e8-105">Phase 8: Decommission legacy pools</span></span>

<span data-ttu-id="124e8-106">次のトピックでは、DNS エントリの更新、コンテンツ管理サーバーの移動、プールの廃止、および従来の展開からのサーバーとプールの非アクティブ化と削除に関するガイダンスを示します。</span><span class="sxs-lookup"><span data-stu-id="124e8-106">The following topic provides guidance for updating DNS entries, moving the Content Management Server, decommissioning pools, and deactivating and removing servers and pools from a legacy deployment.</span></span> <span data-ttu-id="124e8-107">このセクションに記載されているすべての手順を行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="124e8-107">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="124e8-108">ドキュメントを読み、使用する使用停止手順を確認します。</span><span class="sxs-lookup"><span data-stu-id="124e8-108">Read the documentation and determine which decommissioning procedure to use.</span></span> 
  
<span data-ttu-id="124e8-109">サーバーとサーバーの役割を削除する方法について説明していますが、展開を廃止するためのステップバイステップのガイドについては、「 [Microsoft Lync server をアンインストールして、サーバーの役割を削除](https://go.microsoft.com/fwlink/p/?linkId=246227)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="124e8-109">For a dated but exhaustive article on removing servers and server roles, and a step-by-step guide to decommissioning a deployment, download [Uninstalling Microsoft Lync Server and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="124e8-110">Microsoft ユニファイドコミュニケーションマネージ API (UCMA) アプリケーションの移行とアップグレードに関する情報については、従来の環境を廃止する前に、「 [ucma アプリケーション: 共存、移行、アップグレードのシナリオ](https://go.microsoft.com/fwlink/p/?LinkId=269555)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="124e8-110">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, before decommissioning your legacy environment, see [UCMA applications: Coexistence, migration, and upgrade scenarios](https://go.microsoft.com/fwlink/p/?LinkId=269555).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="124e8-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="124e8-111">In this section</span></span>

> [<span data-ttu-id="124e8-112">DNS SRV レコードの更新</span><span class="sxs-lookup"><span data-stu-id="124e8-112">Update DNS SRV records</span></span>](update-dns-srv-records.md)
> 
> [<span data-ttu-id="124e8-113">レガシインストールのセントラルマネジメントサーバーを Skype for Business Server 2019 に移動する</span><span class="sxs-lookup"><span data-stu-id="124e8-113">Move the legacy install Central Management Server to Skype for Business Server 2019</span></span>](move-the-central-management-server.md)
> 
> [<span data-ttu-id="124e8-114">会議ディレクトリの移動</span><span class="sxs-lookup"><span data-stu-id="124e8-114">Move Conference Directories</span></span>](move-conference-directories.md)
> 
> [<span data-ttu-id="124e8-115">アーカイブ サーバーの関連付けの削除</span><span class="sxs-lookup"><span data-stu-id="124e8-115">Remove the Archiving server association</span></span>](remove-the-archiving-server-association.md)
> 
> [<span data-ttu-id="124e8-116">監視サーバーの関連付けの削除</span><span class="sxs-lookup"><span data-stu-id="124e8-116">Remove the Monitoring server association</span></span>](remove-the-monitoring-server-association.md)
> 
> [<span data-ttu-id="124e8-117">Enterprise Edition フロントエンドサーバーまたは Standard Edition フロントエンドサーバーを削除する</span><span class="sxs-lookup"><span data-stu-id="124e8-117">Remove the Enterprise Edition Front End Server or Standard Edition Front End Server</span></span>](remove-the-front-end-server.md)
> 
> [<span data-ttu-id="124e8-118">バックエンド サーバー上の SQL Server インスタンスとデータベースの削除</span><span class="sxs-lookup"><span data-stu-id="124e8-118">Remove SQL Server instances and databases on the Back End Server</span></span>](remove-sql-server-instances-and-databases-on-the-back-end-server.md)
    

