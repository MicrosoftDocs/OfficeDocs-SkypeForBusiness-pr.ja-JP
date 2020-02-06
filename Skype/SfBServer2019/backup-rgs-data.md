---
title: Skype for Business Server 2019 での応答グループサービス (RGS) データのバックアップ
ms.reviewer: rogupta
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.date: 07/22/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: Skype for Business Server 2019 で応答グループサービス (RGS) データをバックアップする方法について説明します。
ms.openlocfilehash: f9c62953dcb859be2aa34bdee84ca76e3303d738
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824071"
---
# <a name="back-up-response-group-service-rgs-data"></a>応答グループサービス (RGS) データをバックアップする

Skype for Business Server 2019 年7月の累積更新プログラムでは、標準バックアップの一部として RGS データを含める機能が含まれています。

## <a name="rgs-data-replication"></a>RGS データレプリケーション

RG データレプリケーション機能を試すには、次の手順に従ってください。

1. ペアリングされたプールのすべてのフロントエンド (FEs) に、7月の累積更新プログラムをインストールします。
1. ペアリングされたプールの両方のメンバーに RGS データベースをインストールします。
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool1 BackendDatabase FQDN>`
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool2 BackendDatabase FQDN>`
1. 次のコマンドレットを両方のプールで実行して、RGSBackupService でデータを取得できるように、既存の RGS データをバックアップテーブルに複製します。
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool1 FQDN>`
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool2 FQDN>`
1. RGSBackupService を有効にします (これにより RGSBackupService がグローバルに有効になります。 このパラメーターが true に設定されている場合は、RGSBackupService によってペアプール上の RG データの同期が開始されます (どちらのプールも CU1 である必要があります)。 数分待ってから開始してください。 最初に、RGS BackupService の状態は初期化されません。):
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 1`
1. BackupServiceStatus を確認するには:
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
1. プール間で DataReplication を確認するには、次のコマンドレットを使用します (これらのコマンドレットは、所有者プールデータのみを示します)。
    - `Get-csRGSWorkflow`
    - `Get-csRGSQueue`
    - `Get-csRGSAgentGroup`
    - `Get-csRGSHourOfBusiness`
    - `Get-csRGSHolidaySet`
1. 所有者プール RG データとそのバックアップデータを確認するには、次の操作を行います。
    - `Get-csRGSWorkflow -showAll`
    - `Get-csRGSQueue  -showAll`
    - `Get-csRGSAgentGroup -showAll`
    - `Get-csRGSHourOfBusiness -showAll`
    - `Get-csRGSHolidaySet -showAll`
1. ワークフローへの音声通話を行うことによってワークフローの機能を確認します。
1. RG 所有者プールをフェールオーバーします。
1. ワークフローへの音声通話を行うことによってワークフローの機能を確認します。
1. プールをフェイルバックします。
1. ソースプールの RGS データを更新し、別のフェールオーバーを実行して、変更がバックアッププールに反映されていることを確認します。 RGS は、フェールオーバー前に動作していたときと同じように動作する必要があります。

> [!TIP]
> これらの手順は大量のデータに対して実行することをお勧めし、フェールオーバーと failbacks を頻繁に行うことをお勧めします。 この CU 更新後に作成されたすべての新しい RG も複製する必要があります。

## <a name="rgs-cmdlets"></a>RGS コマンドレット

- BackupServiceStatus を確認するには、エクスポートの状態が最終または定常状態である必要があります。 インポートの状態は、通常の状態である必要があります。 RGSBackupservice を有効にする必要があります。):
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
- バックアッププールの RGS データを完全に同期するには (これにより、バックアッププール上の完全な RGS データが同期されます):
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSDataStore`
- バックアッププールの RGS filestore を完全に同期するには (これにより、バックアッププール上の完全な RG データが同期されます):
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSFileStore`
- バックアッププール上の RGS デルタデータを同期するには (これにより、RG のバックアッププールの差分データのみが同期されます):
    - `Backup-CsPool -PoolFqdn <Pool FQDN> -Category RGS`
- RGS を含むすべてのモジュールデータを同期するには、次の操作を行います。
    - `Backup-CsPool -PoolFqdn <Pool FQDN>`
- RGSBackupService を無効にするには、RGSBackupService をグローバルに無効にします。 このパラメーターが true に設定されている場合、RGSBackupService はすべてのペアプールで無効になります。):
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 0`
