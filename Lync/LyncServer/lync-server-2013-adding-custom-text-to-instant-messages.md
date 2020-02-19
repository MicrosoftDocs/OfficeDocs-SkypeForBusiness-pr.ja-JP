---
title: 'Lync Server 2013: インスタントメッセージへのカスタムテキストの追加'
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
ms.openlocfilehash: 82ebaaaa693248cd11ebcb663692fa2805cdce20
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137878"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="adding-custom-text-to-instant-messages-in-lync-server-2013"></a><span data-ttu-id="00eae-102">Lync Server 2013 でのインスタントメッセージへのカスタムテキストの追加</span><span class="sxs-lookup"><span data-stu-id="00eae-102">Adding custom text to instant messages in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="00eae-103">_**トピックの最終更新日:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="00eae-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="00eae-104">**新しい-csclientpolicy**または**Set-csclientpolicy** Lync Server 管理シェルコマンドレットを imwarning パラメーター付きで使用して、すべての Lync 2013 インスタントメッセージング (IM) 会話の開始に免責事項または警告を追加します。</span><span class="sxs-lookup"><span data-stu-id="00eae-104">Add a disclaimer or warning to the beginning of every Lync 2013 instant messaging (IM) conversation by using the **New-CSClientPolicy** or **Set-CSClientPolicy** Lync Server Management Shell cmdlets with the IMWarning parameter.</span></span>

<span data-ttu-id="00eae-105">以下の例のコマンドを実行すると、新しい IM 会話が開始されるときにはいつでも、[会話] ウィンドウの上部にセキュリティ アラームが追加されます。</span><span class="sxs-lookup"><span data-stu-id="00eae-105">The command in the following example adds a security reminder at the top of the Conversation window whenever a new IM conversation begins:</span></span>

    New-CsClientPolicy -Identity IMSecurityNotice -IMWarning 
    "Remember, security is everyone's responsibility. Keep it confidential."

<span data-ttu-id="00eae-106">この新しいポリシーをユーザーに割り当てるには、**Grant-CSClientPolicy** を使用します。</span><span class="sxs-lookup"><span data-stu-id="00eae-106">Use **Grant-CSClientPolicy** to assign this new policy to users.</span></span> <span data-ttu-id="00eae-107">詳細については、「Lync Server Management Shell」のドキュメントの「 **New-CSClientPolicy** 」および「 **Grant-csclientpolicy** 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00eae-107">For details, see **New-CSClientPolicy** and **Grant-CSClientPolicy** in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

