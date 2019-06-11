---
title: 'Lync Server 2013: Hosted Exchange ユーザー管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hosted Exchange user management
ms:assetid: e8723af5-0604-4d7d-bad2-463a9832efb4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399037(v=OCS.15)
ms:contentKeyID: 48185887
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ead9762c67f3239f84cc1290b4ff2e9acc976318
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833063"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-user-management-in-lync-server-2013"></a>Lync Server 2013 の Hosted Exchange ユーザー管理

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-18_

ホストされている Exchange サービス上にメールボックスがある Lync Server 2013 ユーザー用のボイスメールサービスを提供するには、ホストされているボイスメールに対してユーザーアカウントを有効にする必要があります。

<div>


> [!NOTE]  
> ホストされているボイスメールに対して Lync Server 2013 ユーザーを有効にするには、対応するユーザーアカウントに適用されるホストされたボイスメールポリシーを展開する必要があります。 ポリシーは、有効にするユーザーに適用される限り、スコープ内でグローバル、サイト、またはユーザーごとに設定できます。 詳細については、「 <A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013 のホスト型ボイスメールポリシー</A>」を参照してください。



</div>

<div>

## <a name="the-msexchucvoicemailsettings-attribute"></a>MsExchUCVoiceMailSettings 属性

Lync Server 2013 には、Lync Server 2013 Active Directory スキーマの準備の一部として作成された**msExchUCVoiceMailSettings**という新しいユーザー属性が導入されています。 この複数値属性は、Lync Server 2013 とホストされる Exchange サービスで共有されるボイスメール設定を保持します。

ホストされた Exchange サービスは、Exchange UM を有効にするプロセス、またはメールボックスをホストされた Exchange サーバーに移行するプロセスで、msExchUCVoiceMailSettings 属性の値を設定する場合があります。 この属性が Exchange によって設定されていない場合は、このトピックで前に説明したように、Set-CsUser コマンドレットを実行して Lync Server 2013 管理者が設定する必要があります。

属性のキー/値ペアとその作成者を次の表に示します。

### <a name="the-msexchucvoicemailsettings-attribute-keyvalue-pairs"></a>MsExchUCVoiceMailSettings 属性のキーと値のペア

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>値</th>
<th>著作者</th>
<th>意味</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ExchangeHostedVoiceMail = 1</p></td>
<td><p>Exchange</p></td>
<td><p>ユーザーは Exchange Server によってホストされた UM アクセスが有効になっています。 Exchange UM ルーティングアプリケーションは、ルーティングの詳細についてユーザーのホストされるボイスメールポリシーを確認します。</p></td>
</tr>
<tr class="even">
<td><p>ExchangeHostedVoiceMail = 0</p></td>
<td><p>Exchange</p></td>
<td><p>Exchange Server でホストされている UM アクセスのユーザーが無効になっています。</p></td>
</tr>
<tr class="odd">
<td><p>CsHostedVoiceMail = 1</p></td>
<td><p>Lync Server</p></td>
<td><p>ユーザーが Lync Server 2013 によってホストされた UM アクセスが有効になっている。 Lync Server 2013 ExUM ルーティングアプリケーションは、ルーティングの詳細について、ユーザーのホストされるボイスメールポリシーを確認します。</p></td>
</tr>
<tr class="even">
<td><p>CsHostedVoiceMail = 0</p></td>
<td><p>Lync Server</p></td>
<td><p>Lync Server 2013 でホストされている UM アクセスのユーザーが無効になっている。</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 属性に既に、Lync Server 2013 の1つ以外の値 (CSHostedVoiceMail = 0 または CSHostedVoiceMail = 1) 以外の値が含まれている場合、その属性は別のアプリケーションによって管理されている可能性があることを示す警告が表示されます。 たとえば、キー/値のペア ExchangeHostedVoiceMail = 0 または ExchangeHostedVoiceMail = 1 が既に存在する場合、警告が表示されます。 この場合、値を変更するには、Active Directory を編集するか、次のコマンドレットを実行して値を null に設定します。<BR>Set-CsUser – identity user – HostedVoicemail $null



</div>

</div>

<div>

## <a name="enabling-users-for-hosted-voice-mail"></a>ホストされたボイスメール用にユーザーを有効にする

ユーザーのボイスメールの呼び出しをホストされた Exchange UM にルーティングできるようにするには、 *HostedVoiceMail*パラメーターの値を設定するために、Set-csuser コマンドレットを実行する必要があります。 また、このパラメーターは、"ボイスメールの呼び出し" インジケーターを明るくするために、Lync Server 2013 にも通知します。

  - 次の例では、ホストされているボイスメールに対して Pilar Ackerman のユーザーアカウントを有効にします。
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $True
    
    このコマンドレットは、ホストされたボイスメールポリシー (グローバル、サイトレベル、またはユーザーごと) がこのユーザーに適用されることを確認します。 ポリシーが適用されない場合、コマンドレットは失敗します。

  - 次の例では、ホストされているボイスメールの Pilar Ackerman のユーザーアカウントを無効にします。
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $False
    
    このコマンドレットは、ホストされているボイスメールポリシー (グローバル、サイトレベル、またはユーザーごと) がこのユーザーに適用されていないことを確認します。 ポリシーが適用されると、コマンドレットは失敗します。

Set-CsUser コマンドレットの使い方の詳細については、「Lync Server 管理シェルのドキュメント」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

