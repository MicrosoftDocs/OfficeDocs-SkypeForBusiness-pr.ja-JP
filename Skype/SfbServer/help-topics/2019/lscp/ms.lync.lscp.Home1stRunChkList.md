---
title: Skype for Business Server コントロール パネルの最初の実行チェックリスト
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.Home1stRunChkList
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d0c7306-e87e-464a-82ad-a5537f141500
ROBOTS: NOINDEX, NOFOLLOW
description: ビジネス サーバー ・ コントロール ・ パネル、Skype のビジネス サーバー用の管理用の web ベースのユーザー インターフェイスは、Skype を開始します。 このコントロール パネルを使用して、以前のリリースの Microsoft 管理コンソールを使用して実行されていた種類の管理タスクを実行することができます。
ms.openlocfilehash: fbd260679b7418535a7775b24b3ade98de790029
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873304"
---
# <a name="first-run-checklist-for-skype-for-business-server-control-panel"></a><span data-ttu-id="2c938-104">Skype for Business Server コントロール パネルの最初の実行チェックリスト</span><span class="sxs-lookup"><span data-stu-id="2c938-104">First Run Checklist for Skype for Business Server Control Panel</span></span>

<span data-ttu-id="2c938-105">ビジネス サーバー ・ コントロール ・ パネル、Skype のビジネス サーバー用の管理用の web ベースのユーザー インターフェイスは、Skype を開始します。</span><span class="sxs-lookup"><span data-stu-id="2c938-105">Welcome to the Skype for Business Server Control Panel, the web-based user interface for administration and management of Skype for Business Server.</span></span> <span data-ttu-id="2c938-106">このコントロール パネルを使用して、以前のリリースの Microsoft 管理コンソールを使用して実行されていた種類の管理タスクを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="2c938-106">You can use the control panel to perform the types of administrative tasks that were performed for by using the Microsoft Management Console in previous releases.</span></span>

<span data-ttu-id="2c938-107">Skype ビジネス サーバーを配置した後に実行するを強くお勧めする重要な作業の多くがあります。</span><span class="sxs-lookup"><span data-stu-id="2c938-107">There are a number of important tasks that we strongly recommend you perform after you have deployed Skype for Business Server.</span></span> <span data-ttu-id="2c938-108">それらのタスクには、展開時にすでに実行した可能性がある初期構成手順や、展開時に構成した設定や既定の設定の微調整または変更などがあります。</span><span class="sxs-lookup"><span data-stu-id="2c938-108">Some of these tasks are initial configuration steps that you may have already performed during deployment, while others are refinements or modifications to settings that you configured during deployment or default settings.</span></span> <span data-ttu-id="2c938-109">このトピックで説明するそれ以外のタスクでは、展開プロセス中に行った構成の検証を行います。</span><span class="sxs-lookup"><span data-stu-id="2c938-109">Other tasks described in this topic validate the configurations you made during the deployment process.</span></span>

> [!NOTE]
> <span data-ttu-id="2c938-110">以下の表のタスクを実行する前に、「[Role-Based Access Control](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx)」のトピックにある「役割とスコープ」セクションの説明に従って、正しいユーザー権限、アクセス許可、および役割を使用してログオンしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="2c938-110">Before performing the tasks in the following table, ensure that you log on using the correct user rights, permissions, and role as described in the "Roles and Scope" section of the [Role-Based Access Control](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) topic.</span></span>

## <a name="first-run-checklist"></a><span data-ttu-id="2c938-111">最初の実行チェックリスト</span><span class="sxs-lookup"><span data-stu-id="2c938-111">First Run Checklist</span></span>

<span data-ttu-id="2c938-112">このトピックで参照されるタスクを確認し、展開するため、組織の適切な手順を実行することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2c938-112">We strongly recommend that you review the tasks referred to in this topic, and then perform the appropriate procedures for deployment in your organization.</span></span>

|<span data-ttu-id="2c938-113">**Task**</span><span class="sxs-lookup"><span data-stu-id="2c938-113">**Task**</span></span>|<span data-ttu-id="2c938-114">**コントロール パネルのグループ**</span><span class="sxs-lookup"><span data-stu-id="2c938-114">**Control Panel group**</span></span>|<span data-ttu-id="2c938-115">**ドキュメント**</span><span class="sxs-lookup"><span data-stu-id="2c938-115">**Documentation**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2c938-116">トポロジ内にインストールしたサービスが正常に実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2c938-116">Verify the services that you installed in your topology are running as expected.</span></span>  <br/> |<span data-ttu-id="2c938-117">**トポロジ**</span><span class="sxs-lookup"><span data-stu-id="2c938-117">**Topology**</span></span> <br/> |[<span data-ttu-id="2c938-118">View Details About a Service</span><span class="sxs-lookup"><span data-stu-id="2c938-118">View Details About a Service</span></span>](https://technet.microsoft.com/library/bc8e8202-cd68-47e4-95b2-bb36e51cc124.aspx) <br/> |
|<span data-ttu-id="2c938-119">ビジネスのサーバーでは、Skype のユーザーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="2c938-119">Enable users for Skype for Business Server.</span></span> <span data-ttu-id="2c938-120">必要に応じて、以前のリリースからの移行、ユーザー移動 Skype をビジネスのサーバーにします。</span><span class="sxs-lookup"><span data-stu-id="2c938-120">Optionally and, if migrating from a previous release, move users to Skype for Business Server.</span></span>  <br/> |<span data-ttu-id="2c938-121">**ユーザー**</span><span class="sxs-lookup"><span data-stu-id="2c938-121">**Users**</span></span> <br/> |[<span data-ttu-id="2c938-122">Managing Users</span><span class="sxs-lookup"><span data-stu-id="2c938-122">Managing Users</span></span>](https://technet.microsoft.com/library/8021087e-5084-4a39-9fef-ab9376c6d371.aspx) <br/> |
|<span data-ttu-id="2c938-123">エンタープライズ VoIP を展開したか、展開することを望む場合は、SIP トランク接続を構成して、公衆交換電話網 (PSTN) への接続を有効にします。</span><span class="sxs-lookup"><span data-stu-id="2c938-123">If you deployed or want to deploy Enterprise Voice, configure a SIP trunk connection to enable connectivity to the public switched telephone network (PSTN).</span></span>  <br/> |<span data-ttu-id="2c938-124">**音声ルーティング**</span><span class="sxs-lookup"><span data-stu-id="2c938-124">**Voice Routing**</span></span> <br/> |[<span data-ttu-id="2c938-125">Configuring Trunks and Translation Rules</span><span class="sxs-lookup"><span data-stu-id="2c938-125">Configuring Trunks and Translation Rules</span></span>](https://technet.microsoft.com/library/0c339511-a185-484e-94f0-dbe918b7e48a.aspx) <br/> |
|<span data-ttu-id="2c938-126">エンタープライズ VoIP を展開した場合は、エンタープライズ VoIP ルーティング設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="2c938-126">If you deployed Enterprise Voice, verify Enterprise Voice routing settings.</span></span>  <br/> |<span data-ttu-id="2c938-127">**音声ルーティング**</span><span class="sxs-lookup"><span data-stu-id="2c938-127">**Voice Routing**</span></span> <br/> |[<span data-ttu-id="2c938-128">Test Voice Routing</span><span class="sxs-lookup"><span data-stu-id="2c938-128">Test Voice Routing</span></span>](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx) <br/> |
|<span data-ttu-id="2c938-129">アーカイブ サーバーを展開した場合は、アーカイブのポリシーと設定が組織の法令順守の必要性に適合することを確認します。</span><span class="sxs-lookup"><span data-stu-id="2c938-129">If you deployed Archiving Server, verify that archiving policies and settings meet the compliance needs of your organization.</span></span>  <br/> |<span data-ttu-id="2c938-130">**監視およびアーカイブ**</span><span class="sxs-lookup"><span data-stu-id="2c938-130">**Monitoring and Archiving**</span></span> <br/> |[<span data-ttu-id="2c938-131">Managing Archiving</span><span class="sxs-lookup"><span data-stu-id="2c938-131">Managing Archiving</span></span>](https://technet.microsoft.com/library/48c6cc8c-c2c1-4534-9a8a-fd5eb738076a.aspx) <br/> |
|<span data-ttu-id="2c938-132">監視サーバーを展開した場合は、監視サーバーのレポートを表示して使用状況と診断情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="2c938-132">If you deployed Monitoring Server, view Monitoring Server reports to view usage and diagnostic information.</span></span>  <br/> |<span data-ttu-id="2c938-133">**ホーム**</span><span class="sxs-lookup"><span data-stu-id="2c938-133">**Home**</span></span> <br/> |[<span data-ttu-id="2c938-134">状態と Skype での監視は、ビジネスのサーバーを管理します。</span><span class="sxs-lookup"><span data-stu-id="2c938-134">Manage health and monitoring in Skype for Business Server</span></span>](../../../manage/health-and-monitoring/health-and-monitoring.md) <br/> |


