---
title: 代理トランザクションを使用した常設チャット サーバー のテスト
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Test Persistent Chat Server with a synthetic transaction
ms:assetid: 414e43f3-0074-4ecf-a232-398de972cb24
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204837(v=OCS.15)
ms:contentKeyID: 48183968
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46fc445032be5a512883fb63437e295188bc0e0f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763621"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-persistent-chat-server-with-a-synthetic-transaction"></a><span data-ttu-id="5482c-102">代理トランザクションを使用した常設チャット サーバー のテスト</span><span class="sxs-lookup"><span data-stu-id="5482c-102">Test Persistent Chat Server with a synthetic transaction</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5482c-103">_**最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="5482c-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="5482c-104">2人のユーザー間のチャットルームでメッセージを送受信するための常設チャットサーバーをテストするには</span><span class="sxs-lookup"><span data-stu-id="5482c-104">To test Persistent Chat Server for sending and receiving messages in a chat room between two users</span></span>

    Test-CsPersistentChatMessage [-Authentication <TrustedServer | Negotiate | ClientCertificate | 
        LiveID>] [-ReceiverSipAddress <String>] [-RegistrarPort <Int32>] [-SenderSipAddress <String>] -TargetFqdn <String> [-Force <SwitchParameter>] [-OutLoggerVariable <String>] 
        [-OutVerboseVariable <String>] [<CommonParameters>]

<span data-ttu-id="5482c-105">または</span><span class="sxs-lookup"><span data-stu-id="5482c-105">or</span></span>

    Test-CsPersistentChatMessage [-Authentication <TrustedServer | Negotiate | ClientCertificate | 
        LiveID>] -ReceiverCredential <PSCredential> -ReceiverSipAddress <String> [-RegistrarPort 
        <Int32>] -SenderCredential <PSCredential> -SenderSipAddress <String> [-TargetFqdn <String>] [-Force <SwitchParameter>] [-OutLoggerVariable <String>] [-OutVerboseVariable <String>] [<CommonParameters>]

<span data-ttu-id="5482c-106">または</span><span class="sxs-lookup"><span data-stu-id="5482c-106">or</span></span>

    Test-CsPersistentChatMessage [-Authentication <TrustedServer | Negotiate | ClientCertificate | 
        LiveID>] [-Force <SwitchParameter>] [-OutLoggerVariable <String>] [-OutVerboseVariable 
        <String>] [<CommonParameters>]

</div>

<span> </span>

</div>

</div>

</div>

