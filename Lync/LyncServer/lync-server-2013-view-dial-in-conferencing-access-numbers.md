---
title: ダイヤルイン会議アクセス番号の表示
TOCTitle: ダイヤルイン会議アクセス番号の表示
ms:assetid: 41a7dfb4-0c89-4650-b61b-0e1bf875c62b
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688037(v=OCS.15)
ms:contentKeyID: 49886932
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ダイヤルイン会議アクセス番号の表示

 

_**トピックの最終更新日:** 2013-02-23_

Lync Server 2013 コントロール パネルで、ダイヤルイン アクセス番号をユーザーに提供し、そのユーザーが外部的に会議に参加できるようにます。

## ダイヤルイン アクセス番号を表示するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**会議**\] をクリックし、\[**ダイヤルイン アクセス番号**\] をクリックします。

4.  \[**ダイヤルイン アクセス番号**\] ページで、表示するアクセス番号をクリックします。

5.  \[**編集**\] で、\[**詳細の表示**\] チェック ボックスをオンにします。

## Lync Server PowerShell コマンドレットを使用してダイヤルイン会議アクセス番号を表示する

Lync Server PowerShell および Get-CsDialInConferencingAccessNumber コマンドレットを使用して、ダイヤルイン会議アクセス番号を表示することもできます。このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## SIP トランク構成情報を表示する

  - すべてのダイヤルイン会議アクセス番号に関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、Enter キーを押します。
    
        Get-CsDialInConferencingAccessNumber
    
    これは次のような情報を返します。
    
        Identity           : CN={20ca8dc8-5ff8-41f4-b5bb-22ba9972ae2e},
                             CN=Application Contacts,CN=RTCService=Services,
                             CN=Configuration,DC=litwareinc,DC=com
        PrimaryUri         : sip:testnumber@litwareinc.com
        DisplayName        : Test
        DisplayNumber      : 1-425-555-1019
        LineUri            : tel:+14255551019
        PrimaryLanguage    : en-US
        SecondaryLanguages : {}
        Pool               : atl-cs-001.litwareinc.com
        HostingProvider    :
        Regions            : {US}

詳細については、[Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsDialInConferencingAccessNumber) コマンドレットのヘルプ トピックを参照してください。

