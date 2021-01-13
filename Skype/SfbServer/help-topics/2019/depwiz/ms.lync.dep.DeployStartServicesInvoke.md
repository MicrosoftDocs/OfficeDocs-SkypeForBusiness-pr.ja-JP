---
title: サービスの開始 (起動)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: '[コマンドの実行] ウィンドウの概要ウィンドウには、展開する Skype for Business Server 役割サーバーのサービスを開始するために発行されたタスクの状態が表示されます。'
ms.openlocfilehash: 34e128fd5c879c80e3e3eb242cd654b19c5f6dd3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808777"
---
# <a name="start-services-invoke"></a><span data-ttu-id="35d2b-103">サービスの開始 (起動)</span><span class="sxs-lookup"><span data-stu-id="35d2b-103">Start Services (Invoke)</span></span>
 
<span data-ttu-id="35d2b-104">[コマンドの実行]ウィンドウの概要ウィンドウには、展開している Skype for Business Server 役割サーバーのサービスを開始するために発行されたタスクの状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="35d2b-104">The summary pane on the **Executing Commands** pane displays the status of the tasks issued to start the services for the Skype for Business Server role server that you are deploying.</span></span> <span data-ttu-id="35d2b-105">作業ウィンドウの概要には、サービス開始のリアルタイムの表示は行われません。</span><span class="sxs-lookup"><span data-stu-id="35d2b-105">The summary in the task pane does not represent a real-time indication of service startup.</span></span> <span data-ttu-id="35d2b-106">一部の Skype for Business Server サービスでは、初期スタートアップ プロセスの開始に時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="35d2b-106">Some of the Skype for Business Server services may take an extended time to begin the initial startup process.</span></span> <span data-ttu-id="35d2b-107">タスクは、開始のコマンドを発行していますが、サービスが正常に開始されたかどうかを確認するようには待機していません。</span><span class="sxs-lookup"><span data-stu-id="35d2b-107">The tasks are issuing the command to start, but do not wait to determine if the service is successfully started.</span></span> <span data-ttu-id="35d2b-108">サービスの開始とサービスの状態を監視する必要がある場合は、Windows サービス Microsoft 管理コンソール (MMC) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35d2b-108">If you must monitor the service startup and service status, you should use the Windows Services Microsoft Management Console (MMC).</span></span>
  
<span data-ttu-id="35d2b-p102">作業ウィンドウの下に、[**サービスの開始**] ログ ファイルを表示するドロップダウン リストがあります。ログ ファイルを表示するには、[**ログの表示**] をクリックします。タスクを完了するには、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="35d2b-p102">Under the task pane is a drop-down list that displays the **Start Services** log file. To view the log file, click **View Log**. Click **Finish** to complete the task.</span></span>
  

