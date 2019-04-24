---
title: 移行のプロセス
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ビジネス サーバー 2019 の Skype の推奨およびサポートされている移行手順は、サイド バイ サイドの移行です。 サイド バイ サイド移行を使用する必要があり、共存のテストに関する情報も含まれます理由について説明します。
ms.openlocfilehash: e14226721cbc09bd1f0ac66b47dbd1710712eb17
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231617"
---
# <a name="migration-process"></a><span data-ttu-id="db737-104">移行のプロセス</span><span class="sxs-lookup"><span data-stu-id="db737-104">Migration process</span></span>

<span data-ttu-id="db737-105">ビジネス サーバー 2019 の Skype の推奨およびサポートされている移行手順は、サイド バイ サイドの移行です。</span><span class="sxs-lookup"><span data-stu-id="db737-105">The recommended and supported migration procedure for Skype for Business Server 2019 is side-by-side migration.</span></span> <span data-ttu-id="db737-106">サイド バイ サイド移行を使用する必要があり、共存のテストに関する情報も含まれます理由について説明します。</span><span class="sxs-lookup"><span data-stu-id="db737-106">This topic describes why you should use side-by-side migration and also includes information about coexistence testing.</span></span>
  
## <a name="side-by-side-migration"></a><span data-ttu-id="db737-107">サイド バイ サイド移行</span><span class="sxs-lookup"><span data-stu-id="db737-107">Side-By-Side Migration</span></span>

<span data-ttu-id="db737-108">ほぼすべての移行では、サイド バイ サイド移行パスを使用してください。</span><span class="sxs-lookup"><span data-stu-id="db737-108">In nearly every migration, you should use the side-by-side migration path.</span></span> <span data-ttu-id="db737-109">サイド バイ サイドの移行では、対応する以前のバージョンを実行しているサーバーと共にビジネス サーバー 2019 の Skype での新しいサーバーを展開し、操作を新しいサーバーに転送します。</span><span class="sxs-lookup"><span data-stu-id="db737-109">In a side-by-side migration, you deploy a new server with Skype for Business Server 2019 alongside a corresponding server that is running a previous version, and then transfer operations to the new server.</span></span> <span data-ttu-id="db737-110">以前のバージョンにロールバックするために必要になると、する必要があるだけの操作を元のサーバーに移動します。</span><span class="sxs-lookup"><span data-stu-id="db737-110">If it becomes necessary to roll back to the previous version, you have only to shift operations back to the original servers.</span></span> <span data-ttu-id="db737-111">なるこのような状況でアップグレードしたクライアントでスケジュールされたすべての新しい会議ができない場合、クライアントをダウン グレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="db737-111">Be aware that in this situation any new meetings scheduled with upgraded clients will not work, and the clients would also need to be downgraded.</span></span>
  
## <a name="coexistence-testing"></a><span data-ttu-id="db737-112">共存テスト</span><span class="sxs-lookup"><span data-stu-id="db737-112">Coexistence Testing</span></span>

<span data-ttu-id="db737-113">ビジネス サーバー 2019 の以前のバージョンと並行して、Skype を配置した後、展開は、ビジネス サーバー 2019 と以前のバージョンの Skype の状態をテストの共存を表します。</span><span class="sxs-lookup"><span data-stu-id="db737-113">After you have deployed Skype for Business Server 2019 in parallel with the previous version, the deployment represents a coexistence testing state of Skype for Business Server 2019 and the previous version.</span></span> <span data-ttu-id="db737-114">この状態では、することが重要をテストし、サービスを開始し、各サイトを管理するには、クライアントが現在とレガシーのユーザーと通信できます。</span><span class="sxs-lookup"><span data-stu-id="db737-114">While in this state, it is important to test and ensure that services are started, each site can be administered, and clients can communicate with current and legacy users.</span></span> <span data-ttu-id="db737-115">、すべてのユーザーの移行前は、それぞれの展開の状態を確認し、ことを確認してそれぞれの展開機能および動作して正しくするには非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="db737-115">Prior to the migration of all users, it is very important that you understand the state of each deployment and ensure that each deployment is functional and working properly.</span></span> <span data-ttu-id="db737-116">通常、テスト フェーズの共存は、ビジネス サーバー 2019 の Skype のパイロット テスト全体にわたって存在します。</span><span class="sxs-lookup"><span data-stu-id="db737-116">Typically, the coexistence testing phase exists throughout the pilot testing of Skype for Business Server 2019.</span></span> <span data-ttu-id="db737-117">従来のユーザーに移動 Skype ビジネス サーバー 2019 の一定期間のアプリケーションの互換性を確保して機能、関数が正常に動作します。</span><span class="sxs-lookup"><span data-stu-id="db737-117">Legacy users are moved to Skype for Business Server 2019 for a period of time to ensure that application compatibility and features and functions are working properly.</span></span> <span data-ttu-id="db737-118">パイロット テストの結果、ユーザーおよびアプリケーションは、生産のバージョンのビジネス サーバー 2019、Skype と従来のプールに移動し、以前のバージョンのアプリケーションが使用されなきます。</span><span class="sxs-lookup"><span data-stu-id="db737-118">After pilot testing, users and applications are moved to the production version of Skype for Business Server 2019, and the legacy pools and applications of the previous version are retired.</span></span>
  
