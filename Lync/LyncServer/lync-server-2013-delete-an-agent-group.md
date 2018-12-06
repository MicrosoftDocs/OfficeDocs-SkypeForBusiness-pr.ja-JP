---
title: エージェント グループの削除
TOCTitle: エージェント グループの削除
ms:assetid: df385fd1-62f4-42b7-a349-4eb38dea50c8
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg182597(v=OCS.15)
ms:contentKeyID: 48273780
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# エージェント グループの削除

 

_**トピックの最終更新日:** 2012-11-01_

次のいずれかの手順を使用して、エージェント グループを削除します。

## Lync Server コントロール パネルを使用してエージェント グループを削除するには

1.  RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで、\[**応答グループ**\] をクリックし、\[**グループ**\] をクリックします。

4.  \[**応答グループ**\] ページで、検索フィールドに削除するエージェント グループの名前または名前の一部を入力します。

5.  結果の一覧で、\[**編集**\] をクリックして、\[**削除**\] をクリックします。

6.  \[**OK**\] をクリックします。

## コマンドレットを使用してエージェント グループを削除するには

1.  RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  コマンド ラインで、次のコマンドを実行します。
    
        Get-CsRgsAgentGroup -Identity <Application Server service> -Name "<name of agent group>" | Remove-CsRgsAgentGroup
    
    例:
    
        Get-CsRgsAgentGroup -Identity service:ApplicationServer:redmond.contoso.com -Name "Human Resources" | Remove-CsRgsAgentGroup

## 関連項目

#### タスク

[Lync Server 2013 エージェント グループの作成または変更](lync-server-2013-create-or-modify-an-agent-group.md)  

#### その他のリソース

[Remove-CsRgsAgentGroup](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsRgsAgentGroup)  
[Get-CsRgsAgentGroup](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsRgsAgentGroup)

