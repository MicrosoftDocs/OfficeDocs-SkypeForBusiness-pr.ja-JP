---
title: 'Lync Server 2013: 常設チャット サーバーの構成'
TOCTitle: 常設チャット サーバーの構成
ms:assetid: 85028aff-a38e-4748-958e-59e707a47532
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205054(v=OCS.15)
ms:contentKeyID: 48272767
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での常設チャット サーバーの構成

 

_**トピックの最終更新日:** 2012-10-06_

常設チャット の新しい構成を作成するには

    New-CsPersistentChatConfiguration -Identity <XdsIdentity> [-DefaultChatHistory <Integer>] [-MaxChatContentSizeMB <Integer>] [-MaxFileSizeKB <Integer>] [-ParticipantUpdateLimit <Integer>] [-FileServiceUrl <UrlForFileUpload>] [-RoomManagementUrl <RoomManagementUrl>] [-Instance <PSObject>] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

常設チャット構成を取得するには

    Get-CsPersistentChatConfiguration [-LocalStore <Switch Parameter>] [-Identity <XdsIdentity>]

常設チャット構成を削除するには

    Remove-CsPersistentChatConfiguration -Identity <XdsIdentity>

常設チャット構成を設定するには

    Set-CsPersistentChatConfiguration [-DefaultChatHistory <Integer>] [-MaxChatContentSizeMB <Integer>] [-MaxFileSizeKB <Integer>] [-ParticipantUpdateLimit <Integer>] [-FileServiceUrl <UrlForFileUpload>] [-RoomManagementUrl <RoomManagementUrl>] [-Instance <PSObject >] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

Lync Server 2013 の場合、すべての Web サービス トラフィックが Lync Server 2013フロント エンド サーバーでサポートされます。したがって、常設チャット サーバーの gcweb01 アドレスは不要です。ただし、(リモート ユーザーの "外部" Web サイトにではなく) "内部" Web サイトに対してのみファイル アップロード/ダウンロード Web サービスを提供しているため、現在も、内部 Web サービス アクセスをサポートしています。

