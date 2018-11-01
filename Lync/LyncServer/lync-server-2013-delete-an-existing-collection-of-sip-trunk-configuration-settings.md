---
title: SIP トランク構成設定の既存コレクションの削除
TOCTitle: SIP トランク構成設定の既存コレクションの削除
ms:assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688024(v=OCS.15)
ms:contentKeyID: 49886918
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# SIP トランク構成設定の既存コレクションの削除

 

_**トピックの最終更新日:** 2013-02-22_

SIP トランク構成設定では、仲介サーバーと公衆交換電話網 (PSTN) ゲートウェイ、IP 構内交換機 (PBX)、またはサービス プロバイダーのセッション境界コントローラー (SBC) との間の関係と機能を定義します。これらの設定では以下を指定します。

  - トランクでメディアのバイパスを有効にする必要があるかどうか

  - リアルタイム転送制御プロトコル (RTCP) パケットを送信する条件

  - 各トランクでセキュア リアルタイム プロトコル (SRTP) 暗号化が必要かどうか

Microsoft Lync Server 2013 をインストールすると、SIP トランク構成設定のグローバル コレクションが作成されます。この設定のグローバル コレクションは削除できません。ただし、グローバル コレクションのプロパティは、Lync Server コントロール パネルまたは [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) コマンドレットを使用して既定値に "リセット" できます。たとえば、Enable3pccRefer プロパティを True に設定した場合、グローバル コレクションをリセットすると、Enable3pccRefer プロパティは既定値である False に戻ります。

管理者がサイト スコープまたはサービス スコープでカスタム トランク構成設定を作成することもできます (個別の PSTN ゲートウェイの場合)。これらのカスタム設定は削除できます。カスタム設定を削除するときは、次の点に注意してください。

  - サービス スコープの設定を削除すると、その設定で管理されていた SIP トランクは、サイトに適用されている設定で管理されます (その設定が存在する場合)。サイトの設定が存在しない場合、これらのトランクは、トランク構成設定のグローバル コレクションによって管理されます。

  - サイト スコープの設定を削除すると、その設定で管理されていたすべての SIP トランクが、トランク構成設定のグローバル コレクションによって管理されます。

## Lync Server コントロール パネルを使用してトランク構成設定を削除する

1.  Lync Server コントロール パネルで、\[**音声のルーティング**\]、\[**トランク構成**\] の順にクリックします。

2.  \[**トランク構成**\] タブで、削除する SIP トランク構成設定のコレクションを選択し、\[**編集**\]、\[**削除**\] の順にクリックします。同じ操作で複数のコレクションを削除するには、削除する最初のコレクションをクリックし、Ctrl キーを押しながら、削除するその他のコレクションをクリックします。

3.  コレクションの \[**状態**\] プロパティが \[**コミットされていません**\] に更新されます。変更をコミットし、コレクションを削除するには、\[**コミット**\]、\[**すべてコミット**\] の順にクリックします。

4.  \[**コミットされていない音声構成設定**\] ダイアログ ボックスで、\[**OK**\] をクリックします。

5.  \[**Microsoft Lync Server 2013 Control Panel**\] ダイアログ ボックスで、\[**OK**\] をクリックします。

6.  後でコレクションを削除しないことにした場合は、\[**コミット**\]、\[**コミットされていないすべての変更を取り消し**\] の順にクリックします。\[**Microsoft Lync Server 2013 Control Panel**\] ダイアログ ボックスが表示されたら、\[**OK**\] をクリックします。

## Lync Server PowerShell コマンドレットを使用してトランク構成設定を削除する

Windows PowerShell および Remove-CsTrunkConfiguration コマンドレットを使用して、トランク構成設定を削除することもできます。このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## 指定した設定のコレクションを削除する

  - 次のコマンドを実行すると、Redmond サイトに適用されていたトランク構成設定が削除されます。
    
        Remove-CsTrunkConfiguration -Identity site:Redmond

## サイト スコープに適用されているすべてのコレクションを削除する

  - 次のコマンドを実行すると、サービス スコープに適用されているすべてのトランク構成設定が削除されます。
    
        Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration

## メディア バイパスが有効になっているすべてのコレクションを削除する

  - 次のコマンドを実行すると、メディア バイパスが有効になっているすべてのトランク構成設定が削除されます。
    
        Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration

詳細については、[Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) コマンドレットのヘルプ トピックを参照してください。

