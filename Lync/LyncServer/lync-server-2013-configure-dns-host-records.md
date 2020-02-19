---
title: 'Lync Server 2013: DNS ホストレコードの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS Host records
ms:assetid: 78a1afcf-41c8-4da5-8740-c6570c19078c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398593(v=OCS.15)
ms:contentKeyID: 48184577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8184568e18f37e2a00316d3b648b5e8813faa268
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140380"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-dns-host-records-for-lync-server-2013"></a>Lync Server 2013 の DNS ホストレコードの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-01_

この手順を適切に完了するには、少なくとも Domain Admins グループのメンバーまたは DnsAdmins グループのメンバーとしてサーバーまたはドメインにログオンする必要があります。

<div>

## <a name="to-configure-dns-host-a-records"></a>DNS ホスト A レコードを構成するには

1.  ドメイン ネーム システム (DNS) サーバーで、[**スタート**]、[**管理ツール**]、および [**DNS**] の順にクリックします。

2.  ドメインのコンソールツリーで、[**前方参照ゾーン**] を展開し、Lync Server 2013 がインストールされるドメインを右クリックします。

3.  [**新しいホスト (A または AAAA)**] をクリックします。

4.  [**名前**] をクリックして、プールのホスト名を入力します (ドメイン名は、レコードが定義されるゾーンから取られるため、A レコードの一部として入力する必要はありません)。

5.  [ **IP アドレス**] をクリックし、フロントエンドプールのロードバランサーの仮想 IP (VIP) を入力します。
    
    <div>
    

    > [!IMPORTANT]  
    > ディレクター プールを使用する展開では、簡易 URL のホスト (A) はディレクター ロード バランサーの VIP をポイントする必要があります。

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > ロード バランサーなしでトポロジに接続する Enterprise Edition サーバーまたはディレクターを 1 つだけ展開する場合、または Standard Edition サーバーを展開する場合は、Enterprise Edition サーバー、Standard Edition サーバー、または Director の IP アドレスを入力します。 プールに複数の Enterprise Edition サーバーまたはディレクターを展開する場合は、ロード バランサーが必要です。 ロード バランサーは、Standard Edition サーバーでは使用されません。

    
    </div>

6.  [**ホストの追加**] をクリックし、[**OK**] をクリックします。

7.  追加の A レコードを作成するには、ステップ 4. と 5. を繰り返します。

8.  必要な A レコードをすべて作成したら、[**完了**] をクリックします。

</div>

</div>

<span> </span>

</div>

</div>

</div>

