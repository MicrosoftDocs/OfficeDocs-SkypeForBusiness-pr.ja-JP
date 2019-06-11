---
title: 'Lync Server 2013: ファイルの記憶域を構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure DFS file storage
ms:assetid: a985be20-5a00-4f38-b45b-83dc82de3827
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205150(v=OCS.15)
ms:contentKeyID: 48185037
ms.date: 05/23/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c34d0f93e94c954b3ad2ab6cbd472a3d6a40e3e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840404"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dfs-file-storage-for-lync-server-2013"></a><span data-ttu-id="6d1fd-102">Lync Server 2013 でファイルの記憶域を構成する</span><span class="sxs-lookup"><span data-stu-id="6d1fd-102">Configure DFS file storage for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d1fd-103">_**最終更新日:** 2016-05-23_</span><span class="sxs-lookup"><span data-stu-id="6d1fd-103">_**Topic Last Modified:** 2016-05-23_</span></span>

<span data-ttu-id="6d1fd-104">Lync Server 2013 は、分散ファイルシステム (DFS) でのファイル共有の使用をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="6d1fd-104">Lync Server 2013 supports using file shares on a Distributed File System (DFS).</span></span> <span data-ttu-id="6d1fd-105">Windows Server 2008 用の DFS の詳細については、Windows Server 2008 の DFS のステップバイステップガイド[http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835)を参照してください。DFS を使用するには、Lync Server 2013 で次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d1fd-105">For details about DFS for Windows Server 2008, see the DFS Step-by-Step Guide for Windows Server 2008 at [http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835).To use a DFS, Lync Server 2013 requires the following:</span></span>

  - <span data-ttu-id="6d1fd-106">名前空間はドメインベース</span><span class="sxs-lookup"><span data-stu-id="6d1fd-106">Namespaces are domain based</span></span>

  - <span data-ttu-id="6d1fd-107">すべての名前空間サーバーは、少なくとも Windows 2008 を実行しています</span><span class="sxs-lookup"><span data-stu-id="6d1fd-107">All namespace servers are running a minimum of Windows 2008</span></span>

<span data-ttu-id="6d1fd-108">Lync Server 2013 セットアップでは、共有フォルダーに対するアクセス許可を付与して、管理者へのフルアクセスを許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d1fd-108">Lync Server 2013 setup requires that permissions on shared folder allow full access to Administrator.</span></span> <span data-ttu-id="6d1fd-109">Lync Server 2013 は、NTFS ファイルのアクセス許可を使用してフォルダーに ACL を設定します。</span><span class="sxs-lookup"><span data-stu-id="6d1fd-109">Lync Server 2013 will then use NTFS file permissions to ACL the folders.</span></span> <span data-ttu-id="6d1fd-110">継承された DFS 共有のアクセス許可は、アクセスを制限するためには使用されません。</span><span class="sxs-lookup"><span data-stu-id="6d1fd-110">Inherited DFS share permissions will not be used to restrict access.</span></span>

<span data-ttu-id="6d1fd-111">ファイル共有の要件の詳細については、サポートドキュメントの「 [Lync Server 2013 でのファイルストレージのサポート](lync-server-2013-file-storage-support.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d1fd-111">For more details about File Share requirements, see [File storage support in Lync Server 2013](lync-server-2013-file-storage-support.md) in the Supportability documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6d1fd-112">DFS 以外の共有を構成する方法については、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d1fd-112">You may be looking for information on configuring a non-DFS share.</span></span> <span data-ttu-id="6d1fd-113">その場合は、「 <A href="lync-server-2013-hardware-setup.md">Lync Server 2013 用のハードウェアのセットアップ</A>」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6d1fd-113">If so, check out <A href="lync-server-2013-hardware-setup.md">Hardware setup for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="6d1fd-114">次の手順では、DFS 名前空間ウィザードを使用して、共有フォルダーのアクセス許可を適切に構成する方法について説明します (「DFS のセットアップガイド」で説明します)。</span><span class="sxs-lookup"><span data-stu-id="6d1fd-114">The following procedure describes how to correctly configure shared folder permissions using the DFS Namespace Wizard (as described in DFS setup guide).</span></span>

<div>

## <a name="to-configure-shared-folder-permissions"></a><span data-ttu-id="6d1fd-115">共有フォルダーのアクセス許可を構成するには</span><span class="sxs-lookup"><span data-stu-id="6d1fd-115">To configure shared folder permissions</span></span>

1.  <span data-ttu-id="6d1fd-116">[**スタート**] をクリックし、[**すべてのプログラム**]、[**管理ツール**] の順にポイントして、[ **DFS の管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d1fd-116">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **DFS Management**.</span></span>

2.  <span data-ttu-id="6d1fd-117">DFS の管理スナップインのコンソールツリーで、名前空間サーバー (たとえば、filesrv1.contoso.com) を右クリックし、[**設定の編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d1fd-117">In the console tree of the DFS Management snap-in, right-click the namespace server (for example filesrv1.contoso.com), and then click **Edit Settings**.</span></span>

3.  <span data-ttu-id="6d1fd-118">[**共有フォルダーの権限**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="6d1fd-118">Select **Shared Folder Permissions**.</span></span>

4.  <span data-ttu-id="6d1fd-119">[**ユーザー設定の権限を使用する**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="6d1fd-119">Select **Use Custom Permissions**.</span></span>

5.  <span data-ttu-id="6d1fd-120">[管理者] グループで、[許可] で次の**よう**に選択します。</span><span class="sxs-lookup"><span data-stu-id="6d1fd-120">For the Administrator group, select the following under **Allow**:</span></span>
    
      - <span data-ttu-id="6d1fd-121">**フルコントロール**</span><span class="sxs-lookup"><span data-stu-id="6d1fd-121">**Full Control**</span></span>
    
      - <span data-ttu-id="6d1fd-122">**変更**</span><span class="sxs-lookup"><span data-stu-id="6d1fd-122">**Change**</span></span>
    
      - <span data-ttu-id="6d1fd-123">**モード**</span><span class="sxs-lookup"><span data-stu-id="6d1fd-123">**Read**</span></span>

6.  <span data-ttu-id="6d1fd-124">[**適用**] をクリックし、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d1fd-124">Click **Apply**, and then click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

