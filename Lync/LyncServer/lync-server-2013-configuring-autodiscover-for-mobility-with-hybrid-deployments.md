---
title: ハイブリッド展開での自動検出の構成によるモビリティ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Autodiscover for mobility with hybrid deployments
ms:assetid: f838af79-d8b4-4122-b81c-7889573d143e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215885(v=OCS.15)
ms:contentKeyID: 48706012
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1865cab188bace472996db6207de62ce8498976
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840276"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-autodiscover-in-lync-server-2013-for-mobility-with-hybrid-deployments"></a>Lync Server 2013 のハイブリッド展開での自動検出の構成によるモビリティ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-06-18_

ハイブリッド展開とは、Microsoft Lync Online クラウドサービスとオンプレミスの展開の両方を使用する構成です。 この種類の構成では、自動検出サービスは、ユーザーが実際に配置されている場所を見つけることができる必要があります。 つまり、自動検出によってユーザーアカウントが検索され、オンプレミスの展開または Lync Online の展開のどちらであるかに関係なく、ユーザーのアカウントをホストしているサーバーはどこにあるかが確認されます。

たとえば、ユーザーのアカウントが Lync Online のサーバーでホストされている場合、ユーザーの検索は次のように行われます。これは、 ** 次のようなプロセスで行われます。

  - ユーザーがオンプレミスの展開、 **contoso.com**への接続試行を開始します。

  - 試行は、自動検出サービスに関連付けられている DNS 名 lyncdiscover.contoso.com に送信されます。

  - 自動検出は、contoso.com オンプレミスの展開で想定されるレジストラープールを指し、ユーザーの実際のホームサーバー上で Lync Online でホストされている情報を提供します。 次に、自動検出によって**lync.com** Online 自動検出サービスへの紹介がユーザーに送信されます。

  - ユーザーは lync.com online 自動検出サービスへの接続試行を開始し、ユーザーのアカウントとユーザーのホームサーバーを特定できます。

モバイルクライアントでユーザーのホームサーバーが配置されている展開を検出できるようにするには、新しい uniform resource locator (URL) を使用して自動検出サービスを構成する必要があります。 自動検出サービスを構成するには、次の手順を実行します。

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a>ハイブリッド展開の自動検出を構成する

1.  属性 ProxyFQDN の値を取得するには、Get-CsHostingProvider を使います。

2.  Lync Server 管理シェルで、「
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
    
    ここ\[で\] 、id は共有 SIP アドレス空間のドメイン名に置き換えられます。

</div>

<div>

## <a name="see-also"></a>関連項目


[Get-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg413078(v=OCS.15))  
[Set-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398532(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

