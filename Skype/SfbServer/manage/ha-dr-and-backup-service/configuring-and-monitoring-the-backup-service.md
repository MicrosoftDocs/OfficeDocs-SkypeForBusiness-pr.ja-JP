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
localization_priority: Normal
description: Skype for Business Server 管理シェル コマンドを使用して、バックアップ サービスを構成および監視できます。
ms.openlocfilehash: d38c9d0b0261fb7e1da89b3422496d94307a791d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817197"
---
# <a name="configuring-and-monitoring-the-backup-service-in-skype-for-business-server"></a>Skype for Business Server でのバックアップ サービスの構成と監視

次の Skype for Business Server 管理シェル コマンドを使用して、バックアップ サービスを構成および監視できます。 フロントエンド プールのファイル ストアに格納されている会議情報を復元するには、以下の「バックアップ サービスを使用して会議コンテンツを復元する [」](#restore-conference-contents-using-the-backup-service)を参照してください。

> [!NOTE]  
> RTCUniversalServerAdmins グループは、既定で **Get-CsBackupServiceStatus** を実行する権限を持つ唯一のグループです。 このコマンドレットを使用するには、このグループのメンバーとしてログオンします。 また **、Set-CsBackupServiceConfiguration** コマンドレットを使用して、このコマンドへのアクセス権を他のグループ (CSAdministrator など) に付与することもできます。

## <a name="to-see-the-backup-service-configuration"></a>バックアップ サービスの構成を確認するには

次のコマンドレットを実行します。

    Get-CsBackupServiceConfiguration

SyncInterval の既定値は 2 分です。

## <a name="to-set-the-backup-service-sync-interval"></a>バックアップ サービスの同期間隔を設定するには

次のコマンドレットを実行します。

    Set-CsBackupServiceConfiguration -SyncInterval interval

たとえば、次の例では間隔を 3 分に設定します。

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00


> [!IMPORTANT]  
> このコマンドレットを使用してバックアップ サービスの既定の同期間隔を変更することもできますが、同期間隔はバックアップ サービスのパフォーマンスと目標復旧ポイント (RPO) に大きな影響を与えるので、絶対に必要な場合を限り変更する必要はありません。

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a>特定のプールのバックアップ サービスの状態を取得するには

次のコマンドレットを実行します。

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

> [!NOTE]  
> バックアップ サービスの同期状態は、プール (P1) からバックアップ プール (P2) に一方向に定義されます。 P1 から P2 への同期状態は、P2 から P1 の同期状態とは異なる場合があります。 P1 ~ P2 の場合、同期間隔内に P1 で行われたすべての変更が P2 に完全にレプリケートされる場合、バックアップ サービスは "安定" 状態になります。 P1 から P2 に同期する変更がこれ以上ない場合は、最終的な状態になります。 どちらの状態も、コマンドレットが実行された時点でのバックアップ サービスのスナップショットを示します。 返された状態が後の状態にとどまるというのではありません。 特に、"final" 状態は、コマンドレットの実行後に P1 が変更を生成しない場合にのみ保持されます。 これは **、Invoke-CsPoolfailover** 実行ロジックの一部として P1 を読み取り専用モードにした後に P1 を P2 にフェールオーバーする場合に当てはまる場合です。

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a>特定のプールのバックアップ関係に関する情報を取得するには

次のコマンドレットを実行します。

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

## <a name="to-force-a-backup-service-sync"></a>バックアップ サービスの同期を強制するには

次のコマンドレットを実行します。

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

## <a name="restore-conference-contents-using-the-backup-service"></a>バックアップ サービスを使用して会議コンテンツを復元する 

フロント エンド プールのファイル ストアに格納されている会議情報が使用できなくなった場合は、プールに格納されているユーザーが会議データを保持するためにこの情報を復元する必要があります。 会議データを失ったフロントエンド プールと他のフロントエンド プールがペアになっている場合は、バックアップ サービスを使用してデータを復元できます。

プール全体で障害が発生し、ユーザーをバックアップ プールにフェールオーバーする必要がある場合も、このタスクを実行します。これらのユーザーが元のプールにフェールオーバーされるときに、この手順を使用して、会議コンテンツも元のプールにコピーする必要があります。

Pool1 と Pool2 がペアで、Pool1 の会議データが失われたとします。 次のコマンドレットを使用して、バックアップ サービスを呼び出してコンテンツを復元できます。

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

会議コンテンツのサイズによっては、コンテンツを復元するのに時間がかかる場合があります。次のコマンドレットを使用すると、プロセスの状態を確認できます。

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

このコマンドレットがデータ会議モジュールに対して安定状態の値を返すと、プロセスは完了です。
