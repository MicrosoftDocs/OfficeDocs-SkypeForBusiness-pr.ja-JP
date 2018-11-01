---
title: 新しいプールへの応答グループの移動
TOCTitle: 新しいプールへの応答グループの移動
ms:assetid: da0db765-41e5-430b-b5a7-5418ec5ff2a7
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205298(v=OCS.15)
ms:contentKeyID: 48273734
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 新しいプールへの応答グループの移動

 

_**トピックの最終更新日:** 2012-11-01_

Lync Server 2013 では、完全修飾ドメイン名 (FQDN) が異なっている場合でも、応答グループをあるプールから別のプールに移動させるための新しいコマンドレット サポートが導入されています。

応答グループをあるフロント エンド プールから異なる FQDN を持つ別のフロント エンド プールに移動するには、次の手順に従います。

> [!NOTE]
> 共存環境では Lync Server 2013フロント エンド プール間でのみ応答グループを移動できます。


## 応答グループを異なる FQDN を持つプールに移動するには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  移動元のプール内の応答グループをエクスポートします。コマンドラインで、次のように入力します。
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source FQDN>" -FileName "<export file name>"
    
    例:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -FileName "C:\RgsExportSource.zip"
    
    エクスポート中に移動元のプールから応答グループを削除するには、–RemoveExportedConfiguration パラメーターを含めます。たとえば、次のように入力します。
    
        Export-CsRgsConfiguration -Source ApplicationServer:source.contoso.com -FileName "C:\RgsExportSource.zip" -RemoveExportedConfiguration

3.  応答グループを移動先のプールにインポートし、移動先のプールを新しい所有者として割り当てます。コマンドラインで、次のように入力します。
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<destination pool>" -FileName "<export file name>" -OverwriteOwner
    
    応答グループのアプリケーションレベルの設定をソース プールから転送先プールにコピーする場合は、–ReplaceExistingSettings パラメーターを含めます。プールごとにアプリケーションレベルの設定のセットを 1 つだけ定義できます。アプリケーションレベルの設定をソース プールから転送先プールにコピーする場合は、転送先プールの設定がソース プールの設定に置き換えられます。アプリケーションレベルの設定をソース プールからコピーしない場合は、転送先プールの既存の設定が、インポートされた応答グループに適用されます。
    
    例:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:destination.contoso.com" -FileName "C:\RgsExportSource.zip" -OverwriteOwner -ReplaceExistingSettings
    
    > [!NOTE]
    > アプリケーションレベルの設定には、既定の保留音の構成、既定の保留音の音声ファイル、エージェント リングバックの猶予期間、および通話コンテキストの構成が含まれます。これらの構成を表示するには、<strong>Get-CsRgsConfiguration</strong> コマンドレットを実行します。このコマンドレットの詳細については、「<a href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">Get-CsRgsConfiguration</a>」を参照してください。


4.  次の操作を実行してインポートされた応答グループの構成を表示することにより、インポートが成功したことを確認します。
    
      - すべてのワークフローがインポートされたことを確認します。コマンドラインで、次のように入力します。
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - すべてのキューがインポートされたことを確認します。コマンドラインで、次のように入力します。
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - すべてのエージェント グループがインポートされたことを確認します。コマンドラインで、次のように入力します。
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - すべての営業時間がインポートされたことを確認します。コマンドラインで、次のように入力します。
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<destination pool FQDN>" 
    
      - すべての休日セットがインポートされたことを確認します。コマンドラインで、次のように入力します。
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<destination pool FQDN>" 

5.  応答グループの 1 つに電話をかけ、通話が正しく処理されることを確認して、インポートが正常に完了したことを確認します。

6.  公式エージェント グループのメンバーであるエージェントに、移動先のプール内のエージェント グループにサインインするように要求します。

7.  前の手順で移動元のプールから応答グループを削除しなかった場合は、移動元のプールから応答グループを削除します。コマンドラインで、次のように入力します。
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source pool FQDN> -RemoveExportedConfiguration -FileName "<temporary export file name>"
    
    例:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -RemoveExportedConfiguration -FileName "C:\TempRGsConfiguration.zip"

