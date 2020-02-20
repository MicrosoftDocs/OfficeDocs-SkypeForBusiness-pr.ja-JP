---
title: 'Lync Server 2013: ネットワークメディアバイパスの有効化'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling network media bypass
ms:assetid: 95c4fa06-49d3-41ac-acdc-7dcda66e5508
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182552(v=OCS.15)
ms:contentKeyID: 48184846
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a269f22eabc294af45697ab1bd2c0eabe4b5aad6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146430"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-network-media-bypass-in-lync-server-2013"></a>Lync Server 2013 でのネットワークメディアバイパスの有効化

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

メディアバイパスの設定は、Microsoft Lync Server 2013 の展開全体でグローバルに適用されます。 メディアバイパスは、呼び出しが仲介サーバーをバイパスすることを許可します。 メディアバイパスを使用するタイミングの詳細については、「計画」セクションの「 [Lync Server 2013 でのメディアバイパスの計画](lync-server-2013-planning-for-media-bypass.md)」を参照してください。

Lync Server コントロールパネルからメディアバイパスを有効にし、構成することができます。

<div>

## <a name="to-enable-and-configure-media-bypass"></a>メディアバイパスを有効にして構成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**ネットワーク構成**] をクリックし、[**グローバル**] をクリックします。

4.  [**グローバル**] ページで [**グローバル**] 構成をクリックします。存在する構成は必ず 1 つのみで、必ずグローバルという名前です。

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。

6.  [**グローバル設定の編集**] ページで、[**メディアバイパスを有効にする**] チェックボックスをオンにします。

7.  以下のいずれかのオプションを選択します。
    
      - **[常にバイパス**   する] このオプションを選択すると、すべての通話でメディアバイパスが試行されます。 通話受付管理 (CAC) が有効になっている場合、このオプションは使用できません。 CAC が有効になっていない場合は、次の状況でこのオプションを選択します。
        
          - 帯域幅を制御する必要はありません。
        
          - バイパスが発生するタイミングを特定するために、詳細に設定する必要はありません。
        
          - ゲートウェイとクライアントの間には、完全な接続があります。
    
      - **[サイトと地域の構成**   を使用する] CAC が有効になっている場合、このオプションは既定でオンになっており、変更することはできません。 このオプションが選択されている場合、ネットワーク構成サイトと地域を使用して、メディアバイパスがいつ可能になるかを判断します。 このオプションを選択した場合は、マップされていないサイトのバイパスを有効にするかどうかを選択できます。 帯域幅制限を持たない同じ地域に関連付けられた1つ以上の大規模なサイト (たとえば、大規模な中央サイト) を所有しており、さらに帯域幅制限がある同じ地域に関連付けられたブランチサイトがある場合にのみ、[**非マッピングサイトのバイパスを有効に**する] チェックボックスをオンにします。 非マッピングサイトのバイパスを有効にすると、すべてのサイトに関連付けられているすべてのサブネットを指定する必要がなく、ブランチサイトに関連付けられたサブネットのみを指定するので、構成は簡素化されます。 CAC が有効になっている場合は、[マップされてい**ないサイトのバイパスを有効に**する] チェックボックスをオンにしないことをお勧めします。

8.  [**確定**] をクリックして変更を保存します。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのネットワークメディアバイパスの無効化](lync-server-2013-disabling-network-media-bypass.md)  


[Lync Server 2013 のグローバルメディアバイパスオプション](lync-server-2013-global-media-bypass-options.md)  


[Lync Server 2013 でのメディアバイパスの計画](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

