---
title: 1 つの標準エディションのサーバーを準備する (呼び出す)
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployAIOInvoke
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5da0aa73-8bf8-41f3-81e7-94f955cda541
description: コマンドの実行中] ページで、[作業ウィンドウで SQL Server Express をインストールして、中央管理ストアとして機能するように構成するタスクを表示できます。 既定では、RTC をという名前の SQL Server ベースのデータベースのインスタンスが作成されます。 サーバーとデータベース インスタンスと通信するためにクライアントの受信および送信のアクセスを許可するファイアウォール規則が作成されます。 タスクが完了したら、ドロップダウン リストからログ ファイルを選択できます。 ログ ファイルをローカル コンピューターのブートス トラップといいます。 ログ ファイルを選択すると、ログの表示] をクリックします。 エラーと警告のログ ファイルを確認します。 続行する準備ができたら、[完了] をクリックします。 されていない場合は、ここでトポロジ ビルダーでトポロジを定義してください。
ms.openlocfilehash: ec6cd9d7f8e7812ca61138e053fd18abf4e24d96
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/20/2018
ms.locfileid: "19964534"
---
# <a name="prepare-single-standard-edition-server-invoke"></a><span data-ttu-id="badbd-111">1 つの標準エディションのサーバーを準備する (呼び出す)</span><span class="sxs-lookup"><span data-stu-id="badbd-111">Prepare Single Standard Edition Server (Invoke)</span></span>
 
<span data-ttu-id="badbd-112">**コマンドの実行中**] ページで、[作業ウィンドウで SQL Server Express をインストールして、中央管理ストアとして機能するように構成するタスクを表示できます。</span><span class="sxs-lookup"><span data-stu-id="badbd-112">On the **Executing commands** page, the tasks of installing the SQL Server Express and configuring to act as the Central Management store can be viewed in the task pane.</span></span> <span data-ttu-id="badbd-113">既定では、RTC をという名前の SQL Server ベースのデータベースのインスタンスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="badbd-113">By default, an instance of a SQL Server-based database named RTC is created.</span></span> <span data-ttu-id="badbd-114">サーバーとデータベース インスタンスと通信するためにクライアントの受信および送信のアクセスを許可するファイアウォール規則が作成されます。</span><span class="sxs-lookup"><span data-stu-id="badbd-114">Firewall rules are also created to allow inbound and outbound access for servers and clients to communicate with the database and instance.</span></span> <span data-ttu-id="badbd-115">タスクが完了したら、ドロップダウン リストからログ ファイルを選択できます。</span><span class="sxs-lookup"><span data-stu-id="badbd-115">After the task is completed, you can select the log file from the drop-down list.</span></span> <span data-ttu-id="badbd-116">ログ ファイルを**ローカル コンピューターのブートス トラップ**といいます。</span><span class="sxs-lookup"><span data-stu-id="badbd-116">The log file is named **Bootstrap local machine**.</span></span> <span data-ttu-id="badbd-117">ログ ファイルを選択すると、**ログの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="badbd-117">After selecting the log file, click **View Log**.</span></span> <span data-ttu-id="badbd-118">エラーと警告のログ ファイルを確認します。</span><span class="sxs-lookup"><span data-stu-id="badbd-118">Review the log file for any errors and warnings.</span></span> <span data-ttu-id="badbd-119">続行する準備ができたらをクリックして**を終了します**。</span><span class="sxs-lookup"><span data-stu-id="badbd-119">When you are ready to proceed, click **Finish.**</span></span> <span data-ttu-id="badbd-120">されていない場合は、ここでトポロジ ビルダーでトポロジを定義してください。</span><span class="sxs-lookup"><span data-stu-id="badbd-120">You should now define your topology with Topology Builder if you have not already done so.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="badbd-121">SQL Server Express のインストールには、完了に時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="badbd-121">The installation of the SQL Server Express can take some time to complete.</span></span> <span data-ttu-id="badbd-122">インストール中は進行状況画面または作業ウィンドウに表示されて、</span><span class="sxs-lookup"><span data-stu-id="badbd-122">During the installation, there is no progress visible on the screen or the task pane.</span></span> <span data-ttu-id="badbd-123">インストールを監視するには、Windows タスク マネージャーを使用して SQL Server の MSIExec プロセスとセットアップ ファイルを探してください。</span><span class="sxs-lookup"><span data-stu-id="badbd-123">To monitor the installation, you should use Windows Task Manager and look for the MSIExec processes and the Setup files for SQL Server.</span></span> <span data-ttu-id="badbd-124">この方法では、インストールのステータスを表示し、インストールが続行であることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="badbd-124">In this way, you can view the status of the install and be sure that the install is proceeding.</span></span> <span data-ttu-id="badbd-125">このヘルプ トピックの範囲外の要因によってファイルに最大 15 分かかるか、複数インストール SQL Server のインスタンス化を完了します。</span><span class="sxs-lookup"><span data-stu-id="badbd-125">Depending on factors beyond the scope of this help topic, it can take up to 15 minutes or more for the install the SQL Server instance to complete.</span></span> 
  

