---
title: 'Lync Server 2013: Lync エラー メッセージへのユーザー設定リンクの追加'
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
ms.openlocfilehash: 63523013d8df74a52fee307192d3f60eb5232121
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738207"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-a-custom-link-to-lync-error-messages-in-lync-server-2013"></a><span data-ttu-id="cad85-102">Lync Server 2013 での Lync エラー メッセージへのユーザー設定リンクの追加</span><span class="sxs-lookup"><span data-stu-id="cad85-102">Adding a custom link to Lync error messages in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cad85-103">_**トピックの最終更新日:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="cad85-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="cad85-104">トラブルシューティングまたはヘルプデスクの情報へのリンクを追加して、Lync 2013 のエラーメッセージをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="cad85-104">Customize Lync 2013 error messages by adding a link to your own troubleshooting or help desk information.</span></span> <span data-ttu-id="cad85-105">これを行うには、CustomLinkInErrorMessages パラメーターを使用して、**新しい csclientpolicy**または**Set-csclientpolicy** Lync Server Management Shell コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="cad85-105">To do this, use the **New-CSClientPolicy** or **Set-CSClientPolicy** Lync Server Management Shell cmdlets with the CustomLinkInErrorMessages parameter.</span></span> <span data-ttu-id="cad85-106">カスタムリンクのテキストは、「管理者からのサポートトピックをここでクリックしてください」というテキストが表示され、カスタマイズすることはできません。</span><span class="sxs-lookup"><span data-stu-id="cad85-106">The text of the custom link is "Click here for support topics from your administrator," and it cannot be customized.</span></span>

<span data-ttu-id="cad85-107">たとえば、次のコマンドを実行すると、すべての Lync 2013 エラーメッセージの [脚注] 領域にユーザー設定のリンクが表示され、リンク先が次のように設定されます。http://contoso.com/help/LyncHelpDesk.aspx:</span><span class="sxs-lookup"><span data-stu-id="cad85-107">For example, the following command causes the custom link to appear in the footnote area of every Lync 2013 error message and sets the link destination to http://contoso.com/help/LyncHelpDesk.aspx:</span></span>

    New-CsClientPolicy -Identity LyncErrorLink -CustomLinkInErrorMessages "http://contoso/help/LyncHelpDesk.aspx"

<span data-ttu-id="cad85-108">ユーザーにこの新しいポリシーを割り当てるには **、グラント Clientpolicy**を使用します。</span><span class="sxs-lookup"><span data-stu-id="cad85-108">Use **Grant-CSClientPolicy** to assign this new policy to users.</span></span> <span data-ttu-id="cad85-109">詳細については、「**新しい-CSClientPolicy** 」と「Lync Server 管理シェルドキュメントの**権限を付与**する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cad85-109">For details, see **New-CSClientPolicy** and **Grant-CSClientPolicy** in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

