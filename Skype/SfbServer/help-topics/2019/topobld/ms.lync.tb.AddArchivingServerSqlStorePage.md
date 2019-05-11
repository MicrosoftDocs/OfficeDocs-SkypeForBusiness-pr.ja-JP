---
title: アーカイブ サーバー SQL Server ストアの追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddArchivingServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26e0a748-e31d-4c66-b225-b37e0a45408f
ROBOTS: NOINDEX, NOFOLLOW
description: アーカイブ サーバーには、アーカイブ ・ データを格納する SQL Server データベース ソフトウェアのサポートされている 64 ビット版が必要です。 アーカイブに使用するか、SQL Server データベースが格納されているサーバーと SQL Server のインスタンスの完全修飾ドメイン名 (FQDN) を指定することで新しい SQL Server データベースを定義する定義済みの SQL Server データベースを選択するかを新しい SQL Server データベース (既定のインスタンスまたは名前付きインスタンスを指定することができます) を使用するには。
ms.openlocfilehash: 340282aabee67e758741e26dc1c586c44c13210d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33889221"
---
# <a name="add-archiving-server-sql-server-store"></a><span data-ttu-id="5a82a-104">アーカイブ サーバー SQL Server ストアの追加</span><span class="sxs-lookup"><span data-stu-id="5a82a-104">Add Archiving Server SQL Server Store</span></span>

<span data-ttu-id="5a82a-105">アーカイブ サーバーには、アーカイブ ・ データを格納する SQL Server データベース ソフトウェアのサポートされている 64 ビット版が必要です。</span><span class="sxs-lookup"><span data-stu-id="5a82a-105">Archiving Server requires a supported 64-bit edition of the SQL Server database software to store the archive data.</span></span> <span data-ttu-id="5a82a-106">アーカイブに使用するか、SQL Server データベースが格納されているサーバーと SQL Server のインスタンスの完全修飾ドメイン名 (FQDN) を指定することで新しい SQL Server データベースを定義する定義済みの SQL Server データベースを選択するかを新しい SQL Server データベース (既定のインスタンスまたは名前付きインスタンスを指定することができます) を使用するには。</span><span class="sxs-lookup"><span data-stu-id="5a82a-106">You can either select a previously defined SQL Server database to be used for archiving or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database will reside, and the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance or a named instance that you specify).</span></span>

> [!NOTE]
> <span data-ttu-id="5a82a-107">トポロジを公開するために使用するアカウントに適切なユーザー権利とアクセス許可がある場合、トポロジを公開するときにアーカイブ データベース (LcsLog) を作成できます。</span><span class="sxs-lookup"><span data-stu-id="5a82a-107">If the account that is used to publish the topology has the appropriate user rights and permissions, you can create the archiving database (LcsLog) when you publish your topology.</span></span> <span data-ttu-id="5a82a-108">以降では、インストール手順の一部として、データベースを作成することもできます。 または、それ以外の場合。</span><span class="sxs-lookup"><span data-stu-id="5a82a-108">You can also create the database later, as part of the installation procedure, or otherwise.</span></span>

> [!NOTE]
> <span data-ttu-id="5a82a-109">インストールして、アーカイブのための SQL Server ベースのサーバー上のデータベースを展開、データベース ファイルをインストールしている SQL Server ベースのサーバーの SQL Server システム管理者グループのメンバーをする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a82a-109">To install and deploy the databases on the SQL Server-based server for archiving, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="5a82a-110">SQL Server のシステム管理者グループのメンバーでない場合は、データベース ファイルを展開するまでに、グループに追加する要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a82a-110">If you are not a member of the SQL Server sysadmins group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="5a82a-111">システム管理者グループのメンバーにすることはできません、スクリプトを構成して、データベースを配置すると、SQL Server データベースの管理者を入力してください。</span><span class="sxs-lookup"><span data-stu-id="5a82a-111">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="5a82a-112">ユーザー権利とアクセス許可の手順を実行する必要があるについての詳細は、展開に関するドキュメントで[SQL Server の展開のアクセス許可](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a82a-112">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in the Deployment documentation.</span></span>


