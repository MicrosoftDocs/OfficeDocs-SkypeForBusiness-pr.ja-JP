---
title: 'Lync Server 2013: ネットワークサブネットの削除'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting network subnets
ms:assetid: c1850f38-40a3-48c9-b6f1-f181c5e63b6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721873(v=OCS.15)
ms:contentKeyID: 49733806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c87ca1cfd91344d8f8cbb0b320c70def47bf5ac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740967"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-network-subnets-in-lync-server-2013"></a>Lync Server 2013 でのネットワークサブネットの削除

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-21_

次の手順を使用して、サブネットを削除することができます。 Lync Server コントロールパネルから、ネットワークサブネットの作成、変更、または削除を行うことができます。 ネットワークサブネットの作成または変更の詳細については、「 [Lync Server 2013 でネットワークサブネットを作成または変更](lync-server-2013-create-or-modify-network-subnets.md)する」を参照してください。

通話受付制御 (CAC) が実装されている Microsoft Lync Server 2013 の大半の展開では、通常、多数のサブネットが存在します。 このため、多くの場合、Lync Server 管理シェルからサブネットを構成することをお勧めします。 そこから、Windows PowerShell コマンドレットの**Import-CSV**と組み合わせて、**新しい csnetworksubnet**を呼び出すことができます。 これらのコマンドレットを一緒に使用することで、サブネットの設定をコンマ区切り値 (.csv) ファイルから読み取り、複数のサブネットを同時に作成することができます。 .Csv ファイルからサブネットを作成する方法の例については、「[新しい-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)」を参照してください。

<div>

## <a name="to-delete-a-network-subnet"></a>ネットワークサブネットを削除するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**サブネット**] をクリックします。

4.  [ **Subnet** ] ページで、削除するサブネットをクリックします。
    
    <div>
    

    > [!NOTE]  
    > 一度に複数のサブネットを削除することができます。 これを行うには、ctrl キーを押しながら、CTRL キーを押しながら複数のサブネットを選択します。 または、すべてのサブネットを選択するには、[<STRONG>編集</STRONG>] メニューの [<STRONG>すべて選択</STRONG>] をクリックします。

    
    </div>

5.  [**編集**] メニューの [**削除**] をクリックします。

6.  **[OK]** をクリックします。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でネットワークサブネットを作成または変更する](lync-server-2013-create-or-modify-network-subnets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

