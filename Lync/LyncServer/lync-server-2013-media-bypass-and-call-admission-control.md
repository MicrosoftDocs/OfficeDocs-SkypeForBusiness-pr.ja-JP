---
title: 'Lync Server 2013: メディア バイパスと通話受付管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media bypass and call admission control
ms:assetid: 120b2a2b-5f97-4735-a2ee-0f849feb8c1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398203(v=OCS.15)
ms:contentKeyID: 48183454
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c5e02a57add6b93f1ad5c5efc3ac644e65e97f4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827558"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-bypass-and-call-admission-control-in-lync-server-2013"></a>Lync Server 2013 でのメディア バイパスと通話受付管理

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-05_

メディア バイパスおよび通話受付管理 (CAC) は、通話メディア帯域幅の制御を連携して管理します。メディア バイパスは、うまく接続されたリンクを介したメディアの流れを円滑にします。CAC は、帯域幅の制限があるリンクのトラフィックを管理します。メディア バイパスと CAC は互換性がないため、一方を計画する際には、もう一方の存在にも注意しなければなりません。次の組み合わせがサポートされています。

  - CAC およびメディア バイパスはどちらも有効です。メディア バイパスは、[**サイトおよび地域情報を使用する**] に設定されていなければなりません。このサイトおよび地域情報は、CAC に使われている情報と同じです。
    
    CAC を有効にすると [**常にバイパスする**] を選択できず、逆も同様です。なぜなら、2 つの構成は互換性がないためです。つまり、2 つのうちの 1 つだけがいずれの PSTN 通話にも適用されます。最初に、メディア バイパスが通話に適用されるかどうかを定義する確認が行われます。その場合、CAC は使われません。これは当然のことです。バイパスが適している通話の場合は、定義上、CAC を必要としない接続を使っているものだからです。通話にバイパスが適用されない場合 (つまり、クライアントおよびゲートウェイのバイパス ID が一致しない場合)、そのときには CAC が通話に適用されます。

  - CAC は無効で、メディア バイパスは [**常にバイパスする**] に設定されています。
    
    この構成では、クライアントおよびトランクの両方のサブネットが、システムによって計算された、唯一のバイパス ID にマップされています。

  - CAC は無効で、メディア バイパスは [**サイトおよび地域情報を使用する**] に設定されています。
    
    [**サイトおよび地域情報を使用する**] が有効である場合には、CAC が有効であるかないかにかかわらず、バイパスの決定は基本的に同じ方法で行われます。つまり、いずれの PSTN 通話でも、クライアントのサブネットは特定のサイトにマップされ、サブネットのバイパス ID が抽出されます。同様に、ゲートウェイのサブネットが特定のサイトにマップされ、サブネットのバイパス ID が抽出されます。2 つのバイパス ID が同一である場合のみ、通話にバイパスが発生します。2 つのバイパス ID が同一でない場合、メディア バイパスは発生しません。
    
    たとえ CAC がグローバルに無効であった場合でも、バイパス決定を制御するのに [サイトおよび地域] 構成を使用したい場合は、帯域幅ポリシーをそれぞれのサイトおよびリンクに定義する必要があります。帯域幅制限または帯域幅モダリティの実際の値は重要ではありません。最大の目標は、システムが、うまく接続されていない異なるロケールと関連付けるため、異なるバイパス ID を自動的に計算できるようにすることです。定義上、帯域幅の制限を定義するということは、リンクがうまく接続されていないことを意味します。

  - CAC は有効ですが、メディア バイパスは有効ではありません。 これは、すべてのゲートウェイまたは IP-PBX がうまく接続されていない、あるいはメディア バイパスのその他の要件が満たされていない場合にのみ適用されます。 メディアバイパスの要件の詳細については、「 [Lync Server 2013 でのメディアのバイパスの技術要件](lync-server-2013-technical-requirements-for-media-bypass.md)」を参照してください。

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのメディアのバイパスの概要](lync-server-2013-overview-of-media-bypass.md)  
[Lync Server 2013 のメディア バイパス モード](lync-server-2013-media-bypass-modes.md)  
[Lync Server 2013 メディア バイパスの技術要件](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

