---
title: 'Lync Server 2013: 既存のネットワーク領域の削除'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting existing network regions
ms:assetid: c7293a2f-2b49-4c4a-903f-f7edcea2bc5f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721882(v=OCS.15)
ms:contentKeyID: 49733815
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3a1c1e697e681eec4886dca9e942d9bc133b0f5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525404"
---
# <a name="deleting-existing-network-regions-in-lync-server-2013"></a>Lync Server 2013 の既存のネットワーク領域の削除

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-21_

ネットワーク地域は、複数の地理的な領域にまたがるネットワークのさまざまな部分を相互接続します。 すべてのネットワーク地域は、セントラル サイトと関連付ける必要があります。 このセントラル サイトは、通話受付管理 (CAC) 帯域幅ポリシー サービスが実行されているデータ センター サイトです。 Lync Server コントロールパネルを使用して、ネットワーク地域を構成できます。 ネットワーク地域には、オーディオとビデオの接続でインターネット経由の代替パスを許可するかどうかを決定する設定が含まれます。 Lync Server コントロールパネルから、ネットワーク地域を作成、変更、または削除することができます。 既存のネットワーク地域を削除するには、このトピックを参考にしてください。 既存のネットワーク地域の作成または変更の詳細については、「 [Lync Server 2013 でのネットワーク地域の作成または変更](lync-server-2013-creating-or-modifying-network-regions.md)」を参照してください。

<div>

## <a name="to-delete-a-network-region"></a>ネットワーク地域を削除するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**ネットワーク構成**]、[**地域**] の順にクリックします。

4.  [**地域**] ページで、削除する地域をクリックします。
    
    <div>
    

    > [!NOTE]  
    > 一度に複数の地域を削除できます。これを実行するには、Ctrl キーを押しながら複数の地域を選択します。また、すべての地域を選択するには、[<STRONG>編集</STRONG>] メニューの [<STRONG>すべて選択</STRONG>] をクリックします。

    
    </div>

5.  [**編集**] メニューの [**削除**] をクリックします。

6.  [**OK**] をクリックします。
    
    <div>
    

    > [!WARNING]  
    > ネットワーク地域がネットワーク サイトに関連付けられている場合は、削除することはできません。サイトに関連付けられている地域を削除しようとすると、エラー メッセージが表示されます。地域がサイトに関連付けられているかどうかを確認するには、その地域を選択して [<STRONG>編集</STRONG>] メニューの [<STRONG>詳細の表示</STRONG>] をクリックします。

    
    </div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのネットワーク地域の作成または変更](lync-server-2013-creating-or-modifying-network-regions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

