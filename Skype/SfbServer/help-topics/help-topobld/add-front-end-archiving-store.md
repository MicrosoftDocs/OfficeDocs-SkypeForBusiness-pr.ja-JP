---
title: フロントエンド アーカイブ ストアの追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndArchivingStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ce1723eb-7c93-424a-a622-9c888bf6d3bc
description: アーカイブには、Microsoft SQL Server データベース ・ ソフトウェア ・ アーカイブ ・ データを格納するのにサポートされている 64 ビット版が必要です。 アーカイブに使用する定義済みの SQL Server データベースを選択するか、SQL Server データベースを SQL の Se のインスタンスだけでなく、あるサーバーの完全修飾ドメイン名 (FQDN) を指定することにより、新しい SQL Server データベースの定義した rver の新しい SQL Server データベース (既定のインスタンスまたは名前付きインスタンスを指定することができます) を使用します。
ms.openlocfilehash: d366dd114bdfcf61b68971553eebdbf0f927ab35
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33886235"
---
# <a name="add-front-end-archiving-store"></a><span data-ttu-id="56f1b-104">フロントエンド アーカイブ ストアの追加</span><span class="sxs-lookup"><span data-stu-id="56f1b-104">Add Front End Archiving Store</span></span>

<span data-ttu-id="56f1b-105">アーカイブには、Microsoft SQL Server データベース ・ ソフトウェア ・ アーカイブ ・ データを格納するのにサポートされている 64 ビット版が必要です。</span><span class="sxs-lookup"><span data-stu-id="56f1b-105">Archiving requires a supported 64-bit edition of the Microsoft SQL Server database software to store the archiving data.</span></span> <span data-ttu-id="56f1b-106">アーカイブに使用する定義済みの SQL Server データベースを選択するか、SQL Server データベースを SQL の Se のインスタンスだけでなく、あるサーバーの完全修飾ドメイン名 (FQDN) を指定することにより、新しい SQL Server データベースの定義した rver の新しい SQL Server データベース (既定のインスタンスまたは名前付きインスタンスを指定することができます) を使用します。</span><span class="sxs-lookup"><span data-stu-id="56f1b-106">You can either select a previously defined SQL Server database to be used for archiving, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database is to reside, in addition to the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span>

> [!NOTE]
> <span data-ttu-id="56f1b-107">トポロジを公開するために使用するアカウントに適切なユーザー権利とアクセス許可がある場合、トポロジを公開すると、監視データベースを作成できます。</span><span class="sxs-lookup"><span data-stu-id="56f1b-107">If the account used to publish the topology has the appropriate user rights and permissions, you can create the monitoring database when you publish your topology.</span></span> <span data-ttu-id="56f1b-108">インストール手順の一部を含め、データベースを後で作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="56f1b-108">You can also create the database later, included as part of the installation procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="56f1b-109">インストールし、監視するための SQL Server ベースのサーバー上のデータベースを展開、データベース ファイルをインストールしている SQL Server ベースのサーバーの SQL Server システム管理者グループのメンバーをする必要があります。</span><span class="sxs-lookup"><span data-stu-id="56f1b-109">To install and deploy the databases on the SQL Server-based server for monitoring, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="56f1b-110">SQL Server の sysadmin グループのメンバーでない場合は、するが、データベース ・ ファイルが配置されるまで、グループに追加することを要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="56f1b-110">If you are not a member of the SQL Server sysadmin group, you must request that you be added to the group until the database files are deployed.</span></span> <span data-ttu-id="56f1b-111">システム管理者グループのメンバーにすることはできません、スクリプトを構成して、データベースを配置すると、SQL Server データベースの管理者を入力してください。</span><span class="sxs-lookup"><span data-stu-id="56f1b-111">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="56f1b-112">ユーザー権利とアクセス許可の手順を実行する必要があるについての詳細は、展開に関するドキュメントで[SQL Server の展開のアクセス許可](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56f1b-112">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in the Deployment documentation.</span></span>


