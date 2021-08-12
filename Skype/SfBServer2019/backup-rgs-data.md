---
title: 2019 年の応答グループ サービス (RGS) データSkype for Business Serverする
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
description: 2019 年に応答グループ サービス (RGS) データをバックアップするSkype for Business Serverします。
ms.openlocfilehash: 8b0cbbb41c7bf2a61d21043141d2475a8c69a79696e8cf5cbde6709e2d196c52
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54280472"
---
# <a name="back-up-response-group-service-rgs-data"></a>応答グループ サービス (RGS) データのバックアップ

2019 Skype for Business Server 7 月の累積的な更新プログラムでは、標準バックアップの一部として RGS データを含める機能が含まれています。

## <a name="rgs-data-replication"></a>RGS データ レプリケーション

RGS データ レプリケーション機能を試す場合は、以下の手順に従ってください。

1. ペアのプールのすべてのフロントエンド (FEs) に 7 月の累積的な更新プログラムをインストールします。
1. ペアのプールの両方のメンバーに RGS データベースをインストールします。
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool1 BackendDatabase FQDN>`
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool2 BackendDatabase FQDN>`
1. 両方のプールで次のコマンドレットを実行して、既存の RGS データをバックアップ テーブルにレプリケートし、RGSBackupService でデータを取得できます。
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool1 FQDN>`
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool2 FQDN>`
1. RGSBackupService を有効にする (これにより、グローバルに RGSBackupService が有効にされます)。 このパラメーターが true に設定されている場合、RGSBackupService はペアのプールで RGS データの同期を開始します (両方のプールは CU1 である必要があります)。 開始するまで数分待ちます。 最初は、RGS BackupService の状態は NotInitialized になります。
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 1`
1. BackupServiceStatus を確認するには、次の操作を行います。
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
1. プール間で DataReplication を確認するには、次のコマンドレットを使用します (これらのコマンドレットでは、所有者プール のデータのみを表示します)。
    - `Get-csRGSWorkflow`
    - `Get-csRGSQueue`
    - `Get-csRGSAgentGroup`
    - `Get-csRGSHourOfBusiness`
    - `Get-csRGSHolidaySet`
1. 所有者プール RGS データとそのバックアップ データを確認するには、次の操作を行います。
    - `Get-csRGSWorkflow -showAll`
    - `Get-csRGSQueue  -showAll`
    - `Get-csRGSAgentGroup -showAll`
    - `Get-csRGSHourOfBusiness -showAll`
    - `Get-csRGSHolidaySet -showAll`
1. ワークフローに音声通話を行って、ワークフローの機能を確認します。
1. RGS 所有者プールをフェールオーバーします。
1. ワークフローに音声通話を行って、ワークフローの機能を確認します。
1. プールをフェールバックします。
1. ソース プール上の RGS Data を更新し、別のフェールオーバーを実行して、変更がバックアップ プールに反映されるのを確認します。 RGS は、フェールオーバー前の動作と同じように動作する必要があります。

> [!TIP]
> これらの手順は、大量のデータに対して実行し、フェールオーバーとフェールバックを頻繁に実行する必要があります。 この CU 更新プログラムの後に作成された新しい RGS もレプリケートする必要があります。

## <a name="rgs-cmdlets"></a>RGS コマンドレット

- BackupServiceStatus を確認するには (エクスポートの状態は、Final または Steady 状態である必要があります。 インポートの状態は[標準]状態である必要があります。 RGSBackupservice を有効にする必要があります。
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
- バックアップ プールの RGS データを完全に同期するには (バックアップ プールの完全な RGS データを同期します)。
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSDataStore`
- バックアップ プール上の RGS ファイルストアを完全に同期するには (バックアップ プールの完全な RGS データを同期します)。
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSFileStore`
- バックアップ プールで RGS デルタ データを同期するには (RGS の場合のみ、バックアップ プールのデルタ データを同期します)。
    - `Backup-CsPool -PoolFqdn <Pool FQDN> -Category RGS`
- RGS を含むすべてのモジュール データを同期するには、次の方法を実行します。
    - `Backup-CsPool -PoolFqdn <Pool FQDN>`
- RGSBackupService を無効にするには (これにより、RGSBackupService がグローバルに無効にされます)。 このパラメーターを true に設定すると、すべてのペアプールで RGSBackupService が無効になります。
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 0`
