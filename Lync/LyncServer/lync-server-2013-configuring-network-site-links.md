---
title: 'Lync Server 2013: ネットワークサイトリンクの構成'
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
ms.openlocfilehash: face7287ecf65a75e335b63f0a657c4534891277
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030510"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-network-site-links-in-lync-server-2013"></a>Lync Server 2013 でのネットワークサイトリンクの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

通話受付管理 (CAC) 構成内で、直接リンクされたサイト間の帯域幅制限を定義するネットワークサイト間ポリシーを作成できます。 ネットワーク サイトが直接リンクを共有している場合、これらの 2 つのサイト間にオーディオ接続およびビデオ接続の帯域幅制限を定義できます。 Lync Server コントロールパネルを使用してネットワークサイトポリシーを構成することはできません。これを行うには、Lync Server 管理シェルのコマンドレットを使用する必要があります。 Lync Server 管理シェルから、ネットワークサイトリンク (ネットワークサイト間ポリシーとも呼ばれます) を作成、変更、および削除することができます。

<div>

## <a name="to-create-a-network-site-link"></a>ネットワーク サイト リンクを作成するには

1.  Lync Server 管理シェルがインストールされているコンピューターに、RTCUniversalServerAdmins グループのメンバーとして、または「 [Lync server 2013 のセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」に説明されている必要なユーザー権限を使用してログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  コマンド プロンプトで、使用している構成で有効な値に置き換えて、次のコマンドを入力します。
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    この例では、リノとポートランドのネットワーク\_サイト間の帯域幅制限を設定するリノポートランドという名前の新しいネットワークサイトリンクを作成します。 ネットワーク サイトと帯域幅ポリシーのプロファイルが、このコマンドを実行する前に既に存在している必要があります。

パラメーターの詳細については、「Lync Server Management Shell」のドキュメントの「 [get-csnetworkintersitepolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) 」を参照してください。 ネットワーク サイト リンクに適用できる帯域幅ポリシーのプロファイルの一覧を取得するには、**Get-CsNetworkBandwidthPolicyProfile** コマンドレットを呼び出します。 詳細については、「Lync Server Management Shell」のドキュメントの「 [get-csnetworkbandwidthpolicyprofile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) 」を参照してください。

</div>

<div>

## <a name="to-modify-a-network-site-link"></a>ネットワーク サイト リンクを変更するには

1.  Lync Server 管理シェルがインストールされているコンピューターに、RTCUniversalServerAdmins グループのメンバーとして、または「 [Lync server 2013 のセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」に説明されている必要なユーザー権限を使用してログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  特定のネットワーク サイト リンクのプロパティを変更するには、**Set-CsNetworkInterSitePolicy** コマンドレットを使用します。 接続されたサイトの一方 (または両方) を変更したり、リンクに関連付けられた帯域幅ポリシーのプロファイルを変更したりできます。 ここでは、リノ\_ポートランドという名前のサイトリンクの帯域幅ポリシープロファイルを変更する例を示します。
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

パラメーターの説明の詳細については、「Lync Server Management Shell」のドキュメントの「 [get-csnetworkintersitepolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy) 」を参照してください。

</div>

<div>

## <a name="to-delete-a-network-site-link"></a>ネットワーク サイト リンクを削除するには

1.  Lync Server 管理シェルがインストールされているコンピューターに、RTCUniversalServerAdmins グループのメンバーとして、または「 [Lync server 2013 のセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」に説明されている必要なユーザー権限を使用してログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  ネットワーク サイト リンクを削除するには、**Remove-CsNetworkInterSitePolicy** コマンドレットを使用します。 次の例では、\_リノポートランドネットワークサイトリンクを削除します。
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

パラメーターの詳細については、「Lync Server Management Shell」のドキュメントの「 [get-csnetworkintersitepolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy) 」を参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での通話受付管理のコマンドレット](https://docs.microsoft.com/powershell/module/skype/)  


[Get-csnetworkintersitepolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)  
[Get-csnetworkintersitepolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  
[Get-csnetworkintersitepolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  
[Get-csnetworkintersitepolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  
[Get-csnetworkbandwidthpolicyprofile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

