---
title: 'Lync Server 2013: SNMP アプリケーションを構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure an SNMP application
ms:assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412972(v=OCS.15)
ms:contentKeyID: 48185346
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e7dafe07796f6d93e6357a5bff9aa058fe29b85
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028748"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-an-snmp-application-in-lync-server-2013"></a>Lync Server 2013 で SNMP アプリケーションを構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-03_

Lync Server 2013 には、MAC アドレスとポートおよびスイッチ情報を一致させる簡易ネットワーク管理プロトコル (SNMP) アプリケーションに場所情報サービスを接続するために使用できる標準の web サービスインターフェイスが含まれています。

SNMP アプリケーションがインストールされていて、場所情報サービスが場所データベースで一致を見つけられない場合、場所情報サービスはクライアントによって指定された MAC アドレスを使用して、アプリケーションに対して自動的にクエリを実行します。 その後、場所情報サービスは、SNMP アプリケーションによって返されるポートとスイッチの情報を使用して、場所データベースに再度クエリを実行します。

詳細については、「 [set-cswebserviceconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration)」を参照してください。

<div>


> [!NOTE]  
> MAC アドレスは、Windows 8 を実行しているコンピューターでは使用できません。



</div>

<div>

## <a name="to-configure-the-snmp-application-url"></a>SNMP アプリケーションの URL を構成するには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  次のコマンドレットを使用して SNMP アプリケーションの URL を構成します。
    
        Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>

