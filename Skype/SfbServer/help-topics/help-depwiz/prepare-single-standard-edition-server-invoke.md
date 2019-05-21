---
title: 単一の Standard Edition サーバーの準備 (起動)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployAIOInvoke
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5da0aa73-8bf8-41f3-81e7-94f955cda541
description: '[コマンドの実行] ページでは、SQL Server Express をインストールして、中央管理ストアとして機能するように構成するタスクを作業ウィンドウで確認できます。 既定では、RTC という名前の SQL Server ベースのデータベースのインスタンスが作成されます。 ファイアウォールルールも作成され、サーバーとクライアントがデータベースとインスタンスと通信できるように、受信および送信のアクセスが許可されます。 タスクが完了したら、ドロップダウンリストからログファイルを選ぶことができます。 ログファイルは、ブートストラップのローカルコンピューターという名前です。 ログファイルを選択したら、[ログの表示] をクリックします。 エラーや警告のログファイルを確認します。 続行する準備ができたら、[完了] をクリックします。 まだトポロジビルダーを使用してトポロジを定義する必要があります。'
ms.openlocfilehash: ec9d3dd8cd1eeadd4d7a69bacdcf6d7e89b1af7d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34292250"
---
# <a name="prepare-single-standard-edition-server-invoke"></a><span data-ttu-id="ce54e-111">単一の Standard Edition サーバーの準備 (起動)</span><span class="sxs-lookup"><span data-stu-id="ce54e-111">Prepare Single Standard Edition Server (Invoke)</span></span>
 
<span data-ttu-id="ce54e-112">[**コマンドの実行**] ページでは、SQL Server Express をインストールして、中央管理ストアとして機能するように構成するタスクを作業ウィンドウで確認できます。</span><span class="sxs-lookup"><span data-stu-id="ce54e-112">On the **Executing commands** page, the tasks of installing the SQL Server Express and configuring to act as the Central Management store can be viewed in the task pane.</span></span> <span data-ttu-id="ce54e-113">既定では、RTC という名前の SQL Server ベースのデータベースのインスタンスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="ce54e-113">By default, an instance of a SQL Server-based database named RTC is created.</span></span> <span data-ttu-id="ce54e-114">ファイアウォールルールも作成され、サーバーとクライアントがデータベースとインスタンスと通信できるように、受信および送信のアクセスが許可されます。</span><span class="sxs-lookup"><span data-stu-id="ce54e-114">Firewall rules are also created to allow inbound and outbound access for servers and clients to communicate with the database and instance.</span></span> <span data-ttu-id="ce54e-115">タスクが完了したら、ドロップダウンリストからログファイルを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="ce54e-115">After the task is completed, you can select the log file from the drop-down list.</span></span> <span data-ttu-id="ce54e-116">ログファイルは、**ブートストラップのローカルコンピューター**という名前です。</span><span class="sxs-lookup"><span data-stu-id="ce54e-116">The log file is named **Bootstrap local machine**.</span></span> <span data-ttu-id="ce54e-117">ログファイルを選択したら、[**ログの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ce54e-117">After selecting the log file, click **View Log**.</span></span> <span data-ttu-id="ce54e-118">エラーや警告のログファイルを確認します。</span><span class="sxs-lookup"><span data-stu-id="ce54e-118">Review the log file for any errors and warnings.</span></span> <span data-ttu-id="ce54e-119">続行する準備ができたら、[完了] をクリックし**ます。**</span><span class="sxs-lookup"><span data-stu-id="ce54e-119">When you are ready to proceed, click **Finish.**</span></span> <span data-ttu-id="ce54e-120">まだトポロジビルダーを使用してトポロジを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce54e-120">You should now define your topology with Topology Builder if you have not already done so.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ce54e-121">SQL Server Express のインストールが完了するまでに時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ce54e-121">The installation of the SQL Server Express can take some time to complete.</span></span> <span data-ttu-id="ce54e-122">インストール中は、画面または作業ウィンドウに進行状況は表示されません。</span><span class="sxs-lookup"><span data-stu-id="ce54e-122">During the installation, there is no progress visible on the screen or the task pane.</span></span> <span data-ttu-id="ce54e-123">インストールを監視するには、Windows タスクマネージャーを使用して、MSIExec プロセスと SQL Server のセットアップファイルを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce54e-123">To monitor the installation, you should use Windows Task Manager and look for the MSIExec processes and the Setup files for SQL Server.</span></span> <span data-ttu-id="ce54e-124">この方法では、インストールの状態を表示して、インストールが進行中であることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="ce54e-124">In this way, you can view the status of the install and be sure that the install is proceeding.</span></span> <span data-ttu-id="ce54e-125">このヘルプトピックの範囲を超える要因によっては、SQL Server インスタンスの実行を完了するために最大15分以上かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ce54e-125">Depending on factors beyond the scope of this help topic, it can take up to 15 minutes or more for the install the SQL Server instance to complete.</span></span> 
  

