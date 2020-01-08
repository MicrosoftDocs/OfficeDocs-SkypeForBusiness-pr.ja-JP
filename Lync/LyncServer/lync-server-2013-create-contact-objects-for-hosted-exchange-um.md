---
title: 'Lync Server 2013: Hosted Exchange UM の連絡先オブジェクトの作成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create contact objects for hosted Exchange UM
ms:assetid: a39be52f-488a-4523-ad5f-ce1f0d681959
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412765(v=OCS.15)
ms:contentKeyID: 48185045
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53d5bdfe3b341f534a3e8066fe85be5e93b0a7f7
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971269"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-contact-objects-for-hosted-exchange-um-in-lync-server-2013"></a>Lync Server 2013 での Hosted Exchange UM の連絡先オブジェクトの作成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-24_

次の手順では、ホストされた Exchange ユニファイドメッセージング (UM) 用に自動応答 (AA) または加入者アクセス (SA) 連絡先オブジェクトを作成する方法について説明します。

詳細については、計画ドキュメントの「 [Lync Server 2013 での Hosted Exchange Contact object management](lync-server-2013-hosted-exchange-contact-object-management.md) 」を参照してください。

連絡先オブジェクトの構成の詳細については、次のコマンドレットの Lync Server 管理シェルに関するドキュメントを参照してください。

  - [New-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/New-CsExUmContact)

  - [Set-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/Set-CsExUmContact)

<div class=" ">


> [!IMPORTANT]  
> Lync Server 2013 連絡先オブジェクトをホストされた Exchange UM に対して有効にする前に、それらに適用されるホストされたボイスメールポリシーを展開する必要があります。 詳細については、「 <A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013 のホスト型ボイスメールポリシー</A>」を参照してください。



</div>

<div>

## <a name="to-create-aa-or-sa-contact-objects-for-hosted-exchange-um"></a>Hosted Exchange UM 用の AA または SA の連絡先オブジェクトを作成するには

1.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

2.  新しい-CsExUmContact コマンドレットを実行して、展開に必要な連絡先オブジェクトを作成します。 たとえば、次のように実行して AA と SA の連絡先オブジェクトを作成します。
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumaa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101" -AutoAttendant $True
       ```
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumsa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101"
       ```
    
    これらの例では、次のパラメーターを設定します。
    
      - **SipAddress**連絡先オブジェクトの SIP アドレスを指定します。 これは、Active Directory ドメインサービスでユーザーまたは連絡先オブジェクトを構成するためにまだ使用されていないアドレスである必要があります。 この値は、前の例で示した\<ように、"sip:*sip アドレス*\>" の形式になっている必要があります。
    
      - **RegistrarPool**は、レジストラーサービスが実行されているプールの完全修飾ドメイン名 (FQDN) を指定します。
        
        <div class=" ">
        

        > [!NOTE]  
        > Lync server 2013 より前の Lync Server 2013 展開の一部であるプールに Exchange UM 連絡先オブジェクトを移動することはできません。

        
        </div>
    
      - **OU**この連絡先オブジェクトを配置する Active Directory の組織単位を指定します。
    
      - **Displaynumber**連絡先オブジェクトの電話番号を指定します。 各連絡先オブジェクトの電話番号は一意である必要があります。
    
      - **Autoattendant**連絡先オブジェクトが自動応答かどうかを指定します。 自動応答では、発信者が電話システムを移動して、連絡を希望する当事者に連絡できるようにする一連の音声プロンプトが用意されています。 このパラメーターの値が**False** (既定値) の場合、サブスクライバーアクセスの contact オブジェクトが示されます。

</div>

</div>

<span> </span>

</div>

</div>

</div>

