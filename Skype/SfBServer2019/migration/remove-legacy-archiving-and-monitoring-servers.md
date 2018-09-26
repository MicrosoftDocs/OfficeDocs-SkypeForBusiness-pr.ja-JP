---
title: 従来のアーカイブおよび監視サーバーを削除します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 場合は、従来の配置には、ビジネス サーバー 2019 の Skype に移行した後のアーカイブ サーバーまたは監視サーバーが含まれているの残りの従来のプールから削除されたすべてのユーザーに提供されるこれらのサーバーは、従来の環境から削除できます。 任意のシーケンスでは、アーカイブ サーバーまたは監視サーバーを削除できます。 重要な要件は、すべてのユーザーが、残りの従来のプールから削除されていることです。
ms.openlocfilehash: 4de6d9db5538864646f978e9fc33a79b39d4c2a4
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028615"
---
# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="3f719-105">従来のアーカイブおよび監視サーバーを削除します。</span><span class="sxs-lookup"><span data-stu-id="3f719-105">Remove legacy Archiving and Monitoring servers</span></span>

<span data-ttu-id="3f719-106">場合は、従来の配置には、ビジネス サーバー 2019 の Skype に移行した後のアーカイブ サーバーまたは監視サーバーが含まれている、それらのサーバーを従来の環境から削除、残りの従来のプールから削除されたすべてのユーザーに提供できます。</span><span class="sxs-lookup"><span data-stu-id="3f719-106">If your legacy deployment contained an Archiving Server or a Monitoring Server, after migrating to Skype for Business Server 2019, those servers can be removed from the legacy environment, provided all users have been removed from any remaining legacy pools.</span></span> <span data-ttu-id="3f719-107">任意のシーケンスでは、アーカイブ サーバーまたは監視サーバーを削除できます。</span><span class="sxs-lookup"><span data-stu-id="3f719-107">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="3f719-108">重要な要件は、すべてのユーザーが、残りの従来のプールから削除されていることです。</span><span class="sxs-lookup"><span data-stu-id="3f719-108">The key requirement is that all users have been removed from any remaining legacy pools.</span></span>
  
<span data-ttu-id="3f719-109">ビジネス サーバー 2019 に記載されている手順に従って、Skype にユーザーを移動できます[フェーズ 4: パイロット プールにテスト ユーザーの移動](phase-4-move-test-users-to-the-pilot-pool.md)。</span><span class="sxs-lookup"><span data-stu-id="3f719-109">You can move users to Skype for Business Server 2019 by following the procedures outlined in [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
<span data-ttu-id="3f719-110">した後は、すべてのユーザーは、残りのプール、decommision、サーバーから削除されているし、ロールの削除を確認しました。</span><span class="sxs-lookup"><span data-stu-id="3f719-110">After you have confirmed that all users have been removed from any remaining pools, decommision the server and remove roles.</span></span> <span data-ttu-id="3f719-111">A は、次の日、ですが、関連性の例は、「をアンインストールする Microsoft Lync サーバーとを削除するサーバーの役割」でダウンロードできる[https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227)。</span><span class="sxs-lookup"><span data-stu-id="3f719-111">A dated, but relevant, example is "Uninstalling Microsoft Lync Server and Removing Server Roles," which can be downloaded at [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span>
  

