---
title: 'Lync Server 2013: 応答グループの障害復旧の計画'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for response group disaster recovery
ms:assetid: 14e0f5dc-77cd-42cd-a9c9-4d0da38fb1cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204699(v=OCS.15)
ms:contentKeyID: 48183482
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db3a196a258198fe0bc65b533841544decd96aa2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41750487"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-response-group-disaster-recovery-in-lync-server-2013"></a>Lync Server 2013 での応答グループの障害復旧の計画

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-01_

このセクションでは、障害回復のための応答グループを準備する方法について説明し、障害回復プロセスの概要を示します。

<div>

## <a name="preparing-for-response-group-disaster-recovery"></a>回答グループの障害回復の準備

災害回復の手順を準備し、実行する場合は、次の点にご注意ください。

<div>


> [!NOTE]  
> 共存環境では、このドキュメントで説明されているディザスタリカバリの手順については、Lync Server 2013 応答グループのみがサポートされています。



</div>

  - キャパシティ計画を行うときの障害回復計画を立てます。 障害回復キャパシティの場合、ペア化されたプール内の各プールは、両方のプールのすべての応答グループのワークロードを処理できる必要があります。 回答グループのキャパシティ計画の詳細については、「 [Lync Server 2013 の応答グループのキャパシティ計画](lync-server-2013-capacity-planning-for-response-group.md)」を参照してください。

  - このドキュメントで説明されているエクスポート手順を使用して、応答グループアプリケーションを展開したすべての [返信グループ] 構成の定期的なバックアップコピーを作成します。 詳細については、「 [Lync Server 2013 での応答グループの障害回復の手順](lync-server-2013-response-group-disaster-recovery-procedures.md)」を参照してください。 バックアップコピーを安全な場所に保管します。

  - 応答グループアプリケーションに使用した元のすべてのオーディオファイルのバックアップコピーを個別に保存しておきます。レコーディングや音楽の保留ファイルも含めます。 バックアップファイルを安全な場所に保管します。

  - Lync Server 2013 の障害回復の場合、すべての応答グループの設定で、展開時に一意の名前を指定する必要があります。 この要件は、ワークフロー、キュー、エージェントグループ、休日セット、および営業時間に適用されます。 プライマリとバックアップのプールがアクティブで、フェールオーバー手順を開始する前に、この要件が満たされていることを確認する必要があります。 応答グループデータをバックアッププールにインポートするときに名前の競合が発生した場合、インポートは失敗します。 インポートとフェールオーバーの手順を完了するには、バックアッププールの応答グループオブジェクトの名前を変更するか、または ResolveNameConflicts パラメーターを指定して**import-CsRgsConfiguration**コマンドレットを使用して、応答グループオブジェクトに一意の識別番号を追加することにより、名前の競合を解決する必要があります。

  - 一般的に、毎日のバックアップを実行することをお勧めしますが、変更の量が多い場合は、より頻繁にバックアップをスケジュールすることをお勧めします。 障害が発生した場合に失われる可能性のある情報の量は、バックアップの頻度と、変更の頻度と量によって異なります。

  - ディザスタまたはフェイルオーバー操作が発生する前に、バックアッププールに応答グループをインポートすることができます。 返信グループの事前インポートは、通話がバックアッププールにルーティングされるとすぐに、Lync Server 応答グループサービスをバックアッププールで復元できるため、ダウンタイムが短縮されます。
    
    <div>
    

    > [!NOTE]  
    > フェールオーバーが完了するまで、応答グループのアプリケーションは、非アクティブなプールに所属しているエージェントに到達できません。 このとき、応答グループアプリケーションは、それらのエージェントが利用できない場合と同様に呼び出しを処理します。

    
    </div>

</div>

<div>

## <a name="response-group-disaster-recovery-process"></a>応答グループの障害回復プロセス

障害が発生した場合は、次のいずれかの回復方法を使用して応答グループを回復できます。

  - バックアッププールにフェイルオーバーし、元のプールにフェイルバックします。

  - バックアッププールにフェールオーバーする場合は、別の完全修飾ドメイン名 (FQDN) を使用して新しいプールを作成し、新しいプールに応答グループをインポートします。

障害回復のフェールオーバーフェーズでは、応答グループは、プライマリプール (使用できない) とバックアッププールの複数のプールに存在します。 両方のプールの応答グループの名前が同じであり、所有者が同じ所有者 (プライマリプール) であるが、それぞれの親が異なっている。

別の FQDN で新しいプールを作成して回復する場合は、新しいプールをインポートするときに、応答グループの所有者として割り当てる必要があります。 応答グループの所有権は、**インポート-CsRgsConfiguration**コマンドレットを使用して– OverwriteOwner パラメーターを使って明示的に所有権を再割り当てする場合を除き、元のプールのままになります。

<div>


> [!NOTE]  
> また、回復中にプールを再構築した場合 (つまり、応答グループのデータベースが空である場合)、同じ FQDN を使用しているかどうかにかかわらず、– OverwriteOwner パラメーターを使用する必要があります。 プールをリビルドしていない場合は、– OverwriteOwner パラメーターを使う必要はありませんが、応答グループをプライマリプールにインポートするたびに、このパラメーターを使うことができます。



</div>

プールごとに1つのアプリケーションレベル応答グループ構成設定のみを定義できます。 これらの設定には、既定の音楽保留の構成、既定の音楽保留中のオーディオファイル、エージェント ringback の猶予期間、通話コンテキストの構成が含まれます。 これらの構成設定を表示するには、 **Get-CsRgsConfiguration**コマンドレットを実行します。 **Get-csrgsconfiguration**コマンドレットの詳細については、「 [Get-csrgsconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration)」を参照してください。

これらのアプリケーションレベルの設定は、– ReplaceExistingSettings パラメーターを指定して**Import-CsRgsConfiguration**コマンドレットを使用して、1つのプールから別のプールに転送できますが、これにより、移動先のプールの設定が上書きされます。

<div>


> [!IMPORTANT]  
> 他のプールへの設定の転送に関するこの制約は、アプリケーションレベルの設定、および既定の音楽/ホールドオーディオファイルに対してのみ適用されます。 エージェントグループ、キュー、ワークフロー、業務時間、休日セットには適用されません。



</div>

障害発生時にバックアッププールのアプリケーションレベルの設定を変更せずに、プライマリプールを復元できない場合、プライマリプールのアプリケーションレベルの設定は失われます。 新しいプールを作成して回復中にプライマリプールを置き換える必要がある場合は、同じ FQDN または別の FQDN を使用して、元のアプリケーションレベルの設定を復元することはできません。 この場合は、これらの設定を使用して新しいプールを構成し、音楽の保留中のオーディオファイルを含める必要があります。

**インポート-CsRgsConfiguration**コマンドレットを使用して、障害発生時にプライマリプールからバックアッププールにアプリケーションレベルの設定を移行する場合は、プライマリプールからバックアッププールに転送した場合と同じ方法で、バックアッププールから新しいプールに設定を転送することができます。

次の表では、応答グループの回復に関連する手順の概要を示します。

これらの手順の実行について詳しくは、「 [Lync Server 2013 の応答グループの障害回復手順](lync-server-2013-response-group-disaster-recovery-procedures.md)」をご覧ください。

### <a name="response-group-disaster-recovery-steps"></a>応答グループの障害回復手順

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>段階</th>
<th>ステップ</th>
<th>必要なグループおよび役割</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>停止前</p></td>
<td><p>ルーチンベースでは、 <strong>Export-CsRgsConfiguration</strong>コマンドレットを実行して、応答グループアプリケーションが展開されているすべてのフロントエンドプールですべての応答グループの構成のバックアップを作成します。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="even">
<td><p>停止中</p></td>
<td><p><strong>インポート-CsRgsConfiguration</strong>コマンドレットを実行し、プライマリプールからバックアッププールに、バックアップされた Lync Server 応答グループサービスの構成をインポートします。</p>
<div>

> [!NOTE]  
> バックアッププールのアプリケーションレベルの応答グループの設定をプライマリプールの設定で置き換える場合は、– ReplaceExistingSettings パラメーターを使います。 アプリケーションレベルの設定をプライマリプールからバックアッププールに転送せず、プライマリプールを復元できない場合、プライマリプールの設定は失われます。


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="odd">
<td><p>インポート後</p></td>
<td><p>応答グループのコマンドレットを実行するには、– ShowAll パラメーター (すべての応答グループを表示) または– Owner パラメーター (インポートされた応答グループのみを表示) を使用して、すべての応答グループの構成がバックアッププールにインポートされたことを確認します。</p>
<div>

> [!IMPORTANT]  
> – ShowAll パラメーターまたは– Owner パラメーターのいずれも使用しない場合、バックアッププールにインポートした応答グループは、コマンドレットによって返された結果に一覧表示されません。


</div>
<p>次のコマンドレットを実行します。</p>
<ul>
<li><p><strong>Get-CsRgsWorkflow</strong></p></li>
<li><p><strong>Get-CsRgsQueue</strong></p></li>
<li><p><strong>Get-CsRgsAgentGroup</strong></p></li>
<li><p><strong>Get-CsRgsHoursOfBusiness</strong></p></li>
<li><p><strong>Get-CsRgsHolidaySet</strong></p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="even">
<td><p>フェールオーバー後</p></td>
<td><ul>
<li><p>バックアッププールにインポートされた応答グループにテスト通話を発信し、通話が正しく処理されていることを確認します。</p></li>
<li><p>すべての正式なエージェントは、バックアッププールの正式グループにもう一度サインインする必要があります。</p></li>
<li><p>構成の変更を管理します。</p>
<p>バックアッププール内の応答グループ (バックアッププールにインポートされているかバックアッププールによって所有されているか) は、停止中に通常どおり変更できます。</p>
<div>

> [!IMPORTANT]  
> バックアッププールにインポートした応答グループを管理するには、Lync Server 管理シェルを使用する必要があります。 Lync Server コントロールパネルを使用して、バックアッププール内の応答グループを管理することはできません。


</div></li>
</ul></td>
<td><p>該当なし</p></td>
</tr>
<tr class="odd">
<td><p>回復後、フェールバック前</p></td>
<td><p><strong>エクスポート-CsRgsConfiguration</strong>コマンドレットを実行して、バックアッププールとして-Source パラメーターを指定し、プライマリプールとして-Owner パラメーターを指定して、バックアッププールからプライマリプールに所有されている応答グループをエクスポートします。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="even">
<td><p>フェイルバック後</p></td>
<td><ul>
<li><p><strong>インポート-CsRgsConfiguration</strong>コマンドレットを実行して、応答グループをプライマリプールにインポートします。</p>
<div>

> [!NOTE]  
> プライマリプールを復元できず、新しいプールを展開して置き換える場合は、– ReplaceExistingSettings パラメーターを使用して、アプリケーションレベルの設定をバックアッププールから新しいプールに転送します。 バックアッププールから設定を転送しない場合、新しいプールでは既定の設定が使用されます。


</div></li>
<li><p>次のコマンドレットを実行するには、– ShowAll パラメーター (すべての応答グループを表示) または– Owner パラメーター (インポートされた応答グループのみを表示) を使用して、すべての応答グループの構成が正常にプライマリプールにインポートされたことを確認します。</p>
<ul>
<li><p><strong>Get-CsRgsWorkflow</strong></p></li>
<li><p><strong>Get-CsRgsQueue</strong></p></li>
<li><p><strong>Get-CsRgsAgentGroup</strong></p></li>
<li><p><strong>Get-CsRgsHoursOfBusiness</strong></p></li>
<li><p><strong>Get-CsRgsHolidaySet</strong></p></li>
</ul></li>
<li><p>プライマリプールにインポートされた応答グループにテスト通話を発信し、通話が正しく処理されていることを確認します。</p></li>
<li><p>必要に応じて、– RemoveExportedConfiguration パラメーターを指定して、バックアッププールに対して<strong>Export-CsRgsConfiguration</strong>コマンドレットを実行し、プライマリプールによって所有されている応答グループをバックアッププールから削除します。</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

