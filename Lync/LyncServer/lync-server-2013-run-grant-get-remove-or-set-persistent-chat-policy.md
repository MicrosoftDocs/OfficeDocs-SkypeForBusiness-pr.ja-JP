---
title: 'Lync Server 2013: 常設チャット ポリシーを実行、付与、削除、または設定する'
TOCTitle: 常設チャット ポリシーを実行、付与、削除、または設定する
ms:assetid: 39ccdbe8-fb3d-47bc-96e2-9486b6d317e0
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204810(v=OCS.15)
ms:contentKeyID: 48271808
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 で常設チャット ポリシーを実行、付与、削除、または設定する

 

_**トピックの最終更新日:** 2012-10-01_

新しい 常設チャット ポリシーを作成するには

    New-CsPersistentChatPolicy -Identity <XdsIdentity> [-Enable <Switch Parameter>] [-Confirm <Switch Parameter>] [-Force <Switch Parameter>] [-WhatIf <Switch Parameter>] [-InMemory <Switch Parameter>]

常設チャット ポリシーを付与するには

    Grant-CsPersistentChatPolicy -Identity <UserIdParameter> -PolicyName <String> [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

常設チャット ポリシーを取得するには

    Get-CsPersistentChatPolicy [-Identity <XdsIdentity>] [-Filter <String>] [-LocalStore <Switch Parameter>]

常設チャット ポリシーを削除するには

    Remove-CsPersistentChatPolicy -Identity <XdsIdentity> [-Confirm <Switch Parameter>] [-Force <Switch Parameter>] [-WhatIf <Switch Parameter>]

常設チャット ポリシーを設定するには

    Set-CsPersistentChatPolicy [-Identity <XdsIdentity>] [-Instance < PSObject>]

