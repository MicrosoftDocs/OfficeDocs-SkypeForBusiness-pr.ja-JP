---
title: ワークフローの削除
TOCTitle: ワークフローの削除
ms:assetid: 0469a6b8-ce1e-459b-bc3d-4c8adf2d97d5
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg520944(v=OCS.15)
ms:contentKeyID: 48271122
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ワークフローの削除

 

_**トピックの最終更新日:** 2012-11-01_

ワークフローを削除するには、以下に示す手順の 1 つを実行します。

## Lync Server コントロール パネルを使用してワークフローを削除するには

1.  RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで、\[**応答グループ**\] をクリックし、\[**ワークフロー**\] をクリックします。

4.  \[**ワークフロー**\] ページで、\[**ワークフローの作成または編集**\] をクリックします。

5.  \[**サービスの選択**\] 検索フィールドに、削除するワークフローをホストする **ApplicationServer** サービスの名前、または名前の一部を入力します。

6.  サービスの一覧で、対象のサービスをクリックして、\[**OK**\] をクリックします。
    
    > [!NOTE]
    > 応答グループ構成ツール Web ページが開きます。 また、Web ブラウザーから直接 <strong>https://<em>&lt;webPoolFqdn&gt;</em>/RgsConfig</strong> に接続して、応答グループ構成ツール Web ページを開くこともできます。


7.  \[**既存ワークフローの管理**\] で、削除するワークフローを見つけて、\[**アクション**\] の \[**削除**\] をクリックします。

8.  \[**はい**\] をクリックします。

## コマンドレットを使用してワークフローを削除するには

1.  RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  コマンド ラインで、次のコマンドを実行します。
    
        Get-CsRgsWorkflow -Identity <Application Server service> -Name "<name of workflow>" | Remove-CsRgsWorkflow
    
    例:
    
        Get-CsRgsWorkflow -Identity service:ApplicationServer:redmond.contoso.com -Name "Help Desk" | Remove-CsRgsWorkflow

