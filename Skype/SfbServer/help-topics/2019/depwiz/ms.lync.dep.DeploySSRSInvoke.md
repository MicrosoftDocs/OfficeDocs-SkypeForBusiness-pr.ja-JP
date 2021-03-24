---
title: SQL Server Reporting Services (起動)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 監視サーバー レポートの展開に必要な情報を Microsoft SQL Server 2008 R2、または Microsoft SQL Server 2012 レポート サービスに提供すると、[コマンドの実行] ページに、SQL Server Reporting Services にレポートをインストールするために発行されたコマンドの概要が表示されます。
ms.openlocfilehash: 17824f79ab0d710d4969d736b864912b424abaa9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109663"
---
# <a name="sql-server-reporting-services-invoke"></a>SQL Server Reporting Services (起動)
 
監視サーバー レポートの展開に必要な情報を Microsoft SQL Server レポート サービスに提供すると、[コマンドの実行] ページに、SQL Server Reporting Services にレポートをインストールするために発行されたコマンドの概要が表示されます。
  
コマンドの概要を調べ、コマンドよって表示されたエラーまたは警告メッセージがないかどうか確認してください。ログ ファイルが生成された場合は、概要ウィンドウのドロップダウン リストからそのログ ファイルを選択し、**[ログの表示]** をクリックしてログ ファイルを表示します。
  
> [!IMPORTANT]
> Reporting Services レポートが正常に展開され、展開が完了した後にレポートにアクセスするには、TCP/IP ポート 80 (および必要に応じて、証明書を Reporting Services に割り当てる場合は、SSL 用 TCP ポート 443) が SQL Server の Windows ファイアウォールで開いている必要があります。 詳細については [、「Configure the Windows Firewall to](/sql/sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access) Allow the Allow SQL Server Access for Microsoft SQL Server 2008 R2」を参照してください。
  
概要を確認したら、[完了] **をクリック** して、レポートのインストールを [レポート サービス] SQL Server完了します。
