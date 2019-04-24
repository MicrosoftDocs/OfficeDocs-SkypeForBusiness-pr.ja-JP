---
title: フェーズ 8 の使用停止のレガシ プール
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: httpsfix
description: 次のトピックでは、DNS エントリを更新、コンテンツの管理サーバーを移動、プールを使用停止しの非アクティブ化および従来の展開からサーバーとプールを削除するためのガイダンスを提供します。 このセクションに記載されている手順の一部は、必要があります。 マニュアルを参照し、どの使用停止の手順を使用するを決定します。
ms.openlocfilehash: 2363b90f1bcc71c3c8c1ee42d258101240bcacb7
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231512"
---
# <a name="phase-8-decommission-legacy-pools"></a><span data-ttu-id="e0ef4-105">フェーズ 8: レガシ プールの使用停止</span><span class="sxs-lookup"><span data-stu-id="e0ef4-105">Phase 8: Decommission legacy pools</span></span>

<span data-ttu-id="e0ef4-106">次のトピックでは、DNS エントリを更新、コンテンツの管理サーバーを移動、プールを使用停止しの非アクティブ化および従来の展開からサーバーとプールを削除するためのガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="e0ef4-106">The following topic provides guidance for updating DNS entries, moving the Content Management Server, decommissioning pools, and deactivating and removing servers and pools from a legacy deployment.</span></span> <span data-ttu-id="e0ef4-107">このセクションに記載されている手順の一部は、必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0ef4-107">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="e0ef4-108">マニュアルを参照し、どの使用停止の手順を使用するを決定します。</span><span class="sxs-lookup"><span data-stu-id="e0ef4-108">Read the documentation and determine which decommissioning procedure to use.</span></span> 
  
<span data-ttu-id="e0ef4-109">サーバーとサーバーの役割、および展開を解除するのにはステップ バイ ステップ ガイドを削除する日付ですが、すべてを網羅した資料、 [Microsoft Lync Server をアンインストールしてサーバーの役割を削除すること](https://go.microsoft.com/fwlink/p/?linkId=246227)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="e0ef4-109">For a dated but exhaustive article on removing servers and server roles, and a step-by-step guide to decommissioning a deployment, download [Uninstalling Microsoft Lync Server and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="e0ef4-110">移行して、従来の環境の使用を停止する前に、マイクロソフト ユニファイド コミュニケーション管理 API (UCMA) アプリケーションをアップグレードする方法についてを参照してください[UCMA アプリケーション: 共存、移行、およびアップグレードのシナリオ](https://go.microsoft.com/fwlink/p/?LinkId=269555)。</span><span class="sxs-lookup"><span data-stu-id="e0ef4-110">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, before decommissioning your legacy environment, see [UCMA applications: Coexistence, migration, and upgrade scenarios](https://go.microsoft.com/fwlink/p/?LinkId=269555).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="e0ef4-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e0ef4-111">In this section</span></span>

> [<span data-ttu-id="e0ef4-112">DNS SRV レコードの更新</span><span class="sxs-lookup"><span data-stu-id="e0ef4-112">Update DNS SRV records</span></span>](update-dns-srv-records.md)
> 
> [<span data-ttu-id="e0ef4-113">ビジネス サーバー 2019 の Skype にレガシー インストールのサーバーの全体管理サーバーを移動します。</span><span class="sxs-lookup"><span data-stu-id="e0ef4-113">Move the legacy install Central Management Server to Skype for Business Server 2019</span></span>](move-the-central-management-server.md)
> 
> [<span data-ttu-id="e0ef4-114">会議ディレクトリの移動</span><span class="sxs-lookup"><span data-stu-id="e0ef4-114">Move Conference Directories</span></span>](move-conference-directories.md)
> 
> [<span data-ttu-id="e0ef4-115">アーカイブ サーバーの関連付けの削除</span><span class="sxs-lookup"><span data-stu-id="e0ef4-115">Remove the Archiving server association</span></span>](remove-the-archiving-server-association.md)
> 
> [<span data-ttu-id="e0ef4-116">監視サーバーの関連付けの削除</span><span class="sxs-lookup"><span data-stu-id="e0ef4-116">Remove the Monitoring server association</span></span>](remove-the-monitoring-server-association.md)
> 
> [<span data-ttu-id="e0ef4-117">エンタープライズ エディションのフロント エンド サーバーまたは Standard Edition フロント エンド サーバーを削除します。</span><span class="sxs-lookup"><span data-stu-id="e0ef4-117">Remove the Enterprise Edition Front End Server or Standard Edition Front End Server</span></span>](remove-the-front-end-server.md)
> 
> [<span data-ttu-id="e0ef4-118">バックエンド サーバー上の SQL Server インスタンスとデータベースの削除</span><span class="sxs-lookup"><span data-stu-id="e0ef4-118">Remove SQL Server instances and databases on the Back End Server</span></span>](remove-sql-server-instances-and-databases-on-the-back-end-server.md)
    

