---
title: アーカイブ サーバー SQL Server ストアの追加
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
- ms.lync.tb.AddArchivingServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26e0a748-e31d-4c66-b225-b37e0a45408f
description: アーカイブサーバーには、アーカイブデータを格納するために、サポートされている64ビット版の SQL Server データベースソフトウェアが必要です。 アーカイブに使用するために定義済みの SQL Server データベースを選択するか、SQL server データベースが存在するサーバーの完全修飾ドメイン名 (FQDN) を指定して新しい sql server データベースを定義するか、または新しい sql server データベースで使用する SQL Server のインスタンス (指定した既定のインスタンスまたは名前付きインスタンス) を指定します。
ms.openlocfilehash: eb25152916c61ff40274705a408fe0a7a618cbcc
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217438"
---
# <a name="add-archiving-server-sql-server-store"></a><span data-ttu-id="4a34e-104">アーカイブ サーバー SQL Server ストアの追加</span><span class="sxs-lookup"><span data-stu-id="4a34e-104">Add Archiving Server SQL Server Store</span></span>

<span data-ttu-id="4a34e-105">アーカイブサーバーには、アーカイブデータを格納するために、サポートされている64ビット版の SQL Server データベースソフトウェアが必要です。</span><span class="sxs-lookup"><span data-stu-id="4a34e-105">Archiving Server requires a supported 64-bit edition of the SQL Server database software to store the archive data.</span></span> <span data-ttu-id="4a34e-106">アーカイブに使用するために定義済みの SQL Server データベースを選択するか、SQL server データベースが存在するサーバーの完全修飾ドメイン名 (FQDN) を指定して新しい sql server データベースを定義するか、または新しい sql server データベースで使用する SQL Server のインスタンス (指定した既定のインスタンスまたは名前付きインスタンス) を指定します。</span><span class="sxs-lookup"><span data-stu-id="4a34e-106">You can either select a previously defined SQL Server database to be used for archiving or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database will reside, and the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance or a named instance that you specify).</span></span>

> [!NOTE]
> <span data-ttu-id="4a34e-p103">トポロジの公開に使用するアカウントに適切なユーザー権限とアクセス許可があれば、トポロジの発行時にアーカイブ データベース (LcsLog) を作成できます。インストール手順の一部として実行するなど、データベースを後で作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="4a34e-p103">If the account that is used to publish the topology has the appropriate user rights and permissions, you can create the archiving database (LcsLog) when you publish your topology. You can also create the database later, as part of the installation procedure, or otherwise.</span></span>

> [!NOTE]
> <span data-ttu-id="4a34e-109">アーカイブ用に SQL Server ベースのサーバーにデータベースをインストールして展開するには、データベースファイルをインストールする sql server ベースのサーバーの SQL Server の [ユーザー] グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a34e-109">To install and deploy the databases on the SQL Server-based server for archiving, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="4a34e-110">SQL Server の [ユーザー] グループのメンバーでない場合は、データベースファイルが展開されるまで、グループに追加するよう要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a34e-110">If you are not a member of the SQL Server sysadmins group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="4a34e-111">システム管理者グループのメンバーになることができない場合は、データベースを構成および展開するためのスクリプトを SQL Server データベース管理者に提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a34e-111">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="4a34e-112">これらの手順を実行するために必要なユーザー権限およびアクセス許可の詳細については、「展開」ドキュメントの「[Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a34e-112">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in the Deployment documentation.</span></span>


