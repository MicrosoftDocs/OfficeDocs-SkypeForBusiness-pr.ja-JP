---
title: 会議の構成設定 の表示
TOCTitle: 会議の構成設定 の表示
ms:assetid: d03a4684-9d8b-4728-917d-5b5c91511e2c
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ721894(v=OCS.15)
ms:contentKeyID: 49887157
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 会議の構成設定 の表示

 

_**トピックの最終更新日:** 2013-02-23_

Lync Server 2013 コントロール パネルでは、会議構成設定を使用して、展開の中で会議をどのように実装するかを制御します。これには、次の会議構成が含まれます。

  - Lync Server 2013 を展開するときに既定で作成されるグローバル構成。

  - 特定のサイトまたはユーザーに対する会議の実装方法を指定するために作成して使用できるオプションのサイトレベルおよびユーザーレベルの構成。

## 会議構成設定を表示するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで、\[**会議**\] をクリックし、\[**会議の構成**\] をクリックします。

4.  \[**会議の構成**\] ページで、表示する会議構成をクリックします。

5.  \[**ファイル フィルターの編集**\] で、\[**詳細の表示**\] チェック ボックスをオンにします。
    
    **会議構成の編集 - \<ポリシー\>** が開き、選択したポリシーの設定が表示されます。設定の構成の詳細については、「[Lync Server 2013 での会議構成設定のコレクションの作成または変更](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md)」を参照してください。

## Lync Server PowerShell コマンドレットを使用して会議構成情報を表示する

会議構成の設定は、Lync Server PowerShell および the Get-CsMeetingConfiguration コマンドレットを使用して表示することもできます。このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## 会議構成情報を表示する

  - すべての会議構成設定の情報を表示するには、Lync Server 管理シェルで次のコマンドを入力して Enter キーを押します。
    
        Get-CsMeetingConfiguration
    
    次のような情報が表示されます。
    
        Identity                        : Global
        PstnCallersBypassLobby          : True
        EnableAssignedConferenceType    : True
        DesignateAsPresenter            : Company
        AssignedConferenceTypeByDefault : True
        AdmitAnonymousUsersByDefault    : True
        RequireRoomSystemsAuthorization : False
        LogoURL                         :
        LegalURL                        :
        HelpURL                         :
        CustomFooterText                :
        AllowConferenceRecording        : True

詳細については、[Get-CsMeetingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsMeetingConfiguration) コマンドレットのヘルプ トピックを参照してください。

