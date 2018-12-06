---
title: カテゴリを管理する
TOCTitle: カテゴリを管理する
ms:assetid: 1b118d91-b4c4-4b2f-b842-b451417ec2c6
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204719(v=OCS.15)
ms:contentKeyID: 48271405
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# カテゴリを管理する

 

_**トピックの最終更新日:** 2012-10-06_

新しい 常設チャット サーバー カテゴリを作成するには

    New-CsPersistentChatCategory -Name Foo -PersistentChatPoolFqdn client.contoso1b118d91-b4c4-4b2f-b842-b451417ec2c6.com [other parameters]


> [!IMPORTANT]
> PersistentChatPoolFqdn は、常設チャット サーバー プールが複数ある場合にのみ必要です。



既存の 常設チャット サーバー カテゴリに変更を加えるには

    Set-CsPersistentChatCategory -Identity testCat -AllowedMembers @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}  -DeniedMembers @{Add="sip:user2@contoso.com"}
    Set-CsPersistentChatCategory -Identity testCat -Creators @{Add="sip:user1@contoso.com"}

Windows PowerShell: AllowedMembers、DeniedMembers、および Creators は同時に設定できます。Creators は、AllowedMembers から DeniedMembers を引いたもののサブセットである必要があります。メンバーおよび作成者と同時にカテゴリのプロパティも設定できます。

## カテゴリの作成、取得、設定、または削除

新しいカテゴリを作成するには

    New-CsPersistentChatCategory -Name <String> [-PersistentChatPoolFqdn <String>] [-Description <String>] [-EnableInvitations<Switch Parameter>] [-EnableFileUpload <Switch Parameter>] [-RemoveChatHistory <Switch Parameter>] [-MaxContentSize <Integer>]

カテゴリを取得するには

    Get-CsPersistentChatCategory -Identity <String>

または

    Get-CsPersistentChatCategory -PersistentChatPoolFqdn <String>

カテゴリを設定するには

    Set-CsPersistentChatCategory -Instance <CategoryObject> [-WhatIf] [-Confirm] [<CommonParameters>]

または

    Set-CsPersistentChatCategory [-Identity] <string> [-Name <string>] [-Description <string>] [-Invitations <bool>] [-FileUpload <bool>] [-ChatHistory <bool>] [-AllowedMembers <PSListModifier[string]>] [-DeniedMembers <PSListModifier[string]>] [-Creators <PSListModifier[string]>] [-WhatIf] [-Confirm]  [<CommonParameters>]

カテゴリを削除するには

    Remove-CsPersistentChatCategory -Instance <CategoryObject> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

または

    Remove-CsPersistentChatCategory -Identity <String> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

