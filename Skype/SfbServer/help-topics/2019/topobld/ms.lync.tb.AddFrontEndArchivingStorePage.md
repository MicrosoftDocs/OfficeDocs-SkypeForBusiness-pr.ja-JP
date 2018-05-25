---
title: アーカイブ ストアのフロント エンドを追加します。
ms.author: heidip
author: microsoftheidi
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
ms.openlocfilehash: 528c8062b07593a4c7e4cc00f3d1d2566c05f77e
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2018
---
# <a name="add-front-end-archiving-store"></a><span data-ttu-id="73921-104">アーカイブ ストアのフロント エンドを追加します。</span><span class="sxs-lookup"><span data-stu-id="73921-104">Add Front End Archiving Store</span></span>
 
<span data-ttu-id="73921-105">アーカイブには、Microsoft SQL Server データベース ・ ソフトウェア ・ アーカイブ ・ データを格納するのにサポートされている 64 ビット版が必要です。</span><span class="sxs-lookup"><span data-stu-id="73921-105">Archiving requires a supported 64-bit edition of the Microsoft SQL Server database software to store the archiving data.</span></span> <span data-ttu-id="73921-106">アーカイブに使用する定義済みの SQL Server データベースを選択するか、SQL Server データベースを SQL の Se のインスタンスだけでなく、あるサーバーの完全修飾ドメイン名 (FQDN) を指定することにより、新しい SQL Server データベースの定義した rver の新しい SQL Server データベース (既定のインスタンスまたは名前付きインスタンスを指定することができます) を使用します。</span><span class="sxs-lookup"><span data-stu-id="73921-106">You can either select a previously defined SQL Server database to be used for archiving, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database is to reside, in addition to the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span>
  
> [!NOTE]
> <span data-ttu-id="73921-107">トポロジを公開するために使用するアカウントに適切なユーザー権利とアクセス許可がある場合、トポロジを公開すると、監視データベースを作成できます。</span><span class="sxs-lookup"><span data-stu-id="73921-107">If the account used to publish the topology has the appropriate user rights and permissions, you can create the monitoring database when you publish your topology.</span></span> <span data-ttu-id="73921-108">インストール手順の一部を含め、データベースを後で作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="73921-108">You can also create the database later, included as part of the installation procedure.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="73921-109">インストールし、監視するための SQL Server ベースのサーバー上のデータベースを展開、データベース ファイルをインストールしている SQL Server ベースのサーバーの SQL Server システム管理者グループのメンバーをする必要があります。</span><span class="sxs-lookup"><span data-stu-id="73921-109">To install and deploy the databases on the SQL Server-based server for monitoring, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="73921-110">SQL Server の sysadmin グループのメンバーでない場合は、するが、データベース ・ ファイルが配置されるまで、グループに追加することを要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="73921-110">If you are not a member of the SQL Server sysadmin group, you must request that you be added to the group until the database files are deployed.</span></span> <span data-ttu-id="73921-111">システム管理者グループのメンバーにすることはできません、スクリプトを構成して、データベースを配置すると、SQL Server データベースの管理者を入力してください。</span><span class="sxs-lookup"><span data-stu-id="73921-111">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="73921-112">ユーザー権利とアクセス許可の手順を実行する必要があるについての詳細は、展開に関するドキュメントで[SQL Server の展開のアクセス許可](http://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73921-112">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](http://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in the Deployment documentation.</span></span>
  

