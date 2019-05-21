---
title: アーカイブ サーバーのファイル ストアの追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddArchivingServerFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e95f938e-4dd2-48b8-95a3-05b4c63d4810
description: インスタント メッセージ (IM) と Web 会議 (ミーティング) の両方のコンテンツのアーカイブを有効にするには、すべての Web 会議のコンテンツのコピー用のファイル ストアとして使用するファイル共有を指定する必要があります。アーカイブ ファイル ストアとして既存のファイル共有を使用することも、ファイル共有を配置するファイル サーバーの完全修飾ドメイン名 (FQDN) と新しいファイル共有のフォルダー名を指定することによって新しいファイル共有を指定することもできます。
ms.openlocfilehash: 99527455af38211ab788676b1072069924da9935
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34304927"
---
# <a name="add-archiving-server-file-store"></a><span data-ttu-id="014dd-104">アーカイブ サーバーのファイル ストアの追加</span><span class="sxs-lookup"><span data-stu-id="014dd-104">Add Archiving Server File Store</span></span>

<span data-ttu-id="014dd-p102">インスタント メッセージ (IM) と Web 会議 (ミーティング) の両方のコンテンツのアーカイブを有効にするには、すべての Web 会議のコンテンツのコピー用のファイル ストアとして使用するファイル共有を指定する必要があります。アーカイブ ファイル ストアとして既存のファイル共有を使用することも、ファイル共有を配置するファイル サーバーの完全修飾ドメイン名 (FQDN) と新しいファイル共有のフォルダー名を指定することによって新しいファイル共有を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="014dd-p102">To enable the archiving of both instant messaging (IM) and web conferencing (meeting) content, you must specify a file share to be used as the file store for copies of all web conferencing content. You can use an existing file share for the archiving file store, or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="014dd-107">ファイル共有は、ファイル共有を作成する前にトポロジ ビルダーで定義できますが、トポロジを公開する前に定義済みの場所に作成しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="014dd-107">You can define the file share in Topology Builder before you create the file share, but you must create the file share in the defined location before you publish the topology.</span></span> <span data-ttu-id="014dd-108">> アーカイブサーバーをトポロジに追加する場合、トポロジビルダーは、アーカイブファイルストアをセットアップし、ファイル共有に使用する随意アクセス制御リスト (Dacl) を構成できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="014dd-108">> When you add an Archiving Server to your topology, Topology Builder must be able to set up the Archiving file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store.</span></span> <span data-ttu-id="014dd-109">そのため、トポロジ ビルダーを実行して新しいトポロジを公開するときに、サイト共有のフル コントロール アクセス許可 (読み取り/書き込み/変更) を持つアカウントでログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="014dd-109">This requires that, when you run Topology Builder to publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span>

<span data-ttu-id="014dd-p104">ファイル共有の記憶域サポートの詳細については、「サポート」のドキュメントの「[File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx)」および「展開」のドキュメントの「[SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)」を参照してください。ファイル共有の併置の詳細については、「サポート」のドキュメントの「[Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="014dd-p104">For details about storage support for file shares, see [File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) in the Supportability documentation and [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation. For details about collocation of the file share, see [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) in the Supportability documentation.</span></span>


