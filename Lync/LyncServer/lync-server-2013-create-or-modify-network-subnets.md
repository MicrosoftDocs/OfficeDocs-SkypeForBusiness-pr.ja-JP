---
title: 'Lync Server 2013: ネットワークサブネットを作成または変更する'
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
ms.openlocfilehash: 4d743e5cdbe8dc7f200175b74f55b1b3d003e769
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734257"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-network-subnets-in-lync-server-2013"></a>Lync Server 2013 でネットワークサブネットを作成または変更する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-21_

ネットワークサブネットは、このサブネットに属しているホストの地理的な場所を判断するために、ネットワークサイトと関連付けられている必要があります。 Lync Server コントロールパネルを使用して、サブネットを構成することができます。 Lync Server コントロールパネルから、ネットワークサブネットの作成、変更、または削除を行うことができます。 ネットワークサブネットの削除の詳細については、「 [Lync Server 2013 でのネットワークサブネットの削除](lync-server-2013-deleting-network-subnets.md)」を参照してください。

通話受付制御 (CAC) が実装されている Microsoft Lync Server 2013 の大半の展開では、通常、多数のサブネットが存在します。 このため、多くの場合、Lync Server 管理シェルからサブネットを構成することをお勧めします。 そこから、Windows PowerShell コマンドレットの**Import-CSV**と組み合わせて、**新しい csnetworksubnet**を呼び出すことができます。 これらのコマンドレットを一緒に使用することで、サブネットの設定をコンマ区切り値 (.csv) ファイルから読み取り、複数のサブネットを同時に作成することができます。 .Csv ファイルからサブネットを作成する方法の例については、「[新しい-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)」を参照してください。

<div>

## <a name="to-create-a-network-subnet"></a>ネットワークサブネットを作成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**サブネット**] をクリックします。

4.  [**サブネット**] ページで、[**新規**] をクリックします。

5.  [**新しいサブネット**] で、[**サブネット ID** ] フィールドに値を入力します。 これは IP アドレス (たとえば、174.11.12.0) である必要があり、サブネットで定義された IP アドレス範囲の最初のアドレスである必要があります。

6.  [**マスク**] フィールドに、1 ~ 32 の数値を入力します。
    
    <div>
    

    > [!NOTE]  
    > この値は、作成されるサブネットに適用されるビットマスクです。

    
    </div>

7.  [**ネットワークサイト ID**] で、このサブネットが所属するサイトを選びます。

8.  省略[**説明**] フィールドに値を入力して、このサブネットについて、名前だけでは表現できない詳細情報を入力します。

9.  [**コミット**] をクリックします。

</div>

<div>

## <a name="to-modify-a-network-subnet"></a>ネットワークサブネットを変更するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**サブネット**] をクリックします。

4.  [ **Subnet** ] ページで、変更するサブネットをクリックします。

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。

6.  [**サブネットの編集**] ページでは、ビットマスク、関連付けられたネットワークサイト、または説明を変更できます。 ビットマスクを変更する場合は、サブネット ID が、サブネットで定義されている IP アドレス範囲の最初のアドレスである必要があることに注意してください。

7.  [**コミット**] をクリックします。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのネットワークサブネットの削除](lync-server-2013-deleting-network-subnets.md)  


[Lync Server 2013 ネットワーク領域、サイト、およびサブネットの構成](lync-server-2013-about-network-regions-sites-and-subnets.md)  


[新しい-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  
[Set-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  
[CsNetworkSubnet の削除](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  
[Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

