---
title: フロント エンド SQL Server ストアの追加
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Standard Edition サーバーの展開では、Express データベース ソフトウェアとデータベースに必要Microsoft SQL Serverが自動的にSQL Serverされます。 したがって、すべてのオプションが事前設定され、既定の構成を変更できない。
ms.openlocfilehash: e369f58afd015953cf0b58ca9788965a4829fd16
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119736"
---
# <a name="add-front-end-sql-server-store"></a><span data-ttu-id="d0dc6-104">フロント エンド SQL Server ストアの追加</span><span class="sxs-lookup"><span data-stu-id="d0dc6-104">Add Front End SQL Server Store</span></span>

<span data-ttu-id="d0dc6-105">Standard Edition サーバーの展開では、Express データベース ソフトウェアとデータベースに必要Microsoft SQL Serverが自動的にSQL Serverされます。</span><span class="sxs-lookup"><span data-stu-id="d0dc6-105">A Standard Edition server deployment automatically installs the required Microsoft SQL Server Express database software and SQL Server database.</span></span> <span data-ttu-id="d0dc6-106">したがって、すべてのオプションが事前設定され、既定の構成を変更できない。</span><span class="sxs-lookup"><span data-stu-id="d0dc6-106">Therefore, all options are prepopulated, and you can't make changes to the default configuration.</span></span>

<span data-ttu-id="d0dc6-107">Enterprise Edition サーバー展開のフロントエンド プールには、サポートされている 64 ビット 版の SQL Server データベース ソフトウェアが必要です。</span><span class="sxs-lookup"><span data-stu-id="d0dc6-107">The Front End pool of an Enterprise Edition server deployment requires a supported 64-bit edition of the SQL Server database software for the back-end database.</span></span> <span data-ttu-id="d0dc6-108">以前に定義した SQL Server データベースを選択するか、SQL Server データベースが存在するサーバーの完全修飾ドメイン名 (FQDN) と、新しい SQL Server データベースに使用する SQL Server のインスタンス (既定のインスタンスを指定できる) を指定して、新しい SQL Server データベースを定義できます。、または指定した名前付きインスタンス)。</span><span class="sxs-lookup"><span data-stu-id="d0dc6-108">You can either select a previously defined SQL Server database to be used for the back-end database, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database is to reside, and the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span> <span data-ttu-id="d0dc6-109">また、サーバー ストアでミラーリングを有効にし、SQL Serverミラーリング監視を指定して自動フェールオーバーを行う方法も選択できます。</span><span class="sxs-lookup"><span data-stu-id="d0dc6-109">You can also choose to enable mirroring on the SQL Server store, and specify a mirroring witness for automatic failover.</span></span>

<span data-ttu-id="d0dc6-110">サポートの詳細SQL Serverサポートのドキュメントの「 [データベース ソフトウェア](/previous-versions/office/lync-server-2013/lync-server-2013-database-software-support) とクラスタリング サポート」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0dc6-110">For details about SQL Server support, see [Database Software and Clustering Support](/previous-versions/office/lync-server-2013/lync-server-2013-database-software-support) in the Supportability documentation.</span></span> <span data-ttu-id="d0dc6-111">バックエンド データベース用の SQL Server の設定の詳細については、「展開」のドキュメントの「[Lync Server 2010 用 SQL Server の構成](/previous-versions/office/lync-server-2013/lync-server-2013-configure-sql-server-for-lync-server)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0dc6-111">For details about setting up SQL Server for the back-end database, see [Configure SQL Server for Lync Server 2010](/previous-versions/office/lync-server-2013/lync-server-2013-configure-sql-server-for-lync-server) in the Deployment documentation.</span></span>

> [!NOTE]
> <span data-ttu-id="d0dc6-112">トポロジの公開に使用されるアカウントに適切なユーザー権限とアクセス許可がある場合は、トポロジを公開するときに、バック エンド データベース (リアルタイム通信 (RTC)) を作成できます。</span><span class="sxs-lookup"><span data-stu-id="d0dc6-112">If the account that is used to publish the topology has the appropriate user rights and permissions, you can create the back-end database (real-time communications (RTC)) when you publish your topology.</span></span> <span data-ttu-id="d0dc6-113">インストール手順の一部を含め、データベースを後で作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="d0dc6-113">You can also create the database later, including as part of the installation procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="d0dc6-114">エンタープライズ エディション展開用の SQL Server ベースのサーバーにデータベースをインストールして展開するには、データベース ファイルをインストールする SQL Server ベースのサーバーの SQL Server sysadmins グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0dc6-114">To install and deploy the databases on the SQL Server-based server for an Enterprise Edition deployment, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="d0dc6-115">SQL Server sysadmins グループのメンバーではない場合は、データベース ファイルが展開されるまでグループへの追加を要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0dc6-115">If you are not a member of the SQL Server sysadmins group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="d0dc6-116">sysadmins グループのメンバーにできない場合は、データベースを構成および展開するためのスクリプトを SQL Server データベース管理者に提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0dc6-116">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="d0dc6-117">手順を実行するために必要なユーザー権限とアクセス許可の詳細については、「展開アクセス許可 for SQL Server」 [を参照してください](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server)。</span><span class="sxs-lookup"><span data-stu-id="d0dc6-117">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server).</span></span>