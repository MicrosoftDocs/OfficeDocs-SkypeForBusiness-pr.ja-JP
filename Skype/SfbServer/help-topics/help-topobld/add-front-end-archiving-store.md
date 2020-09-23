---
title: フロントエンド アーカイブ ストアを追加する
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
- ms.lync.tb.AddFrontEndArchivingStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ce1723eb-7c93-424a-a622-9c888bf6d3bc
description: アーカイブには、アーカイブデータを格納するために、サポートされている64ビット版の Microsoft SQL Server データベースソフトウェアが必要です。 アーカイブ用に定義されている SQL Server データベースを選択するか、または SQL server データベースが存在するサーバーの完全修飾ドメイン名 (FQDN) を指定して、新しい sql server データベースを定義することができます。これは、新しい SQL Server データベースで使用する SQL Server のインスタンス (既定のインスタンスの場合もあります) になります。、または指定した名前付きインスタンス)。
ms.openlocfilehash: 0cf61aa758b2228c065659f518c81d637022ff47
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216718"
---
# <a name="add-front-end-archiving-store"></a><span data-ttu-id="7dd6f-104">フロントエンド アーカイブ ストアを追加する</span><span class="sxs-lookup"><span data-stu-id="7dd6f-104">Add Front End Archiving Store</span></span>

<span data-ttu-id="7dd6f-105">アーカイブには、アーカイブデータを格納するために、サポートされている64ビット版の Microsoft SQL Server データベースソフトウェアが必要です。</span><span class="sxs-lookup"><span data-stu-id="7dd6f-105">Archiving requires a supported 64-bit edition of the Microsoft SQL Server database software to store the archiving data.</span></span> <span data-ttu-id="7dd6f-106">アーカイブ用に定義されている SQL Server データベースを選択するか、または SQL server データベースが存在するサーバーの完全修飾ドメイン名 (FQDN) を指定して、新しい sql server データベースを定義することができます。これは、新しい SQL Server データベースで使用する SQL Server のインスタンス (既定のインスタンスの場合もあります) になります。、または指定した名前付きインスタンス)。</span><span class="sxs-lookup"><span data-stu-id="7dd6f-106">You can either select a previously defined SQL Server database to be used for archiving, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database is to reside, in addition to the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span>

> [!NOTE]
> <span data-ttu-id="7dd6f-p103">トポロジを公開するために使用するアカウントに適切なユーザー権限とアクセス許可がある場合、トポロジを公開するときに監視データベースを作成できます。インストール手順の一部として、データベースを後で作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="7dd6f-p103">If the account used to publish the topology has the appropriate user rights and permissions, you can create the monitoring database when you publish your topology. You can also create the database later, included as part of the installation procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="7dd6f-109">監視用に SQL Server ベースのサーバーにデータベースをインストールして展開するには、データベースファイルをインストールする sql server ベースのサーバーの SQL Server の管理者グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="7dd6f-109">To install and deploy the databases on the SQL Server-based server for monitoring, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="7dd6f-110">SQL Server sysadmin グループのメンバーではない場合は、データベースファイルが展開されるまで、グループに追加するように要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7dd6f-110">If you are not a member of the SQL Server sysadmin group, you must request that you be added to the group until the database files are deployed.</span></span> <span data-ttu-id="7dd6f-111">システム管理者グループのメンバーになることができない場合は、データベースを構成および展開するためのスクリプトを SQL Server データベース管理者に提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7dd6f-111">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="7dd6f-112">これらの手順を実行するために必要なユーザー権限およびアクセス許可の詳細については、「展開」ドキュメントの「[Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7dd6f-112">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in the Deployment documentation.</span></span>


