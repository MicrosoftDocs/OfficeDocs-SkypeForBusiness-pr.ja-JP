---
title: 'Lync Server 2013: メディアバイパスを構成して、仲介サーバーを常にバイパスする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure media bypass to always bypass the Mediation Server
ms:assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425846(v=OCS.15)
ms:contentKeyID: 48183819
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7aca094110036692c5ac5327b166a3f81e4b769f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840349"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-in-lync-server-2013-to-always-bypass-the-mediation-server"></a>Configure media bypass in Lync Server 2013 to always bypass the Mediation Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-25_

<div>


> [!NOTE]  
> このトピックでは、特定のピアに対して、ピア (公衆交換電話網 (PSTN) ゲートウェイ、IP PBX、または、インターネットテレフォニーサービスプロバイダー (ITSP) でのセッション境界コントローラー (SBC)) へのトランク接続に対してメディアバイパスを既に構成していることを前提としています。メディアを仲介サーバーでバイパスするサイトまたはサービス。<BR>通話受付制御を有効にしている間も、常に仲介サーバーをバイパスするようにメディアを構成することはできません。 これらの設定は互換性がないため、Lync Server コントロールパネルのユーザーインターフェイスでは [相互排他] 設定になります。



</div>

ピアに関連付けられた個々のトランク接続でメディアバイパスを仲介サーバーに有効にすることに加えて、メディアバイパスのグローバル設定を構成する必要もあります。 このトピックの手順を使用してメディアのバイパスのグローバル設定を構成する場合、Lync のエンドポイントと、トランク接続でメディアをバイパスするように構成されているすべてのピアとの間に接続が適切であることを前提としています。

Lync Server のエンドポイント間の接続が適切ではなく、各トランク接続がメディアバイパスで有効になっている仲介サーバーへのすべてのピアがある場合は、サイトと地域の情報を使用するようにグローバルメディアバイパス設定を構成する必要があります。メディアバイパスの採用。 これにより、メディアが仲介サーバーをバイパスするタイミングをより細かく制御できます。 これを行うには、「 [Lync server 2013 の [メディアを無視してグローバル設定を構成](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)する」の手順に従って、サイトと地域の情報を使用し、[サブネットを lync server 2013 のネットワークサイトに関連付け](lync-server-2013-associate-a-subnet-with-a-network-site.md)ます。

<div>

## <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a>仲介サーバーを常にバイパスするよう、メディア バイパスをグローバルに有効化するには

1.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

2.  左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。

3.  リスト内の [**グローバル**] 構成をダブルクリックします。

4.  [**グローバル設定の編集**] ページの [**メディア バイパスを有効にする**] チェック ボックスをオンにします。

5.  [**常にバイパスする**] をクリックします。

6.  [**確定**] をクリックします。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 メディア バイパスの構成](lync-server-2013-configure-media-bypass.md)  
[Lync Server 2013 のグローバルメディアバイパスオプション](lync-server-2013-global-media-bypass-options.md)  
[Lync Server 2013 のメディア バイパスと仲介サーバー](lync-server-2013-media-bypass-and-mediation-server.md)  


[Lync Server 2013 でのメディア バイパスの計画](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

