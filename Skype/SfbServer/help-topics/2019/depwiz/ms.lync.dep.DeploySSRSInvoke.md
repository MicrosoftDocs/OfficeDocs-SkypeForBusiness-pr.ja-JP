---
title: SQL Server Reporting Services (起動)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeploySSRSInvoke
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 4a4ba8d6-ba43-45b3-b834-372d092561e7
ROBOTS: NOINDEX, NOFOLLOW
description: 監視サーバーレポートの展開に必要な情報を Microsoft SQL Server 2008 R2、または Microsoft SQL Server 2012 レポートサービスに提供した後、[ページの実行] コマンドには、SQL Server Reporting Services に関するレポート。
ms.openlocfilehash: 30e97757c8ad66df9f706b6bf74549e8f1eec65f
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794676"
---
# <a name="sql-server-reporting-services-invoke"></a><span data-ttu-id="4c3a7-103">SQL Server Reporting Services (起動)</span><span class="sxs-lookup"><span data-stu-id="4c3a7-103">SQL Server Reporting Services (Invoke)</span></span>
 
<span data-ttu-id="4c3a7-104">監視サーバーレポートの展開に必要な情報を Microsoft SQL Server レポートサービスに提供した後、[ページの実行] コマンドに、レポートを SQL Server レポートにインストールするために発行されたコマンドの概要が表示されます。サービス.</span><span class="sxs-lookup"><span data-stu-id="4c3a7-104">After supplying the required information for the deployment of the Monitoring Server reports to the Microsoft SQL Server Report Services, the page Execute Commands displays a summary of commands that are issued to install the reports to the SQL Server Reporting Services.</span></span>
  
<span data-ttu-id="4c3a7-p101">コマンドの概要を調べ、コマンドによって表示されたエラーまたは警告メッセージがないかどうかを確認します。ログ ファイルが生成された場合は、概要ウィンドウのドロップダウン リストからそのログ ファイルを選択し、[**ログの表示**] をクリックしてログ ファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="4c3a7-p101">Review the summary of commands and note any error or warning messages displayed from the commands. If a log file is generated, select the log file from the drop-down list under the summary window, and click **View Log** to display the log file.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="4c3a7-107">Reporting Services レポートが正常に展開され、展開が完了した後にレポートにアクセスするには、SQL Server のセキュリティが強化された Windows ファイアウォールで、TCP/IP ポート 80 (および必要に応じて、SSL 用の TCP ポート 443) を使用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c3a7-107">For the Reporting Services reports to deploy successfully, and to access the reports after deployment is complete, you must have TCP/IP port 80 (and optionally, TCP port 443 for SSL, if you assign a certificate to the Reporting Services) open in the Windows Firewall with Advanced Security on the SQL Server.</span></span> <span data-ttu-id="4c3a7-108">詳細については、「Microsoft SQL server 2008 R2 の[Sql Server アクセスを許可するように Windows ファイアウォールを構成](https://go.microsoft.com/fwlink/p/?linkId=218031)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c3a7-108">For details, see [Configure the Windows Firewall to Allow SQL Server Access](https://go.microsoft.com/fwlink/p/?linkId=218031) for Microsoft SQL Server 2008 R2.</span></span>
  
<span data-ttu-id="4c3a7-109">概要を確認した後、[**完了**] をクリックして、レポートの SQL Server Reporting Services へのインストールを完了します。</span><span class="sxs-lookup"><span data-stu-id="4c3a7-109">After reviewing the summary, click **Finish** to complete the installation of the reports to the SQL Server Reporting Services.</span></span>
  

