---
title: 'Lync Server 2013: ネットワーク帯域幅ポリシープロファイルの削除'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting network bandwidth policy profiles
ms:assetid: 4d6beda8-6aa5-4d5e-8a07-363598f0e0c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688050(v=OCS.15)
ms:contentKeyID: 49733643
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b39dc7279c116dd7643b498882b15076cf69c24f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146160"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deleting-network-bandwidth-policy-profiles-in-lync-server-2013"></a>Lync Server 2013 でのネットワーク帯域幅ポリシープロファイルの削除

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

帯域幅ポリシーは、通話受付管理 (CAC) の一部として、特定のモダリティの帯域幅制限を定義する際に使用します。 Microsoft Lync Server 2013 では、オーディオおよびビデオモダリティのみに帯域幅制限を割り当てることができます。 全体の帯域幅制限とセッション制限を設定できます。 Lync Server コントロールパネルを使用して、これらのポリシーのコンテナープロファイルを作成、変更、または削除することができます。 ネットワーク帯域幅ポリシープロファイルを削除するには、次の手順を使用します。 ネットワーク帯域幅ポリシープロファイルの作成または変更の詳細については、「 [Lync Server 2013 での帯域幅ポリシープロファイルの作成または変更](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)」を参照してください。

<div>

## <a name="to-delete-a-bandwidth-policy-profile"></a>帯域幅ポリシープロファイルを削除するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**ネットワーク構成**] をクリックし、[**帯域幅ポリシー**] をクリックします。

4.  [**帯域幅ポリシー** ] ページで、削除する帯域幅ポリシープロファイルをクリックします。
    
    <div>
    

    > [!NOTE]  
    > 一度に複数のプロファイルを削除することができます。 これを行うには、ctrl キーを押しながら複数のプロファイルを選択し、CTRL キーを押したままにします。 または、すべてのプロファイルを選択するには、[<STRONG>編集</STRONG>] メニューの [<STRONG>すべて選択</STRONG>] をクリックします。

    
    </div>

5.  [**編集**] メニューの [**削除**] をクリックします。
    
    <div>
    

    > [!WARNING]  
    > ネットワークサイトに関連付けられている帯域幅ポリシーのプロファイルを削除することはできません。 最初に、プロファイルを削除する前に、ネットワークサイトとの関連付けを解除する必要があります。 ネットワークサイトの変更方法の詳細については、「 <A href="lync-server-2013-creating-or-modifying-network-sites.md">Lync Server 2013 でのネットワークサイトの作成または変更</A>」を参照してください。

    
    </div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での帯域幅ポリシープロファイルの作成または変更](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[Lync Server 2013 でのネットワーク帯域幅ポリシープロファイル情報の表示](lync-server-2013-viewing-network-bandwidth-policy-profile-information.md)  


[Lync Server 2013 で通話受付管理を構成する](lync-server-2013-configure-call-admission-control.md)  
[Get-csnetworkbandwidthpolicyprofile](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

