---
title: 'Lync Server 2013: ネットワークサブネットの作成または変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify network subnets
ms:assetid: 1ba8c4e3-fbc7-4758-88ac-d651fef17bed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520957(v=OCS.15)
ms:contentKeyID: 48183548
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9fa570d54a4c65c5f69782a57b4074043a26306
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151749"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-network-subnets-in-lync-server-2013"></a>Lync Server 2013 でのネットワークサブネットの作成または変更

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-21_

ネットワーク サブネットは、そのサブネットに所属するホストの地理的な場所を指定するために、ネットワーク サイトに関連付ける必要があります。 Lync Server コントロールパネルを使用して、サブネットを構成できます。 Lync Server コントロールパネルから、ネットワークサブネットを作成、変更、または削除することができます。 ネットワークサブネットの削除の詳細については、「 [Lync Server 2013 でのネットワークサブネットの削除](lync-server-2013-deleting-network-subnets.md)」を参照してください。

通話受付管理 (CAC) が実装されている Microsoft Lync Server 2013 のほとんどの展開では、通常、多くのサブネットがあります。 このため、多くの場合、Lync Server 管理シェルからサブネットを構成することをお勧めします。 そこから、Windows PowerShell コマンドレットの**Import-CSV**と共に、**新しい-csnetworksubnet**を呼び出すことができます。 これらのコマンドレットを使用すると、コンマ区切り値 (.csv) ファイルからサブネット設定を読み込み、同時に複数のサブネットを作成することができます。 csv ファイルからサブネットを作成する方法の例については、「[New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)」を参照してください。

<div>

## <a name="to-create-a-network-subnet"></a>ネットワーク サブネットを作成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**ネットワーク構成**]、[**サブネット**] の順にクリックします。

4.  [**サブネット**] ページで、[**新規**] をクリックします。

5.  [**新しいサブネット**] で、[**サブネット ID**] フィールドに値を入力します。 これは、IP アドレス (174.11.12.0 など) である必要があります。また、サブネットで定義される IP アドレス範囲の最初のアドレスである必要があります。

6.  [**マスク**] フィールドで、1 ～ 32 の数値を入力します。
    
    <div>
    

    > [!NOTE]  
    > この値は、作成するサブネットに適用するビットマスクです。

    
    </div>

7.  [**ネットワーク サイト ID**] で、このサブネットが所属するサイトを選択します。

8.  (オプション) [**説明**] フィールドに値を入力して、名前だけでは表現することのできないこのサブネットの詳細情報を提供します。

9.  [**確定**] をクリックします。

</div>

<div>

## <a name="to-modify-a-network-subnet"></a>ネットワーク サブネットを変更するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**ネットワーク構成**] をクリックし、[**サブネット**] をクリックします。

4.  [**サブネット**] ページで、変更するサブネットをクリックします。

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。

6.  [**サブネットの編集**] ページでは、ビットマスク、関連付けられたネットワーク サイト、または説明を変更できます。 ビットマスクを変更する場合は、変更後もサブネット ID がサブネットで定義される IP アドレス範囲の最初のアドレスでなければならないことに注意してください。

7.  [**確定**] をクリックします。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのネットワークサブネットの削除](lync-server-2013-deleting-network-subnets.md)  


[Lync Server 2013 のネットワーク地域、サイト、およびサブネットについて](lync-server-2013-about-network-regions-sites-and-subnets.md)  


[新しい-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  
[設定-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  
[-CsNetworkSubnet の削除](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  
[-CsNetworkSubnet の取得](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

