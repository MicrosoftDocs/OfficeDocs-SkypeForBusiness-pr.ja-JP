---
title: 'Lync Server 2013: ハイブリッド展開の自動検出の構成'
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
ms.openlocfilehash: 8924194d89eafb75c06ff78ed3b765699e36b196
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734867"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-autodiscover-in-lync-server-2013-for-hybrid-deployments"></a>ハイブリッド展開用の Lync Server 2013 での自動検出の構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-12-12_

ハイブリッド展開とは、Microsoft Lync Online クラウドサービスとオンプレミスの展開の両方を使用する構成です。 この種類の構成では、自動検出サービスは、ユーザーが実際に配置されている場所を見つけることができる必要があります。 つまり、自動検出によってユーザーアカウントが検索され、オンプレミスの展開または Lync Online の展開のどちらであるかに関係なく、ユーザーのアカウントをホストしているサーバーはどこにあるかが確認されます。

たとえば、ユーザーのアカウントが Lync Online のサーバーでホストされている場合、ユーザーの検索は次のように行われ*ます。これは、次の*ようなプロセスで行われます。

  - ユーザーがオンプレミスの展開、 **contoso.com**への接続試行を開始します。

  - 試行は、自動検出サービスに関連付けられている DNS 名 lyncdiscover.contoso.com に送信されます。

  - 自動検出は、contoso.com オンプレミスの展開で想定されるレジストラープールを指し、ユーザーの実際のホームサーバー上で Lync Online でホストされている情報を提供します。 次に、自動検出によって**lync.com** Online 自動検出サービスへの紹介がユーザーに送信されます。

  - ユーザーは lync.com online 自動検出サービスへの接続試行を開始し、ユーザーのアカウントとユーザーのホームサーバーを特定できます。

クライアントでユーザーのホームサーバーが配置されている場所を検出できるようにするには、新しい uniform resource locator (URL) を使用して自動検出サービスを構成する必要があります。 自動検出サービスを構成するには、次の手順を実行します。

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a>ハイブリッド展開の自動検出を構成する

1.  「 [Lync Server 2013 の自動検出サービス要件](lync-server-2013-autodiscover-service-requirements.md)」では、"Get-CsHostingProvider" を使って Attribute proxyfqdn の値を取得しています。

2.  Lync Server 管理シェルで、「
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodisccoverservice.svc/root
    
    ここ\[で\] 、id は共有 SIP アドレス空間のドメイン名に置き換えられます。

</div>

<div>

## <a name="see-also"></a>関連項目


[Get-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/Get-CsHostingProvider)  
[Set-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/Set-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

