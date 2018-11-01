---
title: QoE (Quality of Experience) 構成設定の削除
TOCTitle: QoE (Quality of Experience) 構成設定の削除
ms:assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg182613(v=OCS.15)
ms:contentKeyID: 48274202
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# QoE (Quality of Experience) 構成設定の削除

 

_**トピックの最終更新日:** 2013-02-23_

QoE (Quality of Experience) 指標は、ネットワーク パケットの損失数、バックグラウンド ノイズ、"ジッター" (パケット遅延のばらつき) の量など、組織内で行われる音声通話およびビデオ通話の品質を追跡します。これらの指標は、他のデータ (詳細な通話の記録など) とは別にデータベースに格納されます。このため、QoE は他のデータ記録と関係なく有効および無効にすることができます。

Microsoft Lync Server 2013 をインストールすると、QoE 構成設定の単一のグローバル コレクションが作成されます。また管理者には、個別のサイトに適用できるカスタム設定コレクションを作成するオプションがあります。設計上、サイト スコープで構成した設定は、グローバル スコープで構成した設定より優先されます。サイト スコープの設定を削除すると、サイトの QoE はグローバル設定を使って管理されます。

なお、グローバル設置は「削除」することができます。ただし、グローバル設定は実際に削除されるわけではありません。代わりに、そのコレクションのすべてのプロパティが既定値にリセットされます。たとえば、QoE 構成設定のコレクションでは削除が既定で有効になっています。仮にグローバル コレクションを変更して削除を無効にしたとします。後にグローバル設定を削除すると、すべてのプロパティは既定の値にリセットされます。この場合、削除が再び有効になることを意味します。

QoE 構成設定を削除するには、Lync Server コントロール パネルを使うか、[Remove-CsQoEConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsQoEConfiguration) コマンドレットを使用できます。

## Lync Server コントロール パネルを使って QoE 構成設定を削除するには

1.  RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。詳細については、「[Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**監視とアーカイブ**\] をクリックし、\[**QoE データ**\] をクリックします。

4.  \[**QoE データ**\] ページで対象のポリシーをクリックし、\[**編集**\] をクリックして、\[**削除**\] をクリックします。

5.  \[**OK**\] をクリックします。

## Lync Server 管理シェル コマンドレットを使って QoE 構成設定を削除するには

QoE 構成設定は、Lync Server 管理シェルおよび **Remove-CsQoEConfiguration** コマンドレットを使用して削除することもできます。このコマンドレットは Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## 指定した QoE 構成設定のコレクションを削除するには

  - このコマンドは、Redmond サイトに適用された QoE 構成設定を削除します。
    
        Remove-CsQoEConfiguration -Identity "site:Redmond"

## サイト スコープに適用されたすべての QoE 構成設定を削除するには

  - このコマンドは、サイト スコープに適用されたすべての QoE 構成設定を削除します。
    
        Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration

## QoE 監視が無効にされたすべての QoE 構成設定を削除するには

  - このコマンドは、QoE 監視が無効にされたすべての QoE 構成設定を削除します。
    
        Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration

詳細については、「[Remove-CsQoEConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsQoEConfiguration)」を参照してください。

