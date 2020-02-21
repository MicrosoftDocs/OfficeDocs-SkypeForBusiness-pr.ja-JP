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

# <a name="configure-dfs-file-storage-for-lync-server-2013"></a>Lync Server 2013 の DFS ファイル記憶域を構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2016-05-23_

Lync Server 2013 は、分散ファイルシステム (DFS) でのファイル共有の使用をサポートしています。 Windows Server 2008 の DFS の詳細については、「Windows Server 2008 の DFS のステップバイステップガイド[https://go.microsoft.com/fwlink/p/?linkId=202835](https://go.microsoft.com/fwlink/p/?linkid=202835)」を参照してください。DFS を使用するには、Lync Server 2013 に次のものが必要です。

  - 名前空間はドメインベースであること。

  - すべての名前空間サーバーで Windows 2008 以降を実行すること。

Lync Server 2013 セットアッププログラムを実行するには、共有フォルダーに対するアクセス許可が管理者へのフルアクセスを許可する必要があります。 Lync Server 2013 は、NTFS ファイルアクセス許可を使用してフォルダーに ACL を設定します。 継承された DFS 共有アクセス許可はアクセスの制限に使用されません。

ファイル共有の要件の詳細については、「サポート」のドキュメントの「 [Lync Server 2013 のファイル記憶域サポート](lync-server-2013-file-storage-support.md)」を参照してください。

<div>


> [!NOTE]  
> 非 DFS 共有を構成する方法については、「」を参照してください。 その場合は、「 <A href="lync-server-2013-hardware-setup.md">Lync Server 2013 のハードウェアセットアップ</A>」を確認してください。



</div>

次の手順では、(DFS セットアップ ガイドに示す) DFS 名前空間ウィザードを使用して、共有フォルダー アクセス許可を適切に構成する方法について説明します。

<div>

## <a name="to-configure-shared-folder-permissions"></a>共有フォルダー アクセス許可を構成するには

1.  [**スタート**] ボタンをクリックし、[**すべてのプログラム**] をポイントします。次に、[**管理ツール**] をポイントし、[**DFS の管理**] をクリックします。

2.  DFS の管理スナップインのコンソール ツリーで、名前空間サーバー (たとえば、filesrv1.contoso.com) を右クリックし、[**設定の編集**] をクリックします。

3.  [**共有フォルダーのアクセス許可**] を選択します。

4.  [**カスタムのアクセス許可**] を選択します。

5.  管理者グループの場合、[**許可**] の下で、次の選択を行います。
    
      - [**フル コントロール**]
    
      - **変更**
    
      - **読み取り**

6.  [**適用**] をクリックし、[**OK**] をクリックします。

</div>

</div>

<span> </span>

</div>

</div>

</div>

