---
title: 'Lync Server 2013: Hosted Exchange ユーザー管理'
TOCTitle: Hosted Exchange ユーザー管理
ms:assetid: e8723af5-0604-4d7d-bad2-463a9832efb4
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg399037(v=OCS.15)
ms:contentKeyID: 48274017
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の Hosted Exchange ユーザー管理

 

_**トピックの最終更新日:** 2015-03-09_

Hosted Exchange サービスのメールボックスを使用している Lync Server 2013 ユーザーにボイス メール サービスを提供するには、それらのユーザーのユーザー アカウントでホスト ボイス メールを使用できるようにする必要があります。

> [!NOTE]
> Lync Server 2013 のユーザーがホスト ボイス メールを使用できるようにするには、対応するユーザー アカウントに適用されるホスト ボイス メール ポリシーをまず展開する必要があります。ここで展開するポリシーは、有効化するユーザーに適用するのであれば、そのスコープがグローバルなものでも、サイト レベルのものでも、ユーザー単位のものでもかまいません。詳細については、「 <a href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013 のホスト型ボイス メール ポリシー</a>」を参照してください。


## msExchUCVoiceMailSettings 属性

Lync Server 2013 には、 **msExchUCVoiceMailSettings** という名前の新しいユーザー属性が導入されました。この属性は Lync Server 2013 Active Directory スキーマの準備の一環として生成されます。この複数値の属性は、 Lync Server 2013 と Hosted Exchange サービスで共有されるボイス メール設定を示します。

Hosted Exchange サービスでは、Exchange UM の有効化プロセス、または Hosted Exchange Server へのメールボックスの転送プロセス中に、msExchUCVoiceMailSettings 属性の値が設定されることがあります。この属性が Exchange によって設定されない場合には、 Lync Server 2013 管理者がこのトピックで前述したように Set-CsUser コマンドレットを実行して、この属性を設定する必要があります。

次の表では、属性のキー/値ペアとその設定元について説明します。

### msExchUCVoiceMailSettings 属性のキー/値ペア

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
<td><p>ExchangeHostedVoiceMail=1</p></td>
<td><p>Exchange</p></td>
<td><p>ユーザーによるホスト型 UM へのアクセスは Exchange Server によって有効化されています。 Exchange UM ルーティング アプリケーションが、ユーザーのホスト ボイス メール ポリシーにルーティング詳細があるかどうかをチェックします。</p></td>
</tr>
<tr class="even">
<td><p>ExchangeHostedVoiceMail=0</p></td>
<td><p>Exchange</p></td>
<td><p>ユーザーによるホスト型 UM へのアクセスは Exchange Server によって無効化されています。</p></td>
</tr>
<tr class="odd">
<td><p>CsHostedVoiceMail=1</p></td>
<td><p>Lync Server</p></td>
<td><p>ユーザーによるホスト型 UM へのアクセスは Lync Server 2013 によって有効化されています。 Lync Server 2013 ExUM ルーティング アプリケーションが、ユーザーのホスト ボイス メール ポリシーにルーティング詳細があるかどうかをチェックします。</p></td>
</tr>
<tr class="even">
<td><p>CsHostedVoiceMail=0</p></td>
<td><p>Lync Server</p></td>
<td><p>ユーザーによるホスト型 UM へのアクセスは Lync Server 2013 によって無効化されています。</p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> 属性に Lync Server 2013 のキー/値ペア (CSHostedVoiceMail=0 または CSHostedVoiceMail=1) 以外の値がすでに存在している場合には、その属性が別のアプリケーションで管理される可能性があることを示す警告が表示されます。たとえば、キー/値ペア ExchangeHostedVoiceMail=0 または ExchangeHostedVoiceMail=1 がすでに存在している場合には、警告が表示されます。そのようなときには、Active Directory で値を変更するか、または次のコマンドレットを実行して、値を Null に設定します。<br />
> Set-CsUser -identity user -HostedVoicemail $null


## ユーザーによるホスト ボイス メールの有効化

ユーザーのボイス メール通話が Hosted Exchange UM へルーティングされるようにするには、Set-CsUser コマンドレットを実行して、 *HostedVoiceMail* パラメーターの値を設定する必要があります。また、このパラメーターによって Lync Server 2013 の "ボイス メールの呼び出し" インジケーターが点灯します。

  - 次の例では、Pilar Ackerman のユーザー アカウントでホスト ボイス メールを使用できるようにします。
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $True
    
    これは、ホスト ボイス メールのポリシー (グローバル、サイトレベル、またはユーザー単位) がこのユーザーに適用されていることを確認するコマンドレットです。 適用されるポリシーがない場合には、このコマンドレットは失敗します。

  - 次の例では、Pilar Ackerman のユーザー アカウントでホスト ボイス メールを使用できないようにします。
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $False
    
    これは、ホスト ボイス メールのポリシー (グローバル、サイトレベル、またはユーザー単位) がこのユーザーに適用されていないことを確認するコマンドレットです。 適用されるポリシーがある場合には、このコマンドレットは失敗します。

Set-CsUser コマンドレットの使用方法の詳細については、「 Lync Server 管理シェル」のドキュメントを参照してください。

