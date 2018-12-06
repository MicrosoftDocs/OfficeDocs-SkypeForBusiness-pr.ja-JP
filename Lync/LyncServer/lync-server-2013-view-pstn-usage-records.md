---
title: 'Lync Server 2013: PSTN 使用法レコードの表示'
TOCTitle: PSTN 使用法レコードの表示
ms:assetid: 65025c78-c263-472c-9ff9-e170588f10b5
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398458(v=OCS.15)
ms:contentKeyID: 48272274
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での PSTN 使用法レコードの表示

 

_**トピックの最終更新日:** 2013-02-22_

公衆交換電話網 (PSTN) 使用法レコードは、組織内のさまざまなユーザーまたはグループが利用できる通話のクラス (内部、市内、長距離など) を指定します。詳細については、「計画」のドキュメントの「[Lync Server 2013 の PSTN 使用法レコード](lync-server-2013-pstn-usage-records.md)」を参照してください。

## Lync Server コントロール パネルを使用して PSTN 使用法レコードを表示するには

1.  RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。詳細については、「[Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**音声ルーティング**\] をクリックし、\[**PSTN 使用法**\] をクリックします。

4.  \[**PSTN 使用法**\] ページで、表示する PSTN 使用法レコードを選択状態にし、\[**編集**\] をクリックして、\[**詳細の表示**\] をクリックします。
    
    > [!NOTE]
    > 選択した PSTN 使用法レコードの読み取り専用ページに、関連付けられたルートと関連付けられた音声ポリシーが表示されます。


## Windows PowerShell コマンドレットを使用した PSTN 使用法の表示

PSTN 使用法は、Windows PowerShellと **Get-CsPstnUsage** コマンドレットを使用して表示することもできます。このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShellのリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## PSTN 使用法情報を Windows PowerShell コマンドレットを使用して表示するには

  - すべての PSTN 使用法に関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、Enter キーを押します。
    
        Get-CsPstnUsage
    
    このコマンドは、次のような情報を返します。
    
        Identity : Global
        Usage    : {Internal, Local, Long Distance}

詳細については、「[Get-CsPstnUsage](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsPstnUsage)」を参照してください。

## 関連項目

#### タスク

[Lync Server 2013 での音声ポリシーの作成と PSTN 使用法レコードの構成](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[Lync Server 2013 での音声ポリシーの変更と PSTN 使用法レコードの構成](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)

