---
title: 監視サーバー SQL Server ストアの追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddMonitoringServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d873a2ad-9d3a-4ef6-9f25-ccdd3716218c
ROBOTS: NOINDEX, NOFOLLOW
description: Monitoring Server には、監視データを保存するために、サポートされている64ビット版の SQL Server データベースソフトウェアが必要です。 監視に使用するために定義済みの SQL Server データベースを選択するか、sql Server データベースが存在するサーバーの完全修飾ドメイン名 (FQDN) を指定して新しい sql Server データベースを定義することができます。また、SQL server データベースは、SQL のインスタンスにも含まれます。新しい SQL Server データベースに使用するサーバー (既定のインスタンス、または指定した名前付きインスタンスのいずれか)。
ms.openlocfilehash: 406c1da490506ec3cc762deb388162534084451a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306182"
---
# <a name="add-monitoring-server-sql-server-store"></a><span data-ttu-id="a5269-104">監視サーバー SQL Server ストアの追加</span><span class="sxs-lookup"><span data-stu-id="a5269-104">Add Monitoring Server SQL Server Store</span></span>

<span data-ttu-id="a5269-105">Monitoring Server には、監視データを保存するために、サポートされている64ビット版の SQL Server データベースソフトウェアが必要です。</span><span class="sxs-lookup"><span data-stu-id="a5269-105">Monitoring Server requires a supported 64-bit edition of SQL Server database software to store the monitoring data.</span></span> <span data-ttu-id="a5269-106">監視に使用するために定義済みの SQL Server データベースを選択するか、sql Server データベースが存在するサーバーの完全修飾ドメイン名 (FQDN) を指定して新しい sql Server データベースを定義することができます。また、SQL server データベースは、SQL のインスタンスにも含まれます。新しい SQL Server データベースに使用するサーバー (既定のインスタンス、または指定した名前付きインスタンスのいずれか)。</span><span class="sxs-lookup"><span data-stu-id="a5269-106">You can either select a previously defined SQL Server database to be used for monitoring, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database will reside, in addition to the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span>

<span data-ttu-id="a5269-107">SQL Server のサポートについて詳しくは、「サポートドキュメント」の「[データベースソフトウェアとクラスタリングのサポート](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a5269-107">For details about SQL Server support, see [Database Software and Clustering Support](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="a5269-108">監視データベースの collocation などの監視データベースの詳細については、「[サポートされているサーバーの場所](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx)」を参照してください。計画ドキュメントおよび SQL Server データでの[監視の計画](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) [展開ドキュメントにファイルの配置を記録し](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)ます。</span><span class="sxs-lookup"><span data-stu-id="a5269-108">For details about the monitoring database, including collocation of the monitoring database, see [Supported Server Location](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) in the Supportability documentation,[Planning for Monitoring](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) in the Planning documentation and [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span>

> [!NOTE]
> <span data-ttu-id="a5269-109">トポロジの公開に使用したアカウントに適切なユーザー権限と権限がある場合は、トポロジを公開するときに監視データベースを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="a5269-109">If the account used to publish the topology has the appropriate user rights and permissions, you can create the monitoring database when you publish your topology.</span></span> <span data-ttu-id="a5269-110">また、インストール手順の一部として、後でデータベースを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="a5269-110">You can also create the database later, including as part of the installation procedure.</span></span> <span data-ttu-id="a5269-111">> を監視するために SQL Server ベースのサーバーにデータベースをインストールして展開するには、データベースファイルをインストールする SQL server ベースのサーバーの SQL Server 管理者グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5269-111">> To install and deploy the databases on the SQL Server-based server for monitoring, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="a5269-112">SQL Server sysadmin グループのメンバーでない場合は、データベースファイルが展開されるまで、グループに追加するように依頼する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5269-112">If you are not a member of the SQL Server sysadmin group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="a5269-113">[管理者] グループのメンバーになることができない場合は、SQL Server データベース管理者に、データベースを構成して展開するためのスクリプトを用意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5269-113">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="a5269-114">これらの手順を実行するために必要なユーザー権限と権限の詳細については、「展開ドキュメントの[SQL Server の展開権限](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5269-114">For details about the user rights and permissions that you need to accomplish these procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in the Deployment documentation.</span></span>


