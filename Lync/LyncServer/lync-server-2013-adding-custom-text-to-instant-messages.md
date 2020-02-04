---
title: 'Lync Server 2013: インスタント メッセージへのユーザー設定テキストの追加'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding custom text to instant messages
ms:assetid: cabcc3ec-9d35-42ac-a403-e21b7d538c2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398847(v=OCS.15)
ms:contentKeyID: 48185458
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b54b4724568a4f57bebc7ef6162a553cfdd9a091
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738157"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-custom-text-to-instant-messages-in-lync-server-2013"></a><span data-ttu-id="6da69-102">Lync Server 2013 でのインスタント メッセージへのユーザー設定テキストの追加</span><span class="sxs-lookup"><span data-stu-id="6da69-102">Adding custom text to instant messages in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6da69-103">_**トピックの最終更新日:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="6da69-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="6da69-104">**新しい CSClientPolicy**を使用するか、または imwarning パラメーターを使用し**て、すべて**の lync 2013 インスタントメッセージング (IM) 会話の先頭に免責事項または警告を追加します。</span><span class="sxs-lookup"><span data-stu-id="6da69-104">Add a disclaimer or warning to the beginning of every Lync 2013 instant messaging (IM) conversation by using the **New-CSClientPolicy** or **Set-CSClientPolicy** Lync Server Management Shell cmdlets with the IMWarning parameter.</span></span>

<span data-ttu-id="6da69-105">次の例のコマンドは、新しい IM の会話が開始されるたびに、会話ウィンドウの上部にセキュリティリマインダーを追加します。</span><span class="sxs-lookup"><span data-stu-id="6da69-105">The command in the following example adds a security reminder at the top of the Conversation window whenever a new IM conversation begins:</span></span>

    New-CsClientPolicy -Identity IMSecurityNotice -IMWarning 
    "Remember, security is everyone's responsibility. Keep it confidential."

<span data-ttu-id="6da69-106">ユーザーにこの新しいポリシーを割り当てるには **、グラント Clientpolicy**を使用します。</span><span class="sxs-lookup"><span data-stu-id="6da69-106">Use **Grant-CSClientPolicy** to assign this new policy to users.</span></span> <span data-ttu-id="6da69-107">詳細については、「**新しい-CSClientPolicy** 」と「Lync Server 管理シェルドキュメントの**権限を付与**する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6da69-107">For details, see **New-CSClientPolicy** and **Grant-CSClientPolicy** in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

