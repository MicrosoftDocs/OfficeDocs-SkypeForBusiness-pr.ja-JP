---
title: PIN ポリシー情報の表示
TOCTitle: PIN ポリシー情報の表示
ms:assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ687985(v=OCS.15)
ms:contentKeyID: 49886865
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# PIN ポリシー情報の表示

 

_**トピックの最終更新日:** 2013-02-23_

\[**PIN ポリシー**\] タブを使用して、IP 電話で Lync 2013 に接続しているユーザーの暗証番号 (PIN) 認証を表示できます。PIN 認証を使用するには、Web サービス設定で \[**PIN 認証を有効にする**\] が選択されていることを確認してください。詳細については、「[既存の Web サービス構成設定の変更](lync-server-2013-modify-existing-web-service-configuration-settings.md)」を参照してください。

ユーザー レベルまたはサイト レベルの PIN ポリシーを変更するには、次の手順に従います。

## Lync Server コントロール パネルで PIN ポリシーに関する情報を表示するには

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Lync Server 2013 を展開したネットワーク内の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**セキュリティ**\] をクリックし、\[**PIN ポリシー**\] をクリックします。

4.  \[**PIN ポリシー**\] ページでポリシーをクリックし、\[**編集**\]、\[**詳細の表示**\] の順にクリックします。

## Lync Server PowerShell コマンドレットによる PIN ポリシーの表示

Windows PowerShell および Get-CsPinPolicy コマンドレットを使用して、PIN ポリシーを表示することもできます。このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## PIN ポリシーの表示

  - すべての PIN ポリシーに関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、Enter キーを押します。
    
        Get-CsPinPolicy
    
    これにより、次のような情報が戻されます。
    
        Identity             : Global
        Description          :
        MinPasswordLength    : 5
        PINHistoryCount      : 0
        AllowCommonPatterns  : False
        PINLifetime          : 0
        MaximumLogonAttempts :

詳細については、[Get-CsPinPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsPinPolicy) コマンドレットのヘルプ トピックを参照してください。

## 関連項目

#### タスク

[既存の Web サービス構成設定の変更](lync-server-2013-modify-existing-web-service-configuration-settings.md)  
[新しい PIN ポリシーの作成](lync-server-2013-create-a-new-pin-policy.md)

