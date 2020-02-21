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
ms.openlocfilehash: aa65580cd9138b58792d4a0f0621bfe6f5f10c9c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191390"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="adding-a-custom-link-to-lync-error-messages-in-lync-server-2013"></a>Lync Server 2013 での Lync エラーメッセージへのカスタムリンクの追加

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-20_

トラブルシューティングまたはヘルプデスクの情報へのリンクを追加して、Lync 2013 エラーメッセージをカスタマイズします。 これを行うには、CustomLinkInErrorMessages パラメーターを使用して、**新しい-csclientpolicy**または**Set-csclientpolicy** Lync Server 管理シェルコマンドレットを使用します。 カスタムリンクのテキストは、「管理者からのサポートトピックを参照してください」というテキストがあります。カスタマイズすることはできません。

たとえば、次のコマンドを実行すると、すべての Lync 2013 エラーメッセージの脚注領域にカスタムリンクが表示され、リンク先がに設定されます。http://contoso.com/help/LyncHelpDesk.aspx:

    New-CsClientPolicy -Identity LyncErrorLink -CustomLinkInErrorMessages "http://contoso/help/LyncHelpDesk.aspx"

この新しいポリシーをユーザーに割り当てるには、**Grant-CSClientPolicy** を使用します。 詳細については、「Lync Server Management Shell」のドキュメントの「 **New-CSClientPolicy** 」および「 **Grant-csclientpolicy** 」を参照してください。

</div>

<span> </span>

</div>

</div>

</div>

