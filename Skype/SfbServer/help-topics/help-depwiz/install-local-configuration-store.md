---
title: ローカル構成ストアのインストール
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 4/13/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
description: ビジネス サーバー 2015 の役割を持つサーバーの新しい Skype のインストールを開始するには、最初にローカル構成ストアをホストするローカルの SQL Server をインストールする必要があります。 ローカル構成ストアは、ビジネスのサーバーの中央管理ストア (CMS) の Skype の読み取り専用レプリカとして機能します。 [ローカル構成ストアのインストール] 手順を実行しているサーバーに、そのコンピューターのローカル管理者としてログオンすると共に、RTCUniversalServerAdmins または RTCUniversalGlobalReadOnlyGroup グループのメンバーシップを持っている必要があります。 エッジ サーバーでセットアップを実行する場合は、RTCUniversalServerAdmins または RTCUniversalGlobalReadOnlyGroup グループのメンバーでなくても構いません。 トポロジ ビルダー定義ドキュメントの代わりに中央管理ストアからエクスポートした定義ドキュメントから読み取られます。 トポロジ ビルダー定義ドキュメントをエクスポートしてエッジ サーバーを使用できるように、エッジのインストールのトピックのトポロジーのエクスポートとコピーして、外部メディアを参照してください。
ms.openlocfilehash: e25e43fbcd1001460d7b001d914e1801558af4f1
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2018
ms.locfileid: "26294080"
---
# <a name="install-local-configuration-store"></a><span data-ttu-id="5159a-108">ローカル構成ストアのインストール</span><span class="sxs-lookup"><span data-stu-id="5159a-108">Install Local Configuration Store</span></span>

<span data-ttu-id="5159a-109">ビジネス サーバー 2015 の役割を持つサーバーの新しい Skype のインストールを開始するには、最初にローカル構成ストアをホストするローカルの SQL Server をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5159a-109">To begin the installation of a new Skype for Business Server 2015 role server, you must first install the local SQL Server that will host the local configuration store.</span></span> <span data-ttu-id="5159a-110">ローカル構成ストアは、ビジネスのサーバーの中央管理ストア (CMS) の Skype の読み取り専用レプリカとして機能します。</span><span class="sxs-lookup"><span data-stu-id="5159a-110">The local configuration store will act as a read-only replica of the Skype for Business Server Central Management store (CMS).</span></span> <span data-ttu-id="5159a-111">[**ローカル構成ストアのインストール**] 手順を実行しているサーバーに、そのコンピューターのローカル管理者としてログオンすると共に、RTCUniversalServerAdmins または RTCUniversalGlobalReadOnlyGroup グループのメンバーシップを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5159a-111">You must be logged on to the server that you are running the **Install Local Configuration Store** step as the local administrator on the computer, and have membership in the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="5159a-112">エッジ サーバーでセットアップを実行する場合は、RTCUniversalServerAdmins または RTCUniversalGlobalReadOnlyGroup グループのメンバーでなくても構いません。</span><span class="sxs-lookup"><span data-stu-id="5159a-112">If you are performing the setup on an Edge Server, you do not have to be a member of the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="5159a-113">トポロジ ビルダー定義ドキュメントの代わりに中央管理ストアからエクスポートした定義ドキュメントから読み取られます。</span><span class="sxs-lookup"><span data-stu-id="5159a-113">The Topology Builder definition document will be read from the exported definition document instead of from the Central Management store.</span></span> <span data-ttu-id="5159a-114">トポロジ ビルダー定義ドキュメントをエクスポートしてエッジ サーバーを使用できるように、「[トポロジーのエクスポートとコピーして、エッジ インストール用の外部メディア](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5159a-114">To export the Topology Builder definition document and make it available to the Edge Servers, see the topic[Export Your Topology and Copy It to External Media for Edge Installation](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).</span></span>

<span data-ttu-id="5159a-115">インストールを開始するには、以下の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5159a-115">To begin the installation:</span></span>

1. <span data-ttu-id="5159a-116">ビジネス サーバー 2015 ページの場合は、Skype の横に**ステップ 1: ローカル構成ストアのインストール**を**実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5159a-116">On the Skype for Business Server 2015 page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>

2. <span data-ttu-id="5159a-117">[**ローカル サーバー構成**] ページで、[**中央管理ストアから直接取得する**] オプションがオンになっていることを確認し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5159a-117">On the **Local Server Configuration** page, be sure that the **Retrieve configuration automatically from the Central Management Store** option is selected, and then click **Next**.</span></span>

3. <span data-ttu-id="5159a-118">ローカル サーバー構成のインストールが完了したら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5159a-118">When the local server configuration installation is complete, click **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="5159a-119">ローカルの SQL Server のインストール時間がかかることができます。</span><span class="sxs-lookup"><span data-stu-id="5159a-119">The installation of the local SQL Server can take some time.</span></span> <span data-ttu-id="5159a-120">SQL Server のインストール中に [サマリー] 画面でインストールの進行状況の更新は表示されません。</span><span class="sxs-lookup"><span data-stu-id="5159a-120">You will not see updates on progress in the installation summary screen while SQL Server is being installed.</span></span> <span data-ttu-id="5159a-121">インストールの進行状況を監視する場合は、SQL Server セットアップを監視するタスク マネージャーを使用します。</span><span class="sxs-lookup"><span data-stu-id="5159a-121">If you want to monitor the progress of the installation, use Task Manager to watch the SQL Server setup.</span></span>


