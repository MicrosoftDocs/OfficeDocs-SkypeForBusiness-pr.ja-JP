---
title: フロントエンド ファイル ストアの追加
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
- ms.lync.tb.AddFrontEndFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d18a648-a0e1-4401-a1e6-7a2755ba8c66
description: Standard Edition サーバーまたは Enterprise Edition フロントエンドプールのファイルストアとして使用するファイル共有を指定する必要があります。 既存のファイル共有をファイルストアに使用することも、ファイル共有を配置するファイルサーバーの完全修飾ドメイン名 (FQDN) と新しいファイル共有のフォルダー名を指定して、新しいファイル共有を指定することもできます。
ms.openlocfilehash: 4e2c732e0003f23cf183374880592ccd24fbe9bb
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218348"
---
# <a name="add-front-end-file-store"></a><span data-ttu-id="0a0c8-104">フロントエンド ファイル ストアの追加</span><span class="sxs-lookup"><span data-stu-id="0a0c8-104">Add Front End File Store</span></span>

<span data-ttu-id="0a0c8-105">Standard Edition サーバーまたは Enterprise Edition フロントエンドプールのファイルストアとして使用するファイル共有を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a0c8-105">You must specify a file share to be used as the file store for the Standard Edition server or Enterprise Edition Front End pool.</span></span> <span data-ttu-id="0a0c8-106">既存のファイル共有をファイルストアに使用することも、ファイル共有を配置するファイルサーバーの完全修飾ドメイン名 (FQDN) と新しいファイル共有のフォルダー名を指定して、新しいファイル共有を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="0a0c8-106">You can use an existing file share for the file store, or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0a0c8-107">ファイル共有は Enterprise Edition フロントエンドサーバーに配置することはできませんが、Standard Edition サーバーに配置することができます。</span><span class="sxs-lookup"><span data-stu-id="0a0c8-107">The file share cannot be located on the Enterprise Edition Front End Server, but can be located on a Standard Edition server.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0a0c8-108">ファイル共有を作成する前にトポロジ ビルダーでファイル共有を定義できますが、トポロジを公開する前に定義する定義済みの場所にファイル共有を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a0c8-108">You can define the file share in Topology Builder before you create the file share, but you must create the file share in the defined location you define before you publish the topology.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0a0c8-p103">トポロジに Enterprise フロント エンドのプールまたは Standard Edition サーバーを追加する場合、トポロジ ビルダーでファイル共有を設定し、ファイル ストアに使用するファイル共有に随意アクセス制御リスト (DACL) を構成できる必要があります。これには、トポロジ ビルダーを実行して新しいトポロジを公開するときに、サイト共有のフル コントロール アクセス許可 (読み取り/書き込み/変更) を持つアカウントでログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a0c8-p103">When you add an Enterprise Front End pool or Standard Edition server to your topology, Topology Builder must be able to set up the file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store. This requires that, when you run Topology Builder to publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span>

<span data-ttu-id="0a0c8-111">ファイル共有の記憶域サポートの詳細については、「展開」のドキュメントの「サポート」のドキュメントの「 [File Storage support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) 」、および「 [SQL Server Data And Log file Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a0c8-111">For details about storage support for file shares, see [File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) in the Supportability documentation and [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span> <span data-ttu-id="0a0c8-112">ファイル共有の併置の詳細については、「サポート」のドキュメントの「[サポートされるサーバーの併置](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a0c8-112">For details about collocation of the file share, see [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="0a0c8-113">Enterprise Edition フロント エンドのプールのトポロジ設計の詳細については、「展開」のドキュメントの「[Define and Configure a Front End Pool (フロント エンドのプールの定義と構成)](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a0c8-113">For details about designing the topology for an Enterprise Edition Front End pool, see [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in the Deployment documentation.</span></span>


