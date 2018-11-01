---
title: コール パーク設定の構成
TOCTitle: コール パーク設定の構成
ms:assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg425886(v=OCS.15)
ms:contentKeyID: 48271834
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# コール パーク設定の構成

 

_**トピックの最終更新日:** 2015-03-09_

既定のコール パーク設定を使用したくない場合は、カスタマイズできます。コール パーク アプリケーションをインストールすると、既定でグローバル設定が構成されます。このグローバル設定は変更できます。また、サイト固有の設定を指定することもできます。新しいサイト固有の設定を作成するには、**New-CsCpsConfiguration** コマンドレットを使用します。既存の設定を変更するには、**Set-CsCpsConfiguration** コマンドレットを使用します。

> [!NOTE]
> 少なくとも、保留された通話が時間切れになりリングバックが失敗した場合に使用する代替宛先の [<strong>OnTimeoutURI</strong>] オプションは構成することをお勧めします。


**New-CsCpsConfiguration** コマンドレットまたは **Set-CsCpsConfiguration** コマンドレットを使用して、次のいずれかの設定を構成します。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>このオプション:</th>
<th>指定する内容:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>CallPickupTimeoutThreshold</strong></p></td>
<td><p>通話が保留されてから、呼び出しに応答した電話にかけ直されるまでの経過時間。</p>
<p>この値は、hh:mm:ss の形式で入力し、時間、分、および秒を指定する必要があります。 最小値は 10 秒、最大値は 10 分です。 既定値は 00:01:30 です。</p></td>
</tr>
<tr class="even">
<td><p><strong>EnableMusicOnHold</strong></p></td>
<td><p>通話が保留されている間、発信者に対して音楽を再生するかどうか。</p>
<p>値は True または False です。既定値は True です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MaxCallPickupAttempts</strong></p></td>
<td><p>保留された通話が [<strong>OnTimeoutURI</strong>] で指定した代替 URI (Uniform Resource Identifier) に転送される前に、応答電話にかけ直される回数。既定値は 1 です。</p></td>
</tr>
<tr class="even">
<td><p><strong>OnTimeoutURI</strong></p></td>
<td><p><strong>MaxCallPickupAttempts</strong> を超過した場合に、応答のない保留通話のルーティング先となるユーザーまたは応答グループの SIP アドレス。</p>
<p>値は、文字列 sip: で始まる SIP URI にする必要があります。 たとえば、sip:bob@contoso.com などです。既定値は転送アドレスではありません。</p></td>
</tr>
</tbody>
</table>


## コール パーク設定を構成するには

1.  Lync Server 管理シェルがインストールされているコンピューターに、RTCUniversalServerAdmins グループのメンバーとして、または「[Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」に説明されている必要なユーザー権限を使用してログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  次のコマンドレットを実行します。
    
        New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
    

    > [!TIP]
    > サイトを識別するには、<STRONG>Get-CsSite</STRONG> コマンドレットを使用します。詳細については、Lync Server 管理シェルのドキュメントを参照してください。

    
    次にその例を示します。
    
        New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com

## 関連項目

#### タスク

[コール パーク保留音のカスタマイズ](lync-server-2013-customize-call-park-music-on-hold.md)  

#### その他のリソース

[New-CsCpsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsCpsConfiguration)  
[Set-CsCpsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCpsConfiguration)  
[Get-CsSite](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsSite)

