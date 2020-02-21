---
title: 集中ログサービスの構成設定について
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding Centralized Logging Service configuration settings
ms:assetid: 3c34e600-0b91-43dc-b4cc-90b6a70ee12e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688029(v=OCS.15)
ms:contentKeyID: 49733619
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b326f7ee869b060a423696817c21d7cb763bb0a2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193180"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="understanding-centralized-logging-service-configuration-settings-in-lync-server-2013"></a>Lync Server 2013 での集中ログサービスの構成設定について

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-21_

集中ログサービスは、ログサービスが収集する目的、収集方法、収集される場所、およびログ設定について定義するように構成されています。 これらの設定は、グローバルに (つまり、展開全体で)、またはサイト (展開内の名前付きサイト) で定義します。 定義するすべてのログで、ログを開始、停止、更新、および検索するコマンドに対して使用する ID に適した設定が使用されます。

<div>

## <a name="to-display-the-current-centralized-logging-service-configuration"></a>現在の集中ログサービスの構成を表示するには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  コマンド ライン プロンプトで、次のように入力します。
    
        Get-CsClsConfiguration
    
    <div>
    

    > [!TIP]
    > 定義<CODE>-Identity</CODE>によって返される構成設定の範囲を絞り込んだり展開したり、"Site: redmond" のようにスコープを展開して、サイト Redmond の CsClsConfiguration のみを取得したりすることができます。 構成の特定の部分に関する詳細が必要な場合は、出力を別の Windows PowerShell コマンドレットにパイプ処理できます。 たとえば、"Redmond" サイトの構成で定義されているシナリオの詳細を取得するには、次のように入力します。<CODE>Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandPropery Scenarios</CODE>

    
    </div>
    
    ![Get-CsClsConfiguration からの出力例。](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Get-CsClsConfiguration からの出力例。")
    
    コマンドレットの結果によって、集中ログサービスの現在の構成が表示されます。
    
    
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
    <td><p><strong>ID</strong></p></td>
    <td><p>この構成のスコープと名前を識別します。存在するグローバル構成は 1 つのみで、サイトごとに 1 つの構成があります。</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Scenarios</strong></p></td>
    <td><p>この構成に対して定義されたシナリオの一覧。</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>SearchTerms</strong></p></td>
    <td><p>構成の定義済み検索用語。 Office 365。オンプレミス展開ではありません。</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Securitygroups まとめる</strong></p></td>
    <td><p>コンピューターを確認できるユーザー (つまり、セキュリティ グループのメンバー) を、そのユーザーのサイトに基づいて制御する定義済みセキュリティ グループ。 このコンテキストのサイトは、トポロジビルダーで定義されているサイトです。</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>地域</strong></p></td>
    <td><p>SecurityGroups を地域にまとめる際に定義済み地域が使用されます。</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>EtlFileFolder</strong></p></td>
    <td><p>ログ ファイルが書き込まれるコンピューター上の場所への定義済みパス。CLSAgent はログ ファイルを書き込み、ネットワーク サービスとの関連で実行されます。この場合は、%TEMP% が %WINDIR%\ServiceProfiles\NetworkService\AppData\Local に展開されます。</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Etlfilerolloversizembe</strong></p></td>
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
    <td><p><strong>よる cachefilelocalfolders</strong></p></td>
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
    <td><p>実行が許可されている CLSAgent の最小バージョン。 この要素は、Office 365 を対象としています。</p></td>
    </tr>
    </tbody>
    </table>


</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 の集中ログサービスの概要](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[設定-CsClsConfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))  
[削除-CsClsConfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))  
[新しい-CsClsConfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))  
[取得-CsClsConfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

