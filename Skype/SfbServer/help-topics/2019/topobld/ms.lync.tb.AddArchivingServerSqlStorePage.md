---
title: アーカイブ サーバー SQL Server ストアの追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddArchivingServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26e0a748-e31d-4c66-b225-b37e0a45408f
ROBOTS: NOINDEX, NOFOLLOW
description: アーカイブデータを保存するには、アーカイブサーバーでサポートされている64ビット版の SQL Server データベースソフトウェアが必要です。 以前に定義した SQL Server データベースをアーカイブまたは新しい sql Server データベースとして使用するには、SQL Server データベースが存在するサーバーの完全修飾ドメイン名 (FQDN) を指定し、次のような SQL Server データベースを作成することができます。新しい SQL Server データベース (既定のインスタンスまたは指定した名前付きインスタンス) に使用します。
ms.openlocfilehash: 14a104a28c28c5ea78ab97fd73f7eb7312fffd87
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41689712"
---
# <a name="add-archiving-server-sql-server-store"></a><span data-ttu-id="67e3b-104">アーカイブ サーバー SQL Server ストアの追加</span><span class="sxs-lookup"><span data-stu-id="67e3b-104">Add Archiving Server SQL Server Store</span></span>

<span data-ttu-id="67e3b-105">アーカイブデータを保存するには、アーカイブサーバーでサポートされている64ビット版の SQL Server データベースソフトウェアが必要です。</span><span class="sxs-lookup"><span data-stu-id="67e3b-105">Archiving Server requires a supported 64-bit edition of the SQL Server database software to store the archive data.</span></span> <span data-ttu-id="67e3b-106">以前に定義した SQL Server データベースをアーカイブまたは新しい sql Server データベースとして使用するには、SQL Server データベースが存在するサーバーの完全修飾ドメイン名 (FQDN) を指定し、次のような SQL Server データベースを作成することができます。新しい SQL Server データベース (既定のインスタンスまたは指定した名前付きインスタンス) に使用します。</span><span class="sxs-lookup"><span data-stu-id="67e3b-106">You can either select a previously defined SQL Server database to be used for archiving or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database will reside, and the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance or a named instance that you specify).</span></span>

> [!NOTE]
> <span data-ttu-id="67e3b-107">トポロジを公開するために使用されるアカウントに適切なユーザー権限と権限がある場合は、トポロジを公開するときにアーカイブデータベース (LcsLog) を作成できます。</span><span class="sxs-lookup"><span data-stu-id="67e3b-107">If the account that is used to publish the topology has the appropriate user rights and permissions, you can create the archiving database (LcsLog) when you publish your topology.</span></span> <span data-ttu-id="67e3b-108">また、インストール手順の一部として、またはその他の方法でデータベースを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="67e3b-108">You can also create the database later, as part of the installation procedure, or otherwise.</span></span>

> [!NOTE]
> <span data-ttu-id="67e3b-109">アーカイブのために SQL Server ベースのサーバーにデータベースをインストールして展開するには、データベースファイルをインストールする SQL server ベースのサーバーの SQL Server の [の機能] グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="67e3b-109">To install and deploy the databases on the SQL Server-based server for archiving, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="67e3b-110">SQL Server の [ユーザー名] グループのメンバーでない場合は、データベースファイルが展開されるまで、グループに追加するように依頼する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67e3b-110">If you are not a member of the SQL Server sysadmins group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="67e3b-111">[管理者] グループのメンバーになることができない場合は、SQL Server データベース管理者に、データベースを構成して展開するためのスクリプトを用意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67e3b-111">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="67e3b-112">手順を実行するために必要なユーザー権限とアクセス許可の詳細については、展開ドキュメントの「 [SQL Server の展開権限](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67e3b-112">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in the Deployment documentation.</span></span>


