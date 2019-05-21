---
title: バックアップ サービスの構成と監視
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype for Business Server 管理シェルコマンドを使用して、バックアップサービスの構成と監視を行うことができます。
ms.openlocfilehash: 2170f58fcc60a648788934048f3d0e6bbfac9c77
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303906"
---
# <a name="configuring-and-monitoring-the-backup-service-in-skype-for-business-server"></a>Skype for Business Server のバックアップサービスの構成と監視

次の Skype for Business Server 管理シェルコマンドを使用して、バックアップサービスの構成と監視を行うことができます。 フロントエンドプールのファイルストアに保存されている会議情報を復元するには、下記の「[バックアップサービスを使って会議コンテンツを復元](#restore-conference-contents-using-the-backup-service)する」を参照してください。

> [!NOTE]  
> RTCUniversalServerAdmins グループは、既定で**Get-CsBackupServiceStatus**を実行する権限を持つ唯一のグループです。 このコマンドレットを使うには、このグループのメンバーとしてログオンします。 または、 **CsBackupServiceConfiguration**コマンドレットを使用して、このコマンドへのアクセス権を他のグループ (たとえば、csadministrator) に付与することができます。

## <a name="to-see-the-backup-service-configuration"></a>バックアップサービスの構成を確認するには

次のコマンドレットを実行します。

    Get-CsBackupServiceConfiguration

SyncInterval の既定値は2分です。

## <a name="to-set-the-backup-service-sync-interval"></a>バックアップサービスの同期間隔を設定するには

次のコマンドレットを実行します。

    Set-CsBackupServiceConfiguration -SyncInterval interval

たとえば、次のように間隔を3分に設定します。

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00


> [!IMPORTANT]  
> バックアップサービスの既定の同期間隔を変更するには、このコマンドレットを使用できますが、同期間隔はバックアップサービスのパフォーマンスと回復ポイントの目標 (RPO) に大きな影響を与えるため、絶対に必要な場合以外は、この操作を行わないでください。

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a>特定のプールのバックアップサービスの状態を取得するには

次のコマンドレットを実行します。

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

> [!NOTE]  
> バックアップサービスの同期状態は、プール (P1) からバックアッププール (P2) にまで1つずつ定義されています。 P1 から P2 への同期状態は、P2 から P1 までと異なる場合があります。 P1 から P2 の場合、P1 で行ったすべての変更が同期間隔で P2 に完全に複製されている場合、バックアップサービスは "定常" 状態になります。 P1 から P2 への同期が必要な変更がない場合は、"最終" 状態になります。 どちらの状態も、コマンドレットが実行された時点でのバックアップサービスのスナップショットを示します。 返される状態が後のままになるというわけではありません。 特に、コマンドレットが実行された後も、P1 が変更を生成しない場合に限り、"final" 状態が保持されます。 これは、p1 が**CsPoolfailover**実行ロジックの一部として読み取り専用モードに配置された後に、P1 を P2 に移行した場合に当てはまります。

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a>特定のプールのバックアップ関係に関する情報を取得するには

次のコマンドレットを実行します。

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

## <a name="to-force-a-backup-service-sync"></a>バックアップサービスを強制的に同期するには

次のコマンドレットを実行します。

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

## <a name="restore-conference-contents-using-the-backup-service"></a>バックアップサービスを使用して会議のコンテンツを復元する 

フロントエンドプールのファイルストアに保存されている会議情報が利用できなくなった場合は、この情報を復元して、プールに所属しているユーザーが会議データを保持するようにする必要があります。 会議データを紛失したフロントエンドプールが別のフロントエンドプールとペアリングされている場合は、バックアップサービスを使ってデータを復元することができます。

また、プール全体で障害が発生し、ユーザーがバックアッププールにフェールオーバーしなければならない場合は、このタスクを実行する必要があります。 これらのユーザーが元のプールにフェールバックされた場合は、この手順を使用して、会議のコンテンツを元のプールにもコピーし直す必要があります。

Pool1 が Pool2 とペアリングされていることを前提としていますが、Pool1 の会議データは失われます。 次のコマンドレットを使用して、バックアップサービスを呼び出して内容を復元できます。

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

会議の内容の復元には、サイズによっては時間がかかる場合があります。 プロセスの状態を確認するには、次のコマンドレットを使用します。

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

プロセスは、このコマンドレットがデータ会議モジュールの安定した状態の値を返すときに実行されます。
