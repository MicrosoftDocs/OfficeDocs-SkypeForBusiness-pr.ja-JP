---
title: Skype for Business Server コントロール パネルの最初の実行チェックリスト
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.Home1stRunChkList
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d0c7306-e87e-464a-82ad-a5537f141500
description: Skype for Business Server コントロール パネル、Skype for Business Server の管理と管理のための Web ベースのユーザー インターフェイスへようこそ。 コントロール パネルを使用して、以前のリリースで Microsoft 管理コンソールを使用して実行された管理タスクの種類を実行できます。
ms.openlocfilehash: 262d2d16ad4922909ba08d9628c768e1d1443d12
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099773"
---
# <a name="first-run-checklist-for-skype-for-business-server-control-panel"></a><span data-ttu-id="283a0-104">Skype for Business Server コントロール パネルの最初の実行チェックリスト</span><span class="sxs-lookup"><span data-stu-id="283a0-104">First Run Checklist for Skype for Business Server Control Panel</span></span>

<span data-ttu-id="283a0-105">Skype for Business Server コントロール パネル、Skype for Business Server の管理と管理のための Web ベースのユーザー インターフェイスへようこそ。</span><span class="sxs-lookup"><span data-stu-id="283a0-105">Welcome to the Skype for Business Server Control Panel, the web-based user interface for administration and management of Skype for Business Server.</span></span> <span data-ttu-id="283a0-106">コントロール パネルを使用して、以前のリリースで Microsoft 管理コンソールを使用して実行された管理タスクの種類を実行できます。</span><span class="sxs-lookup"><span data-stu-id="283a0-106">You can use the control panel to perform the types of administrative tasks that were performed for by using the Microsoft Management Console in previous releases.</span></span>

<span data-ttu-id="283a0-107">Skype for Business Server を展開した後に実行することを強く推奨する重要なタスクが多数ある。</span><span class="sxs-lookup"><span data-stu-id="283a0-107">There are a number of important tasks that we strongly recommend you perform after you have deployed Skype for Business Server.</span></span> <span data-ttu-id="283a0-108">これらのタスクの一部は、展開中に既に実行されている可能性がある初期構成手順と、展開中または既定の設定で構成した設定の絞り込みまたは変更です。</span><span class="sxs-lookup"><span data-stu-id="283a0-108">Some of these tasks are initial configuration steps that you may have already performed during deployment, while others are refinements or modifications to settings that you configured during deployment or default settings.</span></span> <span data-ttu-id="283a0-109">このトピックで説明する他のタスクは、展開プロセス中に行った構成を検証します。</span><span class="sxs-lookup"><span data-stu-id="283a0-109">Other tasks described in this topic validate the configurations you made during the deployment process.</span></span>

> [!NOTE]
> <span data-ttu-id="283a0-110">次の表のタスクを実行する前に、役割ベースのアクセス制御トピックの「Role and Scope」セクションで説明されているとおり、正しいユーザー権限、アクセス許可[](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-role-based-access-control)、および役割を使用してログオンしてください。</span><span class="sxs-lookup"><span data-stu-id="283a0-110">Before performing the tasks in the following table, ensure that you log on using the correct user rights, permissions, and role as described in the "Roles and Scope" section of the [Role-Based Access Control](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-role-based-access-control) topic.</span></span>

## <a name="first-run-checklist"></a><span data-ttu-id="283a0-111">最初の実行チェックリスト</span><span class="sxs-lookup"><span data-stu-id="283a0-111">First Run Checklist</span></span>

<span data-ttu-id="283a0-112">このトピックで参照されているタスクを確認し、組織内の Lync Server 展開に適した手順を実行することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="283a0-112">We strongly recommend that you review the tasks referred to in this topic, and then perform the appropriate procedures for the Lync Server deployment in your organization.</span></span>

|<span data-ttu-id="283a0-113">**タスク**</span><span class="sxs-lookup"><span data-stu-id="283a0-113">**Task**</span></span>|<span data-ttu-id="283a0-114">**[コントロール パネル] グループ**</span><span class="sxs-lookup"><span data-stu-id="283a0-114">**Control Panel group**</span></span>|<span data-ttu-id="283a0-115">**ドキュメント**</span><span class="sxs-lookup"><span data-stu-id="283a0-115">**Documentation**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="283a0-116">トポロジにインストールしたサービスが期待通り実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="283a0-116">Verify the services that you installed in your topology are running as expected.</span></span>  <br/> |<span data-ttu-id="283a0-117">**トポロジ**</span><span class="sxs-lookup"><span data-stu-id="283a0-117">**Topology**</span></span> <br/> |[<span data-ttu-id="283a0-118">サービスに関する詳細の表示</span><span class="sxs-lookup"><span data-stu-id="283a0-118">View Details About a Service</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-view-details-about-a-service) <br/> |
|<span data-ttu-id="283a0-119">Skype for Business Server のユーザーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="283a0-119">Enable users for Skype for Business Server.</span></span> <span data-ttu-id="283a0-120">必要に応じて、以前のリリースから移行する場合は、Skype for Business Server にユーザーを移動します。</span><span class="sxs-lookup"><span data-stu-id="283a0-120">Optionally and, if migrating from a previous release, move users to Skype for Business Server.</span></span>  <br/> |<span data-ttu-id="283a0-121">**ユーザー**</span><span class="sxs-lookup"><span data-stu-id="283a0-121">**Users**</span></span> <br/> |[<span data-ttu-id="283a0-122">ユーザーの管理</span><span class="sxs-lookup"><span data-stu-id="283a0-122">Managing Users</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-user-accounts-enabled-for-lync-server) <br/> |
|<span data-ttu-id="283a0-123">展開または展開する場合はエンタープライズ VoIP公衆交換電話網 (PSTN) への接続を有効にするために SIP トランク接続を構成します。</span><span class="sxs-lookup"><span data-stu-id="283a0-123">If you deployed or want to deploy Enterprise Voice, configure a SIP trunk connection to enable connectivity to the public switched telephone network (PSTN).</span></span>  <br/> |<span data-ttu-id="283a0-124">**音声ルーティング**</span><span class="sxs-lookup"><span data-stu-id="283a0-124">**Voice Routing**</span></span> <br/> |[<span data-ttu-id="283a0-125">トランクと変換ルールの構成</span><span class="sxs-lookup"><span data-stu-id="283a0-125">Configuring Trunks and Translation Rules</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-trunks) <br/> |
|<span data-ttu-id="283a0-126">サーバーを展開したエンタープライズ VoIP、ルーティングエンタープライズ VoIP確認します。</span><span class="sxs-lookup"><span data-stu-id="283a0-126">If you deployed Enterprise Voice, verify Enterprise Voice routing settings.</span></span>  <br/> |<span data-ttu-id="283a0-127">**音声ルーティング**</span><span class="sxs-lookup"><span data-stu-id="283a0-127">**Voice Routing**</span></span> <br/> |[<span data-ttu-id="283a0-128">音声ルーティングのテスト</span><span class="sxs-lookup"><span data-stu-id="283a0-128">Test Voice Routing</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-test-voice-routing) <br/> |
|<span data-ttu-id="283a0-129">アーカイブ サーバーを展開した場合は、アーカイブ ポリシーと設定が組織のコンプライアンス ニーズを満たします。</span><span class="sxs-lookup"><span data-stu-id="283a0-129">If you deployed Archiving Server, verify that archiving policies and settings meet the compliance needs of your organization.</span></span>  <br/> |<span data-ttu-id="283a0-130">**監視およびアーカイブ**</span><span class="sxs-lookup"><span data-stu-id="283a0-130">**Monitoring and Archiving**</span></span> <br/> |[<span data-ttu-id="283a0-131">アーカイブの管理</span><span class="sxs-lookup"><span data-stu-id="283a0-131">Managing Archiving</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-managing-archiving) <br/> |
|<span data-ttu-id="283a0-132">監視サーバーを展開した場合は、監視サーバー レポートを表示して使用状況と診断情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="283a0-132">If you deployed Monitoring Server, view Monitoring Server reports to view usage and diagnostic information.</span></span>  <br/> |<span data-ttu-id="283a0-133">**ホーム**</span><span class="sxs-lookup"><span data-stu-id="283a0-133">**Home**</span></span> <br/> |[<span data-ttu-id="283a0-134">Skype for Business Server 2015 での正常性と監視の管理</span><span class="sxs-lookup"><span data-stu-id="283a0-134">Manage health and monitoring in Skype for Business Server 2015</span></span>](../../manage/health-and-monitoring/health-and-monitoring.md) <br/> |