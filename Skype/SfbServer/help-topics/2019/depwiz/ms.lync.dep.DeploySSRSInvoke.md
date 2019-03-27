---
title: SQL Server Reporting Services (起動)
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeploySSRSInvoke
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4a4ba8d6-ba43-45b3-b834-372d092561e7
ROBOTS: NOINDEX, NOFOLLOW
description: 監視サーバーの展開を Microsoft SQL Server 2008 r2 でレポートまたは表示するのには Microsoft SQL Server 2012 レポート サービスでは、ページを実行するコマンドをインストールするのには、発行するコマンドの概要について必要な情報を入力したら、SQL Server Reporting Services にレポートします。
ms.openlocfilehash: 6457d17a3e8fff4d93aeedb5f7526c23ccc5b064
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30877162"
---
# <a name="sql-server-reporting-services-invoke"></a><span data-ttu-id="b77ca-103">SQL Server Reporting Services (起動)</span><span class="sxs-lookup"><span data-stu-id="b77ca-103">SQL Server Reporting Services (Invoke)</span></span>
 
<span data-ttu-id="b77ca-104">後に Microsoft SQL Server レポート サービス サーバーの監視レポートを展開するため必要な情報を指定するには、ページの実行コマンドには、SQL Server レポートにレポートをインストールするのには実行されるコマンドの概要が表示されます。サービスです。</span><span class="sxs-lookup"><span data-stu-id="b77ca-104">After supplying the required information for the deployment of the Monitoring Server reports to the Microsoft SQL Server Report Services, the page Execute Commands displays a summary of commands that are issued to install the reports to the SQL Server Reporting Services.</span></span>
  
<span data-ttu-id="b77ca-p101">コマンドの概要を調べ、コマンドによって表示されたエラーまたは警告メッセージがないかどうかを確認します。ログ ファイルが生成された場合は、概要ウィンドウのドロップダウン リストからそのログ ファイルを選択し、[**ログの表示**] をクリックしてログ ファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="b77ca-p101">Review the summary of commands and note any error or warning messages displayed from the commands. If a log file is generated, select the log file from the drop-down list under the summary window, and click **View Log** to display the log file.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b77ca-107">Reporting Services レポートを配置して、展開が完了した後、レポートにアクセスするため、TCP/IP を設定する必要があります Windows ファイアウォールでポート 80 (および必要に応じて、ssl では、証明書を割り当てるには、Reporting Services には、TCP ポート 443) を開くSQL Server のセキュリティが強化。</span><span class="sxs-lookup"><span data-stu-id="b77ca-107">For the Reporting Services reports to deploy successfully, and to access the reports after deployment is complete, you must have TCP/IP port 80 (and optionally, TCP port 443 for SSL, if you assign a certificate to the Reporting Services) open in the Windows Firewall with Advanced Security on the SQL Server.</span></span> <span data-ttu-id="b77ca-108">詳細については、Microsoft SQL Server 2008 の R2 の[SQL Server アクセスを許可するように Windows ファイアウォールを構成する](https://go.microsoft.com/fwlink/p/?linkId=218031)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b77ca-108">For details, see [Configure the Windows Firewall to Allow SQL Server Access](https://go.microsoft.com/fwlink/p/?linkId=218031) for Microsoft SQL Server 2008 R2.</span></span>
  
<span data-ttu-id="b77ca-109">概要を確認するには、レポートの SQL Server レポート サービスのインストールを完了する**完了**ををクリックします。</span><span class="sxs-lookup"><span data-stu-id="b77ca-109">After reviewing the summary, click **Finish** to complete the installation of the reports to the SQL Server Reporting Services.</span></span>
  

