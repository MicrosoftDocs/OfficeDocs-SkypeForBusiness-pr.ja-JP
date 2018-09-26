---
title: フェーズ 8 の使用停止のレガシ プール
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: httpsfix
description: 次のトピックでは、DNS エントリを更新、コンテンツの管理サーバーを移動、プールを使用停止しの非アクティブ化および従来の展開からサーバーとプールを削除するためのガイダンスを提供します。 このセクションに記載されている手順の一部は、必要があります。 マニュアルを参照し、どの使用停止の手順を使用するを決定します。
ms.openlocfilehash: ddad3714f18b79b5db6efd9421b46e481df81319
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "25029889"
---
# <a name="phase-8-decommission-legacy-pools"></a><span data-ttu-id="dcd1c-105">フェーズ 8: 従来のプールを使用停止します。</span><span class="sxs-lookup"><span data-stu-id="dcd1c-105">Phase 8: Decommission legacy pools</span></span>

<span data-ttu-id="dcd1c-106">次のトピックでは、DNS エントリを更新、コンテンツの管理サーバーを移動、プールを使用停止しの非アクティブ化および従来の展開からサーバーとプールを削除するためのガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="dcd1c-106">The following topic provides guidance for updating DNS entries, moving the Content Management Server, decommissioning pools, and deactivating and removing servers and pools from a legacy deployment.</span></span> <span data-ttu-id="dcd1c-107">このセクションに記載されている手順の一部は、必要があります。</span><span class="sxs-lookup"><span data-stu-id="dcd1c-107">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="dcd1c-108">マニュアルを参照し、どの使用停止の手順を使用するを決定します。</span><span class="sxs-lookup"><span data-stu-id="dcd1c-108">Read the documentation and determine which decommissioning procedure to use.</span></span> 
  
<span data-ttu-id="dcd1c-109">サーバーとサーバーの役割、および展開を解除するのにはステップ バイ ステップ ガイドを削除する日付ですが、すべてを網羅した資料、 [Microsoft Lync Server をアンインストールしてサーバーの役割を削除すること](https://go.microsoft.com/fwlink/p/?linkId=246227)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="dcd1c-109">For a dated but exhaustive article on removing servers and server roles, and a step-by-step guide to decommissioning a deployment, download [Uninstalling Microsoft Lync Server and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="dcd1c-110">移行して、従来の環境の使用を停止する前に、マイクロソフト ユニファイド コミュニケーション管理 API (UCMA) アプリケーションをアップグレードする方法についてを参照してください[UCMA アプリケーション: 共存、移行、およびアップグレードのシナリオ](https://go.microsoft.com/fwlink/p/?LinkId=269555)。</span><span class="sxs-lookup"><span data-stu-id="dcd1c-110">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, before decommissioning your legacy environment, see [UCMA applications: Coexistence, migration, and upgrade scenarios](https://go.microsoft.com/fwlink/p/?LinkId=269555).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="dcd1c-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="dcd1c-111">In this section</span></span>

> [<span data-ttu-id="dcd1c-112">DNS SRV レコードを更新します。</span><span class="sxs-lookup"><span data-stu-id="dcd1c-112">Update DNS SRV records</span></span>](update-dns-srv-records.md)
    
> [<span data-ttu-id="dcd1c-113">ビジネス サーバー 2019 の Skype にレガシー インストールのサーバーの全体管理サーバーを移動します。</span><span class="sxs-lookup"><span data-stu-id="dcd1c-113">Move the legacy install Central Management Server to Skype for Business Server 2019</span></span>](move-the-central-management-server.md)
    
> [<span data-ttu-id="dcd1c-114">会議ディレクトリを移動する</span><span class="sxs-lookup"><span data-stu-id="dcd1c-114">Move Conference Directories</span></span>](move-conference-directories.md)
    
> [<span data-ttu-id="dcd1c-115">アーカイブ サーバーの関連付けを削除します。</span><span class="sxs-lookup"><span data-stu-id="dcd1c-115">Remove the Archiving server association</span></span>](remove-the-archiving-server-association.md)
    
> [<span data-ttu-id="dcd1c-116">監視サーバーの関連付けを削除します。</span><span class="sxs-lookup"><span data-stu-id="dcd1c-116">Remove the Monitoring server association</span></span>](remove-the-monitoring-server-association.md)
    
> [<span data-ttu-id="dcd1c-117">エンタープライズ エディションのフロント エンド サーバーまたは Standard Edition フロント エンド サーバーを削除します。</span><span class="sxs-lookup"><span data-stu-id="dcd1c-117">Remove the Enterprise Edition Front End Server or Standard Edition Front End Server</span></span>](remove-the-front-end-server.md)
    
> [<span data-ttu-id="dcd1c-118">SQL Server のインスタンスおよびバック エンド サーバー上のデータベースを削除します。</span><span class="sxs-lookup"><span data-stu-id="dcd1c-118">Remove SQL Server instances and databases on the Back End Server</span></span>](remove-sql-server-instances-and-databases-on-the-back-end-server.md)
    

