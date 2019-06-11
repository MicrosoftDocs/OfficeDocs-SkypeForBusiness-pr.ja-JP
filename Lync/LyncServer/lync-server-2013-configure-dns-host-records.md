---
title: 'Lync Server 2013: DNS ホスト レコードの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure DNS Host records
ms:assetid: 78a1afcf-41c8-4da5-8740-c6570c19078c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398593(v=OCS.15)
ms:contentKeyID: 48184577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac3bb3c771d99e56e0c584675d77a92d95fdd757
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840386"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-host-records-for-lync-server-2013"></a>Lync Server 2013 での DNS ホスト レコードの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-01_

この手順を正常に完了するには、少なくとも Domain Admins グループのメンバーまたは DnsAdmins グループのメンバーとしてサーバーまたはドメインにログオンしている必要があります。

<div>

## <a name="to-configure-dns-host-a-records"></a>DNS ホスト A レコードを構成するには

1.  ドメインネームシステム (DNS) サーバーで、[**スタート**] をクリックし、[**管理ツール**]、[ **DNS**] の順にクリックします。

2.  ドメインのコンソールツリーで [**前方参照ゾーン**] を展開し、Lync Server 2013 がインストールされているドメインを右クリックします。

3.  [**新しいホスト (A または AAAA)**] をクリックします。

4.  [**名前**] をクリックし、プールのホスト名を入力します (ドメイン名は、レコードが定義されているゾーンから、A レコードの一部として入力する必要はありません)。

5.  [ **IP アドレス**] をクリックし、フロントエンドプールのロードバランサーの仮想 IP (VIP) を入力します。
    
    <div>
    

    > [!IMPORTANT]  
    > ディレクタープールを使用する展開では、シンプルな Url の host (A) レコードはディレクターロードバランサーの VIP を参照する必要があります。

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > ロードバランサーを使用しないトポロジに接続されている Enterprise Edition サーバーまたはディレクターを1つだけ展開する場合、または Standard Edition サーバーを展開する場合は、Enterprise Edition server、Standard Edition server、またはディレクターの IP アドレスを入力します。 プールに複数の Enterprise Edition サーバーまたはディレクターを展開する場合は、ロードバランサーが必要です。 ロードバランサーは、Standard Edition サーバーでは使用されません。

    
    </div>

6.  [**ホストの追加**] をクリックし、[ **OK**] をクリックします。

7.  追加のレコードを作成するには、手順4と5を繰り返します。

8.  必要なすべてのレコードの作成が完了したら、[**完了**] をクリックします。

</div>

</div>

<span> </span>

</div>

</div>

</div>

