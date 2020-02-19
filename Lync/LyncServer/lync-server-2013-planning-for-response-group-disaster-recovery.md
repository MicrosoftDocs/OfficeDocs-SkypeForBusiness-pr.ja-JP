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
ms.openlocfilehash: 7df32074881ffac854294e0835287802126f1fd5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139318"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-response-group-disaster-recovery-in-lync-server-2013"></a>Lync Server 2013 での応答グループの障害復旧の計画

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

このセクションでは、応答グループの障害復旧を準備する方法について説明し、障害復旧プロセスの概要を示します。

<div>

## <a name="preparing-for-response-group-disaster-recovery"></a>応答グループの障害復旧の準備

障害復旧手順を準備および実施する場合、次の点を考慮してください。

<div>


> [!NOTE]  
> 共存環境では、このドキュメントで説明されている障害回復手順で Lync Server 2013 応答グループのみがサポートされます。



</div>

  - 障害復旧の計画は、処理能力の計画時に行います。 障害復旧の処理能力については、ペアにしたプールのそれぞれのプールで、両方のプールのすべての応答グループの負荷を処理できる必要があります。 応答グループの容量計画の詳細については、「 [capacity planning For Response group In Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md)」を参照してください。

  - このドキュメントで説明されているエクスポート手順を使用して、応答グループアプリケーションを展開したすべてのフロントエンドプールで、すべての応答グループ構成のバックアップコピーを定期的に実行します。 詳細については、「 [Lync Server 2013 の応答グループの障害復旧手順](lync-server-2013-response-group-disaster-recovery-procedures.md)」を参照してください。 そのバックアップは安全な場所に保管します。

  - 応答グループアプリケーションで使用したすべての元のオーディオファイル (レコーディングファイルや音楽オンリストファイルを含む) の個別のバックアップコピーを保持します。 そのバックアップ ファイルは安全な場所に保管します。

  - Lync Server 2013 の障害復旧の場合、すべての応答グループの設定には、展開全体で一意の名前を指定する必要があります。 この要件は、ワークフロー、キュー、エージェント グループ、休日セット、および営業時間に適用されます。 プライマリ プールとバックアップ プールがまだアクティブで、フェールオーバー手順の開始が必要になる前に、この要件が満たされていることを確認する必要があります。 バックアップ プールに応答グループ データをインポートするときに名前の競合が発生するとインポートは失敗します。 インポートとフェールオーバー手順を完了するには、バックアップ プールの応答グループ オブジェクトの名前を変更して名前の競合を解決するか、**Import-CsRgsConfiguration** コマンドレットに -ResolveNameConflicts パラメーターを使用することによって応答グループ オブジェクトに一意の識別番号を追加する方法で競合を自動解決する必要があります。

  - 一般に、毎日バックアップを行うことをお勧めしますが、変更が多い場合は、より頻度の高いバックアップのスケジュールが必要になることもあります。障害発生時に失われる情報の量は、バックアップの頻度および変更の頻度と量に左右されます。

  - 障害またはフェールオーバー処理が発生する前に、応答グループをバックアップ プールにインポートしておくことができます。 応答グループを事前にインポートすると、通話がバックアッププールにルーティングされると直ちに Lync Server Response Group service がバックアッププールに復元されるため、ダウンタイムが減少します。
    
    <div>
    

    > [!NOTE]  
    > 応答グループアプリケーションは、フェールオーバーが完了するまで非アクティブなプールに所属するエージェントに到達できません。 この間、応答グループアプリケーションは、それらのエージェントが利用できない場合と同じように通話を処理します。

    
    </div>

</div>

<div>

## <a name="response-group-disaster-recovery-process"></a>応答グループの障害復旧プロセス

障害が発生した場合、次の回復アプローチで応答グループを回復できます。

  - バックアップ プールにフェールオーバーし、次に元のプールにフェールバックします。

  - バックアップ プールにフェールオーバーし、異なる完全修飾ドメイン名 (FQDN) を持つ新しいプールを作成し、その新しいプールに応答グループをインポートします。

障害復旧のフェールオーバー フェーズ中、応答グループは (使用できない) プライマリ プールとバックアップ プールという複数のプールに存在します。どちらのプールでも応答グループの名前と所有者 (プライマリ プール) は同じですが、その親は異なります。

異なる FQDN を持つ新しいプールを作成して回復する場合、応答グループをインポートするときにその所有者として新しいプールを割り当てる必要があります。 **Import-CsRgsConfiguration** コマンドレットに -OverwriteOwner パラメーターを指定して所有権を明示的に割り当て直さない限り、応答グループの所有権は引き続き元のプールにあります。

<div>


> [!NOTE]  
> また、同じ FQDN を使用するかどうかにかかわらず、回復中にプールを再構築した場合 (つまり、応答グループデータベースが空の場合) は、– OverwriteOwner パラメーターを使用する必要があります。 プールを構築し直さなかった場合には -OverwriteOwner パラメーターを使用する必要はありませんが、応答グループをプライマリ プールにインポートして戻す場合はこのパラメーターを使用することが許容されます。



</div>

プールごとに定義できるアプリケーションレベルの応答グループ構成設定は1つだけです。 このような設定として、既定の保留音の構成、既定の保留音オーディオ ファイル、エージェントかけ直し猶予期間、呼び出しコンテキストの構成があります。 これらの構成設定を表示するには、**Get-CsRgsConfiguration** コマンドレットを実行します。 **Get-help**コマンドレットの詳細については、「 [get-help](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration)」を参照してください。

これらのアプリケーション レベル設定は、**Import-CsRgsConfiguration** コマンドレットに -ReplaceExistingSettings パラメーターを指定するとプールから別のプールへ転送できますが、それによって転送先プールの設定はオーバーライドされます。

<div>


> [!IMPORTANT]  
> 設定を別のプールへ転送する場合のこの制約は、アプリケーション レベル設定と既定の保留音オーディオ ファイルのみに適用されます。エージェント グループ、キュー、ワークフロー、営業時間、および休日セットには適用されません。



</div>

障害時にバックアップ プールのアプリケーション レベル設定を置き換えないようにすると、プライマリ プールを回復できない場合にプライマリ プールのアプリケーション レベル設定は失われます。回復時にプライマリ プールを置き換えるために新しいプールを作成する必要がある場合、それが同じ FQDN を持つか異なる FQDN を持つかに関係なく、元のアプリケーション レベル設定は回復できません。この場合、新しいプールにこれらの設定を構成し、保留音オーディオ ファイルを含める必要があります。

障害時に **Import-CsRgsConfiguration** コマンドレットを使用してプライマリ プールからバックアップ プールにアプリケーション レベル設定を転送する場合は、その後の回復時に、プライマリ プールからバックアップ プールに転送したときと同じ方法でバックアップ プールから新しいプールに設定を転送できます。

応答グループを回復するステップの概要を次の表に示します。

これらの手順の実行の詳細については、「 [Lync Server 2013 の応答グループの障害復旧手順](lync-server-2013-response-group-disaster-recovery-procedures.md)」を参照してください。

### <a name="response-group-disaster-recovery-steps"></a>応答グループの障害復旧ステップ

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>フェーズ</th>
<th>手順</th>
<th>必要なグループおよび役割</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>停止前</p></td>
<td><p>定期的に、 <strong>Export-CsRgsConfiguration</strong>コマンドレットを実行して、応答グループアプリケーションが展開されているすべてのフロントエンドプールですべての応答グループ構成のバックアップを作成します。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="even">
<td><p>停止中</p></td>
<td><p><strong>Import-CsRgsConfiguration</strong>コマンドレットを実行して、バックアップされた Lync Server 応答グループサービスの構成をプライマリプールからバックアッププールにインポートします。</p>
<div>

> [!NOTE]  
> バックアッププールのアプリケーションレベルの応答グループの設定をプライマリプールの設定と置き換える場合は、-ReplaceExistingSettings パラメーターを使用します。 プライマリ プールのアプリケーション レベル設定をバックアップ プールに転送しないと、プライマリ プールを回復できない場合にプライマリ プールの設定は失われます。


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="odd">
<td><p>インポート後</p></td>
<td><p>-ShowAll パラメーター (すべての応答グループを表示する場合) または-Owner パラメーター (インポートされた応答グループのみを表示する場合) のいずれかを使用して応答グループのコマンドレットを実行し、すべての応答グループの構成がバックアッププールにインポートされたことを確認します。</p>
<div>

> [!IMPORTANT]  
> -ShowAll パラメーターも -Owner パラメーターも指定しない場合、バックアップ プールにインポートされた応答グループは、コマンドレットから返される結果に表示されません。


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
<li><p>バックアップ プールにインポートした応答グループへテスト通話を行い、通話が適切に処理されることを確認します。</p></li>
<li><p>すべての公式エージェントは、バックアップ プール上の公式グループに再度サインインする必要があります。</p></li>
<li><p>構成の変更を管理します。</p>
<p>バックアップ プールにインポートされるかバックアップ プールに所有されているためにバックアップ プールに含まれる応答グループは、障害時にも通常どおりに変更できます。</p>
<div>

> [!IMPORTANT]  
> バックアッププールにインポートした応答グループを管理するには、Lync Server 管理シェルを使用する必要があります。 Lync Server コントロールパネルを使用して、バックアッププールにあるときにこれらの応答グループを管理することはできません。


</div></li>
</ul></td>
<td><p>該当なし</p></td>
</tr>
<tr class="odd">
<td><p>回復後、フェールバック前</p></td>
<td><p>-Source パラメーターにバックアップ プール、-Owner パラメーターにプライマリ プールを指定して <strong>Export-CsRgsConfiguration</strong> コマンドレットを実行し、プライマリ プールに所有される応答グループをバックアップ プールからエクスポートします。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="even">
<td><p>フェールバック後</p></td>
<td><ul>
<li><p><strong>Import-CsRgsConfiguration</strong> コマンドレットを実行して、応答グループをプライマリ プールにインポートして戻します。</p>
<div>

> [!NOTE]  
> プライマリ プールを回復できない場合に新しいプールを展開してそれを置き換えるには、-ReplaceExistingSettings パラメーターを使用してバックアップ プールのアプリケーション レベル設定を新しいプールに転送します。バックアップ プールから設定を転送しないと、新しいプールでは既定の設定が使用されます。


</div></li>
<li><p>次のコマンドレットに -ShowAll パラメーター (すべての応答グループを表示する場合) または -Owner パラメーター (インポートされた応答グループのみを表示する場合) を指定して実行し、すべての応答グループ構成がプライマリ プールに正常にインポートして戻されたことを確認します。</p>
<ul>
<li><p><strong>Get-CsRgsWorkflow</strong></p></li>
<li><p><strong>Get-CsRgsQueue</strong></p></li>
<li><p><strong>Get-CsRgsAgentGroup</strong></p></li>
<li><p><strong>Get-CsRgsHoursOfBusiness</strong></p></li>
<li><p><strong>Get-CsRgsHolidaySet</strong></p></li>
</ul></li>
<li><p>プライマリ プールにインポートして戻した応答グループへテスト通話を行い、通話が適切に処理されることを確認します。</p></li>
<li><p>必要に応じて、バックアップ プールで -RemoveExportedConfiguration パラメーターを指定して <strong>Export-CsRgsConfiguration</strong> コマンドレットを実行して、プライマリ プールに所有されている応答グループをバックアップ プールから削除します。</p></li>
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

