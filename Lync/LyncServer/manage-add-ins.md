---
title: アドインの管理
TOCTitle: アドインの管理
ms:assetid: b84f868e-b36e-4ab4-b284-7db212d401c3
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205193(v=OCS.15)
ms:contentKeyID: 48273389
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# アドインの管理

 

_**トピックの最終更新日:** 2012-10-06_

新しい 常設チャット サーバー アドインを作成するには

    New-CsPersistentChatAddin -Name Contoso -PersistentChatPoolFqdn client.contoso.com -Url http://contoso.com 

## アドインの作成、取得、設定、削除

新しいアドインを作成するには

    New-CsPersistentChatAddin -PersistentChatPoolFqdn <String> -Name <String> -Url<String>


> [!IMPORTANT]
> PersistentChatPoolFqdn &lt;文字列&gt; は、複数の 常設チャット サーバー プールがある場合にのみ必要です。



アドインを取得するには

    Get-CsPersistentChatAddin -Identity <String>]

または

    Get-CsPersistentChatAddin -PersistentChatPoolFqdn <String>

アドインを設定するには

    Set-CsPersistentChatAddIn -Instance <AddinObject> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

または

    Set-CsPersistentChatAddIn -Identity <String> [-Name <String>] [-Url<String>] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

アドインを削除するには

    Remove-CsPersistentChatAddIn -Instance <AddinObject> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

または

    Remove-CsPersistentChatAddIn -Identity <String> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

