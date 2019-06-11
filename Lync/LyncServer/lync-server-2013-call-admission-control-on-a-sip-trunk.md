---
title: 'Lync Server 2013: SIP トランク上の通話受付管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call admission control on a SIP trunk
ms:assetid: 7eada098-3d47-4be2-839f-8f87d582efe8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398632(v=OCS.15)
ms:contentKeyID: 48184623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36734aa67e350b6c6f5ea5e9da57ce47f57e3d46
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840710"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-on-a-sip-trunk-in-lync-server-2013"></a>Lync Server 2013 の SIP トランク上の通話受付管理

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-22_

SIP トランクに通話受付管理 (CAC) を展開するには、インターネット テレフォニー サービス プロバイダー (ITSP) を表すためのネットワーク サイトを作成します。SIP トランクに帯域幅ポリシーの値を適用するには、企業内のネットワーク サイトと ITSP を表すために作成するネットワーク サイトのサイト間ポリシーを作成します。

次の図は、SIP トランクの CAC 展開の例を示しています。

**SIP トランクの CAC 構成**

![通話受付制御 SIP トランクの図](images/Gg398632.276c0d8f-1dd5-4883-8499-c202399ddbe9(OCS.15).jpg "通話受付制御 SIP トランクの図")

SIP トランクに CAC を構成するには、CAC の展開時に次の作業を行う必要があります。

1.  ITSP を表すためのネットワーク サイトを作成します。 ネットワーク サイトを適切なネットワーク地域に関連付けて、このネットワーク サイトの音声とビデオにゼロの帯域幅を割り当てます。 詳細については、展開ドキュメントの「 [Lync Server 2013 で CAC 用のネットワークサイトを構成する](lync-server-2013-configure-network-sites-for-cac.md)」を参照してください。
    
    <div>
    

    > [!NOTE]  
    > ITSP では、このネットワーク サイト構成は機能しません。 帯域幅ポリシーの値は、手順 2 で実際に適用されます。

    
    </div>

2.  手順 1 で作成したサイトの関連するパラメーター値を使用して、SIP トランクのサイト間リンクを作成します。 たとえば、企業内のネットワーク サイトの名前を NetworkSiteID1 パラメーターの値として使用し、ITSP ネットワーク サイトの名前を NetworkSiteID2 パラメーターの値として使用します。 詳細については、展開ドキュメントの「 [Lync Server 2013 でのネットワークサイト間ポリシーの作成](lync-server-2013-create-network-intersite-policies.md)」を参照してください。 また、CsNetworkInterSitePolicy コマンドレットの Lync Server 管理シェルドキュメントも参照してください。

3.  ITSP からセッション ボーダー コントローラー (SCB) のメディア終端ポイントの IP アドレスを取得します。 サブネット マスクが 32 の IP アドレスを、ITSP を表すネットワーク サイトに追加します。 詳細については、「 [Lync Server 2013 でサブネットとネットワークサイトを関連付ける](lync-server-2013-associate-a-subnet-with-a-network-site.md)」を参照してください。

</div>

<span> </span>

</div>

</div>

</div>

