---
title: 'Lync Server 2013: グローバルでホストされるボイスメールのポリシーを変更する'
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
ms.openlocfilehash: e930e0b1f9a6e2d246a8011c59e2c92c75ba138d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756881"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-global-hosted-voice-mail-policy-in-lync-server-2013"></a>Lync Server 2013 でグローバルにホストされるボイスメールのポリシーを変更する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-24_

*グローバル*にホストされるボイスメールポリシーは、Lync Server 2013 と共にインストールされます。 必要に応じて変更できますが、名前の変更や削除はできません。 グローバルポリシーを変更するには、CsHostedVoicemailPolicy コマンドレットを使用して、特定の展開用にパラメーターを適切な値に設定します。

[CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)コマンドレットの詳細については、「Lync Server 管理シェルのドキュメント」を参照してください。

<div>

## <a name="to-modify-the-global-hosted-voice-mail-policy"></a>グローバルでホストされるボイスメールのポリシーを変更するには

1.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

2.  環境のグローバルポリシーパラメーターを設定するには、CsHostedVoicemailPolicy コマンドレットを実行します。 たとえば、以下を実行します。
    
        Set-CsHostedVoicemailPolicy -Destination ExUM.fabrikam.com -Organization "corp1.litwareinc.com"
    
    このコマンドによってポリシーの Id パラメーターが指定されないため、Windows PowerShell のコマンドラインインターフェイスでは、グローバルにホストされるボイスメールポリシーで次の値を設定します。
    
      - [ **Destination** ] は、ホストされた Exchange UM サービスの完全修飾ドメイン名 (FQDN) を指定します。 このパラメーターは省略可能ですが、ホストされたボイスメールに対してユーザーを有効にしようとしても、ユーザーに割り当てられているポリシーに送信先の値がない場合、有効にすることはできません。
    
      - [**組織**] は、Lync Server ユーザーがホームである Exchange テナントのコンマ区切りリストを指定します。 各テナントは、ホストされた Exchange UM サービスでそのテナントの FQDN として指定する必要があります。
    
    <div>
    

    > [!NOTE]  
    > 前の例のコマンドレットでは、"corp1.litwareinc.com" という値が組織のパラメーターに存在する可能性がある値に置き換えられます。 たとえば、ポリシーに既に組織のコンマ区切りのリストが含まれている場合は、完全な一覧が置換されます。 リスト全体を置換するのではなく、リストに組織を追加する場合は、次のようなコマンドを実行します。

    
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

