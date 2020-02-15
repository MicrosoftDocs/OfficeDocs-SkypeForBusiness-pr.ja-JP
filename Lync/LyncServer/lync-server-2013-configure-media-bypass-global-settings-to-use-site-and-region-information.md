---
title: サイトと地域の情報を使用するためのメディアバイパスグローバル設定の構成
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
ms.openlocfilehash: 5c9b875693fb1fb7c9cfca4ae845709c874b0e8c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038319"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-global-settings-in-lync-server-2013-to-use-site-and-region-information"></a>サイトと地域の情報を使用するように Lync Server 2013 でメディアバイパスグローバル設定を構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-21_

<div>


> [!NOTE]
> ここでは、仲介サーバーをバイパスするためのメディアを必要とする特定のサイトまたはサービス用に、仲介サーバーからピア (公衆交換電話網 (PSTN) ゲートウェイ、IP-PBX、またはインターネット テレフォニー サービス プロバイダー (ITSP) でのセッション ボーダー コントローラー (SBC)) へのトランク接続用のメディア バイパスが構成済みであることを前提とします。<BR>また、このトピックでは、「lync server <A href="lync-server-2013-create-or-modify-a-network-region.md">2013 でのネットワーク地域の作成</A>または変更」、「lync server <A href="lync-server-2013-create-or-modify-a-network-site.md">2013 でのネットワークサイトの作成または変更</A>」、および「lync server 2013 でのネットワークサイトへの<A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">サブネットの関連付け</A>」の手順に従って、実行したネットワーク地域、ネットワークサイト、およびサブネット構成に一致するすべての中央サイトと 一致しない場合、メディア バイパスは成功しません。



</div>

ピアに関連付けられている個々のトランク接続でメディア パイパスを有効にするほか、グローバル設定も構成する必要があります。ここでのステップを使用してメディア バイパスのグローバル設定を構成する場合は、次の状況の一方または両方が構成に影響を与えることが前提となります。

  - Lync Server エンドポイントと、トランク接続でメディアバイパスを構成したすべてのピアとの間の接続が良好では*ありません*。

  - 帯域幅管理の通話受付管理 (CAC) が有効です。
    
    <div>
    

    > [!NOTE]
    > 通話受付管理とメディアバイパスの両方の考慮事項の詳細については、「計画」のドキュメントの「 <A href="lync-server-2013-media-bypass-and-mediation-server.md">media バイパスおよび仲介2013サーバーのメディアバイパスと仲介サーバー</A> 」の「PSTN 接続の通話受付管理」セクションを参照してください。

    
    </div>

ネットワーク地域およびネットワーク サイトの情報は、通話受付管理とメディア バイパスの高度なエンタープライズ VoIP 機能の間で (双方が有効な場合に) 共有されます。したがって、通話受付管理を構成済みの場合は、次の手順を使用してサイトと地域の情報をメディア バイパス用に特に編集する必要はありません。ネットワーク地域およびサイトで通話受付管理を構成しておらず、メディア バイパスの設定を変更したい場合は、この手順のステップを実行します。

または、バイパスを決定するためにサイトと地域の情報を使用し、通話受付管理を有効にすることを意図していない場合は、次の手順を実行します。 このような場合は、「 [Lync Server 2013 でのネットワークサイト間ポリシーの作成](lync-server-2013-create-network-intersite-policies.md)」で説明されているように、帯域幅制限リンクをネットワークサイト間ポリシーで表現する必要があります。 この例では、通話受付管理が有効になっていないため、実際の帯域幅制限は重要ではありません。 代わりに、これらのリンクを使用して、帯域幅制限を持たないサブネットを指定して、メディアバイパスを使用できるようにします。 通話受付管理とメディアバイパスが両方とも有効になっている場合は、この設定が true であることに注意してください。

さらに、バイパスを適切に動作させるには、トポロジビルダーで定義されているサイトと、ネットワーク地域およびネットワークサイトを構成するときに定義されているように、サイト間で一貫性を保つ必要があります。 たとえば、PSTN ゲートウェイのみを展開するようにトポロジビルダーで定義したブランチサイトがある場合は、ブランチサイトのユーザーが pstn 通話を pstn 経由でルーティングできるようにするエンタープライズ Voip ポリシーを構成する必要があります。ブランチサイトのゲートウェイ。

<div>

## <a name="to-configure-site-and-region-information-for-media-bypass"></a>メディア バイパスのサイトおよび地域情報を構成するには

1.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

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

次に、「 [Lync Server 2013 でのメディアバイパスのためにサブネットをネットワーク](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)サイトに関連付ける」の説明に従って、ネットワークサイトにサブネットを追加します。 (サブネットをネットワークサイトに関連付けるための実際の手順については、「 [Lync Server 2013 でサブネットをネットワークサイトに関連付ける](lync-server-2013-associate-a-subnet-with-a-network-site.md)」を参照してください)。すべてのサブネットをネットワークサイトに関連付けると、メディアバイパスの展開が完了します。

<div>


> [!IMPORTANT]
> ネットワーク地域とネットワーク サイトを作成していない場合は、メディア バイパスを展開する前にこれらを作成する必要があります。 詳細については、「lync <A href="lync-server-2013-create-or-modify-a-network-region.md">server 2013 でネットワーク地域を作成または変更</A>する」および「 <A href="lync-server-2013-create-or-modify-a-network-site.md">lync server 2013 でネットワークサイトを作成または変更</A>する」を参照してください。



</div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのメディアバイパスのためにサブネットをネットワークサイトに関連付ける](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

