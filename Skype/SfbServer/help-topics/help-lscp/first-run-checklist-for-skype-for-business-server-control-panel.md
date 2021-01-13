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
description: Skype for Business Server の管理と管理のための Web ベースのユーザー インターフェイスである Skype for Business Server コントロール パネルへようこそ。 コントロール パネルを使用して、以前のリリースで Microsoft 管理コンソールを使用して実行された管理タスクの種類を実行できます。
ms.openlocfilehash: 74c1d4ae7b9ed65932acf5b8491a2cd00c67831c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804897"
---
# <a name="first-run-checklist-for-skype-for-business-server-control-panel"></a><span data-ttu-id="44815-104">Skype for Business Server コントロール パネルの最初の実行チェックリスト</span><span class="sxs-lookup"><span data-stu-id="44815-104">First Run Checklist for Skype for Business Server Control Panel</span></span>

<span data-ttu-id="44815-105">Skype for Business Server の管理と管理のための Web ベースのユーザー インターフェイスである Skype for Business Server コントロール パネルへようこそ。</span><span class="sxs-lookup"><span data-stu-id="44815-105">Welcome to the Skype for Business Server Control Panel, the web-based user interface for administration and management of Skype for Business Server.</span></span> <span data-ttu-id="44815-106">コントロール パネルを使用して、以前のリリースで Microsoft 管理コンソールを使用して実行された管理タスクの種類を実行できます。</span><span class="sxs-lookup"><span data-stu-id="44815-106">You can use the control panel to perform the types of administrative tasks that were performed for by using the Microsoft Management Console in previous releases.</span></span>

<span data-ttu-id="44815-107">Skype for Business Server を展開した後に実行することを強く推奨する重要なタスクが多数ある。</span><span class="sxs-lookup"><span data-stu-id="44815-107">There are a number of important tasks that we strongly recommend you perform after you have deployed Skype for Business Server.</span></span> <span data-ttu-id="44815-108">これらのタスクの一部は、展開時に既に実行した可能性がある初期構成手順と、展開または既定の設定中に構成した設定の絞り込みまたは変更です。</span><span class="sxs-lookup"><span data-stu-id="44815-108">Some of these tasks are initial configuration steps that you may have already performed during deployment, while others are refinements or modifications to settings that you configured during deployment or default settings.</span></span> <span data-ttu-id="44815-109">このトピックで説明する他のタスクは、展開プロセス中に行った構成を検証します。</span><span class="sxs-lookup"><span data-stu-id="44815-109">Other tasks described in this topic validate the configurations you made during the deployment process.</span></span>

> [!NOTE]
> <span data-ttu-id="44815-110">次の表のタスクを実行する前に、役割ベースのアクセス制御のトピックの「役割とスコープ」セクションで説明されているとおり、正しいユーザー権限、アクセス許可、[](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx)およびロールを使用してログオンしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="44815-110">Before performing the tasks in the following table, ensure that you log on using the correct user rights, permissions, and role as described in the "Roles and Scope" section of the [Role-Based Access Control](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) topic.</span></span>

## <a name="first-run-checklist"></a><span data-ttu-id="44815-111">最初の実行チェックリスト</span><span class="sxs-lookup"><span data-stu-id="44815-111">First Run Checklist</span></span>

<span data-ttu-id="44815-112">このトピックで参照するタスクを確認し、組織内の Lync Server 展開に適した手順を実行することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="44815-112">We strongly recommend that you review the tasks referred to in this topic, and then perform the appropriate procedures for the Lync Server deployment in your organization.</span></span>

|<span data-ttu-id="44815-113">**タスク**</span><span class="sxs-lookup"><span data-stu-id="44815-113">**Task**</span></span>|<span data-ttu-id="44815-114">**コントロール パネル グループ**</span><span class="sxs-lookup"><span data-stu-id="44815-114">**Control Panel group**</span></span>|<span data-ttu-id="44815-115">**ドキュメント**</span><span class="sxs-lookup"><span data-stu-id="44815-115">**Documentation**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="44815-116">トポロジにインストールしたサービスが期待通り実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="44815-116">Verify the services that you installed in your topology are running as expected.</span></span>  <br/> |<span data-ttu-id="44815-117">**トポロジ**</span><span class="sxs-lookup"><span data-stu-id="44815-117">**Topology**</span></span> <br/> |[<span data-ttu-id="44815-118">サービスに関する詳細の表示</span><span class="sxs-lookup"><span data-stu-id="44815-118">View Details About a Service</span></span>](https://technet.microsoft.com/library/bc8e8202-cd68-47e4-95b2-bb36e51cc124.aspx) <br/> |
|<span data-ttu-id="44815-119">Skype for Business Server のユーザーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="44815-119">Enable users for Skype for Business Server.</span></span> <span data-ttu-id="44815-120">オプションで、以前のリリースから移行する場合は、ユーザーを Skype for Business Server に移動します。</span><span class="sxs-lookup"><span data-stu-id="44815-120">Optionally and, if migrating from a previous release, move users to Skype for Business Server.</span></span>  <br/> |<span data-ttu-id="44815-121">**Users**</span><span class="sxs-lookup"><span data-stu-id="44815-121">**Users**</span></span> <br/> |[<span data-ttu-id="44815-122">ユーザーの管理</span><span class="sxs-lookup"><span data-stu-id="44815-122">Managing Users</span></span>](https://technet.microsoft.com/library/8021087e-5084-4a39-9fef-ab9376c6d371.aspx) <br/> |
|<span data-ttu-id="44815-123">パブリック 電話網 (PSTN) への接続を有効にエンタープライズ VoIP展開または展開する場合は、SIP トランク接続を構成します。</span><span class="sxs-lookup"><span data-stu-id="44815-123">If you deployed or want to deploy Enterprise Voice, configure a SIP trunk connection to enable connectivity to the public switched telephone network (PSTN).</span></span>  <br/> |<span data-ttu-id="44815-124">**音声ルーティング**</span><span class="sxs-lookup"><span data-stu-id="44815-124">**Voice Routing**</span></span> <br/> |[<span data-ttu-id="44815-125">トランクおよび変換ルールの構成</span><span class="sxs-lookup"><span data-stu-id="44815-125">Configuring Trunks and Translation Rules</span></span>](https://technet.microsoft.com/library/0c339511-a185-484e-94f0-dbe918b7e48a.aspx) <br/> |
|<span data-ttu-id="44815-126">サーバーを展開した場合エンタープライズ VoIPルーティング設定エンタープライズ VoIP確認します。</span><span class="sxs-lookup"><span data-stu-id="44815-126">If you deployed Enterprise Voice, verify Enterprise Voice routing settings.</span></span>  <br/> |<span data-ttu-id="44815-127">**音声ルーティング**</span><span class="sxs-lookup"><span data-stu-id="44815-127">**Voice Routing**</span></span> <br/> |[<span data-ttu-id="44815-128">音声ルーティングのテスト</span><span class="sxs-lookup"><span data-stu-id="44815-128">Test Voice Routing</span></span>](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx) <br/> |
|<span data-ttu-id="44815-129">アーカイブ サーバーを展開した場合は、アーカイブ ポリシーと設定が組織のコンプライアンス ニーズを満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="44815-129">If you deployed Archiving Server, verify that archiving policies and settings meet the compliance needs of your organization.</span></span>  <br/> |<span data-ttu-id="44815-130">**監視およびアーカイブ**</span><span class="sxs-lookup"><span data-stu-id="44815-130">**Monitoring and Archiving**</span></span> <br/> |[<span data-ttu-id="44815-131">アーカイブの管理</span><span class="sxs-lookup"><span data-stu-id="44815-131">Managing Archiving</span></span>](https://technet.microsoft.com/library/48c6cc8c-c2c1-4534-9a8a-fd5eb738076a.aspx) <br/> |
|<span data-ttu-id="44815-132">監視サーバーを展開した場合は、監視サーバー レポートを表示して使用状況と診断情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="44815-132">If you deployed Monitoring Server, view Monitoring Server reports to view usage and diagnostic information.</span></span>  <br/> |<span data-ttu-id="44815-133">**ホーム**</span><span class="sxs-lookup"><span data-stu-id="44815-133">**Home**</span></span> <br/> |[<span data-ttu-id="44815-134">Skype for Business Server 2015 での正常性と監視の管理</span><span class="sxs-lookup"><span data-stu-id="44815-134">Manage health and monitoring in Skype for Business Server 2015</span></span>](../../manage/health-and-monitoring/health-and-monitoring.md) <br/> |


