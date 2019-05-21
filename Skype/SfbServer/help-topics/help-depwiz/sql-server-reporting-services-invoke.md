---
title: SQL Server Reporting Services (起動)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeploySSRSInvoke
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4a4ba8d6-ba43-45b3-b834-372d092561e7
description: 監視サーバーレポートの展開に必要な情報を Microsoft SQL Server 2008 R2、または Microsoft SQL Server 2012 レポートサービスに提供した後、[ページの実行] コマンドには、SQL Server Reporting Services に関するレポート。
ms.openlocfilehash: 5f9fb2a727d9ef43a04b41e247dc421e366170b8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34284789"
---
# <a name="sql-server-reporting-services-invoke"></a><span data-ttu-id="4d82d-103">SQL Server Reporting Services (起動)</span><span class="sxs-lookup"><span data-stu-id="4d82d-103">SQL Server Reporting Services (Invoke)</span></span>
 
<span data-ttu-id="4d82d-104">監視サーバーレポートの展開に必要な情報を Microsoft SQL Server 2008 R2、または Microsoft SQL Server 2012 レポートサービスに提供した後、[ページの実行] コマンドには、SQL Server Reporting Services に関するレポート。</span><span class="sxs-lookup"><span data-stu-id="4d82d-104">After supplying the required information for the deployment of the Monitoring Server reports to the Microsoft SQL Server 2008 R2, or to Microsoft SQL Server 2012 Report Services, the page Execute Commands displays a summary of commands that are issued to install the reports to the SQL Server Reporting Services.</span></span>
  
<span data-ttu-id="4d82d-p101">コマンドの概要を調べ、コマンドによって表示されたエラーまたは警告メッセージがないかどうかを確認します。ログ ファイルが生成された場合は、概要ウィンドウのドロップダウン リストからそのログ ファイルを選択し、[**ログの表示**] をクリックしてログ ファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="4d82d-p101">Review the summary of commands and note any error or warning messages displayed from the commands. If a log file is generated, select the log file from the drop-down list under the summary window, and click **View Log** to display the log file.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="4d82d-107">Reporting Services レポートが正常に展開され、展開が完了した後にレポートにアクセスするには、Windows ファイアウォールで開いた状態で、TCP/IP ポート 80 (および必要に応じて、SSL 用の TCP ポート 443) が必要です。SQL Server の高度なセキュリティを使用しています。</span><span class="sxs-lookup"><span data-stu-id="4d82d-107">For the Reporting Services reports to deploy successfully, and to access the reports after deployment is complete, you must have TCP/IP port 80 (and optionally, TCP port 443 for SSL, if you assign a certificate to the Reporting Services) open in the Windows Firewall with Advanced Security on the SQL Server.</span></span> <span data-ttu-id="4d82d-108">詳細については、「Microsoft SQL server 2008 R2 の[Sql Server アクセスを許可するように Windows ファイアウォールを構成](https://go.microsoft.com/fwlink/p/?linkId=218031)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d82d-108">For details, see [Configure the Windows Firewall to Allow SQL Server Access](https://go.microsoft.com/fwlink/p/?linkId=218031) for Microsoft SQL Server 2008 R2.</span></span>
  
<span data-ttu-id="4d82d-109">概要を確認した後、[**完了**] をクリックして、レポートの SQL Server Reporting Services へのインストールを完了します。</span><span class="sxs-lookup"><span data-stu-id="4d82d-109">After reviewing the summary, click **Finish** to complete the installation of the reports to the SQL Server Reporting Services.</span></span>
  

