---
title: バックアップ サービスの構成と監視
ms.reviewer: ''
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 管理シェル コマンドSkype for Business Server使用して、バックアップ サービスを構成および監視できます。
ms.openlocfilehash: df0e7d985e9941e4af41a4cec5456774e5a3a4dd
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58612296"
---
# <a name="configuring-and-monitoring-the-backup-service-in-skype-for-business-server"></a>バックアップ サービスの構成とSkype for Business Server

次の管理シェル コマンドSkype for Business Server使用して、バックアップ サービスを構成および監視できます。 フロントエンド プールのファイル ストアに格納されている会議情報を復元するには、以下の「Backup Service を使用して会議の [内容を復元する」を](#restore-conference-contents-using-the-backup-service)参照してください。

> [!NOTE]  
> RTCUniversalServerAdmins グループは、既定で **Get-CsBackupServiceStatus** を実行するアクセス許可を持つ唯一のグループです。 このコマンドレットを使用するには、このグループのメンバーとしてログオンします。 または **、Set-CsBackupServiceConfiguration** コマンドレットを使用して、このコマンドへのアクセス権を他のグループ (CSAdministrator など) に付与できます。

## <a name="to-see-the-backup-service-configuration"></a>バックアップ サービスの構成を確認するには

次のコマンドレットを実行します。<br/><br/>Get-CsBackupServiceConfiguration

SyncInterval の既定値は 2 分です。

## <a name="to-set-the-backup-service-sync-interval"></a>バックアップ サービスの同期間隔を設定するには

次のコマンドレットを実行します。<br/><br/>Set-CsBackupServiceConfiguration -SyncInterval 間隔

たとえば、次の例では、間隔を 3 分に設定します。<br/><br/>Set-CsBackupServiceConfiguration -SyncInterval 00:03:00


> [!IMPORTANT]  
> このコマンドレットを使用してバックアップ サービスの既定の同期間隔を変更することもできますが、同期間隔が Backup Service のパフォーマンスと回復ポイントの目標 (RPO) に大きな影響を与えるので、絶対に必要な場合を指定しない限り、これを行う必要はありません。

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a>特定のプールのバックアップ サービスの状態を取得するには

次のコマンドレットを実行します。<br/><br/>Get-CsBackupServiceStatus -PoolFqdn \<pool-FQDN>

> [!NOTE]  
> バックアップ サービスの同期状態は、プール (P1) からバックアップ プール (P2) に一方向に定義されます。 P1 から P2 への同期状態は、P2 から P1 の同期状態とは異なる場合があります。 P1 ~ P2 の場合、同期間隔内に P1 で行われたすべての変更が完全に P2 にレプリケートされる場合、Backup Service は "安定した" 状態になります。 P1 から P2 に同期する変更がこれ以上ない場合は、"final" 状態になります。 どちらの状態も、コマンドレットの実行時にバックアップ サービスのスナップショットを示します。 返された状態が後で残るという結果ではありません。 特に、"final" 状態は、コマンドレットの実行後に P1 が変更を生成しない場合にのみ保持されます。 これは **、P1 が Invoke-CsPoolfailover** 実行ロジックの一部として読み取り専用モードに配置された後に P1 から P2 に失敗した場合に当てはまります。

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a>特定のプールのバックアップ関係に関する情報を取得するには

次のコマンドレットを実行します。<br/><br/>Get-CsPoolBackupRelationship -PoolFQDN \<poolFQDN>

## <a name="to-force-a-backup-service-sync"></a>バックアップ サービスの同期を強制するには

次のコマンドレットを実行します。<br/><br/>Invoke-CsBackupServiceSync -PoolFqdn \<poolFqdn> [-BackupModule {All|PresenceFocus|DataConf|[CMSMaster}]

## <a name="restore-conference-contents-using-the-backup-service"></a>Backup Service を使用して会議の内容を復元する 

フロントエンド プールのファイル ストアに格納されている会議情報が使用できなくなった場合は、プールにユーザーが参加しているユーザーが会議データを保持するために、この情報を復元する必要があります。 会議データを失ったフロントエンド プールと他のフロントエンド プールがペアになっている場合は、バックアップ サービスを使用してデータを復元できます。

プール全体で障害が発生し、ユーザーをバックアップ プールにフェールオーバーする必要がある場合も、このタスクを実行します。これらのユーザーが元のプールにフェールオーバーされるときに、この手順を使用して、会議コンテンツも元のプールにコピーする必要があります。

Pool1 と Pool2 がペアで、Pool1 の会議データが失われたとします。 次のコマンドレットを使用して、バックアップ サービスを呼び出してコンテンツを復元できます。<br/><br/>Invoke-CsBackupServiceSync -PoolFqdn \<Pool2 FQDN> -BackupModule ConfServices.DataConf

会議コンテンツのサイズによっては、コンテンツを復元するのに時間がかかる場合があります。次のコマンドレットを使用すると、プロセスの状態を確認できます。<br/><br/>Get-CsBackupServiceStatus -PoolFqdn \<Pool2 FQDN> -BackupModule ConfServices.DataConf

このコマンドレットがデータ会議モジュールに対して安定状態の値を返すと、プロセスは完了です。
