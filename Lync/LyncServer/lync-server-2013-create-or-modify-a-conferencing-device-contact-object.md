---
title: 会議デバイス連絡先オブジェクトの作成または変更
TOCTitle: 会議デバイス連絡先オブジェクトの作成または変更
ms:assetid: 62ed64be-379c-417d-9453-511881cf5604
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ994035(v=OCS.15)
ms:contentKeyID: 52056620
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 会議デバイス連絡先オブジェクトの作成または変更

 

_**トピックの最終更新日:** 2013-10-02_

会議ルーム オブジェクトを作成するために、最初にデバイスを表す Active Directory ユーザー アカウントを作成します。次に、**Enable-CsMeetingRoom** コマンドレットを使用して、そのアカウントが会議デバイスとして機能するようにします。既存の会議デバイスのプロパティを変更する必要がある場合は、**Set-CsMeetingRoom** コマンドレットを使用します。

これらのコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。

> [!NOTE]
> リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 (<a href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</a>) を参照してください。



## 会議デバイスを作成する

  - 新しい会議デバイスを表す Active Directory ユーザー アカウントを作成した後で、**Enable-CsMeetingRoom** コマンドレットを使用してそれを有効にします。必ず a) 会議デバイス ID、b) ルーム アカウントが所属するレジストラー プール、および c) そのアカウントに割り当てられる SIP アドレスが含まれるようにします。たとえば、次のようになります。
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

## 会議デバイスを修正する

  - 既存の会議デバイスのプロパティ値を変更するには、**Set-CsMeetingRoom** コマンドレットを使用します。たとえば、以下のコマンドは、会議デバイスに関連付けられた電話番号 (LineUri) を更新します。
    
        Set-CsMeetingRoom -Identity "Redmond Conferencing device" -LineUri "tel:+12065551219"

詳細は、[Enable-CsMeetingRoom](https://docs.microsoft.com/en-us/powershell/module/skype/Enable-CsMeetingRoom) コマンドレットおよび [Set-CsMeetingRoom](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsMeetingRoom) コマンドレットのヘルプ トピックを参照してください。

