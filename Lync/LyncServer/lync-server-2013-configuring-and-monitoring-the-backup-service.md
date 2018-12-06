---
title: 'Lync Server 2013: バックアップ サービスの構成と監視'
TOCTitle: バックアップ サービスの構成と監視
ms:assetid: c608280e-a7d1-4ae0-a75c-da6b524752fa
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205252(v=OCS.15)
ms:contentKeyID: 48273523
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのバックアップ サービスの構成と監視

 

_**トピックの最終更新日:** 2012-11-01_

次の Lync Server 管理シェル コマンドレットを使用して、バックアップ サービスを構成および監視できます。

> [!NOTE]
> 既定で <strong>Get-CsBackupServiceStatus</strong> を実行するアクセス許可があるのは、RTCUniversalServerAdmins グループだけです。このコマンドレットを使用するには、このグループのメンバーとしてログオンします。または、 <strong>Set-CsBackupServiceConfiguration</strong> コマンドレットを使用すると、このコマンドへのアクセス権を他のグループ (CSAdministrator など) に付与できます。


## バックアップ サービスの構成を表示するには

次のコマンドレットを実行します。

    Get-CsBackupServiceConfiguration

SyncInterval の既定値は 2 分です。

## バックアップ サービスの同期間隔を設定するには

次のコマンドレットを実行します。

    Set-CsBackupServiceConfiguration -SyncInterval interval

たとえば、次のように指定すると間隔が 3 分に設定されます。

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00


> [!IMPORTANT]
> このコマンドレットを使用してバックアップ サービスの既定の同期間隔を変更できますが、どうしても必要でない限り行わないでください。同期間隔は、バックアップ サービスのパフォーマンスおよび目標復旧ポイント (RPO) に大きく影響します。



## 特定のプールに対するバックアップ サービスのステータスを取得するには

次のコマンドレットを実行します。

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

> [!NOTE]
> バックアップ サービスの同期ステータスは、プール (P1) からバックアップ プール (P2) に対して一方向に定義されています。P1 から P2 への同期ステータスは、P2 から P1 への同期ステータスと異なる場合があります。P1 から P2 の場合、P1 で行われたすべての変更が同期間隔内で P2 に完全に複製される場合、バックアップ サービスは &quot;安定した&quot; 状態です。P1 から P2 に同期する変更がそれ以上ない場合は、&quot;最終&quot; 状態になっています。どちらの状態も、コマンドレットを実行した時点でのバックアップ サービスのスナップショットを示します。返された状態がその後もそのまま変わらないことを意味してはいません。具体的には、&quot;最終&quot; 状態は、コマンドレットの実行後に P1 が何も変更を生成しない場合にのみ維持されます。これは、 <strong>Invoke-CsPoolfailover</strong> の実行ロジックの一部として P1 が読み取り専用モードにされた後で、P1 が P2 にフェールオーバーする場合でも成り立ちます。


## 特定のプールに対するバックアップ関係についての情報を取得するには

次のコマンドレットを実行します。

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

## 強制的にバックアップ サービスを同期するには

次のコマンドレットを実行します。

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

