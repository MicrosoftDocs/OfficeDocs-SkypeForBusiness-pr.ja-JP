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
- NOCSH
ms.custom:
- ms.lync.tb.AddFrontEndSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dace9561-3eb4-4647-83cb-56c246919ae1
description: Standard Edition サーバーの展開では、必要な Microsoft SQL Server Express データベースソフトウェアと SQL Server データベースが自動的にインストールされます。 そのため、すべてのオプションがあらかじめ設定されているため、既定の構成を変更することはできません。
ms.openlocfilehash: 865f9a63902124c57232ba8d8c591622dcbfd84a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820819"
---
# <a name="add-front-end-sql-server-store"></a><span data-ttu-id="3c3ac-104">フロントエンド SQL Server ストアの追加</span><span class="sxs-lookup"><span data-stu-id="3c3ac-104">Add Front End SQL Server Store</span></span>

<span data-ttu-id="3c3ac-105">Standard Edition サーバーの展開では、必要な Microsoft SQL Server Express データベースソフトウェアと SQL Server データベースが自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="3c3ac-105">A Standard Edition server deployment automatically installs the required Microsoft SQL Server Express database software and SQL Server database.</span></span> <span data-ttu-id="3c3ac-106">そのため、すべてのオプションがあらかじめ設定されているため、既定の構成を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="3c3ac-106">Therefore, all options are prepopulated, and you can't make changes to the default configuration.</span></span>

<span data-ttu-id="3c3ac-107">Enterprise Edition server 展開のフロントエンドプールには、バックエンドデータベース用の SQL Server データベースソフトウェアのサポートされている64ビット版が必要です。</span><span class="sxs-lookup"><span data-stu-id="3c3ac-107">The Front End pool of an Enterprise Edition server deployment requires a supported 64-bit edition of the SQL Server database software for the back-end database.</span></span> <span data-ttu-id="3c3ac-108">バックエンドデータベースとして使用するために定義済みの SQL Server データベースを選ぶか、SQL Server データベースが配置されているサーバーの完全修飾ドメイン名 (FQDN) を指定して新しい sql Server データベースを定義するか、SQL S のインスタンスを指定することができます。新しい SQL Server データベース (既定のインスタンスまたは指定した名前付きインスタンス) として使用するサーバー。</span><span class="sxs-lookup"><span data-stu-id="3c3ac-108">You can either select a previously defined SQL Server database to be used for the back-end database, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database is to reside, and the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span> <span data-ttu-id="3c3ac-109">SQL Server ストアでミラーリングを有効にし、自動フェールオーバーのミラーリング監視を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="3c3ac-109">You can also choose to enable mirroring on the SQL Server store, and specify a mirroring witness for automatic failover.</span></span>

<span data-ttu-id="3c3ac-110">SQL Server のサポートについて詳しくは、「サポートドキュメント」の「[データベースソフトウェアとクラスタリングのサポート](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3c3ac-110">For details about SQL Server support, see [Database Software and Clustering Support](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="3c3ac-111">バックエンドデータベース用の SQL Server のセットアップの詳細については、展開ドキュメントの「 [Lync server 2010 用に Sql server を構成する](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c3ac-111">For details about setting up SQL Server for the back-end database, see [Configure SQL Server for Lync Server 2010](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) in the Deployment documentation.</span></span>

> [!NOTE]
> <span data-ttu-id="3c3ac-112">トポロジを公開するために使用されるアカウントに適切なユーザー権限と権限がある場合は、トポロジを公開するときにバックエンドデータベース (リアルタイム通信 (RTC)) を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="3c3ac-112">If the account that is used to publish the topology has the appropriate user rights and permissions, you can create the back-end database (real-time communications (RTC)) when you publish your topology.</span></span> <span data-ttu-id="3c3ac-113">また、インストール手順の一部として、後でデータベースを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="3c3ac-113">You can also create the database later, including as part of the installation procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="3c3ac-114">Enterprise Edition の展開のために SQL Server ベースのサーバーにデータベースをインストールして展開するには、データベースファイルをインストールする SQL server ベースのサーバーの SQL Server 管理者グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c3ac-114">To install and deploy the databases on the SQL Server-based server for an Enterprise Edition deployment, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="3c3ac-115">SQL Server の [ユーザー名] グループのメンバーでない場合は、データベースファイルが展開されるまで、グループに追加するように依頼する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c3ac-115">If you are not a member of the SQL Server sysadmins group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="3c3ac-116">[管理者] グループのメンバーになることができない場合は、SQL Server データベース管理者に、データベースを構成して展開するためのスクリプトを用意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c3ac-116">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="3c3ac-117">手順を実行するために必要なユーザー権限と権限の詳細については、「 [SQL Server の展開権限](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c3ac-117">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx).</span></span>


