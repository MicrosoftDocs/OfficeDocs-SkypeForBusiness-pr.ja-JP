---
title: 移行のプロセス
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype for Business Server 2019 の推奨およびサポートされている移行手順は、並行して移行されます。 このトピックでは、サイドバイサイド移行を使用する必要がある理由と、共存テストに関する情報も含まれている理由について説明します。
ms.openlocfilehash: 6ef8a70aa436663b7ff88723800375eeef620b6d
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237780"
---
# <a name="migration-process"></a><span data-ttu-id="179a5-104">移行のプロセス</span><span class="sxs-lookup"><span data-stu-id="179a5-104">Migration process</span></span>

<span data-ttu-id="179a5-105">Skype for Business Server 2019 の推奨およびサポートされている移行手順は、並行して移行されます。</span><span class="sxs-lookup"><span data-stu-id="179a5-105">The recommended and supported migration procedure for Skype for Business Server 2019 is side-by-side migration.</span></span> <span data-ttu-id="179a5-106">このトピックでは、サイドバイサイド移行を使用する必要がある理由と、共存テストに関する情報も含まれている理由について説明します。</span><span class="sxs-lookup"><span data-stu-id="179a5-106">This topic describes why you should use side-by-side migration and also includes information about coexistence testing.</span></span>
  
## <a name="side-by-side-migration"></a><span data-ttu-id="179a5-107">サイドバイサイド移行</span><span class="sxs-lookup"><span data-stu-id="179a5-107">Side-By-Side Migration</span></span>

<span data-ttu-id="179a5-108">ほぼすべての移行では、並列移行パスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="179a5-108">In nearly every migration, you should use the side-by-side migration path.</span></span> <span data-ttu-id="179a5-109">並行して移行する場合は、以前のバージョンを実行しているサーバーと共に、Skype for Business Server 2019 と共に新しいサーバーを展開してから、新しいサーバーに操作を転送します。</span><span class="sxs-lookup"><span data-stu-id="179a5-109">In a side-by-side migration, you deploy a new server with Skype for Business Server 2019 alongside a corresponding server that is running a previous version, and then transfer operations to the new server.</span></span> <span data-ttu-id="179a5-110">以前のバージョンにロールバックする必要がある場合は、元のサーバーに戻す操作のみを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="179a5-110">If it becomes necessary to roll back to the previous version, you have only to shift operations back to the original servers.</span></span> <span data-ttu-id="179a5-111">この状況では、アップグレードされたクライアントによってスケジュールされた新しい会議が機能しなくなり、クライアントもダウングレードされる必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="179a5-111">Be aware that in this situation any new meetings scheduled with upgraded clients will not work, and the clients would also need to be downgraded.</span></span>
  
## <a name="coexistence-testing"></a><span data-ttu-id="179a5-112">共存テスト</span><span class="sxs-lookup"><span data-stu-id="179a5-112">Coexistence Testing</span></span>

<span data-ttu-id="179a5-113">以前のバージョンと並行して Skype for Business Server 2019 を展開した後、展開は、Skype for Business Server 2019 と以前のバージョンの共存テストの状態を表します。</span><span class="sxs-lookup"><span data-stu-id="179a5-113">After you have deployed Skype for Business Server 2019 in parallel with the previous version, the deployment represents a coexistence testing state of Skype for Business Server 2019 and the previous version.</span></span> <span data-ttu-id="179a5-114">この状態では、サービスが開始されていること、各サイトが管理可能であること、クライアントが現在のユーザーと従来のユーザーと通信できることをテストして確認することが重要です。</span><span class="sxs-lookup"><span data-stu-id="179a5-114">While in this state, it is important to test and ensure that services are started, each site can be administered, and clients can communicate with current and legacy users.</span></span> <span data-ttu-id="179a5-115">すべてのユーザーを移行する前に、展開の状態を理解し、各展開が正常に機能して動作していることを確認することが非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="179a5-115">Prior to the migration of all users, it is very important that you understand the state of each deployment and ensure that each deployment is functional and working properly.</span></span> <span data-ttu-id="179a5-116">通常、共存テストのフェーズは、Skype for Business Server 2019 のパイロットテストを通じて行われます。</span><span class="sxs-lookup"><span data-stu-id="179a5-116">Typically, the coexistence testing phase exists throughout the pilot testing of Skype for Business Server 2019.</span></span> <span data-ttu-id="179a5-117">従来のユーザーは、アプリケーションの互換性と機能が正しく動作していることを確認するため、Skype for Business Server 2019 に一定の期間移動されます。</span><span class="sxs-lookup"><span data-stu-id="179a5-117">Legacy users are moved to Skype for Business Server 2019 for a period of time to ensure that application compatibility and features and functions are working properly.</span></span> <span data-ttu-id="179a5-118">パイロットテストの後、ユーザーとアプリケーションは、Skype for Business Server 2019 の運用バージョンに移行され、以前のバージョンの従来のプールとアプリケーションは廃止されます。</span><span class="sxs-lookup"><span data-stu-id="179a5-118">After pilot testing, users and applications are moved to the production version of Skype for Business Server 2019, and the legacy pools and applications of the previous version are retired.</span></span>
  
