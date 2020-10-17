---
title: 'Lync Server 2013: サーバーでのサービスの開始'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Start services on servers
ms:assetid: fa26eaed-0529-4f32-9f3f-f32c4bd4b1c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413059(v=OCS.15)
ms:contentKeyID: 48185912
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d276dfdedacdcb00b4cc19a486fea1103c0bc8d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532964"
---
# <a name="start-services-on-servers-for-lync-server-2013"></a>Lync Server 2013 のサーバーでのサービスの開始

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-09-03_

この手順を正常に完了するには、RTCUniversalServerAdmins グループのメンバーとしてログオンしているか、適切なアクセス許可が委任されている必要があります。 アクセス許可の委任の詳細については、「 [Lync Server 2013 の委任のセットアップのアクセス許可](lync-server-2013-delegate-setup-permissions.md)」を参照してください。

サーバーにローカル構成ストアをインストールし、Lync Server 2013 コンポーネントをインストールして、フロントエンドサーバーまたはフロントエンドサーバーで証明書を構成すると、サーバー上で Lync Server 2013 サービスを開始する必要があります。 次の手順を使用して、展開内の各フロントエンドサーバーでサービスを開始します。

<div>

## <a name="to-start-services-on-a-standard-edition-or-front-end-server"></a>Standard Edition またはフロントエンドサーバーでサービスを開始するには

1.  Lync Server 展開ウィザードの [ **Lync server 2013** ] ページで、[**ステップ 4: サービスの開始**] の横にある [**実行**] をクリックします。

2.  [ **サービスの開始** ] ページで、[ **次** へ] をクリックして、サーバー上の Lync Server サービスを開始します。

3.  すべてのサービスが正常に開始されたら、**[コマンドの実行]** ページで **[終了]** をクリックします。
    
    <div>
    

    > [!IMPORTANT]  
    > サーバーのサービスを開始するコマンドは、サービスが事実上開始されたことをレポートするベストエフォート型の方法です。 サービスの実際の状態を反映していない場合もあります。 [<STRONG>サービスの開始</STRONG>] の直後に、ステップ [<STRONG>サービスの状態 (オプション)</STRONG>] で Microsoft 管理コンソール (MMC) を開き、サービスが正常に開始されたことを確認することをお勧めします。 いずれかの Lync Server サービスが開始されていない場合は、MMC でそのサービスを右クリックし、[ <STRONG>開始</STRONG>] をクリックします。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

