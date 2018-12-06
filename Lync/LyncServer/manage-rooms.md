---
title: ルームの管理
TOCTitle: ルームの管理
ms:assetid: d4835cf4-cd09-4769-a08e-e92706861b64
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205292(v=OCS.15)
ms:contentKeyID: 48273682
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ルームの管理

 

_**トピックの最終更新日:** 2013-02-21_

新しい 常設チャット サーバー ルームを作成するには

    New-CsPersistentChatRoom -Name Foo1 -PersistentChatPoolFqdn client.contoso.com -Category client.contoso.com\Foo [other parameters]


> [!IMPORTANT]
> 次のいずれかが当てはまる場合、-PersistentChatPoolFqdn は必要ありません。 
> <UL>
> <LI>
> <P>常設チャット サーバー プール が 1 つだけ存在する。</P>
> <LI>
> <P>カテゴリにプール FQDN を提供する。</P>
> <LI>
> <P>ルームの追加にプール FQDN を提供する。</P></LI></UL>



既存の 常設チャット サーバー ルームを変更するには

    Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
    Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
    Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}

Windows PowerShell: メンバー、管理者、発表者を同時に設定できます。これらはすべて、ホスト カテゴリの AllowedMembers から DeniedMembers を除いたもののサブセットである必要があります。type=normal であるルームは発表者を含むことはできません。

## ルームの作成、取得、設定、クリア、または削除

新しいルームを作成するには

    New-CsPersistentChatRoom -Name <String> [-PersistentChatPoolFqdn <String>]-Category <String> [-Description <String>] [-Disabled <Switch Parameter>] [-Type <Normal | Auditorium>] [-AddIn <String>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Invitations <Switch Parameter>]

ルームを設定するには

    Set-CsPersistentChatRoom -Identity <String> [-Name <String>] [-Category <String>] [-Description <String>] [-Disabled <boolean>] [-Type <Normal | Auditorium>] [-AddIn <String>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Invitations <Enum>] [-Members <PSListModifier<String>>] [-Managers <PSListModifier<String>>] [-Presenters <PSListModifier<String>>] [-Force < Switch Parameter >] [-Confirm <Switch Parameter>][-WhatIf <Switch Parameter>]

ルームを取得するには

    Get-CsPersistentChatRoom -Identity <String>

または

    Get-CsPersistentChatRoom -filter <String> [-PersistentChatPoolFqdn <String>] [-SearchDescription] [-Member <String>] [-Manager <string>] [-Category <string>] [-Addin <string>] [-Disabled <bool>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Type <ChatRoomType> {Normal | Auditorium}] [-Invitations <ChatRoomInvitations> {False | Inherit}] [-ChatContentExceedsMB <int>] [-ResultSize <int>]

–filter は名前と説明のみをサポートし、名前/説明がキーワード文字列と一致するルームを検索するのに役立ちます。PoolFqdn は指定した 常設チャット サーバー プール内を検索します。

ルームをクリアし、ルームからメッセージをクリアするには

    Clear-CsPersistentChatRoom [-Identity] <string> -EndDate <DateTime> [-WhatIf] [-Confirm]  [<CommonParameters>]

または

    Clear-CsPersistentChatRoom [-Instance] <ChatRoomObject> -EndDate <DateTime> [-WhatIf] [-Confirm] [<CommonParameters>]

ルームを削除するには

    Remove-CsPersistentChatRoom [-Identity] <string> [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

または

    Remove-CsPersistentChatRoom [-Instance] <ChatRoomObject> [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

