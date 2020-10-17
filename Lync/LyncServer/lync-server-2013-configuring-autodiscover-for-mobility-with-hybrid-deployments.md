---
title: ハイブリッド展開でのモビリティの自動検出の構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Autodiscover for mobility with hybrid deployments
ms:assetid: f838af79-d8b4-4122-b81c-7889573d143e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215885(v=OCS.15)
ms:contentKeyID: 48706012
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3b0617094c9dcab6b6eee0cf634440fea63cf16
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502164"
---
# <a name="configuring-autodiscover-in-lync-server-2013-for-mobility-with-hybrid-deployments"></a>Lync Server 2013 での自動検出の構成 (ハイブリッド展開を使用したモビリティ)

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-06-18_

ハイブリッド展開は、Microsoft Lync Online cloud service とオンプレミス展開の両方を使用する構成です。 この種類の構成では、自動検出サービスは、ユーザーの実際の場所を特定できなければなりません。 つまり、自動検出では、ユーザーアカウントを検索し、ユーザーのアカウントをホストしているサーバーがオンプレミスの展開にあるか、Lync Online の展開であるかに関係なく、ユーザーアカウントをホストしている場所に支援します。

たとえば、ユーザーのアカウントが Lync Online のサーバーでホストされている場合、ユーザーの検索は次のように実行されます。これは、 *発見*性と呼ばれるプロセスにあります。

  - ユーザーは、内部設置型展開である **contoso.com** への接続を試行します.

  - この試行は、自動検出サーバーに関連付けられた DNS 名である lyncdiscover.contoso.com に送信されます。

  - 自動検出は、contoso.com オンプレミス展開の前提となるレジストラープールを参照し、Lync Online でホストされているユーザーのホームサーバー上の情報を指定します。 その後、自動検出はユーザーに、**lync.com** オンライン自動検出サービスへの紹介を送信します。

  - ユーザーは lync.com オンライン自動検出サービスへの接続を試行し、ユーザーのアカウントおよびユーザーのホーム サーバーが特定されます。

ユーザー ホーム サーバーがある場所でモバイル クライアントが展開を検出できるようにするには、新しい URL (uniform resource locator) で自動検出サービスを構成する必要があります。自動検出サービスを構成するには次の手順に従います。

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a>ハイブリッド展開のための自動検出の構成

1.  Get-CsHostingProvider を使用して、属性 ProxyFQDN の値を取得します。

2.  Lync Server 管理シェルで、と入力します。
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
    
    \[Id \] は、共有 SIP アドレススペースのドメイン名に置き換えられます。

</div>

<div>

## <a name="see-also"></a>関連項目


[取得-CsHostingProvider](https://technet.microsoft.com/library/Gg413078(v=OCS.15))  
[Set-CsHostingProvider](https://technet.microsoft.com/library/Gg398532(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

