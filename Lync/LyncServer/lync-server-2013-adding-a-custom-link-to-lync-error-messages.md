---
title: 'Lync Server 2013: Lync エラーメッセージへのカスタムリンクの追加'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding a custom link to Lync error messages
ms:assetid: de756088-fcc3-4e47-bde8-4fa4cc852fd1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398979(v=OCS.15)
ms:contentKeyID: 48185607
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 619bdaaa1a1c3b7723f2df9c74e106321bdb054c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521454"
---
# <a name="adding-a-custom-link-to-lync-error-messages-in-lync-server-2013"></a>Lync Server 2013 での Lync エラーメッセージへのカスタムリンクの追加

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-20_

トラブルシューティングまたはヘルプデスクの情報へのリンクを追加して、Lync 2013 エラーメッセージをカスタマイズします。 これを行うには、CustomLinkInErrorMessages パラメーターを使用して、**新しい-csclientpolicy**または**Set-csclientpolicy**   Lync Server 管理シェルコマンドレットを使用します。 カスタムリンクのテキストは、「管理者からのサポートトピックを参照してください」というテキストがあります。カスタマイズすることはできません。

たとえば、次のコマンドを実行すると、すべての Lync 2013 エラーメッセージの脚注領域にカスタムリンクが表示され、リンク先がに設定されます。 http://contoso.com/help/LyncHelpDesk.aspx:

    New-CsClientPolicy -Identity LyncErrorLink -CustomLinkInErrorMessages "http://contoso/help/LyncHelpDesk.aspx"

この新しいポリシーをユーザーに割り当てるには、**Grant-CSClientPolicy** を使用します。 詳細については、「Lync Server Management Shell」のドキュメントの「 **New-CSClientPolicy** 」および「 **Grant-csclientpolicy** 」を参照してください。

</div>

<span> </span>

</div>

</div>

</div>

