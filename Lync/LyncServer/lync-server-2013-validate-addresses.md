---
title: 'Lync Server 2013: アドレスを確認する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Validate addresses
ms:assetid: aae557c9-e6f5-4d23-8af1-1d4cd7968c54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412808(v=OCS.15)
ms:contentKeyID: 48185108
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57ae7698a50706ed0076650a657a8ec503ffa6aa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848251"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validate-addresses-in-lync-server-2013"></a>Lync Server 2013 で住所を検証する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-17_

位置情報データベースを公開する前に、SIP トランクまたは公衆交換電話網 (PSTN) E9 サービスプロバイダーによって維持されている、主要な住所ガイド (MSAG) に対して新しい場所を検証する必要があります。

SIP トランクの E9 サービスプロバイダの詳細については、「 [Lync Server 2013 の E9 サービスプロバイダーを選択する](lync-server-2013-choosing-an-e9-1-1-service-provider.md)」を参照してください。

住所の検証の詳細については、次のコマンドレットの Lync Server 管理シェルに関するドキュメントを参照してください。

  - **Get-CsLisServiceProvider**

  - **Set-CsLisServiceProvider**

  - **Remove-CsLisServiceProvider**

  - **Get-CsLisCivicAddress**

  - **テスト-CsLisCivicAddress**

<div>

## <a name="to-validate-addresses-located-in-the-location-database"></a>場所データベースにある住所を確認するには

1.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

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

