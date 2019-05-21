---
title: 従来のアーカイブ サーバーおよび監視サーバーの削除
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 従来の展開にアーカイブサーバーまたは監視サーバーが含まれている場合、Skype for Business Server 2019 に移行した後、これらのサーバーは、すべてのユーザーが残っている従来のプールから削除された、従来の環境から削除することができます。 アーカイブサーバーまたは監視サーバーは、任意の順序で削除できます。 主要な要件は、すべてのユーザーが残っている従来のプールから削除されていることです。
ms.openlocfilehash: 918e04bb42853f0203ae8a2a56db5e640985af99
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34301126"
---
# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="ed470-105">従来のアーカイブ サーバーおよび監視サーバーの削除</span><span class="sxs-lookup"><span data-stu-id="ed470-105">Remove legacy Archiving and Monitoring servers</span></span>

<span data-ttu-id="ed470-106">従来の展開にアーカイブサーバーまたは監視サーバーが含まれている場合、Skype for Business Server 2019 に移行した後、これらのサーバーは従来の環境から削除できます。すべてのユーザーが残っている従来のプールから削除されています。</span><span class="sxs-lookup"><span data-stu-id="ed470-106">If your legacy deployment contained an Archiving Server or a Monitoring Server, after migrating to Skype for Business Server 2019, those servers can be removed from the legacy environment, provided all users have been removed from any remaining legacy pools.</span></span> <span data-ttu-id="ed470-107">アーカイブサーバーまたは監視サーバーは、任意の順序で削除できます。</span><span class="sxs-lookup"><span data-stu-id="ed470-107">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="ed470-108">主要な要件は、すべてのユーザーが残っている従来のプールから削除されていることです。</span><span class="sxs-lookup"><span data-stu-id="ed470-108">The key requirement is that all users have been removed from any remaining legacy pools.</span></span>
  
<span data-ttu-id="ed470-109">[「フェーズ 4: テストユーザーをパイロットプールに移動](phase-4-move-test-users-to-the-pilot-pool.md)する」で説明されている手順に従って、ユーザーを Skype For business Server 2019 に移動することができます。</span><span class="sxs-lookup"><span data-stu-id="ed470-109">You can move users to Skype for Business Server 2019 by following the procedures outlined in [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
<span data-ttu-id="ed470-110">すべてのユーザーが残りのプールから削除されたことを確認した後、サーバーを decommision し、役割を削除します。</span><span class="sxs-lookup"><span data-stu-id="ed470-110">After you have confirmed that all users have been removed from any remaining pools, decommision the server and remove roles.</span></span> <span data-ttu-id="ed470-111">意味のあるものの、"Microsoft Lync Server をアンインストールしてサーバーの役割を削除してい[https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227)ます" という例として、ダウンロード可能なものがあります。</span><span class="sxs-lookup"><span data-stu-id="ed470-111">A dated, but relevant, example is "Uninstalling Microsoft Lync Server and Removing Server Roles," which can be downloaded at [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span>
  

