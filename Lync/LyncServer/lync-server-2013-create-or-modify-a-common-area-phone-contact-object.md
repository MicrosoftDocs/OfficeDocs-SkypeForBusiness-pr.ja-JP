---
title: 'Lync Server 2013: 一般的なエリア電話の連絡先オブジェクトを作成または変更する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a common area phone Contact object
ms:assetid: eec33ad1-e4f2-49b2-91d6-d5a9d2e1714b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994083(v=OCS.15)
ms:contentKeyID: 51803995
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee1345477178d7991083332e809de3f764be4c3a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833806"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-common-area-phone-contact-object-in-lync-server-2013"></a>Lync Server 2013 で一般的なエリア電話の連絡先オブジェクトを作成または変更する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-20_

共通するすべての携帯電話の Active Directory ドメインサービス連絡先オブジェクトを作成するには、 **CsCommonAreaPhone**コマンドレットを使用します。 このコマンドレットは、一般的なエリア携帯電話で使用する新しい連絡先オブジェクトを作成するか、既存の連絡先オブジェクトを新しい一般的な市外局番に関連付けることができます。 一般的な市外局番に関連付けられた連絡先オブジェクトのプロパティを変更するには、 **CsCommonAreaPhone**コマンドレットを使用します。 **CsCommonAreaPhone**のオプションパラメーターを使用すると、連絡先の Active Directory 表示名や、電話に関連付けられている行の Uniform resource IDENTIFIER (URI) などの項目を変更して、Lync で使用するアカウントを有効または無効にすることができます。Server. 使用可能なすべての変更の詳細については、「 [Set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone)」の「パラメーター」セクションを参照してください。 **新規 CsCommonAreaPhone**パラメーターの詳細については、「 [CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone)」を参照してください。

これら2つのコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。

<div>


<div>

## <a name="creating-a-common-area-phone-contact-object"></a>一般的なエリア電話の連絡先オブジェクトを作成する

  - 新しい共通エリア電話連絡先オブジェクトを作成するには、 **CsCommonAreaPhone**コマンドレットを使用します。 連絡先オブジェクトの作成時には、少なくとも次の情報を入力する必要があります。
    
      - **Lineuri**: 一般的な市外局番に割り当てられている電話番号。 電話番号を指定するときは、必ず164形式を使用する必要があることに注意してください。
    
      - **RegistrarPool**: 連絡先オブジェクトをホストするレジストラープールの完全修飾ドメイン名 (FQDN) です。
    
      - **OU**: 連絡先オブジェクトを作成する Active Directory コンテナーの識別名。
    
    Active Directory ドメインサービスの表示名も指定することをお勧めします。 それ以外の場合は、電話 Id を指定するために GUID を使用する必要があります。 次に例を示します。
    
        New-CsCommonAreaPhone -LineUri "tel:+12065551219" -RegistrarPool "atl-cs-001.litwareinc.com" -OU "OU=Phones,dc=litwareinc,dc=com" -DisplayName "Lobby"

</div>

<div>

## <a name="modifying-a-common-area-phone-contact-object"></a>一般的なエリア電話の連絡先オブジェクトを変更する

  - 既存の一般的な市外局番のプロパティを変更するには、 **CsCommonAreaPhone**コマンドレットを使用します。 たとえば、次のコマンドは、共通エリア電話の SIP アドレスを DisplayName ロビーで構成します。
    
        Set-CsCommonAreaPhone -Identity "Lobby" -SipAddress "sip:lobby@litwareinc.com"

</div>

詳細については、 [CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone)コマンドレットと[CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone)コマンドレットのヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

