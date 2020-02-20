---
title: 'Lync Server 2013: バックアップサービスを使用した会議コンテンツの復元'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring conference contents using the Backup Service
ms:assetid: 3e0f18ec-7319-4c07-a59b-2938e7787bc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688030(v=OCS.15)
ms:contentKeyID: 49733620
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3aab42110bf1bf8eaafcebeddcd3acd168a80e4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144693"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-conference-contents-using-the-backup-service-in-lync-server-2013"></a>Lync Server 2013 でのバックアップサービスを使用した会議コンテンツの復元

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

フロントエンド プールのファイル ストアに格納されている会議情報が使用できなくなった場合は、この情報を復元する必要があります。これにより、プールのユーザーが会議データを保持できます。会議データを失ったフロントエンド プールと他のフロントエンド プールがペアになっている場合は、バックアップ サービスを使用してデータを復元できます。

プール全体で障害が発生し、ユーザーをバックアップ プールにフェールオーバーする必要がある場合も、このタスクを実行します。これらのユーザーが元のプールにフェールオーバーされるときに、この手順を使用して、会議コンテンツも元のプールにコピーする必要があります。

Pool1 と Pool2 がペアで、Pool1 の会議データが失われたとします。 次のコマンドレットを使用して、バックアップサービスを呼び出してコンテンツを復元できます。

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

会議コンテンツのサイズによっては、コンテンツを復元するのに時間がかかる場合があります。次のコマンドレットを使用すると、プロセスの状態を確認できます。

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

このコマンドレットがデータ会議モジュールに対して安定状態の値を返すと、プロセスは完了です。

</div>

<span> </span>

</div>

</div>

</div>

