---
title: SQL Server Reporting Services (起動)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeploySSRSInvoke
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4a4ba8d6-ba43-45b3-b834-372d092561e7
description: 監視サーバー レポートの展開に必要な情報を Microsoft SQL Server 2008 R2、または Microsoft SQL Server 2012 レポート サービスに提供すると、[コマンドの実行] ページに、SQL Server Reporting Services にレポートをインストールするために発行されたコマンドの概要が表示されます。
ms.openlocfilehash: b861db053a8851b05ce72a08de6dfae39b9d3bfc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096853"
---
# <a name="sql-server-reporting-services-invoke"></a><span data-ttu-id="3f2b9-103">SQL Server Reporting Services (起動)</span><span class="sxs-lookup"><span data-stu-id="3f2b9-103">SQL Server Reporting Services (Invoke)</span></span>
 
<span data-ttu-id="3f2b9-104">監視サーバー レポートの展開に必要な情報を Microsoft SQL Server 2008 R2、または Microsoft SQL Server 2012 レポート サービスに提供すると、[コマンドの実行] ページに、SQL Server Reporting Services にレポートをインストールするために発行されたコマンドの概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3f2b9-104">After supplying the required information for the deployment of the Monitoring Server reports to the Microsoft SQL Server 2008 R2, or to Microsoft SQL Server 2012 Report Services, the page Execute Commands displays a summary of commands that are issued to install the reports to the SQL Server Reporting Services.</span></span>
  
<span data-ttu-id="3f2b9-p101">コマンドの概要を調べ、コマンドよって表示されたエラーまたは警告メッセージがないかどうか確認してください。ログ ファイルが生成された場合は、概要ウィンドウのドロップダウン リストからそのログ ファイルを選択し、**[ログの表示]** をクリックしてログ ファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="3f2b9-p101">Review the summary of commands and note any error or warning messages displayed from the commands. If a log file is generated, select the log file from the drop-down list under the summary window, and click **View Log** to display the log file.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="3f2b9-107">Reporting Services レポートが正常に展開され、展開が完了した後にレポートにアクセスするには、TCP/IP ポート 80 (および必要に応じて、証明書を Reporting Services に割り当てる場合は、SSL 用 TCP ポート 443) が SQL Server の Windows ファイアウォールで開いている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f2b9-107">For the Reporting Services reports to deploy successfully, and to access the reports after deployment is complete, you must have TCP/IP port 80 (and optionally, TCP port 443 for SSL, if you assign a certificate to the Reporting Services) open in the Windows Firewall with Advanced Security on the SQL Server.</span></span> <span data-ttu-id="3f2b9-108">詳細については [、「Configure the Windows Firewall to](/sql/sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access) Allow the Allow SQL Server Access for Microsoft SQL Server 2008 R2」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f2b9-108">For details, see [Configure the Windows Firewall to Allow SQL Server Access](/sql/sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access) for Microsoft SQL Server 2008 R2.</span></span>
  
<span data-ttu-id="3f2b9-109">概要を確認したら、[完了] **をクリック** して、レポートのインストールを [レポート サービス] SQL Server完了します。</span><span class="sxs-lookup"><span data-stu-id="3f2b9-109">After reviewing the summary, click **Finish** to complete the installation of the reports to the SQL Server Reporting Services.</span></span>
