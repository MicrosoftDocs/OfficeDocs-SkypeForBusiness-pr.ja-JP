---
title: 'Lync Server 2013: ネットワーク帯域幅ポリシーのプロファイル情報を表示する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing network bandwidth policy profile information
ms:assetid: eed453fc-04e9-4971-959c-6fad54bf1c96
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721931(v=OCS.15)
ms:contentKeyID: 49733866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 513bd20e9a1ecd40f061c4873e7da8bff4738f36
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848183"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-bandwidth-policy-profile-information-in-lync-server-2013"></a>Lync Server 2013 でネットワーク帯域幅ポリシーのプロファイル情報を表示する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-23_

通話受付制御 (CAC) の一部として、帯域幅ポリシーを使って、特定のモダリティの帯域幅の制限を定義します。 Microsoft Lync Server 2013 では、オーディオとビデオのモダリティのみが帯域幅の制限を割り当てることができます。 全体的な帯域幅の制限とセッションの制限を設定できます。 Lync Server コントロールパネルを使用して、これらのポリシーのコンテナープロファイルを作成、変更、または削除することができます。 各帯域幅ポリシーのプロファイルは、1つ以上のネットワークサイトに関連付けることができます。 帯域幅ポリシーのプロファイルを表示するには、次の手順を使用します。 帯域幅ポリシープロファイルを作成または変更するには、「 [Lync Server 2013 での帯域幅ポリシープロファイルの作成または](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)変更」を参照してください。

<div>

## <a name="to-view-a-bandwidth-policy-profile"></a>帯域幅ポリシーのプロファイルを表示するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**帯域幅ポリシー**] をクリックします。

4.  [**帯域幅ポリシー** ] ページで、表示する帯域幅ポリシープロファイルをクリックします。

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。

</div>

<div>

## <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してネットワーク帯域幅ポリシーのプロファイル情報を表示する

ネットワーク帯域幅プロファイルを表示するには、Windows PowerShell と CsNetworkBandwidthPolicyProfile コマンドレットを使用します。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。

<div>

## <a name="to-view-network-bandwidth-policy-profile-information"></a>ネットワーク帯域幅ポリシーのプロファイル情報を表示するには

  - すべてのネットワーク帯域幅ポリシープロファイルに関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、enter キーを押します。
    
        Get-CsNetworkBandwidthPolicyProfile
    
    次のような情報が表示されます。
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :

</div>

詳細については、 [CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)コマンドレットのヘルプトピックを参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での帯域幅ポリシープロファイルの作成または変更](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[Lync Server 2013 でネットワーク帯域幅ポリシープロファイルを削除する](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  


[Lync Server 2013 での通話受付制御の構成](lync-server-2013-configure-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

