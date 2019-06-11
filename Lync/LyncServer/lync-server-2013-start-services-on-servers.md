---
title: 'Lync Server 2013: サーバーでのサービスの開始'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Start services on servers
ms:assetid: fa26eaed-0529-4f32-9f3f-f32c4bd4b1c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413059(v=OCS.15)
ms:contentKeyID: 48185912
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c0c0c14aea9966e61703e85dd2aff8a2e448d5eb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848662"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="start-services-on-servers-for-lync-server-2013"></a>Lync Server 2013 のサーバーでのサービスの開始

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-09-03_

この手順を正常に完了するには、RTCUniversalServerAdmins グループのメンバーであるか、適切な権限が委任されているユーザーとしてログインしている必要があります。 権限の委任の詳細については、「 [Lync Server 2013 の委任のセットアップのアクセス許可](lync-server-2013-delegate-setup-permissions.md)」を参照してください。

サーバーにローカル構成ストアをインストールし、Lync Server 2013 コンポーネントをインストールして、フロントエンドサーバーまたはフロントエンドサーバーで証明書を構成したら、サーバー上で Lync Server 2013 サービスを開始する必要があります。 展開の各フロントエンドサーバーでサービスを開始するには、次の手順を実行します。

<div>

## <a name="to-start-services-on-a-standard-edition-or-front-end-server"></a>標準エディションまたはフロントエンドサーバーでサービスを開始するには

1.  Lync Server の展開ウィザードの [ **Lync server 2013** ] ページで、[**手順 4: サービスを開始**する] の横にある [**実行**] をクリックします。

2.  [**サービスの開始**] ページで、[**次**へ] をクリックして、サーバー上の Lync Server サービスを開始します。

3.  すべてのサービスが正常に開始されたら、[**コマンドの実行**] ページで [**終了**] をクリックします。
    
    <div>
    

    > [!IMPORTANT]  
    > サーバー上のサービスを開始するコマンドは、実際にサービスが開始されたことを報告するためのベストエフォートメソッドです。 サービスの実際の状態を反映していない場合もあります。 [<STRONG>サービスの開始</STRONG>] のすぐ下にある手順<STRONG>サービスの状態 (オプション)</STRONG>を使って MICROSOFT 管理コンソール (MMC) を開き、サービスが正常に開始されたことを確認することをお勧めします。 いずれかの Lync Server サービスが開始されていない場合は、MMC でそのサービスを右クリックし、[<STRONG>開始</STRONG>] をクリックします。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

