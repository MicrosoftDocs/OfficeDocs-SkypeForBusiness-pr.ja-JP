---
title: 単一の Standard Edition サーバーの準備 (起動)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployAIOInvoke
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 5da0aa73-8bf8-41f3-81e7-94f955cda541
ROBOTS: NOINDEX, NOFOLLOW
description: '[コマンドの実行] ページでは、SQL Server Express をインストールし、中央管理ストアとして機能する構成のタスクを作業ウィンドウに表示できます。 既定では、RTC という名前SQL Serverベースのデータベースのインスタンスが作成されます。 サーバーおよびクライアントの着信および発信アクセスを許可するファイアウォール ルールも作成され、データベースおよびインスタンスとの通信が行われます。 タスクが完了すると、ドロップダウン リストからログ ファイルを選択できます。 ログ ファイルは [ブートストラップ ローカル コンピューター] と命名されます。 ログ ファイルを選択して、[ログの表示] をクリックします。 ログ ファイルにエラーや警告がないかどうか確認します。 次に進む準備ができたら、[完了] をクリックします。 まだ定義していない場合は、トポロジ ビルダーを使用してトポロジを定義する必要があります。'
ms.openlocfilehash: c3e6e01f7aed0471d8f1eed0ad79f8ef6320f86a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820617"
---
# <a name="prepare-single-standard-edition-server-invoke"></a><span data-ttu-id="c5a01-111">単一の Standard Edition サーバーの準備 (起動)</span><span class="sxs-lookup"><span data-stu-id="c5a01-111">Prepare Single Standard Edition Server (Invoke)</span></span>
 
<span data-ttu-id="c5a01-112">[ **コマンドの** 実行] ページでは、SQL Server Express をインストールし、中央管理ストアとして機能する構成のタスクを作業ウィンドウに表示できます。</span><span class="sxs-lookup"><span data-stu-id="c5a01-112">On the **Executing commands** page, the tasks of installing the SQL Server Express and configuring to act as the Central Management store can be viewed in the task pane.</span></span> <span data-ttu-id="c5a01-113">既定では、RTC という名前SQL Serverベースのデータベースのインスタンスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="c5a01-113">By default, an instance of a SQL Server-based database named RTC is created.</span></span> <span data-ttu-id="c5a01-114">サーバーおよびクライアントの着信および発信アクセスを許可するファイアウォール ルールも作成され、データベースおよびインスタンスとの通信が行われます。</span><span class="sxs-lookup"><span data-stu-id="c5a01-114">Firewall rules are also created to allow inbound and outbound access for servers and clients to communicate with the database and instance.</span></span> <span data-ttu-id="c5a01-115">タスクが完了すると、ドロップダウン リストからログ ファイルを選択できます。</span><span class="sxs-lookup"><span data-stu-id="c5a01-115">After the task is completed, you can select the log file from the drop-down list.</span></span> <span data-ttu-id="c5a01-116">ログ ファイルは **[ブートストラップ ローカル コンピューター]** と命名されます。</span><span class="sxs-lookup"><span data-stu-id="c5a01-116">The log file is named **Bootstrap local machine**.</span></span> <span data-ttu-id="c5a01-117">ログ ファイルを選択して、**[ログの表示]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c5a01-117">After selecting the log file, click **View Log**.</span></span> <span data-ttu-id="c5a01-118">ログ ファイルにエラーや警告がないかどうか確認します。</span><span class="sxs-lookup"><span data-stu-id="c5a01-118">Review the log file for any errors and warnings.</span></span> <span data-ttu-id="c5a01-119">次に進む準備ができたら、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c5a01-119">When you are ready to proceed, click **Finish.**</span></span> <span data-ttu-id="c5a01-120">まだ定義していない場合は、トポロジ ビルダーを使用してトポロジを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5a01-120">You should now define your topology with Topology Builder if you have not already done so.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c5a01-121">SQL Server Express のインストールが完了するには、少し時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c5a01-121">The installation of the SQL Server Express can take some time to complete.</span></span> <span data-ttu-id="c5a01-122">インストール中、画面やタスク ウィンドウに進行状況は表示されません。</span><span class="sxs-lookup"><span data-stu-id="c5a01-122">During the installation, there is no progress visible on the screen or the task pane.</span></span> <span data-ttu-id="c5a01-123">インストールを監視するには、Windows タスク マネージャーを使用して、MSIExec プロセスとセットアップ ファイルを探SQL Server。</span><span class="sxs-lookup"><span data-stu-id="c5a01-123">To monitor the installation, you should use Windows Task Manager and look for the MSIExec processes and the Setup files for SQL Server.</span></span> <span data-ttu-id="c5a01-124">この方法により、インストールの状態を表示し、インストールが進行していることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="c5a01-124">In this way, you can view the status of the install and be sure that the install is proceeding.</span></span> <span data-ttu-id="c5a01-125">このヘルプ トピックの範囲を超える要因によっては、インストールが完了するのに最大 15 分以上かかるSQL Serverがあります。</span><span class="sxs-lookup"><span data-stu-id="c5a01-125">Depending on factors beyond the scope of this help topic, it can take up to 15 minutes or more for the install the SQL Server instance to complete.</span></span> 
  

