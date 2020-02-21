---
title: 'Lync Server 2013: アドレスの検証'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validate addresses
ms:assetid: aae557c9-e6f5-4d23-8af1-1d4cd7968c54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412808(v=OCS.15)
ms:contentKeyID: 48185108
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb35c064c304360adb27ecae73dd93c0e616711a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212573"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="validate-addresses-in-lync-server-2013"></a>Lync Server 2013 での住所の検証

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-17_

場所データベースを公開する前に、SIP トランクまたは公衆交換電話網 (PSTN) E9-1-1 サービス プロバイダーが維持する主要道路住所案内 (MSAG) で新しい場所を確認する必要があります。

SIP トランク E9-1-1 サービスプロバイダーの詳細については、「 [Lync Server 2013 の E9-1-1 サービスプロバイダーの選択](lync-server-2013-choosing-an-e9-1-1-service-provider.md)」を参照してください。

住所の検証の詳細については、以下のコマンドレットの Lync Server Management Shell のドキュメントを参照してください。

  - **CsLisServiceProvider**

  - **CsLisServiceProvider**

  - **CsLisServiceProvider**

  - **Test-csliscivicaddress**

  - **Test-csliscivicaddress**

<div>

## <a name="to-validate-addresses-located-in-the-location-database"></a>場所データベースにある住所を確認するには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  次のコマンドレットを実行して、緊急サービス プロバイダーとの接続を構成します。
    
        $pwd = Read-Host -AsSecureString <password>
        Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd

3.  次のコマンドレットを実行して、場所データベース内の住所を確認します。
    
        Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
    
    また、**Test-CsLisCivicAddress** コマンドレットを使用して、個々の住所を確認することもできます。

</div>

</div>

<span> </span>

</div>

</div>

</div>

