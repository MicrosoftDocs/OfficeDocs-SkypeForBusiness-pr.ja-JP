---
title: 'Lync Server 2013: 応答グループの障害復旧手順'
TOCTitle: 応答グループの障害復旧手順
ms:assetid: b49577b7-0ca3-4f20-b614-f3a2a0046b58
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205186(v=OCS.15)
ms:contentKeyID: 48273341
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の応答グループの障害復旧手順

 

_**トピックの最終更新日:** 2016-12-08_

障害復旧のフェールオーバー フェーズでは、応答グループは複数のプールに存在します。プライマリ プール (これは利用できません) と、バックアップ プールに存在します。両方のプールにある応答グループの名前および所有者 (プライマリ プール) は同じですが、親はそれぞれ異なります。この間、 応答グループのコマンドの動作は少し異なります。必ず以下の手順で指定したとおりのパラメーターを使用してください。フェールオーバー フェーズ中のコマンドレットの動作の詳細については、NextHop のブログ記事「Lync Server 2013: 障害復旧中の応答グループの復元」( [http://go.microsoft.com/fwlink/?linkid=263957\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=263957%26clcid=0x411)) を参照してください。このブログ記事は、 Lync Server 2013 の製品版にも適用されます。

次の手順のステップを使用して、 Lync Server 応答グループ サービスの障害復旧を準備および実行します。

## 応答グループをフェールオーバーおよびフェールバックするには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  定期的にバックアップを実行します。コマンドラインで、次のように入力します。
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>"
    
    次に例を示します。
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimary.zip"

3.  停止中、バックアップ プールにフェールオーバーした後で、応答グループをバックアップ プールにインポートします。コマンドラインで、次のように入力します。
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<backup pool FQDN>" -FileName "<backup path and file name>"
    
    バックアップ プールのアプリケーションレベルの設定をプライマリ プールの設定に置き換える場合は、?ReplaceExistingSettings パラメーターを含めます。次に例を示します。
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:backup.contoso.com" -FileName "C:\RgsExportPrimary.zip" -ReplaceExistingSettings
    

    > [!TIP]
    > バックアップ プールの設定を置き換えず、プライマリ プールを復元できない場合、プライマリ プールの設定は失われます。詳細については、「<A href="lync-server-2013-planning-for-response-group-disaster-recovery.md">Lync Server 2013 での応答グループの障害復旧の計画</A>」を参照してください。



4.  インポートされた応答グループを表示して、インポートが成功したことを確認します。インポートされた応答グループはプライマリ プールに所有されたままです。次の手順を実行してください。
    
      - プライマリ プールに所有されているバックアップ プールのすべてのワークフローを表示し、プライマリ プールのワークフローがすべて含まれていることを確認します。コマンドラインで、次のように入力します。
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        次に例を示します。
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com"
    
      - プライマリ プールに所有されているバックアップ プールのすべてのキューを表示し、プライマリ プールのキューがすべて含まれていることを確認します。コマンドラインで、次のように入力します。
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        次に例を示します。
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - プライマリ プールに所有されているバックアップ プールのすべてのエージェント グループを表示し、プライマリ プールのエージェント グループがすべて含まれていることを確認します。コマンドラインで、次のように入力します。
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        次に例を示します。
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - プライマリ プールに所有されているバックアップ プールのすべての営業時間を表示し、プライマリ プールの営業時間がすべて含まれていることを確認します。コマンドラインで、次のように入力します。
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        次に例を示します。
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - プライマリ プールに所有されているバックアップ プールのすべての休日セットを表示し、プライマリ プールの休日セットがすべて含まれていることを確認します。コマンドラインで、次のように入力します。
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        次に例を示します。
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
    また、?Owner パラメーターの代わりに –ShowAll パラメーターを使用して、バックアップ プールのすべての応答グループを表示することもできます。これには、プライマリ プールに所有されているものと、バックアップ プールに所有されているものが含まれます。次に例を示します。
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -ShowAll
    

    > [!IMPORTANT]
    > -ShowAll パラメーターと –Owner パラメーターはどちらかを使用する必要があります。これらのパラメーターのいずれも使用しない場合、バックアップ プールにインポートした応答グループはコマンドレットによって返される結果に表示されません。



5.  インポートが正常に完了したことを確認します。そのためには、インポートされた応答グループに電話をかけて通話が正常に処理されることを確認します。

6.  公式エージェント グループのメンバーであるエージェントに、バックアップ プールのエージェント グループにサインインするよう要求します。

7.  インポートした応答グループを通常どおりに管理および変更します。
    

    > [!IMPORTANT]
    > 応答グループは、バックアップ プールにある間、 Lync Server 管理シェルを使用して管理する必要があります。バックアップ プールにインポートした応答グループを Lync Server コントロール パネルを使用して管理することはできません。



8.  プライマリ プールが復元されてフェールバックが完了したら、バックアップ プールにインポートされたプライマリ プールの応答グループをエクスポートします。コマンドラインで、次のように入力します。
    
        Export-CsRgsConfiguration -Source ApplicationServer:<backup pool FQDN> -Owner ApplicationServer:<primary pool FQDN> -FileName "<backup path and file name>"

9.  応答グループをプライマリ プールに再びインポートします。コマンドラインで、次のように入力します。
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>"
    
    次に例を示します。
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:primary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip"
    
    > [!NOTE]
    > 復旧中にプールを構築し直す場合は、完全修飾ドメイン名 (FQDN) を同じにするか別にするかにかかわらず、-OverwriteOwner パラメーターを使用する必要があります。大まかには、プライマリ プールに応答グループを再びインポートするときは常に -OverwriteOwner パラメーターを使用することができます。
    
    (同じまたは異なる完全修飾ドメイン名 (FQDN) の) 新しいプールを展開してプライマリ プールを置き換え、新しいプールにバックアップ プールからのアプリケーションレベルの設定を使用する場合は、?ReplaceExistingSettings パラメーターを含めます。コマンドラインで、次のように入力します。
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<new primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>" -ReplaceExistingSettings
    
    次に例を示します。
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:newprimary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip" -ReplaceExistingSettings
    

    > [!IMPORTANT]
    > 新しいプールのアプリケーションレベルの設定と既定の保留音のオーディオ ファイルをバックアップ プールからの設定に置き換えない場合、新しいプールは既定のアプリケーションレベルの設定を使用します。



10. 再びインポートされた応答グループ構成を表示して、プライマリ プールへのインポートが成功したことを確認します。次の手順を実行してください。
    
      - プライマリ プールのすべてのワークフローを表示して、インポートされたワークフローがすべて含まれていることを確認します。コマンドラインで、次のように入力します。
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        次に例を示します。
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer: primary.contoso.com" -ShowAll
    
      - プライマリ プールのすべてのキューを表示して、インポートされたキューがすべて含まれていることを確認します。コマンドラインで、次のように入力します。
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        次に例を示します。
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - プライマリ プールのすべてのエージェント グループを表示して、インポートされたエージェント グループがすべて含まれていることを確認します。コマンドラインで、次のように入力します。
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer: <primary pool FQDN>" -ShowAll
        
        次に例を示します。
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - プライマリ プールのすべての営業時間を表示して、インポートされた営業時間がすべて含まれていることを確認します。コマンドラインで、次のように入力します。
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        次に例を示します。
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - プライマリ プールのすべての休日セットを表示して、インポートされた休日セットがすべて含まれていることを確認します。コマンドラインで、次のように入力します。
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        次に例を示します。
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll

11. インポートが正常に完了したことを確認します。そのためには、インポートされた応答グループに電話をかけて通話が正常に処理されることを確認します。

12. オプションで、プライマリ プールが所有する応答グループをバックアップ プールから削除します。コマンドラインで、次のように入力します。
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>" -RemoveExportedConfiguration
    
    次に例を示します。
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration
    
    > [!NOTE]
    > このステップでは、エクスポートされた構成で新しいファイルを作成し、そのファイルをバックアップ プールから削除します。

