---
title: 従来のアーカイブ サーバーおよび監視サーバーの削除
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
description: 従来の展開にアーカイブサーバーまたは監視サーバーが含まれていた場合、Skype for Business Server 2019 に移行した後は、これらのサーバーを従来の環境から削除できます。すべてのユーザーが残りの従来のプールから削除されています。 アーカイブ サーバーまたは監視サーバーはどのような順序で削除してもかまいません。 残りのレガシ プールからすべてのユーザーが削除されていることが重要な要件です。
ms.openlocfilehash: f5f4da7f7ebf5772bc930d1f92ea3feb590465fd
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752169"
---
# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="f0fd4-105">従来のアーカイブ サーバーおよび監視サーバーの削除</span><span class="sxs-lookup"><span data-stu-id="f0fd4-105">Remove legacy Archiving and Monitoring servers</span></span>

<span data-ttu-id="f0fd4-106">従来の展開にアーカイブサーバーまたは監視サーバーが含まれていた場合、Skype for Business Server 2019 に移行した後は、これらのサーバーを従来の環境から削除できます。これにより、すべてのユーザーが残りの従来のプールから削除されています。</span><span class="sxs-lookup"><span data-stu-id="f0fd4-106">If your legacy deployment contained an Archiving Server or a Monitoring Server, after migrating to Skype for Business Server 2019, those servers can be removed from the legacy environment, provided all users have been removed from any remaining legacy pools.</span></span> <span data-ttu-id="f0fd4-107">アーカイブ サーバーまたは監視サーバーはどのような順序で削除してもかまいません。</span><span class="sxs-lookup"><span data-stu-id="f0fd4-107">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="f0fd4-108">残りのレガシ プールからすべてのユーザーが削除されていることが重要な要件です。</span><span class="sxs-lookup"><span data-stu-id="f0fd4-108">The key requirement is that all users have been removed from any remaining legacy pools.</span></span>
  
<span data-ttu-id="f0fd4-109">[「フェーズ 4: テストユーザーをパイロットプールに移動](phase-4-move-test-users-to-the-pilot-pool.md)する」で説明されている手順に従って、ユーザーを Skype For business Server 2019 に移動できます。</span><span class="sxs-lookup"><span data-stu-id="f0fd4-109">You can move users to Skype for Business Server 2019 by following the procedures outlined in [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
<span data-ttu-id="f0fd4-110">すべてのユーザーが残りのプールから削除されたことを確認した後、サーバーを decommision し、役割を削除します。</span><span class="sxs-lookup"><span data-stu-id="f0fd4-110">After you have confirmed that all users have been removed from any remaining pools, decommision the server and remove roles.</span></span> <span data-ttu-id="f0fd4-111">日付に関連するものの、「Microsoft Lync Server をアンインストールしてサーバーの役割を削除する」の例は、にダウンロードでき [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227) ます。</span><span class="sxs-lookup"><span data-stu-id="f0fd4-111">A dated, but relevant, example is "Uninstalling Microsoft Lync Server and Removing Server Roles," which can be downloaded at [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span>
  

