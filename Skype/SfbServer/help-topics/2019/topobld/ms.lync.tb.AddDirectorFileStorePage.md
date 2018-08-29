---
title: ディレクターのファイル ストアの追加
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a15b69e0-d3d1-4648-af25-1c0f25e5da8e
ROBOTS: NOINDEX, NOFOLLOW
description: ディレクターのファイル ストアとして使用するファイル共有を指定する必要があります。既存のファイル共有をファイル ストアに使用できます。または、ファイル共有を配置するファイル サーバーの完全修飾ドメイン名 (FQDN) と新しいファイル共有のフォルダー名を指定して、新しいファイル共有を指定することもできます。
ms.openlocfilehash: 76968644617b6ec9e8fe255c0aae93ee07eaa207
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2018
ms.locfileid: "23245070"
---
# <a name="add-director-file-store"></a><span data-ttu-id="f7d6d-104">ディレクターのファイル ストアの追加</span><span class="sxs-lookup"><span data-stu-id="f7d6d-104">Add Director File Store</span></span>

<span data-ttu-id="f7d6d-p102">ディレクターのファイル ストアとして使用するファイル共有を指定する必要があります。既存のファイル共有をファイル ストアに使用できます。または、ファイル共有を配置するファイル サーバーの完全修飾ドメイン名 (FQDN) と新しいファイル共有のフォルダー名を指定して、新しいファイル共有を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="f7d6d-p102">You must specify a file share to be used as the file store for Directors. You can use an existing file share for the file store, or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f7d6d-p103">トポロジにディレクターを追加する場合、トポロジの公開には、ファイル共有を設定し、ファイル ストアに使用するファイル共有に随意アクセス制御リスト (DACL) を構成するための適切なアクセス権が必要になります。そのため、トポロジ ビルダーを実行して新しいトポロジを公開するときに、ファイル共有のフル コントロール アクセス許可 (読み取り/書き込み/変更) を持つアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7d6d-p103">When you add Directors to a topology, topology publication requires appropriate access to set up the file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store. This requires that, when you run Topology Builder and publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span>

<span data-ttu-id="f7d6d-109">ファイル共有のストレージ ・ サポートの詳細についてを参照してください[ファイル記憶域をサポート](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx)サポート マニュアルと[SQL Server のデータとログ ファイルの配置](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)の展開に関するドキュメント。</span><span class="sxs-lookup"><span data-stu-id="f7d6d-109">For details about storage support for file shares, see [File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) in the Supportability documentation and [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span> <span data-ttu-id="f7d6d-110">コロケーション ファイル共有の詳細については、サポート ドキュメントで[サポートされているサーバーのコロケーション](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7d6d-110">For details about collocation of the file share, see [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="f7d6d-111">ディレクターのトポロジの設計についての詳細は、展開に関するドキュメントで[定義するトポロジ ビルダーで単一のディレクター](https://technet.microsoft.com/library/8e9a659d-23b0-401d-b296-59c7df414d49.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7d6d-111">For details about designing the topology for Directors, see [Define a Single Director in Topology Builder](https://technet.microsoft.com/library/8e9a659d-23b0-401d-b296-59c7df414d49.aspx) in the Deployment documentation.</span></span>


