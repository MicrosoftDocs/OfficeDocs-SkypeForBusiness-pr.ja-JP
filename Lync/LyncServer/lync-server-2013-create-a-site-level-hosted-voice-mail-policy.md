---
title: 'Lync Server 2013: サイトレベルのホストボイスメールポリシーの作成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a site-level hosted voice mail policy
ms:assetid: 145892c8-a6ca-45fb-9e83-786f709dd775
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398216(v=OCS.15)
ms:contentKeyID: 48183481
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e23f14b1db7c846d5dbaa0aa6861274a7b6a2611
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501884"
---
# <a name="create-a-site-level-hosted-voice-mail-policy-in-lync-server-2013"></a>Lync Server 2013 でサイトレベルのホストボイスメールポリシーを作成する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-24_

** サイト ポリシーは、このポリシーが定義されているサイトに所属するすべてのユーザーに影響します。 Hosted Exchange UM にアクセスできるように構成されているユーザーにユーザー単位のポリシーが割り当てられていない場合には、サイト ポリシーが適用されます。 サイト ポリシーを展開してない場合は、グローバル ポリシーが適用されます。

サイトポリシーの構成の詳細については、以下のコマンドレットの Lync Server Management Shell のドキュメントを参照してください。

  - [New-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [Get-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-site-hosted-voice-mail-policy"></a>サイトのホスト ボイス メール ポリシーを作成するには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  New-CsHostedVoicemailPolicy コマンドレットを実行して、ポリシーを作成します。 たとえば、以下を実行します。
    
        New-CsHostedVoicemailPolicy -Identity site:Redmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for the Redmond site." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    この例では、サイト スコープを使用してホスト ボイス メール ポリシーを作成し、次のパラメーターを設定しています。
    
      - **Identity** は、スコープを含むポリシーの一意識別子を指定します。 サイトスコープを持つポリシーの場合は、Identity パラメーターの値を形式で指定する必要があり `site:` *\<name\>* ます (例:) `site:Redmond` 。
    
      - **Destination** では、Hosted Exchange UM サービスの完全修飾ドメイン名 (FQDN) を指定します。このパラメーターは省略可能ですが、ユーザーに割り当てられているポリシーで送信先の値が設定されていないと、ユーザーのホスト ボイス メールを有効にしようとしても失敗します。
    
      - **Description** では、ポリシーに関する説明情報を指定します (オプション)。
    
      - **Organization** Lync Server 2013 のホームユーザーが持つ Exchange テナントのコンマ区切りリストを指定します。 各テナントは、Hosted Exchange UM サービス上のテナントの FQDN として指定する必要があります。

</div>

</div>

<span> </span>

</div>

</div>

</div>

