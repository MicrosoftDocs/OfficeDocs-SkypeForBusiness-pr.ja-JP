---
title: 会議デバイスの有効化または無効化
TOCTitle: 会議デバイスの有効化または無効化
ms:assetid: d5140e38-d015-4706-9bde-cf2fa748c36b
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ994070(v=OCS.15)
ms:contentKeyID: 52056713
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 会議デバイスの有効化または無効化

 

_**トピックの最終更新日:** 2013-02-20_

**Enable-CsMeetingRoom** コマンドレットおよび **Disable-CsMeetingRoom** コマンドレットを使用して、会議デバイスを有効化または無効化します。これらのコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。

> [!NOTE]
> リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 (<a href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</a>) を参照してください。



## 会議デバイスを有効化する

  - 会議デバイスを有効化する場合は、**Enable-CsMeetingRoom** コマンドレットを使用します。会議デバイスを有効化するときは、a) 会議デバイス ID、b) 部屋のアカウントが属するレジストラー プール、c) そのアカウントに割り当てられる SIP アドレスを含める必要があります。
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

## 会議デバイスを無効化する

  - 会議デバイスを無効化する場合は、**Disable-CsMeetingRoom** コマンドレットを使用します。無効化する会議デバイスの ID を必ず指定してください。
    
        Disable-CsMeetingRoom -Identity "sip:RedmondMeetingRoom@litwareinc.com"

詳細については、[Enable-CsMeetingRoom](https://docs.microsoft.com/en-us/powershell/module/skype/Enable-CsMeetingRoom) コマンドレットおよび [Disable-CsMeetingRoom](https://docs.microsoft.com/en-us/powershell/module/skype/Disable-CsMeetingRoom) コマンドレットに関するヘルプ トピックを参照してください。

