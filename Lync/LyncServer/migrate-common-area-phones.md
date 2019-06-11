---
title: 共通領域電話の移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate Common Area Phones
ms:assetid: 31bd26fc-861b-45c6-8221-18df16e575de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688015(v=OCS.15)
ms:contentKeyID: 49733604
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94be64fea569a898e35c0519c0d1b081431c7f38
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848075"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-common-area-phones"></a>共通領域電話の移行

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-29_

一般的なエリア携帯電話は、共通のワークスペースや一般的な領域 (ロビー、台所、工場など) に存在する IP 電話です。 Lync Server UC 機能を提供するには、一般的なエリア携帯電話がコンピューターに接続されている必要はありません。 Lync Server 2010 の展開を Lync Server 2013 に移行した後、従来の一般的な市外局番に関連付けられた連絡先オブジェクトも移行する必要があります。 Lync Server 管理シェルを使用して、まず Lync Server 2010 共通エリア電話に関連付けられているすべての連絡先オブジェクトを取得してから、それらのオブジェクトを Lync Server 2013 プールに移動します。

**共通領域電話の移行**

1.  Lync Server 2013 フロントエンドサーバーから、Lync Server 管理シェルを開きます。

2.  コマンドラインで、次のように入力します。
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net

3.  すべての連絡先オブジェクトが Lync Server 2013 プールに移動されたことを確認するには、Lync Server 管理シェルで次のように入力します。
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
    
    すべての連絡先オブジェクトが Lync Server 2013 プールと関連付けられていることを確認します。

</div>

<span> </span>

</div>

</div>

</div>

