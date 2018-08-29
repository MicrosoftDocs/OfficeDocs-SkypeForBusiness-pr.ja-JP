---
title: 監視サーバーの SQL Server ストアを追加します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddMonitoringServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d873a2ad-9d3a-4ef6-9f25-ccdd3716218c
ROBOTS: NOINDEX, NOFOLLOW
description: サーバーの監視には、監視データを格納する SQL Server データベースのソフトウェアのサポートされている 64 ビット版が必要です。 監視に使用する定義済みの SQL Server データベースを選択するか、SQL Server データベースが格納されている、SQL のインスタンスだけでなく、サーバーの完全修飾ドメイン名 (FQDN) を指定することで新しい SQL Server データベースの定義新しい SQL Server データベース (既定のインスタンスまたは名前付きインスタンスを指定することができます) を使用するサーバーです。
ms.openlocfilehash: 8147aa95ef3f4289d95a8c40e6045960de25371a
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2018
ms.locfileid: "23258586"
---
# <a name="add-monitoring-server-sql-server-store"></a><span data-ttu-id="531cd-104">監視サーバーの SQL Server ストアを追加します。</span><span class="sxs-lookup"><span data-stu-id="531cd-104">Add Monitoring Server SQL Server Store</span></span>

<span data-ttu-id="531cd-105">サーバーの監視には、監視データを格納する SQL Server データベースのソフトウェアのサポートされている 64 ビット版が必要です。</span><span class="sxs-lookup"><span data-stu-id="531cd-105">Monitoring Server requires a supported 64-bit edition of SQL Server database software to store the monitoring data.</span></span> <span data-ttu-id="531cd-106">監視に使用する定義済みの SQL Server データベースを選択するか、SQL Server データベースが格納されている、SQL のインスタンスだけでなく、サーバーの完全修飾ドメイン名 (FQDN) を指定することで新しい SQL Server データベースの定義新しい SQL Server データベース (既定のインスタンスまたは名前付きインスタンスを指定することができます) を使用するサーバーです。</span><span class="sxs-lookup"><span data-stu-id="531cd-106">You can either select a previously defined SQL Server database to be used for monitoring, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database will reside, in addition to the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span>

<span data-ttu-id="531cd-107">詳細については SQL Server のサポートは、[データベース ソフトウェアとクラスタ リングをサポート](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx)サポート マニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="531cd-107">For details about SQL Server support, see [Database Software and Clustering Support](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="531cd-108">監視データベースのコロケーションを含め、監視データベースの詳細について計画マニュアルと[のデータを SQL Server の[監視を計画](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)、サポート ドキュメントで[サポートされているサーバーの場所](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx)を参照してください。ログ ファイルの配置](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)の展開に関するドキュメントです。</span><span class="sxs-lookup"><span data-stu-id="531cd-108">For details about the monitoring database, including collocation of the monitoring database, see [Supported Server Location](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) in the Supportability documentation,[Planning for Monitoring](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) in the Planning documentation and [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span>

> [!NOTE]
> <span data-ttu-id="531cd-109">トポロジを公開するために使用するアカウントに適切なユーザー権利とアクセス許可がある場合、トポロジを公開すると、監視データベースを作成できます。</span><span class="sxs-lookup"><span data-stu-id="531cd-109">If the account used to publish the topology has the appropriate user rights and permissions, you can create the monitoring database when you publish your topology.</span></span> <span data-ttu-id="531cd-110">インストール手順の一部として含め、後でデータベースを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="531cd-110">You can also create the database later, including as part of the installation procedure.</span></span> <span data-ttu-id="531cd-111">> をインストールし、監視するための SQL Server ベースのサーバー上のデータベースを展開、データベース ファイルをインストールしている SQL Server ベースのサーバーの SQL Server システム管理者グループのメンバーをする必要があります。</span><span class="sxs-lookup"><span data-stu-id="531cd-111">> To install and deploy the databases on the SQL Server-based server for monitoring, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="531cd-112">SQL Server の sysadmin グループのメンバーでない場合は、データベース ファイルを展開するまでに、グループに追加する要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="531cd-112">If you are not a member of the SQL Server sysadmin group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="531cd-113">システム管理者グループのメンバーにすることはできません、スクリプトを構成して、データベースを配置すると、SQL Server データベースの管理者を入力してください。</span><span class="sxs-lookup"><span data-stu-id="531cd-113">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="531cd-114">これらの手順を実行する必要があるアクセス許可とユーザー権利の詳細については、展開に関するドキュメントで[SQL Server の展開のアクセス許可](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="531cd-114">For details about the user rights and permissions that you need to accomplish these procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in the Deployment documentation.</span></span>


