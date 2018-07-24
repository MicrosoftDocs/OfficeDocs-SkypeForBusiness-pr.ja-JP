---
title: フロントエンド ファイル ストアの追加
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d18a648-a0e1-4401-a1e6-7a2755ba8c66
ROBOTS: NOINDEX, NOFOLLOW
description: Standard Edition サーバーまたは Enterprise Edition フロントエンド プールのファイル ストアとして使用するファイル共有を指定する必要があります。既存のファイル共有をファイル ストアに使用できます。または、ファイル共有を配置するファイル サーバーの完全修飾ドメイン名 (FQDN) と新しいファイル共有のフォルダー名を指定して、新しいファイル共有を指定することもできます。
ms.openlocfilehash: cb280a8c9bb554ee3321fc38cf075d039388dfc6
ms.sourcegitcommit: 1f7299f535ec6b34f92301b4abc14d8922492eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "21059929"
---
# <a name="add-front-end-file-store"></a><span data-ttu-id="ef7e3-104">フロントエンド ファイル ストアの追加</span><span class="sxs-lookup"><span data-stu-id="ef7e3-104">Add Front End File Store</span></span>
 
<span data-ttu-id="ef7e3-p102">Standard Edition サーバーまたは Enterprise Edition フロントエンド プールのファイル ストアとして使用するファイル共有を指定する必要があります。既存のファイル共有をファイル ストアに使用できます。または、ファイル共有を配置するファイル サーバーの完全修飾ドメイン名 (FQDN) と新しいファイル共有のフォルダー名を指定して、新しいファイル共有を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="ef7e3-p102">You must specify a file share to be used as the file store for the Standard Edition server or Enterprise Edition Front End pool. You can use an existing file share for the file store, or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ef7e3-107">ファイル共有は、Enterprise Edition フロントエンド サーバーに配置することはできませんが、Standard Edition サーバーに配置することができます。</span><span class="sxs-lookup"><span data-stu-id="ef7e3-107">The file share cannot be located on the Enterprise Edition Front End Server, but can be located on a Standard Edition server.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="ef7e3-108">ファイル共有を作成する前にトポロジ ビルダーでファイル共有を定義できますが、トポロジを公開する前に定義する定義済みの場所にファイル共有を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef7e3-108">You can define the file share in Topology Builder before you create the file share, but you must create the file share in the defined location you define before you publish the topology.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="ef7e3-p103">トポロジに Enterprise フロントエンドのプールまたは Standard Edition サーバーを追加する場合、トポロジ ビルダーでファイル共有を設定し、ファイル ストアに使用するファイル共有に随意アクセス制御リスト (DACL) を構成できる必要があります。これには、トポロジ ビルダーを実行して新しいトポロジを公開するときに、サイト共有のフル コントロール アクセス許可 (読み取り/書き込み/変更) を持つアカウントでログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef7e3-p103">When you add an Enterprise Front End pool or Standard Edition server to your topology, Topology Builder must be able to set up the file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store. This requires that, when you run Topology Builder to publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span> 
  
<span data-ttu-id="ef7e3-111">ファイル共有のストレージ ・ サポートの詳細についてを参照してください[ファイル記憶域をサポート](http://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx)サポート マニュアルと[SQL Server のデータとログ ファイルの配置](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)の展開に関するドキュメント。</span><span class="sxs-lookup"><span data-stu-id="ef7e3-111">For details about storage support for file shares, see [File Storage Support](http://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) in the Supportability documentation and [SQL Server Data and Log File Placement](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span> <span data-ttu-id="ef7e3-112">コロケーション ファイル共有の詳細については、サポート ドキュメントで[サポートされているサーバーのコロケーション](http://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef7e3-112">For details about collocation of the file share, see [Supported Server Collocation](http://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="ef7e3-113">エンタープライズ エディションのフロント エンド プールのトポロジの設計に関する詳細については、展開に関するドキュメントの[定義およびフロント エンド プールを構成する](http://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef7e3-113">For details about designing the topology for an Enterprise Edition Front End pool, see [Define and Configure a Front End Pool](http://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in the Deployment documentation.</span></span>
  

