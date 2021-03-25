---
title: フロント エンド ファイル ストアの追加
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d18a648-a0e1-4401-a1e6-7a2755ba8c66
ROBOTS: NOINDEX, NOFOLLOW
description: Standard Edition サーバーまたは Enterprise Edition フロントエンド プールのファイル ストアとして使用するファイル共有を指定する必要があります。 ファイル ストアに既存のファイル共有を使用するか、ファイル共有を保存するファイル サーバーの完全修飾ドメイン名 (FQDN) と、新しいファイル共有のフォルダー名を指定して、新しいファイル共有を指定できます。
ms.openlocfilehash: e1dc0c94880bd161fae41be811847e1b0da3dbb5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118696"
---
# <a name="add-front-end-file-store"></a><span data-ttu-id="0979f-104">フロント エンド ファイル ストアの追加</span><span class="sxs-lookup"><span data-stu-id="0979f-104">Add Front End File Store</span></span>

<span data-ttu-id="0979f-105">Standard Edition サーバーまたは Enterprise Edition フロントエンド プールのファイル ストアとして使用するファイル共有を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0979f-105">You must specify a file share to be used as the file store for the Standard Edition server or Enterprise Edition Front End pool.</span></span> <span data-ttu-id="0979f-106">ファイル ストアに既存のファイル共有を使用するか、ファイル共有を保存するファイル サーバーの完全修飾ドメイン名 (FQDN) と、新しいファイル共有のフォルダー名を指定して、新しいファイル共有を指定できます。</span><span class="sxs-lookup"><span data-stu-id="0979f-106">You can use an existing file share for the file store, or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0979f-107">ファイル共有は Enterprise Edition フロント エンド サーバー上に保存することはできませんが、Standard Edition サーバー上に保存できます。</span><span class="sxs-lookup"><span data-stu-id="0979f-107">The file share cannot be located on the Enterprise Edition Front End Server, but can be located on a Standard Edition server.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0979f-108">ファイル共有を作成する前にトポロジ ビルダーでファイル共有を定義できますが、トポロジを公開する前に定義する定義済みの場所にファイル共有を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0979f-108">You can define the file share in Topology Builder before you create the file share, but you must create the file share in the defined location you define before you publish the topology.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0979f-p103">トポロジに Enterprise フロント エンドのプールまたは Standard Edition サーバーを追加する場合、トポロジ ビルダーでファイル共有を設定し、ファイル ストアに使用するファイル共有に随意アクセス制御リスト (DACL) を構成できる必要があります。これには、トポロジ ビルダーを実行して新しいトポロジを公開するときに、サイト共有のフル コントロール アクセス許可 (読み取り/書き込み/変更) を持つアカウントでログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0979f-p103">When you add an Enterprise Front End pool or Standard Edition server to your topology, Topology Builder must be able to set up the file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store. This requires that, when you run Topology Builder to publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span>

<span data-ttu-id="0979f-111">ファイル共有の記憶域のサポートの詳細については、「サポート」のドキュメントの「File [Storage Support」](/previous-versions/office/lync-server-2013/lync-server-2013-file-storage-support) と「展開」SQL Serverの「 [データ](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) とログ ファイルの配置」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0979f-111">For details about storage support for file shares, see [File Storage Support](/previous-versions/office/lync-server-2013/lync-server-2013-file-storage-support) in the Supportability documentation and [SQL Server Data and Log File Placement](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) in the Deployment documentation.</span></span> <span data-ttu-id="0979f-112">ファイル共有の併置の詳細については、「サポート」のドキュメントの「[サポートされるサーバーの併置](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0979f-112">For details about collocation of the file share, see [Supported Server Collocation](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation) in the Supportability documentation.</span></span> <span data-ttu-id="0979f-113">Enterprise Edition フロント エンドのプールのトポロジ設計の詳細については、「展開」のドキュメントの「[Define and Configure a Front End Pool (フロント エンドのプールの定義と構成)](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0979f-113">For details about designing the topology for an Enterprise Edition Front End pool, see [Define and Configure a Front End Pool](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server) in the Deployment documentation.</span></span>