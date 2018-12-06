---
title: ユーザー単位の音声 ポリシーの割り当て
TOCTitle: ユーザー単位の音声 ポリシーの割り当て
ms:assetid: 9ee47ee7-1030-43b8-a4dc-bf685ea24659
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688155(v=OCS.15)
ms:contentKeyID: 49887073
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ユーザー単位の音声 ポリシーの割り当て

 

_**トピックの最終更新日:** 2013-02-22_

エンタープライズ VoIP が有効になっているすべての Lync Server 2013 ユーザー アカウントには、グローバルとサイト レベルの音声ポリシーが自動的に割り当てられます。Lync Server 2013 コントロール パネルまたは Lync Server 2013 管理シェルを使用して、特定のユーザーに音声ポリシーを割り当てることもできます。ここでは、Lync Server ユーザーにユーザーごとのポリシーを明示的に割り当てる手順を説明します。

## Lync Server コントロール パネルを使用してユーザー固有の音声ポリシーを割り当てるには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**ユーザー**\] をクリックし、構成するユーザー アカウントを検索します。

4.  検索結果一覧の表でユーザー アカウントをクリックし、\[**編集**\] をクリックして、\[**詳細の表示**\] をクリックします。

5.  \[**Lync Server ユーザーの編集**\] の \[**音声ポリシー**\] で、適用するユーザー ポリシーを選択します。
    
    > [!NOTE]
    > [<strong>&lt;自動&gt;</strong>] 設定では、既定のサーバー ポリシーまたはグローバル ポリシーの設定が適用されます。


## Lync Server 管理シェルを使用してユーザー固有の音声ポリシーを割り当てるには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  既存のユーザー音声ポリシーをユーザーに割り当てるには、コマンド プロンプトで次のコマンドを実行します。
    
        Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
    
    次に例を示します。
    
        Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
    
    この例では、Bob Kelly という表示名のユーザーに、**VoicePolicyJapan** という名前の音声ポリシーを割り当てています。

ユーザー固有の音声ポリシーの割り当てまたは **Grant-CsVoicePolicy** コマンドレットの実行の詳細については、「[Lync Server 2013 管理シェル](lync-server-2013-lync-server-management-shell.md)」のドキュメントを参照してください。

## Windows PowerShell コマンドレットを使用してユーザーごとの音声ポリシーを割り当てる

ユーザーごとの音声ポリシーは、Windows PowerShell と **Grant-CsVoicePolicy** コマンドレットを使用して割り当てることもできます。このコマンドレットは、Lync Server 2013 管理シェルから実行することも、Windows PowerShell のリモート セッションから実行することもできます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## ユーザーごとの音声ポリシーを 1 人のユーザーに割り当てる

  - 次のコマンドは、ユーザーごとの音声ポリシー RedmondVoicePolicy をユーザー Ken Myer に割り当てます。
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

## ユーザーごとの音声ポリシーを複数のユーザーに割り当てる

  - このコマンドは、ユーザーごとの音声ポリシー FinanceVoicePolicy を、Active Directory 内の Finance OU にアカウントがあるすべてのユーザーに割り当てます。このコマンドで使用されている OU パラメーターの詳細については、[Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) コマンドレットのドキュメントを参照してください。
    
        Get-CsUser -OU "ou=Finance,ou=North America,dc=litwareinc,dc=com" | Grant-CsVoicePolicy -PolicyName "FinanceVoicePolicy"

## ユーザーごとの音声ポリシーの割り当てを解除する

  - 次のコマンドは、以前に Ken Myer に割り当てられたユーザーごとの音声ポリシーの割り当てを解除します。ユーザー単位のポリシーが割り当て解除された後、Ken Myer は、グローバル ポリシー、または存在する場合は Ken Myer のローカル サイト ポリシーによって、自動的に管理されます。サイト ポリシーは、グローバル ポリシーよりも優先されます。
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName $Null

詳細については、[Grant-CsVoicePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsVoicePolicy) コマンドレットのヘルプ トピックを参照してください。

## 関連項目

#### タスク

[エンタープライズ VoIP に対するユーザーの無効化](lync-server-2013-disable-a-user-for-enterprise-voice.md)  

#### その他のリソース

[Lync Server 2013 管理シェル](lync-server-2013-lync-server-management-shell.md)

