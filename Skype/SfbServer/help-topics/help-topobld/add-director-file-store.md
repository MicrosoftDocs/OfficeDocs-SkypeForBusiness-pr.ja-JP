---
title: ディレクター ファイル ストアの追加
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a15b69e0-d3d1-4648-af25-1c0f25e5da8e
description: ディレクターのファイル ストアとして使用するファイル共有を指定する必要があります。 既存のファイル共有をファイル ストアに使用するか、ファイル共有を格納するファイル サーバーの完全修飾ドメイン名 (FQDN) と新しいファイル共有のフォルダー名を指定して、新しいファイル共有を指定できます。
ms.openlocfilehash: 2c7ad609ea3e58f0368f8c1e3d8716223aa68700
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824287"
---
# <a name="add-director-file-store"></a><span data-ttu-id="5b689-104">ディレクター ファイル ストアの追加</span><span class="sxs-lookup"><span data-stu-id="5b689-104">Add Director File Store</span></span>

<span data-ttu-id="5b689-105">ディレクターのファイル ストアとして使用するファイル共有を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b689-105">You must specify a file share to be used as the file store for Directors.</span></span> <span data-ttu-id="5b689-106">既存のファイル共有をファイル ストアに使用するか、ファイル共有を格納するファイル サーバーの完全修飾ドメイン名 (FQDN) と新しいファイル共有のフォルダー名を指定して、新しいファイル共有を指定できます。</span><span class="sxs-lookup"><span data-stu-id="5b689-106">You can use an existing file share for the file store, or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5b689-p103">トポロジにディレクターを追加する場合、トポロジの公開には、ファイル共有を設定し、ファイル ストアに使用するファイル共有に随意アクセス制御リスト (DACL) を構成するための適切なアクセスが必要になります。これには、トポロジ ビルダーを実行して新しいトポロジを公開するときに、ファイル共有のフル コントロール アクセス許可 (読み取り/書き込み/変更) を持つアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b689-p103">When you add Directors to a topology, topology publication requires appropriate access to set up the file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store. This requires that, when you run Topology Builder and publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span>

<span data-ttu-id="5b689-109">ファイル共有の記憶域のサポートの詳細については、「[](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx)サポート」のドキュメントの「ファイル 記憶域のサポート」および「展開」のドキュメントの「SQL Server [Data and Log File Placement」](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b689-109">For details about storage support for file shares, see [File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) in the Supportability documentation and [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span> <span data-ttu-id="5b689-110">ファイル共有の併置の詳細については、「サポート」のドキュメントの「[サポートされるサーバーの併置](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b689-110">For details about collocation of the file share, see [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="5b689-111">ディレクターのトポロジ設計の詳細については、「展開」のドキュメントの [「Define a Single Director in Topology Builder」](https://technet.microsoft.com/library/8e9a659d-23b0-401d-b296-59c7df414d49.aspx) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b689-111">For details about designing the topology for Directors, see [Define a Single Director in Topology Builder](https://technet.microsoft.com/library/8e9a659d-23b0-401d-b296-59c7df414d49.aspx) in the Deployment documentation.</span></span>


