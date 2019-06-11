---
title: 'Lync Server 2013: Lync Server 用 SQL Server の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure SQL Server for Lync Server 2013
ms:assetid: 375e5cc4-e436-46dc-9b02-5063f35cdcc1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425848(v=OCS.15)
ms:contentKeyID: 48183869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0154b468540873f9b8ae6796f30336327809d394
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840331"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-for-lync-server-2013"></a><span data-ttu-id="ed041-102">Lync Server 2013 用 SQL Server の構成</span><span class="sxs-lookup"><span data-stu-id="ed041-102">Configure SQL Server for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed041-103">_**最終更新日:** 2013-08-12_</span><span class="sxs-lookup"><span data-stu-id="ed041-103">_**Topic Last Modified:** 2013-08-12_</span></span>

<span data-ttu-id="ed041-104">このセクションのトピックでは、Lync Server のエンタープライズ展開で使用するように SQL Server を展開して構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ed041-104">The topics in this section discuss how to deploy and configure SQL Server to use in an Enterprise deployment of Lync Server.</span></span> <span data-ttu-id="ed041-105">Standard Edition サーバーでは、標準エディションサーバーのワークロードに合わせて適切にサイズ調整された sql Server Express バージョンの SQL Server を使用します。</span><span class="sxs-lookup"><span data-stu-id="ed041-105">Standard Edition servers use a collocated SQL Server Express version of SQL Server that is right sized for the workloads of a Standard Edition server.</span></span>

<span data-ttu-id="ed041-106">Lync Server 2013 の中央管理ストアは、プール内のすべての Enterprise Edition サーバーのユーザーデータを保持し、SQL Server ベースのバックエンドサーバーに配置されるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="ed041-106">The Lync Server 2013 Central Management store holds user data for all Enterprise Edition servers within a pool, and is designed to be located on a SQL Server -based Back End Server.</span></span> <span data-ttu-id="ed041-107">一元的なリポジトリとして、中央管理ストアは、他の Lync Server 2013 の役割と同じコンピューターにインストールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="ed041-107">As a centralized repository, the Central Management store cannot be installed on the same computer as any other Lync Server 2013 role.</span></span> <span data-ttu-id="ed041-108">中央管理ストアは、プール内の Enterprise Edition サーバー上に配置できません。</span><span class="sxs-lookup"><span data-stu-id="ed041-108">The Central Management store cannot reside on an Enterprise Edition server in the pool.</span></span> <span data-ttu-id="ed041-109">最初にトポロジを公開し、選択してデータベースを作成すると、中央管理ストアが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="ed041-109">The Central Management store is created automatically when you publish the topology for the first time and select to create the databases.</span></span> <span data-ttu-id="ed041-110">インストールを正常に実行するためには、バックエンドサーバーとして指定したコンピューターで SQL Server データベースソフトウェアが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed041-110">The computer that you designate as the Back End Server must already be running SQL Server database software in order for the installation to succeed.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ed041-111">このセクション中</span><span class="sxs-lookup"><span data-stu-id="ed041-111">In This Section</span></span>

  - [<span data-ttu-id="ed041-112">Lync Server 2013 の SQL Server データとログ ファイルの配置</span><span class="sxs-lookup"><span data-stu-id="ed041-112">SQL Server data and log file placement for Lync Server 2013</span></span>](lync-server-2013-sql-server-data-and-log-file-placement.md)

  - [<span data-ttu-id="ed041-113">Lync Server 2013 での SQL Server の構成</span><span class="sxs-lookup"><span data-stu-id="ed041-113">Configure SQL Server in Lync Server 2013</span></span>](lync-server-2013-configure-sql-server.md)

  - [<span data-ttu-id="ed041-114">Lync Server 2013 の SQL Server の展開のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="ed041-114">Deployment permissions for SQL Server in Lync Server 2013</span></span>](lync-server-2013-deployment-permissions-for-sql-server.md)

  - [<span data-ttu-id="ed041-115">Lync Server 2013 での Lync Server 管理シェルを使用したデータベースのインストール</span><span class="sxs-lookup"><span data-stu-id="ed041-115">Database installation using Lync Server Management Shell in Lync Server 2013</span></span>](lync-server-2013-database-installation-using-lync-server-management-shell.md)

  - [<span data-ttu-id="ed041-116">Lync Server 2013 での SQL Server のファイアウォール要件について</span><span class="sxs-lookup"><span data-stu-id="ed041-116">Understanding firewall requirements for SQL Server with Lync Server 2013</span></span>](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)

  - [<span data-ttu-id="ed041-117">Lync Server 2013 用の SQL Server クラスタリングを構成する</span><span class="sxs-lookup"><span data-stu-id="ed041-117">Configure SQL Server clustering for Lync Server 2013</span></span>](lync-server-2013-configure-sql-server-clustering.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

