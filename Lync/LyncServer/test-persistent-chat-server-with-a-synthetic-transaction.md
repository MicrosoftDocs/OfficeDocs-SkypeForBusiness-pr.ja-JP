---
title: 代理トランザクションを使用した常設チャット サーバー のテスト
TOCTitle: 代理トランザクションを使用した常設チャット サーバー のテスト
ms:assetid: 414e43f3-0074-4ecf-a232-398de972cb24
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204837(v=OCS.15)
ms:contentKeyID: 48271899
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 代理トランザクションを使用した常設チャット サーバー のテスト

 

_**トピックの最終更新日:** 2012-09-21_

常設チャット サーバーで、チャット ルームでの 2 人のユーザー間のメッセージの送受信をテストするには

    Test-CsPersistentChatMessage [-Authentication <TrustedServer | Negotiate | ClientCertificate | 
        LiveID>] [-ReceiverSipAddress <String>] [-RegistrarPort <Int32>] [-SenderSipAddress <String>] -TargetFqdn <String> [-Force <SwitchParameter>] [-OutLoggerVariable <String>] 
        [-OutVerboseVariable <String>] [<CommonParameters>]

または

    Test-CsPersistentChatMessage [-Authentication <TrustedServer | Negotiate | ClientCertificate | 
        LiveID>] -ReceiverCredential <PSCredential> -ReceiverSipAddress <String> [-RegistrarPort 
        <Int32>] -SenderCredential <PSCredential> -SenderSipAddress <String> [-TargetFqdn <String>] [-Force <SwitchParameter>] [-OutLoggerVariable <String>] [-OutVerboseVariable <String>] [<CommonParameters>]

または

    Test-CsPersistentChatMessage [-Authentication <TrustedServer | Negotiate | ClientCertificate | 
        LiveID>] [-Force <SwitchParameter>] [-OutLoggerVariable <String>] [-OutVerboseVariable 
        <String>] [<CommonParameters>]

