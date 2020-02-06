---
title: フロントエンド アーカイブ ストアの追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndArchivingStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ce1723eb-7c93-424a-a622-9c888bf6d3bc
ROBOTS: NOINDEX, NOFOLLOW
description: アーカイブには、アーカイブデータを保存するために、Microsoft SQL Server データベースソフトウェアのサポートされている64ビット版が必要です。 アーカイブに使用するために定義済みの SQL Server データベースを選ぶか、sql Server データベースが存在するサーバーの完全修飾ドメイン名 (FQDN) を指定して新しい SQL Server データベースを定義することができます。また、SQL Se のインスタンスについてもかまいません。新しい SQL Server データベース (既定のインスタンスまたは指定した名前付きインスタンス) として使用する rver。
ms.openlocfilehash: 234d0a2d4ef14aa969b8ef8c7445558e53ca2fee
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794906"
---
# <a name="add-front-end-archiving-store"></a><span data-ttu-id="11236-104">フロントエンド アーカイブ ストアの追加</span><span class="sxs-lookup"><span data-stu-id="11236-104">Add Front End Archiving Store</span></span>

<span data-ttu-id="11236-105">アーカイブには、アーカイブデータを保存するために、Microsoft SQL Server データベースソフトウェアのサポートされている64ビット版が必要です。</span><span class="sxs-lookup"><span data-stu-id="11236-105">Archiving requires a supported 64-bit edition of the Microsoft SQL Server database software to store the archiving data.</span></span> <span data-ttu-id="11236-106">アーカイブに使用するために定義済みの SQL Server データベースを選ぶか、sql Server データベースが存在するサーバーの完全修飾ドメイン名 (FQDN) を指定して新しい SQL Server データベースを定義することができます。また、SQL Se のインスタンスについてもかまいません。新しい SQL Server データベース (既定のインスタンスまたは指定した名前付きインスタンス) として使用する rver。</span><span class="sxs-lookup"><span data-stu-id="11236-106">You can either select a previously defined SQL Server database to be used for archiving, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database is to reside, in addition to the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span>

> [!NOTE]
> <span data-ttu-id="11236-107">トポロジの公開に使用したアカウントに適切なユーザー権限と権限がある場合は、トポロジを公開するときに監視データベースを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="11236-107">If the account used to publish the topology has the appropriate user rights and permissions, you can create the monitoring database when you publish your topology.</span></span> <span data-ttu-id="11236-108">インストール手順の一部を含め、データベースを後で作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="11236-108">You can also create the database later, included as part of the installation procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="11236-109">監視用に SQL Server ベースのサーバーにデータベースをインストールして展開するには、データベースファイルをインストールする SQL server ベースのサーバーの SQL Server 管理者グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="11236-109">To install and deploy the databases on the SQL Server-based server for monitoring, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="11236-110">SQL Server sysadmin グループのメンバーでない場合は、データベースファイルが展開されるまで、グループに追加するように依頼する必要があります。</span><span class="sxs-lookup"><span data-stu-id="11236-110">If you are not a member of the SQL Server sysadmin group, you must request that you be added to the group until the database files are deployed.</span></span> <span data-ttu-id="11236-111">[管理者] グループのメンバーになることができない場合は、SQL Server データベース管理者に、データベースを構成して展開するためのスクリプトを用意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="11236-111">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="11236-112">手順を実行するために必要なユーザー権限とアクセス許可の詳細については、展開ドキュメントの「 [SQL Server の展開権限](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11236-112">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in the Deployment documentation.</span></span>


