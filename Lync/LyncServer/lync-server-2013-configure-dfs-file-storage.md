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

# <a name="configure-dfs-file-storage-for-lync-server-2013"></a>Lync Server 2013 でファイルの記憶域を構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2016-05-23_

Lync Server 2013 は、分散ファイルシステム (DFS) でのファイル共有の使用をサポートしています。 Windows Server 2008 用の DFS の詳細については、Windows Server 2008 の DFS のステップバイステップガイド[http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835)を参照してください。DFS を使用するには、Lync Server 2013 で次のことを行う必要があります。

  - 名前空間はドメインベース

  - すべての名前空間サーバーは、少なくとも Windows 2008 を実行しています

Lync Server 2013 セットアップでは、共有フォルダーに対するアクセス許可を付与して、管理者へのフルアクセスを許可する必要があります。 Lync Server 2013 は、NTFS ファイルのアクセス許可を使用してフォルダーに ACL を設定します。 継承された DFS 共有のアクセス許可は、アクセスを制限するためには使用されません。

ファイル共有の要件の詳細については、サポートドキュメントの「 [Lync Server 2013 でのファイルストレージのサポート](lync-server-2013-file-storage-support.md)」を参照してください。

<div>


> [!NOTE]  
> DFS 以外の共有を構成する方法については、こちらを参照してください。 その場合は、「 <A href="lync-server-2013-hardware-setup.md">Lync Server 2013 用のハードウェアのセットアップ</A>」をご覧ください。



</div>

次の手順では、DFS 名前空間ウィザードを使用して、共有フォルダーのアクセス許可を適切に構成する方法について説明します (「DFS のセットアップガイド」で説明します)。

<div>

## <a name="to-configure-shared-folder-permissions"></a>共有フォルダーのアクセス許可を構成するには

1.  [**スタート**] をクリックし、[**すべてのプログラム**]、[**管理ツール**] の順にポイントして、[ **DFS の管理**] をクリックします。

2.  DFS の管理スナップインのコンソールツリーで、名前空間サーバー (たとえば、filesrv1.contoso.com) を右クリックし、[**設定の編集**] をクリックします。

3.  [**共有フォルダーの権限**] を選びます。

4.  [**ユーザー設定の権限を使用する**] を選びます。

5.  [管理者] グループで、[許可] で次の**よう**に選択します。
    
      - **フルコントロール**
    
      - **変更**
    
      - **モード**

6.  [**適用**] をクリックし、[ **OK]** をクリックします。

</div>

</div>

<span> </span>

</div>

</div>

</div>

