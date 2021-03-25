---
title: フェーズ 8 レガシ プールの使用停止
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: httpsfix
description: 次のトピックでは、DNS エントリの更新、コンテンツ管理サーバーの移動、プールの使用停止、従来の展開からのサーバーとプールの非アクティブ化と削除に関するガイダンスを提供します。 このセクションに記載された手順をすべて実行する必要はありません。 ドキュメントを読んで、どの使用停止の手順を実行すればよいかを判断してください。
ms.openlocfilehash: b1080c68e3b4075ce92aaef497854855135dc47d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113243"
---
# <a name="phase-8-decommission-legacy-pools"></a><span data-ttu-id="8b05f-105">フェーズ 8: レガシ プールの使用停止</span><span class="sxs-lookup"><span data-stu-id="8b05f-105">Phase 8: Decommission legacy pools</span></span>

<span data-ttu-id="8b05f-106">次のトピックでは、DNS エントリの更新、コンテンツ管理サーバーの移動、プールの使用停止、従来の展開からのサーバーとプールの非アクティブ化と削除に関するガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="8b05f-106">The following topic provides guidance for updating DNS entries, moving the Content Management Server, decommissioning pools, and deactivating and removing servers and pools from a legacy deployment.</span></span> <span data-ttu-id="8b05f-107">このセクションに記載された手順をすべて実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="8b05f-107">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="8b05f-108">ドキュメントを読んで、どの使用停止の手順を実行すればよいかを判断してください。</span><span class="sxs-lookup"><span data-stu-id="8b05f-108">Read the documentation and determine which decommissioning procedure to use.</span></span> 
  
<span data-ttu-id="8b05f-109">サーバーとサーバーの役割の削除に関する日付が付いたが網羅的な記事、および展開の使用停止に関する詳細なガイドについては [、「Microsoft Lync Server](https://go.microsoft.com/fwlink/p/?linkId=246227)のアンインストール」と「サーバーの役割の削除」をダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="8b05f-109">For a dated but exhaustive article on removing servers and server roles, and a step-by-step guide to decommissioning a deployment, download [Uninstalling Microsoft Lync Server and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="8b05f-110">従来の環境を使用停止する前に、Microsoft Unified Communications Managed API (UCMA) アプリケーションの移行とアップグレードの詳細については [、「UCMA](/previous-versions/office/jj728782(v=office.15))アプリケーション: 共存、移行、およびアップグレードのシナリオ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b05f-110">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, before decommissioning your legacy environment, see [UCMA applications: Coexistence, migration, and upgrade scenarios](/previous-versions/office/jj728782(v=office.15)).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="8b05f-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="8b05f-111">In this section</span></span>

> [<span data-ttu-id="8b05f-112">DNS SRV レコードの更新</span><span class="sxs-lookup"><span data-stu-id="8b05f-112">Update DNS SRV records</span></span>](update-dns-srv-records.md)
> 
> [<span data-ttu-id="8b05f-113">従来のインストールのサーバーの全体管理サーバーを Skype for Business Server 2019 に移動する</span><span class="sxs-lookup"><span data-stu-id="8b05f-113">Move the legacy install Central Management Server to Skype for Business Server 2019</span></span>](move-the-central-management-server.md)
> 
> [<span data-ttu-id="8b05f-114">会議ディレクトリの移動</span><span class="sxs-lookup"><span data-stu-id="8b05f-114">Move Conference Directories</span></span>](move-conference-directories.md)
> 
> [<span data-ttu-id="8b05f-115">アーカイブ サーバーの関連付けの削除</span><span class="sxs-lookup"><span data-stu-id="8b05f-115">Remove the Archiving server association</span></span>](remove-the-archiving-server-association.md)
> 
> [<span data-ttu-id="8b05f-116">監視サーバーの関連付けの削除</span><span class="sxs-lookup"><span data-stu-id="8b05f-116">Remove the Monitoring server association</span></span>](remove-the-monitoring-server-association.md)
> 
> [<span data-ttu-id="8b05f-117">Enterprise Edition フロントエンド サーバーまたは Standard Edition フロントエンド サーバーを削除する</span><span class="sxs-lookup"><span data-stu-id="8b05f-117">Remove the Enterprise Edition Front End Server or Standard Edition Front End Server</span></span>](remove-the-front-end-server.md)
> 
> [<span data-ttu-id="8b05f-118">バックエンド サーバー上の SQL Server インスタンスとデータベースの削除</span><span class="sxs-lookup"><span data-stu-id="8b05f-118">Remove SQL Server instances and databases on the Back End Server</span></span>](remove-sql-server-instances-and-databases-on-the-back-end-server.md)
