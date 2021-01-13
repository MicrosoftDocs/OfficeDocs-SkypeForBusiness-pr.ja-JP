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
description: 新しい Skype for Business Server 2015 役割サーバーのインストールを開始するには、まず、ローカル構成ストアをホストするローカル SQL Server をインストールする必要があります。 ローカル構成ストアは、Skype for Business Server Central Management Store (CMS) の読み取り専用レプリカとして機能します。 [ローカル構成ストアのインストール] 手順を実行しているサーバーに、そのコンピューターのローカル管理者としてログオンするとともに、RTCUniversalServerAdmins または RTCUniversalGlobalReadOnlyGroup グループのメンバーシップを持っている必要があります。 エッジ サーバーでセットアップを実行する場合は、RTCUniversalServerAdmins または RTCUniversalGlobalReadOnlyGroup グループのメンバーでなくても構いません。 トポロジ ビルダー定義ドキュメントは、中央管理ストアからではなく、エクスポートされた定義ドキュメントから読み取されます。 トポロジ ビルダー定義ドキュメントをエクスポートしてエッジ サーバーで使用するには、「トポロジのエクスポート」および「エッジ インストール用に外部メディアにコピーする」を参照してください。
ms.openlocfilehash: 630a3682d3dd5ca12381d5f5b549bb22121b579e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827147"
---
# <a name="install-local-configuration-store"></a><span data-ttu-id="cce0c-108">ローカル構成ストアのインストール</span><span class="sxs-lookup"><span data-stu-id="cce0c-108">Install Local Configuration Store</span></span>

<span data-ttu-id="cce0c-109">新しい Skype for Business Server 2015 役割サーバーのインストールを開始するには、まず、ローカル構成ストアをホストするローカル SQL Server をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cce0c-109">To begin the installation of a new Skype for Business Server 2015 role server, you must first install the local SQL Server that will host the local configuration store.</span></span> <span data-ttu-id="cce0c-110">ローカル構成ストアは、Skype for Business Server Central Management Store (CMS) の読み取り専用レプリカとして機能します。</span><span class="sxs-lookup"><span data-stu-id="cce0c-110">The local configuration store will act as a read-only replica of the Skype for Business Server Central Management store (CMS).</span></span> <span data-ttu-id="cce0c-111">**[ローカル構成ストアのインストール]** 手順を実行しているサーバーに、そのコンピューターのローカル管理者としてログオンするとともに、RTCUniversalServerAdmins または RTCUniversalGlobalReadOnlyGroup グループのメンバーシップを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="cce0c-111">You must be logged on to the server that you are running the **Install Local Configuration Store** step as the local administrator on the computer, and have membership in the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="cce0c-112">エッジ サーバーでセットアップを実行する場合は、RTCUniversalServerAdmins または RTCUniversalGlobalReadOnlyGroup グループのメンバーでなくても構いません。</span><span class="sxs-lookup"><span data-stu-id="cce0c-112">If you are performing the setup on an Edge Server, you do not have to be a member of the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="cce0c-113">トポロジ ビルダー定義ドキュメントは、中央管理ストアからではなく、エクスポートされた定義ドキュメントから読み取されます。</span><span class="sxs-lookup"><span data-stu-id="cce0c-113">The Topology Builder definition document will be read from the exported definition document instead of from the Central Management store.</span></span> <span data-ttu-id="cce0c-114">トポロジ ビルダー定義ドキュメントをエクスポートしてエッジ サーバーで使用するには、「トポロジのエクスポート」および「エッジ インストール用に外部メディアにコピーする」を参照 [してください](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx)。</span><span class="sxs-lookup"><span data-stu-id="cce0c-114">To export the Topology Builder definition document and make it available to the Edge Servers, see the topic [Export Your Topology and Copy It to External Media for Edge Installation](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).</span></span>

<span data-ttu-id="cce0c-115">インストールを開始するには、以下の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="cce0c-115">To begin the installation:</span></span>

1. <span data-ttu-id="cce0c-116">On the Skype for Business Server 2015 page, next to **Step1: Install Local Configuration Store,** click **Run**.</span><span class="sxs-lookup"><span data-stu-id="cce0c-116">On the Skype for Business Server 2015 page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>

2. <span data-ttu-id="cce0c-117">[**ローカル サーバー構成**] ページで、[**中央管理ストアから直接取得する**] オプションがオンになっていることを確認し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cce0c-117">On the **Local Server Configuration** page, be sure that the **Retrieve configuration automatically from the Central Management Store** option is selected, and then click **Next**.</span></span>

3. <span data-ttu-id="cce0c-118">ローカル サーバー構成のインストールが完了したら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cce0c-118">When the local server configuration installation is complete, click **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="cce0c-119">ローカル アプリケーションのインストールにはSQL Server時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="cce0c-119">The installation of the local SQL Server can take some time.</span></span> <span data-ttu-id="cce0c-120">インストール中は、インストールの概要画面に更新プログラムSQL Server表示されません。</span><span class="sxs-lookup"><span data-stu-id="cce0c-120">You will not see updates on progress in the installation summary screen while SQL Server is being installed.</span></span> <span data-ttu-id="cce0c-121">インストールの進行状況を監視する場合は、タスク マネージャーを使用してセットアップのSQL Serverします。</span><span class="sxs-lookup"><span data-stu-id="cce0c-121">If you want to monitor the progress of the installation, use Task Manager to watch the SQL Server setup.</span></span>


