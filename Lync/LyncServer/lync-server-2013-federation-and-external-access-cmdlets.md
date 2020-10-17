---
title: 'Lync Server 2013: フェデレーションと外部アクセスのコマンドレット'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Federation and external access cmdlets
ms:assetid: 4a384a57-257f-47a6-98d9-54cea2c647b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415651(v=OCS.15)
ms:contentKeyID: 48184018
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a4f02160ad9991905bf0f149a2beb72ef21169e7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507294"
---
# <a name="federation-and-external-access-cmdlets-in-lync-server-2013"></a>Lync Server 2013 のフェデレーションと外部アクセスのコマンドレット

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-06-26_

フェデレーションと外部アクセスでは、次の2つの重要な機能が提供されます。フェデレーションにより、ユーザーは組織外のユーザーと通信できます。外部アクセスでは、ユーザーは内部ネットワークの外部から Microsoft Lync Server 2013 に接続できます。 Lync Server 2013 でフェデレーションと外部アクセスを管理するために使用できるコマンドレットでは、ユーザーが内部ネットワークにログオンしなくても、ユーザーが Lync Server に接続できるかどうかを判断できます。

<div>

## <a name="federation-and-external-access-cmdlets"></a>フェデレーションおよび外部アクセスのコマンドレット

フェデレーションと外部アクセスに適用されるほとんどの管理タスクは、Lync Server コントロールパネルから実行できます。 これらの同じタスクは、Lync Server 管理シェルまたはスクリプト内からコマンドレットを使用して実行できます。スクリプトを使用すると、特定のタスクを自動化できます。 以下に、フェデレーションと外部アクセスの管理に直接関連するコマンドレットの一覧を示します。

  - <span></span>  
    [Get-CsAllowedDomain](https://technet.microsoft.com/library/Gg398164(v=OCS.15))

  - <span></span>  
    [新しい-CsAllowedDomain](https://technet.microsoft.com/library/Gg398628(v=OCS.15))

  - <span></span>  
    [-CsAllowedDomain の削除](https://technet.microsoft.com/library/Gg398913(v=OCS.15))

  - <span></span>  
    [設定-CsAllowedDomain](https://technet.microsoft.com/library/Gg398931(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csblockeddomain](https://technet.microsoft.com/library/Gg398424(v=OCS.15))

  - <span></span>  
    [Get-csblockeddomain](https://technet.microsoft.com/library/Gg398822(v=OCS.15))

  - <span></span>  
    [Get-csblockeddomain](https://technet.microsoft.com/library/Gg425832(v=OCS.15))

  - <span></span>  
    [Get-csblockeddomain](https://technet.microsoft.com/library/Gg398090(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg425805(v=OCS.15))

  - <span></span>  
    [Get-csexternalaccesspolicy](https://technet.microsoft.com/library/Gg425942(v=OCS.15))

  - <span></span>  
    [Get-csexternalaccesspolicy](https://technet.microsoft.com/library/Gg398441(v=OCS.15))

  - <span></span>  
    [Get-csexternalaccesspolicy](https://technet.microsoft.com/library/Gg399057(v=OCS.15))

  - <span></span>  
    [Get-csexternalaccesspolicy](https://technet.microsoft.com/library/Gg398916(v=OCS.15))

<!-- end list -->

  - [-CsFIPSConfiguration の取得](https://technet.microsoft.com/library/JJ204904(v=OCS.15))

  - [新しい-CsFIPSConfiguration](https://technet.microsoft.com/library/JJ205114(v=OCS.15))

  - [削除-CsFIPSConfiguration](https://technet.microsoft.com/library/JJ205201(v=OCS.15))

  - [設定-CsFIPSConfiguration](https://technet.microsoft.com/library/JJ205084(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Disable-CsHostingProvider](https://technet.microsoft.com/library/Gg398481(v=OCS.15))

  - <span></span>  
    [Enable-CsHostingProvider](https://technet.microsoft.com/library/Gg398166(v=OCS.15))

  - <span></span>  
    [取得-CsHostingProvider](https://technet.microsoft.com/library/Gg413078(v=OCS.15))

  - <span></span>  
    [新規-CsHostingProvider](https://technet.microsoft.com/library/Gg398490(v=OCS.15))

  - <span></span>  
    [Remove-CsHostingProvider](https://technet.microsoft.com/library/Gg425809(v=OCS.15))

  - <span></span>  
    [Set-CsHostingProvider](https://technet.microsoft.com/library/Gg398532(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Enable-cspublicprovider](https://technet.microsoft.com/library/Gg398984(v=OCS.15))

  - <span></span>  
    [Enable-cspublicprovider](https://technet.microsoft.com/library/Gg398780(v=OCS.15))

  - <span></span>  
    [Enable-cspublicprovider](https://technet.microsoft.com/library/Gg412945(v=OCS.15))

  - <span></span>  
    [Enable-cspublicprovider](https://technet.microsoft.com/library/Gg398161(v=OCS.15))

  - <span></span>  
    [Enable-cspublicprovider](https://technet.microsoft.com/library/Gg412906(v=OCS.15))

  - <span></span>  
    [Enable-cspublicprovider](https://technet.microsoft.com/library/Gg413087(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-csfederatedpartner](https://technet.microsoft.com/library/Gg398281(v=OCS.15))

<!-- end list -->

  - [Get-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204981(v=OCS.15))

  - [新しい-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204631(v=OCS.15))

  - [削除-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ205055(v=OCS.15))

  - [Set-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204686(v=OCS.15))

<!-- end list -->

  - [-CsXmppGatewayConfiguration の取得](https://technet.microsoft.com/library/JJ204869(v=OCS.15))

  - [-CsXmppGatewayConfiguration の設定](https://technet.microsoft.com/library/JJ204769(v=OCS.15))

<!-- end list -->

  - [テスト-CsXmppIM](https://technet.microsoft.com/library/JJ205423(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server PowerShell ブログ](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

