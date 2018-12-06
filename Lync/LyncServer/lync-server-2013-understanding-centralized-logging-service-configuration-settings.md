---
title: 集中ログ サービスの構成設定について
TOCTitle: 集中ログ サービスの構成設定について
ms:assetid: 3c34e600-0b91-43dc-b4cc-90b6a70ee12e
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688029(v=OCS.15)
ms:contentKeyID: 49886921
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 集中ログ サービスの構成設定について

 

_**トピックの最終更新日:** 2015-03-09_

集中ログ サービス は、ログ サービスが収集する情報、収集方法、収集元、およびログ設定を定義するように構成されています。これらの設定は、グローバル (展開全体) またはサイト (展開内で指定されたサイト) に対して定義します。定義するすべてのログで、ログを開始、停止、更新、および検索するコマンドに対して使用する ID に適した設定が使用されます。

## 現在の 集中ログ サービス 構成を表示するには

Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

コマンド ライン プロンプトで、次のように入力します。

    Get-CsClsConfiguration


> [!TIP]
> Redmond サイトの CsClsConfiguration のみを返すように <CODE>-Identity</CODE> およびスコープ ("Site:Redmond" など) を定義して、返された構成設定のスコープを縮小または拡大できます。構成の一部を指定してその詳細を確認するには、出力を他の Windows PowerShell コマンドレットにパイプ処理します。たとえば、"Redmond" サイトの構成で定義されたシナリオに関する詳細を取得するには、「<CODE>Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandPropery Scenarios</CODE>」と入力します。



![Get-CsClsConfiguration からのサンプル出力](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Get-CsClsConfiguration からのサンプル出力")

コマンドレットの結果には、集中ログ サービス の現在の構成が表示されます。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>構成設定</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Identity</strong></p></td>
<td><p>この構成のスコープと名前を識別します。存在するグローバル構成は 1 つのみで、サイトごとに 1 つの構成があります。</p></td>
</tr>
<tr class="even">
<td><p><strong>Scenarios</strong></p></td>
<td><p>この構成に対して定義されたシナリオの一覧。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SearchTerms</strong></p></td>
<td><p>構成の定義済み検索用語。設置型配置ではなく Office 365 です。</p></td>
</tr>
<tr class="even">
<td><p><strong>SecurityGroups</strong></p></td>
<td><p>コンピューターを確認できるユーザー (つまり、セキュリティ グループのメンバー) を、そのユーザーのサイトに基づいて制御する定義済みセキュリティ グループ。この状況におけるサイトは、トポロジ ビルダーで定義されています。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Regions</strong></p></td>
<td><p>SecurityGroups を地域にまとめる際に定義済み地域が使用されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>EtlFileFolder</strong></p></td>
<td><p>ログ ファイルが書き込まれるコンピューター上の場所への定義済みパス。CLSAgent はログ ファイルを書き込み、ネットワーク サービスとの関連で実行されます。この場合は、%TEMP% が %WINDIR%\ServiceProfiles\NetworkService\AppData\Local に展開されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EtlFileRolloverSizeMB</strong></p></td>
<td><p>パラメーターは、新しいイベント トレース ログ (.etl) ファイルが作成される前のログ ファイルの最大サイズを示します。定義したサイズに達すると、EtlFileRolloverMinutes で設定された最大時間に達していなくても、新しいログ ファイルが作成されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>EtlFileRolloverMinutes</strong></p></td>
<td><p>新しい .etl ファイルが作成されるまでのログの定義済み最大経過時間 (分単位)。指定した時間が過ぎると、EtlFileRolloverSizeMBE で設定された最大サイズに達していなくても、新しいログ ファイルが作成されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>TmfFileSearchPath</strong></p></td>
<td><p>トレース メッセージ形式のファイルを検索する場所。トレース メッセージ形式のファイルは、バイナリ ファイルを人が読み取れる形式に変換するときに使用されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>CacheFileLocalFolders</strong></p></td>
<td><p>キャッシュ ファイルが書き込まれるコンピューター上の場所への定義済みパス。CLSAgent はキャッシュ ファイルを書き込み、ネットワーク サービスとの関連で実行されます。この場合は、%TEMP% が %WINDIR%\ServiceProfiles\NetworkService\AppData\Local に展開されます。既定では、キャッシュ ファイルとログ ファイルは同じディレクトリに書き込まれます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CacheFileNetworkFolder</strong></p></td>
<td><p>汎用名前付け規則 (UNC) パスを定義すると、ログ操作中にキャッシュ ファイルを受け取ることができます。</p></td>
</tr>
<tr class="even">
<td><p><strong>CacheFileLocalRetentionPeriod</strong></p></td>
<td><p>キャッシュ ファイルが保持される最大時間 (日単位) として定義されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CacheFileMaxDiskUsage</strong></p></td>
<td><p>キャッシュ ファイルで使用できるディスク容量の割合として定義されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>ComponentThrottleLimit</strong></p></td>
<td><p>自動調整制限がトリガーされるまでの、コンポーネントが生成できる秒あたりの最大トレース数として定義されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ComponentThrottleSample</strong></p></td>
<td><p>ComponentThrottleLimit を超えることができる 60 秒単位の回数。</p></td>
</tr>
<tr class="even">
<td><p><strong>MinimumClsAgentServiceVersion</strong></p></td>
<td><p>実行が許可されている CLSAgent の最小バージョン。この要素は Office 365 を対象としています。</p></td>
</tr>
</tbody>
</table>


## 関連項目

#### 概念

[集中ログサービスの概要](lync-server-2013-overview-of-the-centralized-logging-service.md)  

#### その他のリソース

[Set-CsClsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClsConfiguration)  
[Remove-CsClsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsClsConfiguration)  
[New-CsClsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClsConfiguration)  
[Get-CsClsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClsConfiguration)

