---
title: サービスの開始 (起動)
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployStartServicesInvoke
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7992440b-8545-4af9-b3ac-ea200b9de084
ROBOTS: NOINDEX, NOFOLLOW
description: コマンドの実行中のウィンドウの [概要] パネルには、ビジネスのサーバーの役割を持つサーバーを展開することで Skype のサービスを開始するに発行されたタスクのステータスが表示されます。
ms.openlocfilehash: db2e0282e15b1995aa6b83bcfdd4ecbecd922207
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32215956"
---
# <a name="start-services-invoke"></a><span data-ttu-id="6796b-103">サービスの開始 (起動)</span><span class="sxs-lookup"><span data-stu-id="6796b-103">Start Services (Invoke)</span></span>
 
<span data-ttu-id="6796b-104">**コマンドの実行中**のウィンドウの [概要] パネルには、ビジネスのサーバーの役割を持つサーバーを展開することで Skype のサービスを開始するに発行されたタスクのステータスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6796b-104">The summary pane on the **Executing Commands** pane displays the status of the tasks issued to start the services for the Skype for Business Server role server that you are deploying.</span></span> <span data-ttu-id="6796b-105">作業ウィンドウの概要には、サービス開始のリアルタイムの表示は行われません。</span><span class="sxs-lookup"><span data-stu-id="6796b-105">The summary in the task pane does not represent a real-time indication of service startup.</span></span> <span data-ttu-id="6796b-106">ビジネス サーバー サービスの Skype の初期起動処理を開始するのには長時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6796b-106">Some of the Skype for Business Server services may take an extended time to begin the initial startup process.</span></span> <span data-ttu-id="6796b-107">タスクは、開始のコマンドを発行していますが、サービスが正常に開始されたかどうかを確認するために待機はしません。</span><span class="sxs-lookup"><span data-stu-id="6796b-107">The tasks are issuing the command to start, but do not wait to determine if the service is successfully started.</span></span> <span data-ttu-id="6796b-108">サービスの開始とサービスの状態を監視する必要がある場合は、Windows サービス Microsoft 管理コンソール (MMC) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6796b-108">If you must monitor the service startup and service status, you should use the Windows Services Microsoft Management Console (MMC).</span></span>
  
<span data-ttu-id="6796b-p102">作業ウィンドウの下に、[**サービスの開始**] ログ ファイルを表示するドロップダウン リストがあります。ログ ファイルを表示するには、[**ログの表示**] をクリックします。タスクを完了するには、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6796b-p102">Under the task pane is a drop-down list that displays the **Start Services** log file. To view the log file, click **View Log**. Click **Finish** to complete the task.</span></span>
  

