---
title: 'Lync Server 2013: DFS ファイルストレージの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DFS file storage
ms:assetid: a985be20-5a00-4f38-b45b-83dc82de3827
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205150(v=OCS.15)
ms:contentKeyID: 48185037
ms.date: 05/23/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4a9c0bbce2ced36e9df99d7239c2f562b20edbd
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204923"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-dfs-file-storage-for-lync-server-2013"></a><span data-ttu-id="48b08-102">Lync Server 2013 の DFS ファイル記憶域を構成する</span><span class="sxs-lookup"><span data-stu-id="48b08-102">Configure DFS file storage for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48b08-103">_**トピックの最終更新日:** 2016-05-23_</span><span class="sxs-lookup"><span data-stu-id="48b08-103">_**Topic Last Modified:** 2016-05-23_</span></span>

<span data-ttu-id="48b08-104">Lync Server 2013 は、分散ファイルシステム (DFS) でのファイル共有の使用をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="48b08-104">Lync Server 2013 supports using file shares on a Distributed File System (DFS).</span></span> <span data-ttu-id="48b08-105">Windows Server 2008 の DFS の詳細については、「Windows Server 2008 の DFS のステップバイステップガイド[https://go.microsoft.com/fwlink/p/?linkId=202835](https://go.microsoft.com/fwlink/p/?linkid=202835)」を参照してください。DFS を使用するには、Lync Server 2013 に次のものが必要です。</span><span class="sxs-lookup"><span data-stu-id="48b08-105">For details about DFS for Windows Server 2008, see the DFS Step-by-Step Guide for Windows Server 2008 at [https://go.microsoft.com/fwlink/p/?linkId=202835](https://go.microsoft.com/fwlink/p/?linkid=202835).To use a DFS, Lync Server 2013 requires the following:</span></span>

  - <span data-ttu-id="48b08-106">名前空間はドメインベースであること。</span><span class="sxs-lookup"><span data-stu-id="48b08-106">Namespaces are domain based</span></span>

  - <span data-ttu-id="48b08-107">すべての名前空間サーバーで Windows 2008 以降を実行すること。</span><span class="sxs-lookup"><span data-stu-id="48b08-107">All namespace servers are running a minimum of Windows 2008</span></span>

<span data-ttu-id="48b08-108">Lync Server 2013 セットアッププログラムを実行するには、共有フォルダーに対するアクセス許可が管理者へのフルアクセスを許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="48b08-108">Lync Server 2013 setup requires that permissions on shared folder allow full access to Administrator.</span></span> <span data-ttu-id="48b08-109">Lync Server 2013 は、NTFS ファイルアクセス許可を使用してフォルダーに ACL を設定します。</span><span class="sxs-lookup"><span data-stu-id="48b08-109">Lync Server 2013 will then use NTFS file permissions to ACL the folders.</span></span> <span data-ttu-id="48b08-110">継承された DFS 共有アクセス許可はアクセスの制限に使用されません。</span><span class="sxs-lookup"><span data-stu-id="48b08-110">Inherited DFS share permissions will not be used to restrict access.</span></span>

<span data-ttu-id="48b08-111">ファイル共有の要件の詳細については、「サポート」のドキュメントの「 [Lync Server 2013 のファイル記憶域サポート](lync-server-2013-file-storage-support.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48b08-111">For more details about File Share requirements, see [File storage support in Lync Server 2013](lync-server-2013-file-storage-support.md) in the Supportability documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="48b08-112">非 DFS 共有を構成する方法については、「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48b08-112">You may be looking for information on configuring a non-DFS share.</span></span> <span data-ttu-id="48b08-113">その場合は、「 <A href="lync-server-2013-hardware-setup.md">Lync Server 2013 のハードウェアセットアップ</A>」を確認してください。</span><span class="sxs-lookup"><span data-stu-id="48b08-113">If so, check out <A href="lync-server-2013-hardware-setup.md">Hardware setup for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="48b08-114">次の手順では、(DFS セットアップ ガイドに示す) DFS 名前空間ウィザードを使用して、共有フォルダー アクセス許可を適切に構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="48b08-114">The following procedure describes how to correctly configure shared folder permissions using the DFS Namespace Wizard (as described in DFS setup guide).</span></span>

<div>

## <a name="to-configure-shared-folder-permissions"></a><span data-ttu-id="48b08-115">共有フォルダー アクセス許可を構成するには</span><span class="sxs-lookup"><span data-stu-id="48b08-115">To configure shared folder permissions</span></span>

1.  <span data-ttu-id="48b08-116">[**スタート**] ボタンをクリックし、[**すべてのプログラム**] をポイントします。次に、[**管理ツール**] をポイントし、[**DFS の管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="48b08-116">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **DFS Management**.</span></span>

2.  <span data-ttu-id="48b08-117">DFS の管理スナップインのコンソール ツリーで、名前空間サーバー (たとえば、filesrv1.contoso.com) を右クリックし、[**設定の編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="48b08-117">In the console tree of the DFS Management snap-in, right-click the namespace server (for example filesrv1.contoso.com), and then click **Edit Settings**.</span></span>

3.  <span data-ttu-id="48b08-118">[**共有フォルダーのアクセス許可**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="48b08-118">Select **Shared Folder Permissions**.</span></span>

4.  <span data-ttu-id="48b08-119">[**カスタムのアクセス許可**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="48b08-119">Select **Use Custom Permissions**.</span></span>

5.  <span data-ttu-id="48b08-120">管理者グループの場合、[**許可**] の下で、次の選択を行います。</span><span class="sxs-lookup"><span data-stu-id="48b08-120">For the Administrator group, select the following under **Allow**:</span></span>
    
      - <span data-ttu-id="48b08-121">[**フル コントロール**]</span><span class="sxs-lookup"><span data-stu-id="48b08-121">**Full Control**</span></span>
    
      - <span data-ttu-id="48b08-122">**変更**</span><span class="sxs-lookup"><span data-stu-id="48b08-122">**Change**</span></span>
    
      - <span data-ttu-id="48b08-123">**読み取り**</span><span class="sxs-lookup"><span data-stu-id="48b08-123">**Read**</span></span>

6.  <span data-ttu-id="48b08-124">[**適用**] をクリックし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="48b08-124">Click **Apply**, and then click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

