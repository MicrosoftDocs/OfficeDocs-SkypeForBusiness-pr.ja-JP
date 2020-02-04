---
title: IM 会話でハイパーリンクを処理するための新しい URL フィルターを作成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a new URL filter to handle hyperlinks in IM conversations
ms:assetid: d0ee01e5-f039-4a34-ac9d-659fe4e9e879
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182590(v=OCS.15)
ms:contentKeyID: 48185426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a7f6cd39034dbc3114f5b89fb15d252b71149762
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740387"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-new-url-filter-in-lync-server-2013-to-handle-hyperlinks-in-im-conversations"></a><span data-ttu-id="3c69d-102">Lync Server 2013 で新しい URL フィルターを作成して、IM 会話のハイパーリンクを処理する</span><span class="sxs-lookup"><span data-stu-id="3c69d-102">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c69d-103">_**最終更新日:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="3c69d-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="3c69d-104">グローバル URL フィルターを変更するだけでなく、Lync Server 2013 展開内の個々のサイトのカスタム URL フィルターを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="3c69d-104">In addition to modifying the global URL filter, you can configure custom URL filters for individual sites within your Lync Server 2013 deployment.</span></span> <span data-ttu-id="3c69d-105">URL フィルタリングの詳細については、「 [Lync Server 2013 でインスタントメッセージング (IM) のファイル転送と URL フィルタリングを構成する](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c69d-105">For details about URL filtering, see [Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span></span>

<div>

## <a name="to-create-a-new-url-filter"></a><span data-ttu-id="3c69d-106">新しい URL フィルターを作成するには</span><span class="sxs-lookup"><span data-stu-id="3c69d-106">To create a new URL filter</span></span>

1.  <span data-ttu-id="3c69d-107">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="3c69d-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3c69d-108">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="3c69d-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3c69d-109">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3c69d-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3c69d-110">左側のナビゲーションバーで、[ **IM とプレゼンス**] をクリックし、[ **URL フィルター**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3c69d-110">In the left navigation bar, click **IM and Presence**, and then click **URL Filter**.</span></span>

4.  <span data-ttu-id="3c69d-111">[ **URL フィルター** ] ページで、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3c69d-111">On the **URL Filter** page, click **New**.</span></span>

5.  <span data-ttu-id="3c69d-112">[**サイトの選択**] で、URL フィルターを作成するサイトをクリックし、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3c69d-112">In **Select a Site**, click the site for which you want to create the URL filter, and then click **OK**.</span></span>

6.  <span data-ttu-id="3c69d-113">[**新しい Url フィルター** ] ダイアログボックスで、[url フィルターを**有効**にする] チェックボックスをオンにして、サイトの url フィルタリングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="3c69d-113">In the **New URL Filter** dialog box, select the **Enable URL Filter** check box to enable URL filtering for the site.</span></span>

7.  <span data-ttu-id="3c69d-114">[ファイルの種類の**編集**] で、[**ブロックするファイルの種類の拡張子**] の下に一覧表示されている拡張子を持つファイルをブロックするには、[**ファイル拡張子を含む url をブロック**する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="3c69d-114">To block any active URL that contains a file with an extension listed under **File type extensions to block** in **Edit File Filter**, select the **Block URLs with file extension** check box.</span></span>

8.  <span data-ttu-id="3c69d-115">[**ハイパーリンクのプレフィックス**] ドロップダウンリストボックスで、インスタントメッセージの会話で url を処理する方法に対応するオプションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3c69d-115">In the **Hyperlink prefix** drop-down list box, click the option that corresponds to how you want to handle URLs in instant message conversations.</span></span>
    
    <span data-ttu-id="3c69d-116">[**許可] メッセージ**ボックスを使用すると、送信が許可されているハイパーリンクを送信するときに、ユーザーに警告メッセージが送信されます。</span><span class="sxs-lookup"><span data-stu-id="3c69d-116">The **Allow message** box enables a warning message to be sent to the user when sending hyperlinks that are allowed to be sent.</span></span>

9.  <span data-ttu-id="3c69d-117">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3c69d-117">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3c69d-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="3c69d-118">See Also</span></span>


[<span data-ttu-id="3c69d-119">Lync Server 2013 でのインスタントメッセージング (IM) のファイル転送と URL フィルタリングの構成</span><span class="sxs-lookup"><span data-stu-id="3c69d-119">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[<span data-ttu-id="3c69d-120">Lync Server 2013 で特定のサイト用の新しいファイル転送フィルターを作成する</span><span class="sxs-lookup"><span data-stu-id="3c69d-120">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[<span data-ttu-id="3c69d-121">Lync Server 2013 で既定のファイル転送フィルターを変更する</span><span class="sxs-lookup"><span data-stu-id="3c69d-121">Modify the default file transfer filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[<span data-ttu-id="3c69d-122">Lync Server 2013 で既定の URL フィルターを変更する</span><span class="sxs-lookup"><span data-stu-id="3c69d-122">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

