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
# <a name="adding-a-custom-link-to-lync-error-messages-in-lync-server-2013"></a><span data-ttu-id="ecf82-102">Lync Server 2013 での Lync エラーメッセージへのカスタムリンクの追加</span><span class="sxs-lookup"><span data-stu-id="ecf82-102">Adding a custom link to Lync error messages in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ecf82-103">_**トピックの最終更新日:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="ecf82-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="ecf82-104">トラブルシューティングまたはヘルプデスクの情報へのリンクを追加して、Lync 2013 エラーメッセージをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="ecf82-104">Customize Lync 2013 error messages by adding a link to your own troubleshooting or help desk information.</span></span> <span data-ttu-id="ecf82-105">これを行うには、CustomLinkInErrorMessages パラメーターを使用して、**新しい-csclientpolicy**または**Set-csclientpolicy**   Lync Server 管理シェルコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="ecf82-105">To do this, use the **New-CSClientPolicy** or **Set-CSClientPolicy** Lync Server Management Shell cmdlets with the CustomLinkInErrorMessages parameter.</span></span> <span data-ttu-id="ecf82-106">カスタムリンクのテキストは、「管理者からのサポートトピックを参照してください」というテキストがあります。カスタマイズすることはできません。</span><span class="sxs-lookup"><span data-stu-id="ecf82-106">The text of the custom link is "Click here for support topics from your administrator," and it cannot be customized.</span></span>

<span data-ttu-id="ecf82-107">たとえば、次のコマンドを実行すると、すべての Lync 2013 エラーメッセージの脚注領域にカスタムリンクが表示され、リンク先がに設定されます。 http://contoso.com/help/LyncHelpDesk.aspx:</span><span class="sxs-lookup"><span data-stu-id="ecf82-107">For example, the following command causes the custom link to appear in the footnote area of every Lync 2013 error message and sets the link destination to http://contoso.com/help/LyncHelpDesk.aspx:</span></span>

    New-CsClientPolicy -Identity LyncErrorLink -CustomLinkInErrorMessages "http://contoso/help/LyncHelpDesk.aspx"

<span data-ttu-id="ecf82-108">この新しいポリシーをユーザーに割り当てるには、**Grant-CSClientPolicy** を使用します。</span><span class="sxs-lookup"><span data-stu-id="ecf82-108">Use **Grant-CSClientPolicy** to assign this new policy to users.</span></span> <span data-ttu-id="ecf82-109">詳細については、「Lync Server Management Shell」のドキュメントの「 **New-CSClientPolicy** 」および「 **Grant-csclientpolicy** 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ecf82-109">For details, see **New-CSClientPolicy** and **Grant-CSClientPolicy** in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

