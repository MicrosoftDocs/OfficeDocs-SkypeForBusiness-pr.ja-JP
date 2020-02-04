---
title: 'Lync Server 2013: ユーザーごとにホストされるボイスメールポリシーを作成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a per-user hosted voice mail policy
ms:assetid: 39018a7c-e0c3-46a2-be4e-05604ec67a50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425867(v=OCS.15)
ms:contentKeyID: 48183902
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 535515fd11c0cb736b5b6fb4b70d041ea3af8a3c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740377"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a>Lync Server 2013 でユーザーごとにホストされるボイスメールのポリシーを作成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-24_

*ユーザーごと*のポリシーは、個々のユーザー、グループ、連絡先オブジェクトにのみ影響を与える可能性があります。 ユーザーごとのポリシーを展開するには、ポリシーを1つ以上のユーザー、グループ、または連絡先オブジェクトに明示的に割り当てる必要があります。 詳細については、「 [Lync Server 2013 でユーザーごとにホストされるボイスメールのポリシーを割り当てる](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)」を参照してください。

ユーザーごとにホストされるボイスメールポリシーの使用について詳しくは、次のコマンドレットの Lync Server 管理シェルに関するドキュメントをご覧ください。

  - [New-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [Get-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-per-user-hosted-voice-mail-policy"></a>ユーザーごとにホストされるボイスメールポリシーを作成するには

1.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

2.  CsHostedVoicemailPolicy コマンドレットを実行して、ポリシーを作成します。 たとえば、以下を実行します。
    
        New-CsHostedVoicemailPolicy -Identity ExRedmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for Redmond users." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    上の例では、ホストされたボイスメールポリシーをユーザーごとのスコープで作成し、次のパラメーターを設定します。
    
      - **Id**は、スコープを含むポリシーの一意の識別子を指定します。 ユーザーごとのスコープを持つポリシーの場合、このパラメーター値は単純な文字列 (ExRedmond など) として指定されます。
    
      - [ **Destination** ] は、ホストされた Exchange UM サービスの完全修飾ドメイン名 (FQDN) を指定します。 このパラメーターは省略可能ですが、ホストされたボイスメールに対してユーザーを有効にしようとしても、ユーザーに割り当てられているポリシーに送信先の値がない場合、有効にすることはできません。
    
      - **説明**ポリシーに関するオプションの説明情報を提供します。
    
      - [**組織**] は、Lync Server 2013 のホームユーザーである Exchange テナントのコンマ区切りリストを指定します。 各テナントは、ホストされた Exchange UM サービスでそのテナントの FQDN として指定する必要があります。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でユーザーごとにホストされるボイスメールのポリシーを割り当てる](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

