---
title: 'Lync Server 2013: 共通領域電話の連絡先オブジェクトを作成または変更する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a common area phone Contact object
ms:assetid: eec33ad1-e4f2-49b2-91d6-d5a9d2e1714b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994083(v=OCS.15)
ms:contentKeyID: 51803995
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0855db68e1f08a26070689b1699bd200a1edbfaf
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504744"
---
# <a name="create-or-modify-a-common-area-phone-contact-object-in-lync-server-2013"></a>Lync Server 2013 で共通領域電話の連絡先オブジェクトを作成または変更する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-20_

すべての共通領域電話に対して Active Directory ドメインサービスの連絡先オブジェクトを作成するには、 **move-cscommonareaphone** コマンドレットを使用します。 このコマンドレットでは、共通領域電話で使用する新しい連絡先オブジェクトを作成するか、既存の連絡先オブジェクトを新しい共通領域電話に関連付けることができます。 共通領域電話に関連付けられている連絡先オブジェクトのプロパティを変更するには、 **move-cscommonareaphone** コマンドレットを使用します。 **Move-cscommonareaphone**のオプションのパラメーターを使用すると、連絡先の Active Directory 表示名や電話に関連付けられている回線 Uri (Uniform resource Identifier) などのアイテムを変更し、Lync Server で使用するアカウントを有効または無効にすることができます。 使用可能なすべての変更の詳細については、「 [move-cscommonareaphone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone)」のパラメータセクションを参照してください。 **Move-cscommonareaphone**パラメーターの詳細については、「 [move-cscommonareaphone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone)」を参照してください。

これら2つのコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>


<div>

## <a name="creating-a-common-area-phone-contact-object"></a>共通領域電話の連絡先オブジェクトの作成

  - 新しい共通領域電話の連絡先オブジェクトを作成するには、 **move-cscommonareaphone** コマンドレットを使用します。 連絡先オブジェクトを作成するときには、少なくとも次の情報を指定する必要があります。
    
      - **Lineuri**: 共通領域電話に割り当てられた電話番号です。 電話番号を指定するときは、e.164 形式を使用する必要があることに注意してください。
    
      - **RegistrarPool**: 連絡先オブジェクトをホストするレジストラープールの完全修飾ドメイン名 (FQDN)。
    
      - **OU**: 連絡先オブジェクトを作成する Active Directory コンテナーの識別名。
    
    また、Active Directory ドメインサービスの表示名を指定することもお勧めします。 それ以外の場合は、電話 Id を指定するために GUID を使用する必要があります。 以下に例を示します。
    
        New-CsCommonAreaPhone -LineUri "tel:+12065551219" -RegistrarPool "atl-cs-001.litwareinc.com" -OU "OU=Phones,dc=litwareinc,dc=com" -DisplayName "Lobby"

</div>

<div>

## <a name="modifying-a-common-area-phone-contact-object"></a>共通領域電話の連絡先オブジェクトを変更する

  - 既存の共通領域電話のプロパティを変更するには、連絡先オブジェクトで **move-cscommonareaphone** コマンドレットを使用します。 たとえば、次のコマンドは、共通領域電話の SIP アドレスを DisplayName ロビーで構成します。
    
        Set-CsCommonAreaPhone -Identity "Lobby" -SipAddress "sip:lobby@litwareinc.com"

</div>

詳細については、 [move-cscommonareaphone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone) コマンドレットおよび [move-cscommonareaphone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone) コマンドレットのヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

