---
title: 'Lync Server 2013: バックアップ サービスを使用した会議コンテンツの復元'
TOCTitle: バックアップ サービスを使用した会議コンテンツの復元
ms:assetid: 3e0f18ec-7319-4c07-a59b-2938e7787bc9
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688030(v=OCS.15)
ms:contentKeyID: 49886926
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのバックアップ サービスを使用した会議コンテンツの復元

 

_**トピックの最終更新日:** 2012-11-01_

フロントエンド プールのファイル ストアに格納されている会議情報が使用できなくなった場合は、この情報を復元する必要があります。これにより、プールのユーザーが会議データを保持できます。会議データを失ったフロントエンド プールと他のフロントエンド プールがペアになっている場合は、バックアップ サービスを使用してデータを復元できます。

プール全体で障害が発生し、ユーザーをバックアップ プールにフェールオーバーする必要がある場合も、このタスクを実行します。これらのユーザーが元のプールにフェールオーバーされるときに、この手順を使用して、会議コンテンツも元のプールにコピーする必要があります。

Pool1 と Pool2 がペアで、Pool1 の会議データが失われたとします。次のコマンドレットを使用すると、バックアップ サービスを呼び出して、contentsL を復元できます。

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

会議コンテンツのサイズによっては、コンテンツを復元するのに時間がかかる場合があります。次のコマンドレットを使用すると、プロセスの状態を確認できます。

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

このコマンドレットがデータ会議モジュールに対して安定状態の値を返すと、プロセスは完了です。

