---
title: 'Lync Server 2013: セカンダリの場所情報サービスを構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure a secondary Location Information service
ms:assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398138(v=OCS.15)
ms:contentKeyID: 48183334
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8219aa234330120e6462a600b9c2c27b4b11c100
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840445"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-secondary-location-information-service-in-lync-server-2013"></a>Lync Server 2013 でセカンダリ場所情報サービスを構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-30_

Lync Server 2013 には、位置情報サービスをセカンダリの場所のソース (SLS) データベースにポイントするために使用できる web サービスインターフェイスが用意されています。 SLS データベースに接続する web サービスインターフェイスは、位置情報サービスの WSDL に準拠している必要があります。 ロケーションデータベースとセカンダリロケーションデータベースの両方が構成されている場合、位置情報サービスは最初に位置情報データベースを照会し、一致が見つからない場合は、クライアントから SLS データベースに位置情報要求を送信します。 場所が SLS に存在する場合、位置情報サービスはその場所をクライアントに送り返します。

詳細については、次のコマンドレットの Lync Server 管理シェルに関するドキュメントを参照してください。

  - **Set-CsWebServiceConfiguration**

<div>

## <a name="to-configure-secondary-location-database"></a>セカンダリの場所データベースを構成するには

1.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

2.  次のコマンドレットを実行して、セカンダリ場所データベースの場所の URL を構成します。
    
        Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>

