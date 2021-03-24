---
title: ローカル構成ストアのインストール
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
ROBOTS: NOINDEX, NOFOLLOW
description: 新しい Skype for Business Server 役割サーバーのインストールを開始するには、まずローカル構成ストアをホストするローカル SQL Serverをインストールする必要があります。 ローカル構成ストアは、Skype for Business Server Central Management ストア (CMS) の読み取り専用レプリカとして機能します。
ms.openlocfilehash: 78492f8ce913d8f73336ae4f6cdf06fd340ed5f5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095981"
---
# <a name="install-local-configuration-store"></a><span data-ttu-id="75571-104">ローカル構成ストアのインストール</span><span class="sxs-lookup"><span data-stu-id="75571-104">Install Local Configuration Store</span></span>

<span data-ttu-id="75571-105">新しい Skype for Business Server 役割サーバーのインストールを開始するには、まずローカル構成ストアをホストするローカル SQL Serverをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="75571-105">To begin the installation of a new Skype for Business Server role server, you must first install the local SQL Server that will host the local configuration store.</span></span> <span data-ttu-id="75571-106">ローカル構成ストアは、Skype for Business Server Central Management ストア (CMS) の読み取り専用レプリカとして機能します。</span><span class="sxs-lookup"><span data-stu-id="75571-106">The local configuration store will act as a read-only replica of the Skype for Business Server Central Management store (CMS).</span></span> <span data-ttu-id="75571-107">**[ローカル構成ストアのインストール]** 手順を実行しているサーバーに、そのコンピューターのローカル管理者としてログオンするとともに、RTCUniversalServerAdmins または RTCUniversalGlobalReadOnlyGroup グループのメンバーシップを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="75571-107">You must be logged on to the server that you are running the **Install Local Configuration Store** step as the local administrator on the computer, and have membership in the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="75571-108">エッジ サーバーでセットアップを実行する場合は、RTCUniversalServerAdmins または RTCUniversalGlobalReadOnlyGroup グループのメンバーでなくても構いません。</span><span class="sxs-lookup"><span data-stu-id="75571-108">If you are performing the setup on an Edge Server, you do not have to be a member of the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="75571-109">トポロジ ビルダー定義ドキュメントは、中央管理ストアではなく、エクスポートされた定義ドキュメントから読み取されます。</span><span class="sxs-lookup"><span data-stu-id="75571-109">The Topology Builder definition document will be read from the exported definition document instead of from the Central Management store.</span></span> <span data-ttu-id="75571-110">トポロジ ビルダー定義ドキュメントをエクスポートしてエッジ サーバーで使用するには、トピック「トポロジのエクスポートとエッジ インストール用の外部メディアへのコピー」を[参照してください](/previous-versions/office/lync-server-2013/lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation)。</span><span class="sxs-lookup"><span data-stu-id="75571-110">To export the Topology Builder definition document and make it available to the Edge Servers, see the topic[Export Your Topology and Copy It to External Media for Edge Installation](/previous-versions/office/lync-server-2013/lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation).</span></span>

<span data-ttu-id="75571-111">インストールを開始するには、以下の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="75571-111">To begin the installation:</span></span>

1. <span data-ttu-id="75571-112">[Skype for Business Server] ページで、[手順 **1:** ローカル構成ストアのインストール] の横にある [実行] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="75571-112">On the Skype for Business Server page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>

2. <span data-ttu-id="75571-113">[**ローカル サーバー構成**] ページで、[**中央管理ストアから直接取得する**] オプションがオンになっていることを確認し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="75571-113">On the **Local Server Configuration** page, be sure that the **Retrieve configuration automatically from the Central Management Store** option is selected, and then click **Next**.</span></span>

3. <span data-ttu-id="75571-114">ローカル サーバー構成のインストールが完了したら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="75571-114">When the local server configuration installation is complete, click **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="75571-115">ローカル アプリケーションのインストールにはSQL Server時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="75571-115">The installation of the local SQL Server can take some time.</span></span> <span data-ttu-id="75571-116">インストール中にインストールの概要画面に進行状況の更新SQL Server表示されません。</span><span class="sxs-lookup"><span data-stu-id="75571-116">You will not see updates on progress in the installation summary screen while SQL Server is being installed.</span></span> <span data-ttu-id="75571-117">インストールの進行状況を監視する場合は、タスク マネージャーを使用して、インストールのSQL Serverします。</span><span class="sxs-lookup"><span data-stu-id="75571-117">If you want to monitor the progress of the installation, use Task Manager to watch the SQL Server setup.</span></span>