---
title: 'Lync Server 2013: ネットワークサイトリンクを構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring network site links
ms:assetid: 7e9147ae-e727-46c8-8c1a-6c13201f09be
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521023(v=OCS.15)
ms:contentKeyID: 48184622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e379a8195dd0a50d97a514307ac594908be4736c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763481"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-network-site-links-in-lync-server-2013"></a>Lync Server 2013 でネットワークサイトリンクを構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-01_

通話受付制御 (CAC) 構成では、直接リンクされているサイト間の帯域幅の制限を定義するネットワーク間ポリシーを作成できます。 ネットワークサイトが直接リンクを共有している場合、オーディオおよびビデオ接続の帯域幅の制限は、これら2つのサイト間で定義できます。 Lync Server コントロールパネルを使ってネットワークサイトポリシーを構成することはできません。これは、Lync Server 管理シェルのコマンドレットを使用することによってのみ実行できます。 Lync Server 管理シェルからネットワークサイトリンク (ネットワークのサイト間ポリシーとも呼ばれます) を作成、変更、削除することができます。

<div>

## <a name="to-create-a-network-site-link"></a>ネットワークサイトのリンクを作成するには

1.  Lync Server 管理シェルが RTCUniversalServerAdmins グループのメンバーとして、または「 [Lync server 2013 の委任セットアップの権限](lync-server-2013-delegate-setup-permissions.md)」で説明されているように、必要なユーザー権限を持つコンピューターにログオンします。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  コマンドプロンプトで、次のコマンドを入力します。これは、構成に対して有効な値に置き換えます。
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    この例では、Reno とポートランドのネットワーク\_サイト間の帯域幅の制限を設定する Reno ポートランドという名前の新しいネットワークサイトリンクを作成します。 このコマンドを実行する前に、ネットワークサイトと帯域幅ポリシーのプロファイルが既に存在している必要があります。

パラメーターの詳細については、「Lync Server Management Shell ドキュメントの[CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) 」を参照してください。 ネットワークサイトリンクに適用できる帯域幅ポリシープロファイルの一覧を取得するには、 **CsNetworkBandwidthPolicyProfile**コマンドレットを呼び出します。 詳細については、「Lync Server 管理シェルドキュメントの[CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) 」を参照してください。

</div>

<div>

## <a name="to-modify-a-network-site-link"></a>ネットワークサイトのリンクを変更するには

1.  Lync Server 管理シェルが RTCUniversalServerAdmins グループのメンバーとして、または「 [Lync server 2013 の委任セットアップの権限](lync-server-2013-delegate-setup-permissions.md)」で説明されているように、必要なユーザー権限を持つコンピューターにログオンします。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  指定のネットワークサイトリンクのプロパティを変更するには、 **CsNetworkInterSitePolicy**コマンドレットを使用します。 いずれか (または両方) または接続されたサイトを変更することができます。また、リンクに関連付けられている帯域幅ポリシープロファイルを変更することもできます。 Reno\_ポートランドという名前のサイトリンクの帯域幅ポリシープロファイルを変更する例を次に示します。
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

パラメーターの詳細については、「Lync Server Management Shell ドキュメントの[CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy) 」を参照してください。

</div>

<div>

## <a name="to-delete-a-network-site-link"></a>ネットワークサイトのリンクを削除するには

1.  Lync Server 管理シェルが RTCUniversalServerAdmins グループのメンバーとして、または「 [Lync server 2013 の委任セットアップの権限](lync-server-2013-delegate-setup-permissions.md)」で説明されているように、必要なユーザー権限を持つコンピューターにログオンします。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  ネットワークサイトへのリンクを削除するには、 **CsNetworkInterSitePolicy**コマンドレットを使用します。 次の例では、\_Reno ポートランドネットワークサイトのリンクを削除します。
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

パラメーターの詳細については、「Lync Server Management Shell ドキュメントの[CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy) 」を参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での通話受付制御コマンドレット](https://docs.microsoft.com/powershell/module/skype/)  


[新規-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)  
[Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  
[Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  
[Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  
[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

