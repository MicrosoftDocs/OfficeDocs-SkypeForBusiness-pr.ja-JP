---
title: 'Lync Server 2013: グローバルホストボイスメールポリシーの変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the global hosted voice mail policy
ms:assetid: f059b3ce-a7d8-4ea9-b10b-0052222ec2ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412994(v=OCS.15)
ms:contentKeyID: 48185757
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9a7e9dcb3c626c076d51fa32fa195f0787a922c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515174"
---
# <a name="modify-the-global-hosted-voice-mail-policy-in-lync-server-2013"></a>Lync Server 2013 でのグローバルホストボイスメールポリシーの変更

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-24_

*グローバル*ホストボイスメールポリシーは、Lync Server 2013 と共にインストールされます。 グローバル ポリシーを必要に応じて変更することはできますが、名前変更や削除はできません。 グローバルポリシーを変更するには、Set-CsHostedVoicemailPolicy コマンドレットを使用して、特定の展開についてパラメーターを適切な値に設定します。

[Set-cshostedvoicemailpolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)コマンドレットの詳細については、「Lync Server Management Shell」のドキュメントを参照してください。

<div>

## <a name="to-modify-the-global-hosted-voice-mail-policy"></a>グローバルホストボイスメールポリシーを変更するには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  Set-CsHostedVoicemailPolicy コマンドレットを実行して、環境のグローバルポリシーパラメーターを設定します。 たとえば、以下を実行します。
    
        Set-CsHostedVoicemailPolicy -Destination ExUM.fabrikam.com -Organization "corp1.litwareinc.com"
    
    このコマンドではポリシーの Identity パラメーターが指定されていないため、Windows PowerShell コマンドラインインターフェイスでは、グローバルホストボイスメールポリシーに次の値を設定します。
    
      - **Destination** では、Hosted Exchange UM サービスの完全修飾ドメイン名 (FQDN) を指定します。このパラメーターは省略可能ですが、ユーザーに割り当てられているポリシーで送信先の値が設定されていないと、ユーザーのホスト ボイス メールを有効にしようとしても失敗します。
    
      - **Organization** Lync Server ユーザーが所属する Exchange テナントのコンマ区切りリストを指定します。 各テナントは、Hosted Exchange UM サービス上のテナントの FQDN として指定する必要があります。
    
    <div>
    

    > [!NOTE]  
    > 前の例のコマンドレットでは、値 "corp1.litwareinc.com" は、組織パラメーターに既に存在している可能性のある任意の値に置き換えられます。 たとえば、ポリシーに組織のコンマ区切りの一覧が既に含まれている場合は、完全なリストが置き換えられます。 リスト全体を置換するのではなく、リストに組織を追加する場合は、次のようなコマンドを実行します。

    
    </div>
    
        $a = Get-CsHostedVoicemailPolicy
        $a.Organization += ",corp3.litwareinc.com"
        Set-CsHostedVoicemailPolicy -Organization $a.Organization

</div>

</div>

<span> </span>

</div>

</div>

</div>

