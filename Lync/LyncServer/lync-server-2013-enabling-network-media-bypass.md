---
title: 'Lync Server 2013: ネットワークメディアのバイパスを有効にする'
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
ms.openlocfilehash: 4e0b5e7b060d056a785e80fdf29ded718d120bc1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735797"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-network-media-bypass-in-lync-server-2013"></a>Lync Server 2013 でネットワークメディアのバイパスを有効にする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-01_

メディアバイパスの設定は、Microsoft Lync Server 2013 の展開でグローバルに適用されます。 メディアのバイパスでは、仲介サーバーを経由せずに通話を発信できます。 メディアのバイパスを使用する場合の詳細については、「計画」セクションの「 [Lync Server 2013 でのメディアのバイパスの計画](lync-server-2013-planning-for-media-bypass.md)」を参照してください。

Lync Server コントロールパネルでメディアのバイパスを有効にして構成することができます。

<div>

## <a name="to-enable-and-configure-media-bypass"></a>メディアバイパスを有効にして構成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**グローバル**] をクリックします。

4.  [**グローバル**] ページで、[**グローバル**構成] をクリックします。 構成は常に1つだけであり、常に Global という名前が付いています。

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。

6.  [**グローバル設定の編集**] ページで、[**メディアバイパスを有効にする**] チェックボックスをオンにします。

7.  次のいずれかのオプションを選択します。
    
      - **[常にスキップ**   ] このチェックボックスをオンにすると、すべての通話でメディアのバイパスが試行されます。 通話受付制御 (CAC) が有効になっている場合、このオプションは使用できません。 CAC が有効になっていない場合は、次のような場合にこのオプションを選択します。
        
          - 帯域幅の調整は必要ありません。
        
          - 何度も設定する必要はありません。
        
          - ゲートウェイとクライアントの間には完全な接続があります。
    
      - **サイトと地域の構成**   を使用する CAC が有効になっている場合、このオプションは既定でオンになっており、変更できません。 このオプションが選択されている場合は、メディアのバイパスを可能にするかどうかを判断するためにネットワーク構成サイトと領域が使用されます。 このオプションを選択すると、マップされていないサイトに対しては、[バイパス] を有効にすることができます。 帯域幅の制約がない1つ以上の大規模なサイト (たとえば、大規模なセントラルサイトなど) が、帯域幅の制約がある同じ地域に関連付けられている場合にのみ、[**非マッピングサイトに対してバイパスを有効に**する] チェックボックスをオンにします。 非マッピングサイトに対してバイパスを有効にすると、すべてのサイトに関連付けられているすべてのサブネットを指定する必要がなく、ブランチサイトに関連付けられているサブネットのみを指定しているため、構成が効率化されます。 CAC が有効になっている場合は、[**非マッピングサイトに対してバイパスを有効に**する] チェックボックスをオンにしないことをお勧めします。

8.  [**コミット**] をクリックして変更内容を保存します。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でネットワークメディアのバイパスを無効にする](lync-server-2013-disabling-network-media-bypass.md)  


[Lync Server 2013 のグローバルメディアバイパスオプション](lync-server-2013-global-media-bypass-options.md)  


[Lync Server 2013 でのメディア バイパスの計画](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

