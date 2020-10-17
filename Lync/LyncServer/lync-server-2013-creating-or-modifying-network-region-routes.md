---
title: 'Lync Server 2013: ネットワーク地域ルートの作成または変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network region routes
ms:assetid: 76993daa-76c2-4cec-8363-de8aebef0145
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521016(v=OCS.15)
ms:contentKeyID: 48184540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cdc05978b6fb8d81c81995d7b089d14ed4bec3b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516744"
---
# <a name="creating-or-modifying-network-region-routes-in-lync-server-2013"></a>Lync Server 2013 でのネットワーク地域ルートの作成または変更

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-08_

通話受付管理 (CAC) 構成内のすべての地域には、他のすべての地域へのアクセス方法がいくつかある必要があります。 地域のリンクが地域間の接続に対する帯域幅制限を設定し、物理リンクも表す一方、ルートはある地域から別の地域へ接続が通過するリンクされたパスを決定します。 Lync Server コントロールパネルを使用して、ネットワーク地域ルートを構成できます。 Lync Server コントロールパネルから、ネットワーク地域ルートを作成、変更、または削除することができます。 このトピックでは、ネットワーク地域ルートの作成または変更について説明します。 既存のネットワーク地域ルートの削除の詳細については、「 [Lync Server 2013 で既存のネットワーク地域ルートを削除](lync-server-2013-deleting-existing-network-region-routes.md)する」を参照してください。

<div>

## <a name="to-create-a-network-region-route"></a>ネットワーク地域ルートを作成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**ネットワーク構成**] をクリックし、[**地域ルート**] をクリックします。

4.  [**地域ルート**] ページで、[**新規**] をクリックします。

5.  [**新しい地域ルート**] で、[**名前**] フィールドに値を入力します。
    
    <div>
    

    > [!NOTE]  
    > この値は、Microsoft Lync Server 2013 展開内で一意である必要があります。

    
    </div>

6.  [ **ネットワーク地域 \# 1** ] ドロップダウンリストから、このルートによって接続する2つの地域のいずれかを選択します。

7.  [ **ネットワーク地域 \# 2** ] ドロップダウンリストから、このルートの他の地域を選択します。 この地域は、[ネットワーク地域1に選択した地域とは別のものにする必要があり \# ます。

8.  [**ネットワーク地域リンク**] リスト ボックスを使用して、地域リンクをルートに追加します。 [**追加**] ボタンをクリックし、[**地域リンク**] ページを表示します。 このルートに追加する地域リンクをクリックして、[**OK**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > [<STRONG>追加</STRONG>] ボタンのクリックを続けて、さらにリンクを追加できます。また、リンクを選択して [<STRONG>削除</STRONG>] をクリックすると、リンクを削除できます。

    
    </div>

9.  [**確定**] をクリックします。

</div>

<div>

## <a name="to-modify-a-network-region-route"></a>ネットワーク地域ルートを変更するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**ネットワーク構成**] をクリックし、[**地域ルート**] をクリックします。

4.  [**地域ルート**] ページで、変更する地域ルートをクリックします。

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。

6.  [**地域ルートの編集**] で、このルートが接続する地域やこのルートに関連付ける地域リンクを変更できます。

7.  [**確定**] をクリックします。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での既存のネットワーク地域ルートの削除](lync-server-2013-deleting-existing-network-region-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

