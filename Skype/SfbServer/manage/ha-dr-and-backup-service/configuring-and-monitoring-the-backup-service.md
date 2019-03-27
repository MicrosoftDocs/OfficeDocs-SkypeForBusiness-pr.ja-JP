---
title: バックアップ サービスの構成と監視
ms.reviewer: ''
author: heidip
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype ビジネス サーバー管理シェル コマンドを使用するにを構成し、バックアップ サービスを監視します。
ms.openlocfilehash: 3a41caecb4e123505da2d529ea74c22a5d0e28e7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30896834"
---
# <a name="configuring-and-monitoring-the-backup-service-in-skype-for-business-server"></a>構成して、Skype でバックアップ サービスをビジネス サーバーの監視

ビジネス サーバー管理シェル コマンドの次の Skype を使用するには構成し、バックアップ サービスを監視します。 フロント エンド プールのファイル ストアに格納されている会議の情報を復元するには、下[バックアップ サービスを使用して会議の内容を復元](#restore-conference-contents-using-the-backup-service)するにはを参照してください。

> [!NOTE]  
> RTCUniversalServerAdmins グループは、既定では、 **Get CsBackupServiceStatus**を実行するアクセス許可を持つ唯一のグループです。 このコマンドレットを使用するには、このグループのメンバーとしてログオンします。 または、**セット CsBackupServiceConfiguration**コマンドレットを使用して他のグループ (たとえば、CSAdministrator) に次のコマンドへのアクセス権を与えることができます。

## <a name="to-see-the-backup-service-configuration"></a>バックアップ サービス構成を確認するには

次のコマンドレットを実行します。

    Get-CsBackupServiceConfiguration

SyncInterval の既定値は、2 つ分です。

## <a name="to-set-the-backup-service-sync-interval"></a>バックアップ サービスの同期間隔を設定するのには

次のコマンドレットを実行します。

    Set-CsBackupServiceConfiguration -SyncInterval interval

など、次の間隔を設定 3 分です。

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00


> [!IMPORTANT]  
> バックアップ サービスの既定の同期間隔を変更するのには、このコマンドレットを使用できますを使用しないので、絶対に必要である限り、同期間隔が、バックアップ サービスのパフォーマンスと、目標復旧時点 (RPO) に大きな影響を与えます。

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a>特定のプールに対するバックアップ サービスの状態を取得するには

次のコマンドレットを実行します。

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

> [!NOTE]  
> (P2) のバックアップのプールに、プール (P1) から、unidirectionally バックアップ サービスの同期の状態が定義されます。 同期状態を P1 から P2 を P1 を P2 からとは異なることができます。 P2 を P1、バックアップ サービスは「安定」状態で P1 で行われたすべての変更が完全にレプリケートされている場合 P2 に同期間隔内でします。 状態になって、"final"がある場合は、P1 と P2 を同期する変更です。 両方の状態は、コマンドレットの実行時に、バックアップ サービスのスナップショットを示しています。 その後は、返された状態のままとは限りません。 具体的には、「最後」の状態が引き続きかどうか P1 は生成されません、変更、コマンドレットが実行された後にのみ保持されます。 フェールオーバー P1 P2 を P1 が読み取り専用モードに**呼び出し CsPoolfailover**実行ロジックの一部として配置された後の場合も同様です。

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a>特定のプールに対するバックアップの関係についての情報を取得するには

次のコマンドレットを実行します。

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

## <a name="to-force-a-backup-service-sync"></a>バックアップ サービスの同期を強制するには

次のコマンドレットを実行します。

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

## <a name="restore-conference-contents-using-the-backup-service"></a>バックアップ サービスを使用して会議の内容を復元します。 

できるように、ユーザーのホーム プールに、この情報を復元する必要がありますフロント エンド プールのファイル ストアに格納されている会議の情報が使用できなくなった場合、会議のデータを保持します。 会議のデータが失われたが、フロント エンド プールは、別のフロント エンド プールと共に場合、は、データを復元するバックアップ サービスを使用できます。

プール全体が障害が発生し、バックアップ ・ プールには、そのユーザーがフェールオーバーする必要がある場合にも、このタスクを実行する必要があります。 これらのユーザーは、フェールバック、元のプールにときにも、元のプールに、会議のコンテンツをコピーするのにはこの手順を使用する必要があります。

Pool1、Pool2 とペアにし、Pool1 に会議のデータは失われますことを想定しています。 内容を復元するのにバックアップ サービスの起動には、次のコマンドレットを使用できます。

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

会議の内容を復元すると、そのサイズによっては、時間がかかる場合があります。 次のコマンドレットを使用して、プロセスの状態を確認できます。

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

プロセスは、このコマンドレットは、データ会議モジュールの定常状態の値を返す場合に行われます。
