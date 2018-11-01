---
title: 会議ポリシー情報の表示
TOCTitle: 会議ポリシー情報の表示
ms:assetid: e99fdc4d-926a-4e36-ac99-ab5035568847
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ721918(v=OCS.15)
ms:contentKeyID: 49887195
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 会議ポリシー情報の表示

 

_**トピックの最終更新日:** 2013-02-23_

Lync Server 2013 コントロール パネルでは、会議ポリシーを使用して、会議をどのように展開に実装するかを制御します。これには、次の会議ポリシーが含まれます。

  - Lync Server 2013 を展開するときに既定で作成されるグローバル ポリシー。

  - 特定のサイトまたはユーザーに対する会議の実装方法を指定するために作成して使用できるオプションのサイトレベルおよびユーザーレベルのポリシー。

## 会議ポリシーの設定を表示するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで、\[**会議**\] をクリックし、\[**会議ポリシー**\] をクリックします。

4.  \[**会議ポリシー**\] ページで、表示する会議ポリシーをダブルクリックします。

5.  \[**ファイル フィルターの編集**\] で、\[**詳細の表示**\] チェック ボックスをオンにします。
    
    \[**編集 電話会議ポリシー - \<ポリシー\>**\] が開き、選択したポリシーの設定が表示されます。設定の構成に関する詳細については、「[Lync Server 2013 での会議ポリシーの作成または変更](lync-server-2013-create-or-modify-a-conferencing-policy.md)」を参照してください。

## Lync Server PowerShell コマンドレットを使用して会議ポリシーを表示する

会議ポリシーは、Lync Server PowerShell と Get-CsConferencingPolicy コマンドレットを使用して表示することもできます。このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## 会議ポリシーを表示する

  - すべての会議ポリシーに関する情報を表示するには、Lync Server 管理シェルに次のコマンドを入力し、Enter キーを押します。
    
        Get-CsConferencingPolicy
    
    次のような情報が表示されます。
    
        Identity                                  : Global
        AllowIPAudio                              : True
        AllowIPVideo                              : True
        AllowMultiView                            : True
        Description                               :
        AllowParticipantControl                   : True
        AllowAnnotations                          : True
        DisablePowerPointAnnotations              : False
        AllowUserToScheduleMeetingsWithAppSharing : True
        AllowNonEnterpriseVoiceUsersToDialOut     : False
        AllowAnonymousUsersToDialOut              : False
        AllowAnonymousParticipantsInMeetings      : True
        AllowExternalUsersToSaveContent           : True
        AllowExternalUserControl                  : False
        AllowExternalUsersToRecordMeeting         : False
        AllowPolls                                : True
        AllowSharedNotes                          : True
        EnableDialInConferencing                  : True
        EnableAppDesktopSharing                   : Desktop
        AllowConferenceRecording                  : False
        EnableP2PRecording                        : False
        EnableFileTransfer                        : True
        EnableP2PFileTransfer                     : True
        EnableP2PVideo                            : True
        AllowLargeMeetings                        : False
        EnableDataCollaboration                   : True
        MaxVideoConferenceResolution              : VGA
        MaxMeetingSize                            : 250
        AudioBitRateKb                            : 200
        VideoBitRateKb                            : 50000
        AppSharingBitRateKb                       : 50000
        FileTransferBitRateKb                     : 50000
        TotalReceiveVideoBitRateKb                : 6000
        EnableMultiViewJoin                       : True

詳細については、[Get-CsConferencingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsConferencingPolicy) コマンドレットのヘルプ トピックを参照してください。

