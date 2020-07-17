---
title: 移行のプロセス
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
description: Skype for Business Server 2019 の推奨およびサポートされている移行手順は、並行して移行されます。 このトピックでは、サイド バイ サイド移行を使用する理由について説明し、共存のテストに関する情報も示します。
ms.openlocfilehash: 2343e3d6dd7eadbcfbf2b900d51594253e22f933
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752639"
---
# <a name="migration-process"></a><span data-ttu-id="c640f-104">移行のプロセス</span><span class="sxs-lookup"><span data-stu-id="c640f-104">Migration process</span></span>

<span data-ttu-id="c640f-105">Skype for Business Server 2019 の推奨およびサポートされている移行手順は、並行して移行されます。</span><span class="sxs-lookup"><span data-stu-id="c640f-105">The recommended and supported migration procedure for Skype for Business Server 2019 is side-by-side migration.</span></span> <span data-ttu-id="c640f-106">このトピックでは、サイド バイ サイド移行を使用する理由について説明し、共存のテストに関する情報も示します。</span><span class="sxs-lookup"><span data-stu-id="c640f-106">This topic describes why you should use side-by-side migration and also includes information about coexistence testing.</span></span>
  
## <a name="side-by-side-migration"></a><span data-ttu-id="c640f-107">サイド バイ サイド移行</span><span class="sxs-lookup"><span data-stu-id="c640f-107">Side-By-Side Migration</span></span>

<span data-ttu-id="c640f-108">ほとんどすべての移行では、サイド バイ サイド移行パスの使用をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c640f-108">In nearly every migration, you should use the side-by-side migration path.</span></span> <span data-ttu-id="c640f-109">Side-by-side 移行では、以前のバージョンを実行している対応するサーバーと共に、Skype for Business Server 2019 と共に新しいサーバーを展開し、新しいサーバーに操作を転送します。</span><span class="sxs-lookup"><span data-stu-id="c640f-109">In a side-by-side migration, you deploy a new server with Skype for Business Server 2019 alongside a corresponding server that is running a previous version, and then transfer operations to the new server.</span></span> <span data-ttu-id="c640f-110">以前のバージョンにロールバックする必要が生じた場合は、元のサーバーに戻す操作のみを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c640f-110">If it becomes necessary to roll back to the previous version, you have only to shift operations back to the original servers.</span></span> <span data-ttu-id="c640f-111">ただし、この状況では、アップグレードされたクライアントによって新しい会議がスケジュールされていた場合、それらの会議がすべて機能しなくなるのでクライアントのダウングレードも必要になります。</span><span class="sxs-lookup"><span data-stu-id="c640f-111">Be aware that in this situation any new meetings scheduled with upgraded clients will not work, and the clients would also need to be downgraded.</span></span>
  
## <a name="coexistence-testing"></a><span data-ttu-id="c640f-112">共存のテスト</span><span class="sxs-lookup"><span data-stu-id="c640f-112">Coexistence Testing</span></span>

<span data-ttu-id="c640f-113">以前のバージョンと並行して Skype for Business Server 2019 を展開した後、展開は、Skype for Business Server 2019 と以前のバージョンの共存テストの状態を表します。</span><span class="sxs-lookup"><span data-stu-id="c640f-113">After you have deployed Skype for Business Server 2019 in parallel with the previous version, the deployment represents a coexistence testing state of Skype for Business Server 2019 and the previous version.</span></span> <span data-ttu-id="c640f-114">この状態のときに、サービスが開始されていること、各サイトを管理できること、クライアントが現在および従来のユーザーと通信できることをテストして確認することが重要です。</span><span class="sxs-lookup"><span data-stu-id="c640f-114">While in this state, it is important to test and ensure that services are started, each site can be administered, and clients can communicate with current and legacy users.</span></span> <span data-ttu-id="c640f-115">すべてのユーザーを移行する前に、各展開の状態を把握し、各展開が適切に機能および動作することを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c640f-115">Prior to the migration of all users, it is very important that you understand the state of each deployment and ensure that each deployment is functional and working properly.</span></span> <span data-ttu-id="c640f-116">通常、Skype for Business Server 2019 のパイロットテストにおいて、共存のテスト段階が存在します。</span><span class="sxs-lookup"><span data-stu-id="c640f-116">Typically, the coexistence testing phase exists throughout the pilot testing of Skype for Business Server 2019.</span></span> <span data-ttu-id="c640f-117">従来のユーザーは、アプリケーションの互換性と機能が正しく動作していることを確認するために、長期間 Skype for Business Server 2019 に移動されます。</span><span class="sxs-lookup"><span data-stu-id="c640f-117">Legacy users are moved to Skype for Business Server 2019 for a period of time to ensure that application compatibility and features and functions are working properly.</span></span> <span data-ttu-id="c640f-118">パイロットテストの後、ユーザーとアプリケーションが Skype for Business Server 2019 の運用バージョンに移行され、以前のバージョンの従来のプールとアプリケーションは廃止されます。</span><span class="sxs-lookup"><span data-stu-id="c640f-118">After pilot testing, users and applications are moved to the production version of Skype for Business Server 2019, and the legacy pools and applications of the previous version are retired.</span></span>
  
