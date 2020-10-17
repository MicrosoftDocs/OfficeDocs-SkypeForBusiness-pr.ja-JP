---
title: 'Lync Server 2013: hosted Exchange UM の連絡先オブジェクトの作成'
description: 'Lync Server 2013: hosted Exchange UM の連絡先オブジェクトを作成します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create contact objects for hosted Exchange UM
ms:assetid: a39be52f-488a-4523-ad5f-ce1f0d681959
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412765(v=OCS.15)
ms:contentKeyID: 48185045
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9760e2a39b5182f9b5194e364e059bddc6a63d2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562303"
---
# <a name="create-contact-objects-for-hosted-exchange-um-in-lync-server-2013"></a>Lync Server 2013 で hosted Exchange UM の連絡先オブジェクトを作成する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-24_

次の手順では、Hosted Exchange ユニファイド メッセージング (UM) の自動応答 (AA) またはサブスクライバー アクセス (SA) の連絡先オブジェクトを作成する方法について説明します。

詳細については、「計画」のドキュメントの「 [Hosted Exchange Contact object management In Lync Server 2013](lync-server-2013-hosted-exchange-contact-object-management.md) 」を参照してください。

連絡先オブジェクトの構成の詳細については、以下のコマンドレットの Lync Server Management Shell のドキュメントを参照してください。

  - [New-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/New-CsExUmContact)

  - [Set-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/Set-CsExUmContact)

<div class=" ">


> [!IMPORTANT]  
> ホストされた Exchange UM に対して Lync Server 2013 連絡先オブジェクトを有効にする前に、それらに適用されるホストボイスメールポリシーを展開する必要があります。 詳細については、「 <A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013 のホストボイスメールポリシー</A>」を参照してください。



</div>

<div>

## <a name="to-create-aa-or-sa-contact-objects-for-hosted-exchange-um"></a>Hosted Exchange UM の AA または SA の連絡先オブジェクトを作成するには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  New-CsExUmContact コマンドレットを実行して、展開に必要な連絡先オブジェクトを作成します。 たとえば、AA および SA の連絡先オブジェクトを作成するには、次のように実行します。
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumaa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101" -AutoAttendant $True
       ```
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumsa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101"
       ```
    
    これらの例は、次のパラメーターを設定します。
    
      - **SipAddress** は、連絡先オブジェクトの SIP アドレスを指定します。 これは、Active Directory ドメイン サービスでユーザーまたは連絡先オブジェクトを構成するために以前使用したことのないアドレスである必要があります。 この値は、前の例で示されているように、"sip:" という形式で指定する必要があり \<*SIP address*\> ます。
    
      - **RegistrarPool** は、レジストラー サービスが実行されているプールの完全修飾ドメイン名 (FQDN) を指定します。
        
        <div class=" ">
        

        > [!NOTE]  
        > Lync Server 2013 の前に、Lync Server 2013 展開の一部であるプールに Exchange UM 連絡先オブジェクトを移動することはできません。

        
        </div>
    
      - **OU** は、この連絡先オブジェクトの配置先となる Active Directory 組織単位を指定します。
    
      - **DisplayNumber** は、連絡先オブジェクトの電話番号を指定します。 各連絡先オブジェクトの電話番号は一意である必要があります。
    
      - **AutoAttendant** は、連絡先オブジェクトを自動応答にするかどうかを指定します。 発信者は自動応答の音声案内セットを利用することで、電話システムを通して、希望する相手先に連絡することができます。 このパラメーターに **False** (既定値) の値が設定されている場合、それはサブスクライバー アクセスの連絡先オブジェクトです。

</div>

</div>

<span> </span>

</div>

</div>

</div>

