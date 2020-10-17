---
title: 共通領域電話の移行
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Common Area Phones
ms:assetid: 31bd26fc-861b-45c6-8221-18df16e575de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688015(v=OCS.15)
ms:contentKeyID: 49733604
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af08e6de9b832289e898fd27003b896dd40fa81c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503574"
---
# <a name="migrate-common-area-phones"></a>共通領域電話の移行

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-29_

共通領域電話は、ロビー、調理場、または工場の作業場のような、共有ワークスペースまたは共用エリアによく設置されている IP 電話です。 一般的なエリア電話は、Lync Server の UC 機能を提供するためにコンピューターに接続する必要はありません。 Lync server 2010 の展開を Lync Server 2013 に移行した後、従来の共通領域電話に関連付けられている連絡先オブジェクトも移行する必要があります。 Lync Server 管理シェルを使用して、まず、Lync Server 2010 共通領域電話に関連付けられているすべての連絡先オブジェクトを取得し、そのオブジェクトを Lync Server 2013 プールに移動します。

**共通領域電話の移行**

1.  Lync Server 2013 フロントエンドサーバーから、Lync Server 管理シェルを開きます。

2.  コマンド ラインで、次のように入力します。
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net

3.  すべての連絡先オブジェクトが Lync Server 2013 プールに移動されたことを確認するには、Lync Server 管理シェルから次のように入力します。
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
    
    すべての連絡先オブジェクトが Lync Server 2013 プールに関連付けられていることを確認します。

</div>

<span> </span>

</div>

</div>

</div>

