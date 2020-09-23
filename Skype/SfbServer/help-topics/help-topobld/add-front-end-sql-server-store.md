---
title: フロントエンド SQL Server ストアの追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dace9561-3eb4-4647-83cb-56c246919ae1
description: Standard Edition サーバーの展開では、必要な Microsoft SQL Server Express データベースソフトウェアと SQL Server データベースが自動的にインストールされます。 そのため、すべてのオプションが事前に設定されており、既定の構成を変更することはできません。
ms.openlocfilehash: 614c3a852bb52a73c8a3f71ee467a2d71f82e9b6
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216498"
---
# <a name="add-front-end-sql-server-store"></a><span data-ttu-id="1b3e3-104">フロントエンド SQL Server ストアの追加</span><span class="sxs-lookup"><span data-stu-id="1b3e3-104">Add Front End SQL Server Store</span></span>

<span data-ttu-id="1b3e3-105">Standard Edition サーバーの展開では、必要な Microsoft SQL Server Express データベースソフトウェアと SQL Server データベースが自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="1b3e3-105">A Standard Edition server deployment automatically installs the required Microsoft SQL Server Express database software and SQL Server database.</span></span> <span data-ttu-id="1b3e3-106">そのため、すべてのオプションが事前に設定されており、既定の構成を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="1b3e3-106">Therefore, all options are prepopulated, and you can't make changes to the default configuration.</span></span>

<span data-ttu-id="1b3e3-107">Enterprise Edition サーバー展開のフロントエンドプールでは、バックエンドデータベース用にサポートされている64ビット版の SQL Server データベースソフトウェアが必要です。</span><span class="sxs-lookup"><span data-stu-id="1b3e3-107">The Front End pool of an Enterprise Edition server deployment requires a supported 64-bit edition of the SQL Server database software for the back-end database.</span></span> <span data-ttu-id="1b3e3-108">以前に定義した SQL Server データベースをバックエンドデータベースに使用するように選択するか、または SQL server データベースを配置するサーバーの完全修飾ドメイン名 (FQDN) を指定して新しい SQL Server データベースを定義するか、または新しい sql server データベースで使用する SQL server のインスタンス (既定のインスタンスにすることができます。、または指定した名前付きインスタンス)。</span><span class="sxs-lookup"><span data-stu-id="1b3e3-108">You can either select a previously defined SQL Server database to be used for the back-end database, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database is to reside, and the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span> <span data-ttu-id="1b3e3-109">また、SQL Server ストアでミラーリングを有効にし、自動フェールオーバーのミラーリング監視を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="1b3e3-109">You can also choose to enable mirroring on the SQL Server store, and specify a mirroring witness for automatic failover.</span></span>

<span data-ttu-id="1b3e3-110">SQL Server のサポートの詳細については、「サポート」のドキュメントの「 [データベースソフトウェアとクラスタリングのサポート](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b3e3-110">For details about SQL Server support, see [Database Software and Clustering Support](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="1b3e3-111">バックエンド データベース用の SQL Server の設定の詳細については、「展開」のドキュメントの「[Lync Server 2010 用 SQL Server の構成](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b3e3-111">For details about setting up SQL Server for the back-end database, see [Configure SQL Server for Lync Server 2010](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) in the Deployment documentation.</span></span>

> [!NOTE]
> <span data-ttu-id="1b3e3-112">トポロジの公開に使用されるアカウントに適切なユーザー権限とアクセス許可がある場合は、トポロジを公開するときにバックエンドデータベース (リアルタイム通信 (RTC)) を作成できます。</span><span class="sxs-lookup"><span data-stu-id="1b3e3-112">If the account that is used to publish the topology has the appropriate user rights and permissions, you can create the back-end database (real-time communications (RTC)) when you publish your topology.</span></span> <span data-ttu-id="1b3e3-113">インストール手順の一部を含め、データベースを後で作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="1b3e3-113">You can also create the database later, including as part of the installation procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="1b3e3-114">Enterprise Edition 展開用の SQL Server ベースのサーバーにデータベースをインストールして展開するには、データベースファイルをインストールする sql server ベースのサーバーの SQL server 管理者グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b3e3-114">To install and deploy the databases on the SQL Server-based server for an Enterprise Edition deployment, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="1b3e3-115">SQL Server の [ユーザー] グループのメンバーでない場合は、データベースファイルが展開されるまで、グループに追加するよう要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b3e3-115">If you are not a member of the SQL Server sysadmins group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="1b3e3-116">システム管理者グループのメンバーになることができない場合は、データベースを構成および展開するためのスクリプトを SQL Server データベース管理者に提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b3e3-116">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="1b3e3-117">手順を実行するために必要なユーザー権限とアクセス許可の詳細については、「 [SQL Server の展開権限](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b3e3-117">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx).</span></span>


