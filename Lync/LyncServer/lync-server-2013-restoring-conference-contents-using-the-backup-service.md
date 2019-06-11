---
title: 'Lync Server 2013: バックアップ サービスを使用した会議コンテンツの復元'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring conference contents using the Backup Service
ms:assetid: 3e0f18ec-7319-4c07-a59b-2938e7787bc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688030(v=OCS.15)
ms:contentKeyID: 49733620
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14ee33f24f7b1a58812db146901695cba1ae05f2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822945"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-conference-contents-using-the-backup-service-in-lync-server-2013"></a>Lync Server 2013 でのバックアップ サービスを使用した会議コンテンツの復元

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-01_

フロントエンドプールのファイルストアに保存されている会議情報が利用できなくなった場合。 この情報を復元すると、プールをホームにしているユーザーが会議データを保持するようになります。 会議データを紛失したフロントエンドプールが別のフロントエンドプールとペアリングされている場合は、バックアップサービスを使ってデータを復元することができます。

また、プール全体で障害が発生し、ユーザーがバックアッププールにフェールオーバーしなければならない場合は、このタスクを実行する必要があります。 これらのユーザーが元のプールにフェールバックされた場合は、この手順を使用して、会議のコンテンツを元のプールにもコピーし直す必要があります。

Pool1 が Pool2 とペアリングされていることを前提としていますが、Pool1 の会議データは失われます。 次のコマンドレットを使用して、バックアップサービスを呼び出して内容を復元できます。

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

会議の内容の復元には、サイズによっては時間がかかる場合があります。 プロセスの状態を確認するには、次のコマンドレットを使用します。

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

プロセスは、このコマンドレットがデータ会議モジュールの安定した状態の値を返すときに実行されます。

</div>

<span> </span>

</div>

</div>

</div>

