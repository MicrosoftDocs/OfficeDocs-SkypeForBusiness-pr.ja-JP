---
title: フロントエンド SQL Server ストアの追加
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dace9561-3eb4-4647-83cb-56c246919ae1
description: Standard Edition サーバーの展開は、必要なデータベース ソフトウェアの高速に Microsoft SQL Server と SQL Server データベースに自動的にインストールします。 したがって、すべてのオプション、事前に設定されて、既定の構成に変更を加えることはできません。
ms.openlocfilehash: b85c98f81be4dc53a9a7b5d0bfea708fd267135b
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894389"
---
# <a name="add-front-end-sql-server-store"></a><span data-ttu-id="0a1d5-104">フロントエンド SQL Server ストアの追加</span><span class="sxs-lookup"><span data-stu-id="0a1d5-104">Add Front End SQL Server Store</span></span>

<span data-ttu-id="0a1d5-105">Standard Edition サーバーの展開は、必要なデータベース ソフトウェアの高速に Microsoft SQL Server と SQL Server データベースに自動的にインストールします。</span><span class="sxs-lookup"><span data-stu-id="0a1d5-105">A Standard Edition server deployment automatically installs the required Microsoft SQL Server Express database software and SQL Server database.</span></span> <span data-ttu-id="0a1d5-106">したがって、すべてのオプション、事前に設定されて、既定の構成に変更を加えることはできません。</span><span class="sxs-lookup"><span data-stu-id="0a1d5-106">Therefore, all options are prepopulated, and you can't make changes to the default configuration.</span></span>

<span data-ttu-id="0a1d5-107">Enterprise Edition サーバー展開のフロント エンド プールには、バック エンド データベースの SQL Server データベース ソフトウェアのサポート対象の 64 ビット版が必要です。</span><span class="sxs-lookup"><span data-stu-id="0a1d5-107">The Front End pool of an Enterprise Edition server deployment requires a supported 64-bit edition of the SQL Server database software for the back-end database.</span></span> <span data-ttu-id="0a1d5-108">バック エンド データベースに使用する定義済みの SQL Server データベースを選択するか、サーバーを SQL Server データベースが存在するが、S の SQL のインスタンスの完全修飾ドメイン名 (FQDN) を指定することで新しい SQL Server データベースの定義erver、新しい SQL Server データベース (既定のインスタンスまたは名前付きインスタンスを指定することができます) を使用します。</span><span class="sxs-lookup"><span data-stu-id="0a1d5-108">You can either select a previously defined SQL Server database to be used for the back-end database, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database is to reside, and the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span> <span data-ttu-id="0a1d5-109">SQL Server ストアのミラーリングを有効にするを選択し、自動フェイル オーバーのミラーリング ・ ミラーリング監視サーバーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="0a1d5-109">You can also choose to enable mirroring on the SQL Server store, and specify a mirroring witness for automatic failover.</span></span>

<span data-ttu-id="0a1d5-110">詳細については SQL Server のサポートは、[データベース ソフトウェアとクラスタ リングをサポート](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx)サポート マニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a1d5-110">For details about SQL Server support, see [Database Software and Clustering Support](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="0a1d5-111">バック エンド データベースの SQL Server の設定に関する詳細については、展開に関するドキュメントで[Lync Server 2010 用の SQL Server の構成](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a1d5-111">For details about setting up SQL Server for the back-end database, see [Configure SQL Server for Lync Server 2010](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) in the Deployment documentation.</span></span>

> [!NOTE]
> <span data-ttu-id="0a1d5-112">(リアルタイム通信 (RTC)) のバック エンド データベースを作成するには、トポロジを公開するために使用されるアカウントに適切なユーザー権利とアクセス許可がある場合、トポロジを公開するとします。</span><span class="sxs-lookup"><span data-stu-id="0a1d5-112">If the account that is used to publish the topology has the appropriate user rights and permissions, you can create the back-end database (real-time communications (RTC)) when you publish your topology.</span></span> <span data-ttu-id="0a1d5-113">インストール手順の一部として含め、後でデータベースを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="0a1d5-113">You can also create the database later, including as part of the installation procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="0a1d5-114">インストールおよび展開の場合エンタープライズ版の SQL Server ベースのサーバー上のデータベースを展開、データベース ファイルをインストールしている SQL Server ベースのサーバーの SQL Server システム管理者グループのメンバーをする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a1d5-114">To install and deploy the databases on the SQL Server-based server for an Enterprise Edition deployment, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="0a1d5-115">SQL Server のシステム管理者グループのメンバーでない場合は、データベース ファイルを展開するまでに、グループに追加する要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a1d5-115">If you are not a member of the SQL Server sysadmins group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="0a1d5-116">システム管理者グループのメンバーにすることはできません、スクリプトを構成して、データベースを配置すると、SQL Server データベースの管理者を入力してください。</span><span class="sxs-lookup"><span data-stu-id="0a1d5-116">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="0a1d5-117">ユーザー権利とアクセス許可の手順を実行する必要があるの詳細については、 [SQL Server の展開のアクセス許可](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a1d5-117">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx).</span></span>


