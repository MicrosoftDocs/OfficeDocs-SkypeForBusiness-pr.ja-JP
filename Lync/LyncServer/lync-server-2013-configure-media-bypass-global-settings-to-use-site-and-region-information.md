---
title: サイトおよび地域情報を使用するためのメディア バイパス グローバル設定の構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass global settings to use site and region information
ms:assetid: 0a21cdf1-f350-49da-b346-70806f256bea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398150(v=OCS.15)
ms:contentKeyID: 48183360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac820c444f894aabf060c06d6f034f7d92b696c2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757751"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-global-settings-in-lync-server-2013-to-use-site-and-region-information"></a>Configure media bypass global settings in Lync Server 2013 to use site and region information

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-21_

<div>


> [!NOTE]
> このトピックでは、仲介サーバーからピア (公衆交換電話網 (PSTN) ゲートウェイ、IP PBX、またはインターネットテレフォニーサービスでのセッション境界コントローラー (SBC) へのトランク接続に対してメディアバイパスを既に構成していることを前提としています。メディアが仲介サーバーをバイパスする特定のサイトまたはサービスのプロバイダー (ITSP)。<BR>また、このトピックでは、「 <A href="lync-server-2013-create-or-modify-a-network-region.md">lync server 2013 でネットワーク領域を作成または変更</A>する」、「lync server <A href="lync-server-2013-create-or-modify-a-network-site.md">2013 でネットワークサイトを作成または変更</A>する」、「lync server <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">2013 でサブネットを</A>作成または変更する」の手順に従って、トポロジビルダー内のすべてのセントラルサイトとブランチサイトを定義していることを前提とします 一致しない場合、メディアのバイパスは成功しません。



</div>

ピアに関連付けられた個々のトランク接続でメディアバイパスを有効にするだけでなく、グローバル設定も構成する必要があります。 このトピックの手順を使用してメディアのバイパスのグローバル設定を構成する場合は、次のいずれかまたは両方の状況が構成に影響することを前提としています。

  - トランク接続でメディアをバイパスするように構成した Lync Server エンドポイントとピアの間の接続は良好ではあり*ません*。

  - 帯域幅管理の通話受付制御 (CAC) が有効になっています。
    
    <div>
    

    > [!NOTE]
    > 通話受付制御とメディアバイパスの両方の考慮事項の詳細については、計画ドキュメントの「 <A href="lync-server-2013-media-bypass-and-mediation-server.md">Lync server 2013 のメディアバイパスと仲介サーバー</A> 」の「PSTN 接続の通話受付制御」セクションを参照してください。

    
    </div>

ネットワーク地域およびネットワーク サイトの情報は、通話受付管理とメディア バイパスの高度なエンタープライズ VoIP 機能の間で (双方が有効な場合に) 共有されます。したがって、通話受付管理を構成済みの場合は、次の手順を使用してサイトと地域の情報をメディア バイパス用に特に編集する必要はありません。ネットワーク地域およびサイトで通話受付管理を構成しておらず、メディア バイパスの設定を変更したい場合は、この手順のステップを実行します。

または、バイパスの意思決定を行うためにサイトと地域の情報を使用するが、通話受付制御を有効にすることを意図していない場合は、次の手順を実行します。 この場合も、「 [Lync Server 2013 でネットワークのサイト間ポリシーを作成](lync-server-2013-create-network-intersite-policies.md)する」で説明されているように、帯域幅制限のあるリンクは、ネットワークのサイト間ポリシーを通じて表示される必要があります。 この場合、通話受付制御が有効になっていないため、実際の帯域幅制約は重要ではありません。 代わりに、これらのリンクを使用して、帯域幅の制限を持たないサブネットを指定して、メディアのバイパスを使うことができるようにします。 これは、通話受付制御とメディアのバイパスが両方とも有効になっている場合にも当てはまります。

さらに、[スキップ] が適切に機能するには、トポロジビルダーで定義されているサイトと、ネットワーク領域とネットワークサイトを構成するときに定義されているサイトの間で一貫性が保たれている必要があります。 たとえば、PSTN ゲートウェイのみが展開されていることを示すために、トポロジビルダーで定義したブランチサイトがある場合、そのブランチサイトは、ブランチサイトユーザーが pstn 経由でルーティングする PSTN 通話を使用できるようにするエンタープライズ Voip ポリシーを使って構成する必要があります。ブランチサイトのゲートウェイ。

<div>

## <a name="to-configure-site-and-region-information-for-media-bypass"></a>メディア バイパスのサイトおよび地域情報を構成するには

1.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

2.  左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。

3.  表の [**グローバル**] 構成をダブルクリックします。

4.  [**グローバル設定の編集**] ページの [**メディア バイパスを有効にする**] チェック ボックスをオンにします。

5.  [**サイトと地域の構成を使用する**] をクリックします。

6.  必要に応じて、[**マップされていないサイトのバイパスを有効にする**] チェック ボックスをオンにします。
    
    <div>
    

    > [!NOTE]
    > このチェック ボックスは、帯域幅制限のない同一地域に関連付けられた 1 つまたは複数の大規模なサイト (大規模なセントラル サイトなど) があり、帯域幅制限がある同一地域に関連付けられたいくつかのブランチ サイトもある場合のみオンにします。マップされていないサイトのバイパスを有効にすると、すべてのサイトに関連付けられたすべてのサブネットを指定する必要がなく、ブランチ サイトに関連付けられたサブネットのみを指定するため、構成が効率的になります。通話受付管理が有効な場合は、このチェック ボックスをオンにしないことをお勧めします。

    
    </div>

7.  [**確定**] をクリックします。

次に、「 [Lync Server 2013 のメディアバイパスのネットワークサイトにサブネットを関連付ける](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)」の説明に従って、ネットワークサイトにサブネットを追加します。 (ネットワークサイトと共にサブネットを関連付けるための実際の手順については、「 [Lync Server 2013 でサブネットとネットワークサイトを関連付ける](lync-server-2013-associate-a-subnet-with-a-network-site.md)」を参照してください。)すべてのサブネットをネットワークサイトと関連付けると、メディアバイパスの展開が完了します。

<div>


> [!IMPORTANT]
> ネットワーク地域とネットワーク サイトを作成していない場合は、メディア バイパスを展開する前にこれらを作成する必要があります。 詳細については、「 <A href="lync-server-2013-create-or-modify-a-network-region.md">Lync server 2013 でネットワーク領域を作成または変更</A>する」および「 <A href="lync-server-2013-create-or-modify-a-network-site.md">lync server 2013 でネットワークサイトを作成または変更</A>する」を参照してください。



</div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 で、サブネットをメディアバイパスのネットワークサイトと関連付ける](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

