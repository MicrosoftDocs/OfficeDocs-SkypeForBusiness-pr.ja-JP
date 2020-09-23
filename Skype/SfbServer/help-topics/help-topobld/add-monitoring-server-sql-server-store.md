---
title: 監視サーバー SQL Server ストアを追加する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddMonitoringServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d873a2ad-9d3a-4ef6-9f25-ccdd3716218c
description: 監視サーバーには、監視データを格納するために、64ビット版の SQL Server データベースソフトウェアがサポートされている必要があります。 以前に定義した SQL Server データベースを監視に使用するように選択するか、または SQL server データベースが存在するサーバーの完全修飾ドメイン名 (FQDN) を指定することによって、新しい sql server データベースを定義することができます。これは、新しい SQL Server データベースで使用する SQL Server のインスタンス (既定のインスタンス) です。、または指定した名前付きインスタンス)。
ms.openlocfilehash: adeb5385b385345163d7dc99b0a652837ab8bca4
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217898"
---
# <a name="add-monitoring-server-sql-server-store"></a><span data-ttu-id="4c634-104">監視サーバー SQL Server ストアを追加する</span><span class="sxs-lookup"><span data-stu-id="4c634-104">Add Monitoring Server SQL Server Store</span></span>

<span data-ttu-id="4c634-105">監視サーバーには、監視データを格納するために、64ビット版の SQL Server データベースソフトウェアがサポートされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c634-105">Monitoring Server requires a supported 64-bit edition of SQL Server database software to store the monitoring data.</span></span> <span data-ttu-id="4c634-106">以前に定義した SQL Server データベースを監視に使用するように選択するか、または SQL server データベースが存在するサーバーの完全修飾ドメイン名 (FQDN) を指定することによって、新しい sql server データベースを定義することができます。これは、新しい SQL Server データベースで使用する SQL Server のインスタンス (既定のインスタンス) です。、または指定した名前付きインスタンス)。</span><span class="sxs-lookup"><span data-stu-id="4c634-106">You can either select a previously defined SQL Server database to be used for monitoring, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database will reside, in addition to the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span>

<span data-ttu-id="4c634-107">SQL Server のサポートの詳細については、「サポート」のドキュメントの「 [データベースソフトウェアとクラスタリングのサポート](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c634-107">For details about SQL Server support, see [Database Software and Clustering Support](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="4c634-108">監視データベースの詳細については、「サポート」のドキュメントの「 [サポートされるサーバーの場所](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) 」を参照してください。「計画」のドキュメントの「[監視の計画](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) 」、および「展開」のドキュメントの「planning for Monitoring」および「 [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c634-108">For details about the monitoring database, including collocation of the monitoring database, see [Supported Server Location](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) in the Supportability documentation,[Planning for Monitoring](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) in the Planning documentation and [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span>

> [!NOTE]
> <span data-ttu-id="4c634-109">トポロジを公開するために使用するアカウントに適切なユーザー権限とアクセス許可がある場合、トポロジを公開するときに監視データベースを作成できます。</span><span class="sxs-lookup"><span data-stu-id="4c634-109">If the account used to publish the topology has the appropriate user rights and permissions, you can create the monitoring database when you publish your topology.</span></span> <span data-ttu-id="4c634-110">インストール手順の一部として、データベースを後で作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="4c634-110">You can also create the database later, including as part of the installation procedure.</span></span> <span data-ttu-id="4c634-111">監視用に SQL Server ベースのサーバーにデータベースをインストールして展開する > は、データベースファイルをインストールする SQL server ベースのサーバーの SQL Server 管理者グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c634-111">> To install and deploy the databases on the SQL Server-based server for monitoring, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="4c634-112">SQL Server sysadmin グループのメンバーではない場合は、データベースファイルが展開されるまで、グループへの追加を要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c634-112">If you are not a member of the SQL Server sysadmin group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="4c634-113">システム管理者グループのメンバーになることができない場合は、データベースを構成および展開するためのスクリプトを SQL Server データベース管理者に提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c634-113">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="4c634-114">これらの手順を実行するために必要なユーザー権限およびアクセス許可の詳細については、「展開」ドキュメントの「[Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c634-114">For details about the user rights and permissions that you need to accomplish these procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in the Deployment documentation.</span></span>


