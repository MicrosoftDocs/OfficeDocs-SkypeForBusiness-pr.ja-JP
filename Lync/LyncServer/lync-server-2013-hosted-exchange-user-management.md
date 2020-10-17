---
title: 'Lync Server 2013: Hosted Exchange ユーザー管理'
description: 'Lync Server 2013: Hosted Exchange ユーザー管理。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange user management
ms:assetid: e8723af5-0604-4d7d-bad2-463a9832efb4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399037(v=OCS.15)
ms:contentKeyID: 48185887
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ceda9352fc627fc7b762b5995d788ffafa159ae
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550113"
---
# <a name="hosted-exchange-user-management-in-lync-server-2013"></a>Lync Server 2013 での Hosted Exchange ユーザー管理

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-18_

ホストされた Exchange サービスにメールボックスがある Lync Server 2013 ユーザーにボイスメールサービスを提供するには、ホストボイスメールに対して自分のユーザーアカウントを有効にする必要があります。

<div>


> [!NOTE]  
> ホストボイスメールに対して Lync Server 2013 ユーザーを有効にするには、対応するユーザーアカウントに適用されるホストボイスメールポリシーを展開する必要があります。 ここで展開するポリシーは、有効化するユーザーに適用するのであれば、そのスコープがグローバルなものでも、サイト レベルのものでも、ユーザー単位のものでもかまいません。 詳細については、「 <A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013 のホストボイスメールポリシー</A>」を参照してください。



</div>

<div>

## <a name="the-msexchucvoicemailsettings-attribute"></a>msExchUCVoiceMailSettings 属性

Lync Server 2013 は、 **msExchUCVoiceMailSettings**という名前の新しいユーザー属性を導入しています。これは、lync Server 2013 Active Directory スキーマの準備の一部として作成されます。 この複数値属性は、Lync Server 2013 と hosted Exchange サービスで共有されるボイスメール設定を保持します。

Hosted Exchange サービスでは、Exchange UM の有効化プロセス、または Hosted Exchange Server へのメールボックスの転送プロセス中に、msExchUCVoiceMailSettings 属性の値が設定されることがあります。 この属性が Exchange によって設定されていない場合は、このトピックで前述したように、Lync Server 2013 管理者が Set-CsUser コマンドレットを実行して設定する必要があります。

次の表では、属性のキー/値ペアとその設定元について説明します。

### <a name="the-msexchucvoicemailsettings-attribute-keyvalue-pairs"></a>msExchUCVoiceMailSettings 属性のキー/値ペア

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>値</th>
<th>設定元</th>
<th>意味</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ExchangeHostedVoiceMail = 1</p></td>
<td><p>Exchange</p></td>
<td><p>ユーザーによるホスト型 UM へのアクセスは Exchange Server によって有効化されています。 Exchange UM ルーティングアプリケーションは、ルーティングの詳細について、ユーザーのホストボイスメールポリシーをチェックします。</p></td>
</tr>
<tr class="even">
<td><p>ExchangeHostedVoiceMail = 0</p></td>
<td><p>Exchange</p></td>
<td><p>ユーザーによるホスト型 UM へのアクセスは Exchange Server によって無効化されています。</p></td>
</tr>
<tr class="odd">
<td><p>CsHostedVoiceMail = 1</p></td>
<td><p>Lync Server</p></td>
<td><p>ユーザーが Lync Server 2013 によってホストされた UM アクセスが有効になっている。 Lync Server 2013 ExUM ルーティングアプリケーションは、ルーティングの詳細についてユーザーのホストボイスメールポリシーをチェックします。</p></td>
</tr>
<tr class="even">
<td><p>CsHostedVoiceMail = 0</p></td>
<td><p>Lync Server</p></td>
<td><p>Lync Server 2013 によるホスト型 UM へのアクセスがユーザーに対して無効になっています。</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 属性に既に Lync Server 2013 のキー/値ペア (CSHostedVoiceMail = 0 または CSHostedVoiceMail = 1) 以外の値が設定されている場合は、その属性が別のアプリケーションによって管理されている可能性があることを示す警告が表示されます。 たとえば、キー/値ペア ExchangeHostedVoiceMail=0 または ExchangeHostedVoiceMail=1 がすでに存在している場合には、警告が表示されます。 そのようなときには、Active Directory で値を変更するか、または次のコマンドレットを実行して、値を Null に設定します。<BR>Set-CsUser –identity user –HostedVoicemail $null



</div>

</div>

<div>

## <a name="enabling-users-for-hosted-voice-mail"></a>ユーザーによるホスト ボイス メールの有効化

ユーザーのボイス メール通話が Hosted Exchange UM へルーティングされるようにするには、Set-CsUser コマンドレットを実行して、*HostedVoiceMail* パラメーターの値を設定する必要があります。 また、このパラメーターは Lync Server 2013 に通知して、"ボイスメールの呼び出し" インジケーターを明るくします。

  - 次の例では、Pilar Ackerman のユーザー アカウントでホスト ボイス メールを使用できるようにします。
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $True
    
    これは、ホスト ボイス メールのポリシー (グローバル、サイトレベル、またはユーザー単位) がこのユーザーに適用されていることを確認するコマンドレットです。 適用されるポリシーがない場合には、このコマンドレットは失敗します。

  - 次の例では、Pilar Ackerman のユーザー アカウントでホスト ボイス メールを使用できないようにします。
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $False
    
    これは、ホスト ボイス メールのポリシー (グローバル、サイトレベル、またはユーザー単位) がこのユーザーに適用されていないことを確認するコマンドレットです。 適用されるポリシーがある場合には、このコマンドレットは失敗します。

Set-CsUser コマンドレットの使用の詳細については、「Lync Server Management Shell」のドキュメントを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

