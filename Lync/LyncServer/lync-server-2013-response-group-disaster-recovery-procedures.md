---
title: 'Lync Server 2013: 応答グループの障害復旧手順'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response group disaster recovery procedures
ms:assetid: b49577b7-0ca3-4f20-b614-f3a2a0046b58
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205186(v=OCS.15)
ms:contentKeyID: 48185171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5325f84ff5bf5a0f8d9d1a856110e0ac18b37d93
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723627"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-disaster-recovery-procedures-in-lync-server-2013"></a>Lync Server 2013 の応答グループの障害復旧手順

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-01_

障害回復のフェールオーバーフェーズでは、応答グループは、プライマリプール (使用できない) とバックアッププールの複数のプールに存在します。 両方のプールの応答グループの名前が同じであり、所有者が同じ所有者 (プライマリプール) であるが、それぞれの親が異なっている。 このとき、応答グループコマンドレットの動作は少し異なります。 次の手順で示されているように、必ずパラメーターを使用してください。 フェールオーバーフェーズでのコマンドレットの動作の詳細については、「NextHop ブログ」「Lync Server 2013: ディザスターリカバリー中[http://go.microsoft.com/fwlink/p/?LinkId=263957](http://go.microsoft.com/fwlink/p/?linkid=263957)の応答グループの回復」を参照してください。 このブログ記事は、リリース版の Lync Server 2013 にも適用されます。

Lync Server 応答グループサービスの障害回復を準備して実行するには、次の手順に従います。

<div>

## <a name="to-fail-over-and-fail-back-response-group"></a>フェールオーバーと応答の返信グループをフェイルバックするには

1.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

2.  定期的にバックアップを実行します。 コマンドラインで、次のように入力します。
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>"
    
    例:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimary.zip"

3.  停止中は、バックアッププールにフェールオーバーした後、バックアッププールに応答グループをインポートします。 コマンド ラインで次を入力します。
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<backup pool FQDN>" -FileName "<backup path and file name>"
    
    バックアッププール内のアプリケーションレベルの設定をプライマリプールの設定で置き換える場合は、– ReplaceExistingSettings パラメーターを指定します。 次に例を示します。
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:backup.contoso.com" -FileName "C:\RgsExportPrimary.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!WARNING]  
    > バックアッププールの設定を変更せずに、プライマリプールを復元できない場合、プライマリプールの設定は失われます。 詳細については、「 <A href="lync-server-2013-planning-for-response-group-disaster-recovery.md">Lync Server 2013 での応答グループの障害回復の計画</A>」を参照してください。

    
    </div>

4.  インポートされた応答グループを表示して、インポートが正常に完了したことを確認します。 インポートされた応答グループは、依然としてプライマリプールによって所有されます。 次の手順を実行します。
    
      - プライマリプールによって所有されているバックアッププール内のすべてのワークフローを表示し、プライマリプールワークフローがすべて含まれていることを確認します。 コマンドラインで、次のように入力します。
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        例:
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com"
    
      - プライマリプールによって所有されているバックアッププール内のすべてのキューを表示し、すべてのプライマリプールキューが含まれていることを確認します。 コマンドラインで、次のように入力します。
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        例:
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - プライマリプールによって所有されているバックアッププール内のすべてのエージェントグループを表示し、プライマリプールエージェントグループがすべて含まれていることを確認します。 コマンドラインで、次のように入力します。
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        例:
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - プライマリプールによって所有されているバックアッププール内のビジネス時間をすべて表示し、プライマリプールのすべての業務時間が含まれていることを確認します。 コマンドラインで、次のように入力します。
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        例:
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - プライマリプールによって所有されているバックアッププール内のすべての休日セットを表示し、すべてのプライマリプールの休日セットが含まれていることを確認します。 コマンドラインで、次のように入力します。
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        例:
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
    または、[-Owner] パラメーターの代わりに– ShowAll パラメーターを使用して、プライマリプールに所有されているものとバックアッププールに所有されているものを含め、すべての応答グループをバックアッププールに表示することができます。 次に例を示します。
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -ShowAll
    
    <div>
    

    > [!IMPORTANT]  
    > – ShowAll パラメーターまたは– Owner パラメーターのいずれかを使用する必要があります。 これらのパラメーターのどちらも使用しない場合、バックアッププールにインポートした応答グループは、コマンドレットによって返される結果に一覧表示されません。

    
    </div>

5.  インポートされた応答グループに通話を発信し、通話が正しく処理されていることを確認して、インポートが成功したことを確認します。

6.  バックアッププールのエージェントグループにサインインするために、正式なエージェントグループのメンバーであるエージェントを要求します。

7.  インポートした応答グループを通常どおりに管理および変更します。
    
    <div>
    

    > [!IMPORTANT]  
    > 応答グループはバックアッププールに含まれていますが、Lync Server 管理シェルを使用してそれらを管理する必要があります。 Lync Server コントロールパネルを使用して、バックアッププールにインポートした応答グループを管理することはできません。

    
    </div>

8.  プライマリプールが復元され、フェールバックが完了したら、バックアッププールにインポートされたプライマリプール応答グループをエクスポートします。 コマンド ラインで次を入力します。
    
        Export-CsRgsConfiguration -Source ApplicationServer:<backup pool FQDN> -Owner ApplicationServer:<primary pool FQDN> -FileName "<backup path and file name>"

9.  応答グループをプライマリプールにインポートします。 コマンドラインで、次のように入力します。
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>"
    
    例:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:primary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip"
    
    <div>
    

    > [!NOTE]  
    > 回復中にプールを再構築する場合、同一または別の完全修飾ドメイン名 (FQDN) を使用している場合は、– OverwriteOwner パラメーターを使う必要があります。 原則として、応答グループをプライマリプールにインポートするときに、常に– OverwriteOwner パラメーターを使うことができます。

    
    </div>
    
    新しいプール (同じまたは別の FQDN を含む) を展開して、プライマリプールの代わりにバックアッププールのアプリケーションレベルの設定を使用する場合は、– ReplaceExistingSettings パラメーターを含めます。 コマンドラインで、次のように入力します。
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<new primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>" -ReplaceExistingSettings
    
    例:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:newprimary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!IMPORTANT]  
    > 新しいプールのアプリケーションレベルの設定と既定の音楽の保留オーディオファイルをバックアッププールの設定で置き換える必要がない場合は、新しいプールで既定のアプリケーションレベルの設定が使用されます。

    
    </div>

10. インポートされた応答グループの構成を表示して、プライマリプールへのインポートが正常に完了したことを確認します。 次の手順を実行します。
    
      - プライマリプール内のすべてのワークフローを表示し、インポートされたすべてのワークフローが含まれていることを確認します。 コマンドラインで、次のように入力します。
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        例:
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer: primary.contoso.com" -ShowAll
    
      - プライマリプール内のすべてのキューを表示し、インポートされたすべてのキューが含まれていることを確認します。 コマンドラインで、次のように入力します。
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        例:
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - プライマリプール内のすべてのエージェントグループを表示し、インポートされたすべてのエージェントグループが含まれていることを確認します。 コマンドラインで、次のように入力します。
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer: <primary pool FQDN>" -ShowAll
        
        例:
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - プライマリプールのビジネス時間をすべて表示し、インポートされたすべての勤務時間が含まれていることを確認します。 コマンドラインで、次のように入力します。
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        例:
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - プライマリプールのすべての休日セットを表示し、インポートされたすべての祝日セットが含まれていることを確認します。 コマンドラインで、次のように入力します。
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        例:
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll

11. インポートされた応答グループに通話を発信し、通話が正しく処理されていることを確認して、インポートが成功したことを確認します。

12. 必要に応じて、プライマリプールによって所有されている応答グループをバックアッププールから削除します。 コマンドラインで、次のように入力します。
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>" -RemoveExportedConfiguration
    
    例:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration
    
    <div>
    

    > [!NOTE]  
    > この手順では、エクスポートされた構成で新しいファイルを作成し、それをバックアッププールから削除します。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

