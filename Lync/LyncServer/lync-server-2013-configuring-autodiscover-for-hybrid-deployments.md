---
title: 'Lync Server 2013: ハイブリッド展開のための自動検出の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Autodiscover for hybrid deployments
ms:assetid: ca605e62-181c-42ca-80a1-e37e610f8277
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945653(v=OCS.15)
ms:contentKeyID: 51541521
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6015603d2c8c151cbe9d9b76410e51708f3ba9e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188450"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-autodiscover-in-lync-server-2013-for-hybrid-deployments"></a>Lync Server 2013 でのハイブリッド展開の自動検出の構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-12-12_

ハイブリッド展開は、Microsoft Lync Online cloud service とオンプレミス展開の両方を使用する構成です。 この種類の構成では、自動検出サービスは、ユーザーの実際の場所を特定できなければなりません。 つまり、自動検出では、ユーザーアカウントを検索し、ユーザーのアカウントをホストしているサーバーがオンプレミスの展開にあるか、Lync Online の展開であるかに関係なく、ユーザーアカウントをホストしている場所に支援します。

たとえば、ユーザーのアカウントが Lync Online のサーバーでホストされている場合、ユーザーの検索は次のように実行されます。これは、*発見*性と呼ばれるプロセスにあります。

  - ユーザーは、内部設置型展開である **contoso.com** への接続を試行します.

  - この試行は、自動検出サーバーに関連付けられた DNS 名である lyncdiscover.contoso.com に送信されます。

  - 自動検出は、contoso.com オンプレミス展開の前提となるレジストラープールを参照し、Lync Online でホストされているユーザーのホームサーバー上の情報を指定します。 その後、自動検出はユーザーに、**lync.com** オンライン自動検出サービスへの紹介を送信します。

  - ユーザーは lync.com オンライン自動検出サービスへの接続を試行し、ユーザーのアカウントおよびユーザーのホーム サーバーが特定されます。

クライアントが、ユーザーのホームサーバーが配置されている展開を検出できるようにするには、新しい uniform resource locator (URL) を使用して自動検出サービスを構成する必要があります。 自動検出サービスを構成するには次の手順に従います。

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a>ハイブリッド展開のための自動検出の構成

1.  トピック「 [Lync Server 2013 の自動検出サービス要件](lync-server-2013-autodiscover-service-requirements.md)」では、Get-CsHostingProvider を使用して、属性 proxyfqdn の値を取得します。

2.  Lync Server 管理シェルで、と入力します。
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodisccoverservice.svc/root
    
    \[Id\]は、共有 SIP アドレススペースのドメイン名に置き換えられます。

</div>

<div>

## <a name="see-also"></a>関連項目


[取得-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/Get-CsHostingProvider)  
[Set-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/Set-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

