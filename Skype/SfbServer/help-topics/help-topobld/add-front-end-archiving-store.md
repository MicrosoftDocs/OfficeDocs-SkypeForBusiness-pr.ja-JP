---
title: フロントエンド アーカイブ ストアを追加する
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
- ms.lync.tb.AddFrontEndArchivingStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ce1723eb-7c93-424a-a622-9c888bf6d3bc
description: アーカイブには、アーカイブ データを格納するために、サポートされている 64 ビット 版Microsoft SQL Serverデータベース ソフトウェアが必要です。 アーカイブに使用する定義済みの SQL Server データベースを選択するか、新しい SQL Server データベースに使用する SQL Server データベースのインスタンスに加えて、SQL Server SQL Server データベースが存在するサーバーの完全修飾ドメイン名 (FQDN) を指定して、新しい SQL Server データベースを定義できます (既定のインスタンスを指定できます)。、または指定した名前付きインスタンス)。
ms.openlocfilehash: 9f3ee74944ca19f827229bcfcaea2a1e37d2bfcb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51107843"
---
# <a name="add-front-end-archiving-store"></a><span data-ttu-id="0f9e2-104">フロント エンド アーカイブ ストアの追加</span><span class="sxs-lookup"><span data-stu-id="0f9e2-104">Add Front End Archiving Store</span></span>

<span data-ttu-id="0f9e2-105">アーカイブには、アーカイブ データを格納するために、サポートされている 64 ビット 版Microsoft SQL Serverデータベース ソフトウェアが必要です。</span><span class="sxs-lookup"><span data-stu-id="0f9e2-105">Archiving requires a supported 64-bit edition of the Microsoft SQL Server database software to store the archiving data.</span></span> <span data-ttu-id="0f9e2-106">アーカイブに使用する定義済みの SQL Server データベースを選択するか、新しい SQL Server データベースに使用する SQL Server データベースのインスタンスに加えて、SQL Server SQL Server データベースが存在するサーバーの完全修飾ドメイン名 (FQDN) を指定して、新しい SQL Server データベースを定義できます (既定のインスタンスを指定できます)。、または指定した名前付きインスタンス)。</span><span class="sxs-lookup"><span data-stu-id="0f9e2-106">You can either select a previously defined SQL Server database to be used for archiving, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database is to reside, in addition to the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span>

> [!NOTE]
> <span data-ttu-id="0f9e2-p103">トポロジを公開するために使用するアカウントに適切なユーザー権限とアクセス許可がある場合、トポロジを公開するときに監視データベースを作成できます。インストール手順の一部として、データベースを後で作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="0f9e2-p103">If the account used to publish the topology has the appropriate user rights and permissions, you can create the monitoring database when you publish your topology. You can also create the database later, included as part of the installation procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="0f9e2-109">SQL Server ベースのサーバーにデータベースをインストールして展開して監視するには、データベース ファイルをインストールする SQL Server ベースのサーバーの SQL Server sysadmins グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f9e2-109">To install and deploy the databases on the SQL Server-based server for monitoring, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="0f9e2-110">SQL Server sysadmin グループのメンバーではない場合は、データベース ファイルが展開されるまでグループに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f9e2-110">If you are not a member of the SQL Server sysadmin group, you must request that you be added to the group until the database files are deployed.</span></span> <span data-ttu-id="0f9e2-111">sysadmins グループのメンバーにできない場合は、データベースを構成および展開するためのスクリプトを SQL Server データベース管理者に提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f9e2-111">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="0f9e2-112">これらの手順を実行するために必要なユーザー権限およびアクセス許可の詳細については、「展開」ドキュメントの「[Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f9e2-112">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server) in the Deployment documentation.</span></span>