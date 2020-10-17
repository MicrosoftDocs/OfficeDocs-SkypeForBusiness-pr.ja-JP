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
ms.openlocfilehash: 466eac15cf75728578e7d517d15ddb222d1c4b70
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521364"
---
# <a name="adding-custom-text-to-instant-messages-in-lync-server-2013"></a>Lync Server 2013 でのインスタントメッセージへのカスタムテキストの追加

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-20_

**新しい-csclientpolicy**または**Set-csclientpolicy** Lync Server 管理シェルコマンドレットを imwarning パラメーター付きで使用して、すべての Lync 2013 インスタントメッセージング (IM) 会話の開始に免責事項または警告を追加します。

以下の例のコマンドを実行すると、新しい IM 会話が開始されるときにはいつでも、[会話] ウィンドウの上部にセキュリティ アラームが追加されます。

    New-CsClientPolicy -Identity IMSecurityNotice -IMWarning 
    "Remember, security is everyone's responsibility. Keep it confidential."

この新しいポリシーをユーザーに割り当てるには、**Grant-CSClientPolicy** を使用します。 詳細については、「Lync Server Management Shell」のドキュメントの「 **New-CSClientPolicy** 」および「 **Grant-csclientpolicy** 」を参照してください。

</div>

<span> </span>

</div>

</div>

</div>

