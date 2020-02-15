---
title: 'Lync Server 2013: ユーザーごとのホストボイスメールポリシーの作成'
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
ms.openlocfilehash: 055d65fe691d99c8b960ebed088ba47cbcb2f988
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034879"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a>Lync Server 2013 でユーザーごとのホストボイスメールポリシーを作成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-24_

** ユーザー単位のポリシーは、個々のユーザー、グループ、および連絡先オブジェクトにのみ影響します。 ユーザー単位のポリシーを展開するには、ポリシーを 1 つ以上のユーザー、グループ、または連絡先オブジェクトに明示的に割り当てる必要があります。 詳細については、「 [Lync Server 2013 でユーザーごとにホストされるボイスメールポリシーを割り当てる](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)」を参照してください。

ユーザー単位のホストボイスメールポリシーの使用の詳細については、以下のコマンドレットについて、「Lync Server Management Shell」のドキュメントを参照してください。

  - [Set-cshostedvoicemailpolicy](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [Set-cshostedvoicemailpolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [Get-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-per-user-hosted-voice-mail-policy"></a>ユーザー単位のホスト ボイス メール ポリシーを作成するには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  New-CsHostedVoicemailPolicy コマンドレットを実行して、ポリシーを作成します。たとえば、以下を実行します。
    
        New-CsHostedVoicemailPolicy -Identity ExRedmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for Redmond users." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    前の例では、ユーザー単位のスコープを使用してホスト ボイス メール ポリシーを作成し、次のパラメーターを設定しています。
    
      - **Identity** では、ポリシーの一意の識別子を指定します。これにはスコープも含まれます。 ユーザー単位のスコープを使用するポリシーの場合、このパラメーター値には単純な文字列 (ExRedmond など) を指定します。
    
      - **Destination** では、Hosted Exchange UM サービスの完全修飾ドメイン名 (FQDN) を指定します。このパラメーターは省略可能ですが、ユーザーに割り当てられているポリシーで送信先の値が設定されていないと、ユーザーのホスト ボイス メールを有効にしようとしても失敗します。
    
      - **Description** では、ポリシーに関する説明情報を指定します (オプション)。
    
      - **Organization** Lync Server 2013 のホームユーザーが持つ Exchange テナントのコンマ区切りリストを指定します。 各テナントは、Hosted Exchange UM サービス上のテナントの FQDN として指定する必要があります。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でユーザーごとにホストされるボイスメールポリシーを割り当てる](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

