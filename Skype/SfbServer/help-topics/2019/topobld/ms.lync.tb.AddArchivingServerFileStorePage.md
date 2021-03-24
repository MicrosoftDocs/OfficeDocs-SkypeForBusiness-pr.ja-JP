---
title: アーカイブ サーバーのファイル ストアを追加する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddArchivingServerFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e95f938e-4dd2-48b8-95a3-05b4c63d4810
ROBOTS: NOINDEX, NOFOLLOW
description: インスタント メッセージ (IM) と Web 会議 (ミーティング) の両方のコンテンツのアーカイブを有効にするには、すべての Web 会議のコンテンツのコピー用のファイル ストアとして使用するファイル共有を指定する必要があります。アーカイブ ファイル ストアとして既存のファイル共有を使用することも、ファイル共有を配置するファイル サーバーの完全修飾ドメイン名 (FQDN) と新しいファイル共有のフォルダー名を指定することによって新しいファイル共有を指定することもできます。
ms.openlocfilehash: 2e8c4ac23ce68eab111bbb7775eec23aba2f12d9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100233"
---
# <a name="add-archiving-server-file-store"></a><span data-ttu-id="e9c24-104">アーカイブ サーバーのファイル ストアの追加</span><span class="sxs-lookup"><span data-stu-id="e9c24-104">Add Archiving Server File Store</span></span>

<span data-ttu-id="e9c24-p102">インスタント メッセージ (IM) と Web 会議 (ミーティング) の両方のコンテンツのアーカイブを有効にするには、すべての Web 会議のコンテンツのコピー用のファイル ストアとして使用するファイル共有を指定する必要があります。アーカイブ ファイル ストアとして既存のファイル共有を使用することも、ファイル共有を配置するファイル サーバーの完全修飾ドメイン名 (FQDN) と新しいファイル共有のフォルダー名を指定することによって新しいファイル共有を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="e9c24-p102">To enable the archiving of both instant messaging (IM) and web conferencing (meeting) content, you must specify a file share to be used as the file store for copies of all web conferencing content. You can use an existing file share for the archiving file store, or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e9c24-107">ファイル共有は、ファイル共有を作成する前にトポロジ ビルダーで定義できますが、トポロジを公開する前に定義済みの場所に作成しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9c24-107">You can define the file share in Topology Builder before you create the file share, but you must create the file share in the defined location before you publish the topology.</span></span> <span data-ttu-id="e9c24-108">> トポロジにアーカイブ サーバーを追加する場合、トポロジ ビルダーは、アーカイブ ファイル ストアをセットアップし、ファイル ストアに使用するファイル共有の随意アクセス制御リスト (DACLs) を構成できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9c24-108">> When you add an Archiving Server to your topology, Topology Builder must be able to set up the Archiving file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store.</span></span> <span data-ttu-id="e9c24-109">これには、トポロジ ビルダーを実行して新しいトポロジを公開するときに、サイト共有のフル コントロール アクセス許可 (読み取り/書き込み/変更) を持つアカウントでログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9c24-109">This requires that, when you run Topology Builder to publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span>

<span data-ttu-id="e9c24-110">ファイル共有の記憶域のサポートの詳細については、「サポート」のドキュメントの「File [Storage Support」](/previous-versions/office/lync-server-2013/lync-server-2013-file-storage-support) と「展開」SQL Serverの「 [データ](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) とログ ファイルの配置」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9c24-110">For details about storage support for file shares, see [File Storage Support](/previous-versions/office/lync-server-2013/lync-server-2013-file-storage-support) in the Supportability documentation and [SQL Server Data and Log File Placement](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) in the Deployment documentation.</span></span> <span data-ttu-id="e9c24-111">ファイル共有の併置の詳細については、「サポート」のドキュメントの「[Supported Server Collocation](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9c24-111">For details about collocation of the file share, see [Supported Server Collocation](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation) in the Supportability documentation.</span></span>