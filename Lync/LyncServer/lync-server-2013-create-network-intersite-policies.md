---
title: 'Lync Server 2013: ネットワークのサイト間ポリシーを作成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create network intersite policies
ms:assetid: b0714aae-55dc-4587-b718-34a03f596b22
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412844(v=OCS.15)
ms:contentKeyID: 48185148
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 655cde30a3d798d57520c57e3882b2162010888c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740327"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-network-intersite-policies-in-lync-server-2013"></a>Lync Server 2013 でネットワークのサイト間ポリシーを作成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-19_

*ネットワークのサイト間ポリシー*は、それらの間に直接 WAN リンクがあるサイト間の帯域幅制限を定義します。

詳細については、次のコマンドレットの Lync Server 管理シェルに関するドキュメントを参照してください。

  - [新規-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)

  - [Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)

  - [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)

  - [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)

<div>


> [!IMPORTANT]  
> ネットワークのサイト間ポリシーは、2つのネットワークサイト間に直接クロスリンクがある場合に<EM>のみ</EM>必要です。



</div>

North America 地域のトポロジの例では、Reno と Albuquerque のサイト間に直接リンクがあります。 この2つのサイトでは、適切な帯域幅ポリシープロファイルを適用するサイト間ポリシーが必要です。 次の例では、\_20 ~ 20 のリンクプロファイルを適用します。

<div>

## <a name="to-create-a-network-intersite-policy"></a>ネットワークのサイト間ポリシーを作成するには

1.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

2.  CsNetworkInterSitePolicy コマンドレットを実行して、ネットワークのサイト間ポリシーを作成し、ダイレクトクロスリンクを持つ2つのサイトに対して、適切な帯域幅ポリシープロファイルを適用します。 たとえば、以下を実行します。
    
        New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link

3.  必要に応じて、手順2を繰り返して、ダイレクトクロスリンクを含むすべてのネットワークサイトペアのネットワークサイト間ポリシーを作成します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

