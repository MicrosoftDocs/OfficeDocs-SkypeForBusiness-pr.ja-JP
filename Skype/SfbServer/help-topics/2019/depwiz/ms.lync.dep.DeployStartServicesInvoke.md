---
title: サービスの開始 (起動)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployStartServicesInvoke
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 7992440b-8545-4af9-b3ac-ea200b9de084
ROBOTS: NOINDEX, NOFOLLOW
description: '[コマンド実行] ウィンドウの [概要] ウィンドウには、展開している Skype for Business Server ロールサーバーのサービスを開始するために発行されたタスクの状態が表示されます。'
ms.openlocfilehash: 50d161c024b7e85e995cdde407ec380125e5b318
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794626"
---
# <a name="start-services-invoke"></a><span data-ttu-id="b9a96-103">サービスの開始 (起動)</span><span class="sxs-lookup"><span data-stu-id="b9a96-103">Start Services (Invoke)</span></span>
 
<span data-ttu-id="b9a96-104">[**コマンド実行**] ウィンドウの [概要] ウィンドウには、展開している Skype For business server ロールサーバーのサービスを開始するために発行されたタスクの状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b9a96-104">The summary pane on the **Executing Commands** pane displays the status of the tasks issued to start the services for the Skype for Business Server role server that you are deploying.</span></span> <span data-ttu-id="b9a96-105">作業ウィンドウの概要には、サービス開始のリアルタイムの表示は行われません。</span><span class="sxs-lookup"><span data-stu-id="b9a96-105">The summary in the task pane does not represent a real-time indication of service startup.</span></span> <span data-ttu-id="b9a96-106">一部の Skype for Business Server サービスでは、最初のスタートアッププロセスが開始されるまでに時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b9a96-106">Some of the Skype for Business Server services may take an extended time to begin the initial startup process.</span></span> <span data-ttu-id="b9a96-107">タスクは、開始のコマンドを発行していますが、サービスが正常に開始されたかどうかを確認するために待機はしません。</span><span class="sxs-lookup"><span data-stu-id="b9a96-107">The tasks are issuing the command to start, but do not wait to determine if the service is successfully started.</span></span> <span data-ttu-id="b9a96-108">サービスの開始とサービスの状態を監視する必要がある場合は、Windows サービス Microsoft 管理コンソール (MMC) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9a96-108">If you must monitor the service startup and service status, you should use the Windows Services Microsoft Management Console (MMC).</span></span>
  
<span data-ttu-id="b9a96-p102">作業ウィンドウの下に、[**サービスの開始**] ログ ファイルを表示するドロップダウン リストがあります。ログ ファイルを表示するには、[**ログの表示**] をクリックします。タスクを完了するには、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9a96-p102">Under the task pane is a drop-down list that displays the **Start Services** log file. To view the log file, click **View Log**. Click **Finish** to complete the task.</span></span>
  

