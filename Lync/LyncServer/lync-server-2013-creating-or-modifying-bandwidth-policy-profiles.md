---
title: 'Lync Server 2013: 帯域幅ポリシープロファイルの作成または変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying bandwidth policy profiles
ms:assetid: 08a2e18f-9b0d-4a2f-aa14-13bbf79ec745
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520945(v=OCS.15)
ms:contentKeyID: 48183336
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c46ec104972eff34f73825fbb384259fc6eb4ba
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213253"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-bandwidth-policy-profiles-in-lync-server-2013"></a>Lync Server 2013 での帯域幅ポリシープロファイルの作成または変更

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-15_

帯域幅ポリシーは、通話受付管理 (CAC) の一部として、特定のモダリティの帯域幅制限を定義する際に使用します。 Microsoft Lync Server 2013 では、オーディオおよびビデオモダリティのみに帯域幅制限を割り当てることができます。 全体の帯域幅制限とセッション制限を設定できます。 Lync Server コントロールパネルを使用して、これらのポリシーのコンテナープロファイルを作成、変更、または削除することができます。 各帯域幅ポリシー プロファイルは、1 つ以上のネットワーク サイトに関連付けることができます。 帯域幅ポリシープロファイルを作成または変更するには、以下の手順を使用します。 帯域幅ポリシープロファイルを削除するには、「 [Lync Server 2013 でのネットワーク帯域幅ポリシープロファイルの削除](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)」を参照してください。

<div>

## <a name="to-create-a-new-bandwidth-policy-profile"></a>新しい帯域幅ポリシープロファイルを作成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**ネットワーク構成**] をクリックし、[**帯域幅ポリシー**] をクリックします。

4.  [**帯域幅ポリシー** ] ページで、[**新規**] をクリックします。

5.  [**新しい帯域幅ポリシープロファイル**] で、[**名前**] フィールドに名前を入力します。 この名前は、すべての帯域幅ポリシープロファイルの間で一意である必要があります。

6.  [**音声制限**] フィールドに、数値を入力します。 この値は、すべてのオーディオ接続に割り当てる最大帯域幅 (kbps) で表されます。

7.  [**オーディオセッション制限**] フィールドに数値を入力します。 この値は、個々の音声接続に割り当てる最大帯域幅 (kbps) で表されます。 この値は、40以上である必要があります。

8.  [**ビデオの制限**] フィールドに数値を入力します。 この値は、すべてのビデオ接続に割り当てる最大帯域幅 (kbps で表されます) です。

9.  [**ビデオセッション制限**] フィールドに数値を入力します。 この値は、個々のビデオ接続に割り当てる最大帯域幅 (kbps で表されます) です。 この値は、100以上である必要があります。

10. オプション[**説明**] フィールドに値を入力して、名前だけでは表現できないこの帯域幅ポリシープロファイルの詳細情報を提供します。

11. [**確定**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > 新しい帯域幅ポリシープロファイルを作成しても、帯域幅制限が自動的に適用されることはありません。 最初にポリシープロファイルをサイトに関連付ける必要があります。 ポリシープロファイルをサイトに関連付ける方法の詳細については、「 <A href="lync-server-2013-creating-or-modifying-network-sites.md">Lync Server 2013 でのネットワークサイトの作成または変更</A>」を参照してください。

    
    </div>

</div>

<div>

## <a name="to-modify-a-bandwidth-policy-profile"></a>帯域幅ポリシー プロファイルを変更するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**ネットワーク構成**] をクリックし、[**帯域幅ポリシー**] をクリックします。

4.  [**帯域幅ポリシー**] ページで、変更する帯域幅ポリシー プロファイルをクリックします。

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。

6.  [**帯域幅ポリシープロファイルの編集**] ページで、必要に応じてフィールドを変更します (詳細については、このトピックで前述した「帯域幅ポリシープロファイルを作成するには」を参照してください)。

7.  [**確定**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > 帯域幅ポリシープロファイルを変更すると、この帯域幅ポリシープロファイルに関連付けられているすべてのネットワークサイトの帯域幅制限がすぐに更新されます。

    
    </div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのネットワーク帯域幅ポリシープロファイルの削除](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  


[Lync Server 2013 で通話受付管理を構成する](lync-server-2013-configure-call-admission-control.md)  
[Get-csnetworkbandwidthpolicyprofile](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  
[Get-csnetworkbandwidthpolicyprofile](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  
[Get-csnetworkbandwidthpolicyprofile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

