---
title: ローカル構成ストアのインストール
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/13/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
description: 新しい Skype for Business Server 2015 役割サーバーのインストールを開始するには、まず、ローカル構成ストアをホストするローカル SQL Serverをインストールする必要があります。 ローカル構成ストアは、Skype for Business Server Central Management ストア (CMS) の読み取り専用レプリカとして機能します。 [ローカル構成ストアのインストール] 手順を実行しているサーバーに、そのコンピューターのローカル管理者としてログオンするとともに、RTCUniversalServerAdmins または RTCUniversalGlobalReadOnlyGroup グループのメンバーシップを持っている必要があります。 エッジ サーバーでセットアップを実行する場合は、RTCUniversalServerAdmins または RTCUniversalGlobalReadOnlyGroup グループのメンバーでなくても構いません。 トポロジ ビルダー定義ドキュメントは、中央管理ストアではなく、エクスポートされた定義ドキュメントから読み取されます。 トポロジ ビルダー定義ドキュメントをエクスポートしてエッジ サーバーで使用するには、「トポロジのエクスポート」および「エッジ インストール用に外部メディアにコピーする」を参照してください。
ms.openlocfilehash: 62a16e441cc95e77aaed7e09152ef2a79221d85f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51108743"
---
# <a name="install-local-configuration-store"></a><span data-ttu-id="76ece-108">ローカル構成ストアのインストール</span><span class="sxs-lookup"><span data-stu-id="76ece-108">Install Local Configuration Store</span></span>

<span data-ttu-id="76ece-109">新しい Skype for Business Server 2015 役割サーバーのインストールを開始するには、まず、ローカル構成ストアをホストするローカル SQL Serverをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="76ece-109">To begin the installation of a new Skype for Business Server 2015 role server, you must first install the local SQL Server that will host the local configuration store.</span></span> <span data-ttu-id="76ece-110">ローカル構成ストアは、Skype for Business Server Central Management ストア (CMS) の読み取り専用レプリカとして機能します。</span><span class="sxs-lookup"><span data-stu-id="76ece-110">The local configuration store will act as a read-only replica of the Skype for Business Server Central Management store (CMS).</span></span> <span data-ttu-id="76ece-111">**[ローカル構成ストアのインストール]** 手順を実行しているサーバーに、そのコンピューターのローカル管理者としてログオンするとともに、RTCUniversalServerAdmins または RTCUniversalGlobalReadOnlyGroup グループのメンバーシップを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="76ece-111">You must be logged on to the server that you are running the **Install Local Configuration Store** step as the local administrator on the computer, and have membership in the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="76ece-112">エッジ サーバーでセットアップを実行する場合は、RTCUniversalServerAdmins または RTCUniversalGlobalReadOnlyGroup グループのメンバーでなくても構いません。</span><span class="sxs-lookup"><span data-stu-id="76ece-112">If you are performing the setup on an Edge Server, you do not have to be a member of the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="76ece-113">トポロジ ビルダー定義ドキュメントは、中央管理ストアではなく、エクスポートされた定義ドキュメントから読み取されます。</span><span class="sxs-lookup"><span data-stu-id="76ece-113">The Topology Builder definition document will be read from the exported definition document instead of from the Central Management store.</span></span> <span data-ttu-id="76ece-114">トポロジ ビルダー定義ドキュメントをエクスポートしてエッジ サーバーで使用するには、トピック「トポロジのエクスポートとエッジ インストール用の外部メディアへのコピー」を [参照してください](/previous-versions/office/lync-server-2013/lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation)。</span><span class="sxs-lookup"><span data-stu-id="76ece-114">To export the Topology Builder definition document and make it available to the Edge Servers, see the topic [Export Your Topology and Copy It to External Media for Edge Installation](/previous-versions/office/lync-server-2013/lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation).</span></span>

<span data-ttu-id="76ece-115">インストールを開始するには、以下の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="76ece-115">To begin the installation:</span></span>

1. <span data-ttu-id="76ece-116">[Skype for Business Server 2015] ページで、[手順 **1:** ローカル構成ストアのインストール] の横にある [実行] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="76ece-116">On the Skype for Business Server 2015 page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>

2. <span data-ttu-id="76ece-117">[**ローカル サーバー構成**] ページで、[**中央管理ストアから直接取得する**] オプションがオンになっていることを確認し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76ece-117">On the **Local Server Configuration** page, be sure that the **Retrieve configuration automatically from the Central Management Store** option is selected, and then click **Next**.</span></span>

3. <span data-ttu-id="76ece-118">ローカル サーバー構成のインストールが完了したら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76ece-118">When the local server configuration installation is complete, click **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="76ece-119">ローカル アプリケーションのインストールにはSQL Server時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="76ece-119">The installation of the local SQL Server can take some time.</span></span> <span data-ttu-id="76ece-120">インストール中にインストールの概要画面に進行状況の更新SQL Server表示されません。</span><span class="sxs-lookup"><span data-stu-id="76ece-120">You will not see updates on progress in the installation summary screen while SQL Server is being installed.</span></span> <span data-ttu-id="76ece-121">インストールの進行状況を監視する場合は、タスク マネージャーを使用して、インストールのSQL Serverします。</span><span class="sxs-lookup"><span data-stu-id="76ece-121">If you want to monitor the progress of the installation, use Task Manager to watch the SQL Server setup.</span></span>