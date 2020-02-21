---
title: 'Lync Server 2013: メディアバイパスを構成して仲介サーバーを常にバイパスする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass to always bypass the Mediation Server
ms:assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425846(v=OCS.15)
ms:contentKeyID: 48183819
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ae9bfa8be276cccc6f31def6fb7014e417841d8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190560"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-in-lync-server-2013-to-always-bypass-the-mediation-server"></a>Lync Server 2013 でメディアバイパスを構成して仲介サーバーを常にバイパスする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-25_

<div>


> [!NOTE]  
> このトピックは、メディアに仲介サーバーをバイパスさせたい特定のサイトまたはサービスのピア (公衆交換電話網 (PSTN) ゲートウェイ、IP-PBX、またはインターネット テレフォニー サービス プロバイダー (ITSP) のセッション ボーダー コントローラー (SBC)) へのすべてのトランク接続に、すでにメディア バイパスを構成したことを前提にしています。<BR>通話受付管理もまた有効である状態で、常に仲介サーバーをバイパスするようにメディアを構成することはできません。 これらの設定は互換性がありません。そのため、Lync Server コントロールパネルのユーザーインターフェイスでは [相互排他的] 設定になります。



</div>

仲介サーバーへのピアに関連付けられた個別のトランク接続に対してメディア バイパスを有効にするのに加え、メディア バイパスのグローバル設定もまた構成する必要があります。 このトピックの手順を使用してメディアバイパスのグローバル設定を構成する場合、Lync エンドポイントと、トランク接続でメディアバイパスを構成したすべてのピアとの間の接続が良好であることを前提としています。

Lync Server エンドポイントと、それぞれのトランク接続がメディアバイパスが有効になっている仲介サーバーへの接続が良好ではない場合は、次の場合にサイトと地域の情報を使用するようにグローバルメディアバイパス設定を構成する必要があります。メディアバイパスの採用。 これにより、メディアが仲介サーバーをバイパスするか判定する際に、よりよく制御できます。 そのためには、「 [Configure media バイパス global settings In Lync server 2013」](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)の手順を使用して、サイトと地域の情報を使用し、[サブネットを lync server 2013 のネットワークサイトに関連付け](lync-server-2013-associate-a-subnet-with-a-network-site.md)ます。

<div>

## <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a>仲介サーバーを常にバイパスするよう、メディア バイパスをグローバルに有効化するには

1.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

2.  左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。

3.  リスト内の [**グローバル**] 構成をダブルクリックします。

4.  [**グローバル設定の編集**] ページの [**メディア バイパスを有効にする**] チェック ボックスをオンにします。

5.  [**常にバイパスする**] をクリックします。

6.  [**確定**] をクリックします。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でメディアバイパスを構成する](lync-server-2013-configure-media-bypass.md)  
[Lync Server 2013 のグローバルメディアバイパスオプション](lync-server-2013-global-media-bypass-options.md)  
[Lync Server 2013 のメディアバイパスと仲介サーバー](lync-server-2013-media-bypass-and-mediation-server.md)  


[Lync Server 2013 でのメディアバイパスの計画](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

