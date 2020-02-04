---
title: 'Lync Server 2013: 帯域幅ポリシープロファイルを作成または変更する'
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
ms.openlocfilehash: 06019464d6d37c601c9077d36c81976d43b6e37c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733687"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-bandwidth-policy-profiles-in-lync-server-2013"></a>Lync Server 2013 での帯域幅ポリシープロファイルの作成または変更

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-15_

通話受付制御 (CAC) の一部として、帯域幅ポリシーを使って、特定のモダリティの帯域幅の制限を定義します。 Microsoft Lync Server 2013 では、オーディオとビデオのモダリティのみが帯域幅の制限を割り当てることができます。 全体的な帯域幅の制限とセッションの制限を設定できます。 Lync Server コントロールパネルを使用して、これらのポリシーのコンテナープロファイルを作成、変更、または削除することができます。 各帯域幅ポリシーのプロファイルは、1つ以上のネットワークサイトに関連付けることができます。 帯域幅ポリシープロファイルを作成または変更するには、次の手順を使用します。 帯域幅ポリシーのプロファイルを削除する方法については、「 [Lync Server 2013 でネットワーク帯域幅ポリシープロファイルを削除](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)する」を参照してください。

<div>

## <a name="to-create-a-new-bandwidth-policy-profile"></a>新しい帯域幅ポリシープロファイルを作成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**帯域幅ポリシー**] をクリックします。

4.  [**帯域幅ポリシー** ] ページで、[**新規**] をクリックします。

5.  **新しい帯域幅ポリシープロファイル**で、[**名前**] フィールドに名前を入力します。 この名前は、すべての帯域幅ポリシープロファイルの間で一意である必要があります。

6.  [**オーディオ制限**] フィールドに数値を入力します。 この値は、すべてのオーディオ接続に割り当てることができる最大帯域幅です。 kbps で表されます。

7.  [**オーディオセッションの制限**] フィールドに数値を入力します。 この値は、個々の音声接続に割り当てられる帯域幅の上限です。 kbps で表されます。 この値は40以上である必要があります。

8.  [**ビデオの制限**] フィールドに数値を入力します。 この値は、すべてのビデオ接続に割り当てることができる最大帯域幅です。 kbps で表されます。

9.  [**ビデオセッションの制限**] フィールドに数値を入力します。 この値は、個々のビデオ接続に割り当てることができる最大帯域幅です。 kbps で表されます。 この値は100以上である必要があります。

10. 省略[**説明**] フィールドに値を入力して、この帯域幅ポリシープロファイルの詳細情報を指定します。

11. [**コミット**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > 新しい帯域幅ポリシープロファイルを作成しても、帯域幅の制限は自動的に適用されません。 最初にポリシープロファイルをサイトに関連付ける必要があります。 ポリシープロファイルをサイトに関連付ける方法の詳細については、「 <A href="lync-server-2013-creating-or-modifying-network-sites.md">Lync Server 2013 でネットワークサイトを作成または変更</A>する」を参照してください。

    
    </div>

</div>

<div>

## <a name="to-modify-a-bandwidth-policy-profile"></a>帯域幅ポリシーのプロファイルを変更するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**帯域幅ポリシー**] をクリックします。

4.  [**帯域幅ポリシー** ] ページで、変更する帯域幅ポリシープロファイルをクリックします。

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。

6.  [**帯域幅ポリシープロファイルの編集**] ページで、必要に応じてフィールドを変更します (詳細については、このトピックの前の「帯域幅ポリシープロファイルを作成する」セクションを参照してください)。

7.  [**コミット**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > 帯域幅ポリシーのプロファイルを変更すると、この帯域幅ポリシープロファイルに関連付けられたすべてのネットワークサイトの帯域幅の制限がすぐに更新されます。

    
    </div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でネットワーク帯域幅ポリシープロファイルを削除する](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  


[Lync Server 2013 での通話受付制御の構成](lync-server-2013-configure-call-admission-control.md)  
[新規-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  
[Set-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  
[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

