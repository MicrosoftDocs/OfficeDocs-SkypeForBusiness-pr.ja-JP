---
title: ローカル構成ストアのインストール
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
ROBOTS: NOINDEX, NOFOLLOW
description: 新しい Skype for Business Server の役割サーバーのインストールを開始するには、まず、ローカル構成ストアをホストするローカル SQL Server をインストールする必要があります。 ローカル構成ストアは、Skype for Business Server Central Management store (CMS) の読み取り専用レプリカとして機能します。
ms.openlocfilehash: 699294889008f0d353e1ba727cbc078f9616f4ec
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303405"
---
# <a name="install-local-configuration-store"></a><span data-ttu-id="e6b06-104">ローカル構成ストアのインストール</span><span class="sxs-lookup"><span data-stu-id="e6b06-104">Install Local Configuration Store</span></span>

<span data-ttu-id="e6b06-105">新しい Skype for Business Server の役割サーバーのインストールを開始するには、まず、ローカル構成ストアをホストするローカル SQL Server をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6b06-105">To begin the installation of a new Skype for Business Server role server, you must first install the local SQL Server that will host the local configuration store.</span></span> <span data-ttu-id="e6b06-106">ローカル構成ストアは、Skype for Business Server Central Management store (CMS) の読み取り専用レプリカとして機能します。</span><span class="sxs-lookup"><span data-stu-id="e6b06-106">The local configuration store will act as a read-only replica of the Skype for Business Server Central Management store (CMS).</span></span> <span data-ttu-id="e6b06-107">[**ローカル構成ストアのインストール**] 手順を実行しているサーバーに、そのコンピューターのローカル管理者としてログオンすると共に、RTCUniversalServerAdmins または RTCUniversalGlobalReadOnlyGroup グループのメンバーシップを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6b06-107">You must be logged on to the server that you are running the **Install Local Configuration Store** step as the local administrator on the computer, and have membership in the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="e6b06-108">エッジ サーバーでセットアップを実行する場合は、RTCUniversalServerAdmins または RTCUniversalGlobalReadOnlyGroup グループのメンバーでなくても構いません。</span><span class="sxs-lookup"><span data-stu-id="e6b06-108">If you are performing the setup on an Edge Server, you do not have to be a member of the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="e6b06-109">トポロジビルダー定義ドキュメントは、中央管理ストアからではなく、エクスポートされた定義ドキュメントから読み取ります。</span><span class="sxs-lookup"><span data-stu-id="e6b06-109">The Topology Builder definition document will be read from the exported definition document instead of from the Central Management store.</span></span> <span data-ttu-id="e6b06-110">トポロジビルダーの定義ドキュメントをエクスポートして、エッジサーバーで利用できるようにするには、「[トポロジをエクスポートして、edge のインストール用に外部メディアにコピー](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx)する」のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6b06-110">To export the Topology Builder definition document and make it available to the Edge Servers, see the topic[Export Your Topology and Copy It to External Media for Edge Installation](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).</span></span>

<span data-ttu-id="e6b06-111">インストールを開始するには、以下の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e6b06-111">To begin the installation:</span></span>

1. <span data-ttu-id="e6b06-112">[Skype for Business Server] ページで、[**ステップ 2: ローカル構成ストアをインストール**します] の横にある [**実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e6b06-112">On the Skype for Business Server page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>

2. <span data-ttu-id="e6b06-113">[**ローカル サーバー構成**] ページで、[**中央管理ストアから直接取得する**] オプションがオンになっていることを確認し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e6b06-113">On the **Local Server Configuration** page, be sure that the **Retrieve configuration automatically from the Central Management Store** option is selected, and then click **Next**.</span></span>

3. <span data-ttu-id="e6b06-114">ローカル サーバー構成のインストールが完了したら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e6b06-114">When the local server configuration installation is complete, click **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="e6b06-115">ローカル SQL Server のインストールには時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="e6b06-115">The installation of the local SQL Server can take some time.</span></span> <span data-ttu-id="e6b06-116">SQL Server がインストールされている間、インストールの概要画面の [更新の進行状況] は表示されません。</span><span class="sxs-lookup"><span data-stu-id="e6b06-116">You will not see updates on progress in the installation summary screen while SQL Server is being installed.</span></span> <span data-ttu-id="e6b06-117">インストールの進行状況を監視する場合は、タスクマネージャーを使って SQL Server のセットアップを確認します。</span><span class="sxs-lookup"><span data-stu-id="e6b06-117">If you want to monitor the progress of the installation, use Task Manager to watch the SQL Server setup.</span></span>


