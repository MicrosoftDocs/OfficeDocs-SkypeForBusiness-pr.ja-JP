---
title: ディレクター ファイル ストアの追加
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a15b69e0-d3d1-4648-af25-1c0f25e5da8e
ROBOTS: NOINDEX, NOFOLLOW
description: ディレクターのファイル ストアとして使用するファイル共有を指定する必要があります。 ファイル ストアに既存のファイル共有を使用するか、ファイル共有を保存するファイル サーバーの完全修飾ドメイン名 (FQDN) と、新しいファイル共有のフォルダー名を指定して、新しいファイル共有を指定できます。
ms.openlocfilehash: 56fb33653f2f463e9b336ae447a1c665680ed6df
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100143"
---
# <a name="add-director-file-store"></a><span data-ttu-id="e87dd-104">ディレクター ファイル ストアの追加</span><span class="sxs-lookup"><span data-stu-id="e87dd-104">Add Director File Store</span></span>

<span data-ttu-id="e87dd-105">ディレクターのファイル ストアとして使用するファイル共有を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e87dd-105">You must specify a file share to be used as the file store for Directors.</span></span> <span data-ttu-id="e87dd-106">ファイル ストアに既存のファイル共有を使用するか、ファイル共有を保存するファイル サーバーの完全修飾ドメイン名 (FQDN) と、新しいファイル共有のフォルダー名を指定して、新しいファイル共有を指定できます。</span><span class="sxs-lookup"><span data-stu-id="e87dd-106">You can use an existing file share for the file store, or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e87dd-p103">トポロジにディレクターを追加する場合、トポロジの公開には、ファイル共有を設定し、ファイル ストアに使用するファイル共有に随意アクセス制御リスト (DACL) を構成するための適切なアクセスが必要になります。これには、トポロジ ビルダーを実行して新しいトポロジを公開するときに、ファイル共有のフル コントロール アクセス許可 (読み取り/書き込み/変更) を持つアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e87dd-p103">When you add Directors to a topology, topology publication requires appropriate access to set up the file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store. This requires that, when you run Topology Builder and publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span>

<span data-ttu-id="e87dd-109">ファイル共有の記憶域のサポートの詳細については、「サポート」のドキュメントの「File [Storage Support」](/previous-versions/office/lync-server-2013/lync-server-2013-file-storage-support) と「展開」SQL Serverの「 [データ](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) とログ ファイルの配置」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e87dd-109">For details about storage support for file shares, see [File Storage Support](/previous-versions/office/lync-server-2013/lync-server-2013-file-storage-support) in the Supportability documentation and [SQL Server Data and Log File Placement](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) in the Deployment documentation.</span></span> <span data-ttu-id="e87dd-110">ファイル共有の併置の詳細については、「サポート」のドキュメントの「[サポートされるサーバーの併置](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e87dd-110">For details about collocation of the file share, see [Supported Server Collocation](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation) in the Supportability documentation.</span></span> <span data-ttu-id="e87dd-111">ディレクターのトポロジの設計の詳細については、「展開」のドキュメントの [「Define a Single Director in Topology Builder」](/previous-versions/office/lync-server-2013/lync-server-2013-define-optional-director-topologies-in-your-topology) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e87dd-111">For details about designing the topology for Directors, see [Define a Single Director in Topology Builder](/previous-versions/office/lync-server-2013/lync-server-2013-define-optional-director-topologies-in-your-topology) in the Deployment documentation.</span></span>