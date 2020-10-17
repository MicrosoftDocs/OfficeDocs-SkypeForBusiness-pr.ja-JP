---
title: IM 会話でのハイパーリンクを処理するための新しい URL フィルターを作成する
description: IM 会話内のハイパーリンクを処理するための新しい URL フィルターを作成します。
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
ms.openlocfilehash: 6e583b3e8cbd04279ab7f54b4138a349fa0d1e85
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554663"
---
# <a name="create-a-new-url-filter-in-lync-server-2013-to-handle-hyperlinks-in-im-conversations"></a><span data-ttu-id="60af4-103">IM 会話でのハイパーリンクを処理するために Lync Server 2013 で新しい URL フィルターを作成する</span><span class="sxs-lookup"><span data-stu-id="60af4-103">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60af4-104">_**トピックの最終更新日:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="60af4-104">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="60af4-105">グローバル URL フィルターを変更するだけでなく、Lync Server 2013 展開内の個々のサイトに対してカスタム URL フィルターを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="60af4-105">In addition to modifying the global URL filter, you can configure custom URL filters for individual sites within your Lync Server 2013 deployment.</span></span> <span data-ttu-id="60af4-106">URL フィルターの詳細については、「 [Lync Server 2013 でインスタントメッセージング (IM) のファイル転送と url フィルターを構成する](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60af4-106">For details about URL filtering, see [Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span></span>

<div>

## <a name="to-create-a-new-url-filter"></a><span data-ttu-id="60af4-107">新しい URL フィルターを作成するには</span><span class="sxs-lookup"><span data-stu-id="60af4-107">To create a new URL filter</span></span>

1.  <span data-ttu-id="60af4-108">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="60af4-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="60af4-109">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="60af4-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="60af4-110">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60af4-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="60af4-111">左側のナビゲーション バーで [**IM とプレゼンス**] をクリックし、[**URL フィルター**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="60af4-111">In the left navigation bar, click **IM and Presence**, and then click **URL Filter**.</span></span>

4.  <span data-ttu-id="60af4-112">[**URL フィルター**] ページで [**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="60af4-112">On the **URL Filter** page, click **New**.</span></span>

5.  <span data-ttu-id="60af4-113">[**サイトの選択**] で URL フィルターを作成するサイトをクリックしてから、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="60af4-113">In **Select a Site**, click the site for which you want to create the URL filter, and then click **OK**.</span></span>

6.  <span data-ttu-id="60af4-114">[**新しい URL フィルター**] ダイアログ ボックスで、[**URL フィルターを有効にする**] チェック ボックスをオンにして、サイトの URL フィルターを有効にします。</span><span class="sxs-lookup"><span data-stu-id="60af4-114">In the **New URL Filter** dialog box, select the **Enable URL Filter** check box to enable URL filtering for the site.</span></span>

7.  <span data-ttu-id="60af4-115">[**ファイル フィルタの編集**] の [**禁止するファイル拡張子の種類**] に一覧表示されている拡張子を持つファイルを含むすべてのアクティブな URL を禁止するには、[**ファイル拡張子を持つ URL を禁止する**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="60af4-115">To block any active URL that contains a file with an extension listed under **File type extensions to block** in **Edit File Filter**, select the **Block URLs with file extension** check box.</span></span>

8.  <span data-ttu-id="60af4-116">[**ハイパーリンクのプレフィックス**] ドロップダウン リスト ボックスで、インスタント メッセージ会話内の URL の処理方法に対応するオプションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="60af4-116">In the **Hyperlink prefix** drop-down list box, click the option that corresponds to how you want to handle URLs in instant message conversations.</span></span>
    
    <span data-ttu-id="60af4-117">[**メッセージを許可**] ボックスでは、送信が許可されているハイパーリンクの送信時に、ユーザーに対して警告メッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="60af4-117">The **Allow message** box enables a warning message to be sent to the user when sending hyperlinks that are allowed to be sent.</span></span>

9.  <span data-ttu-id="60af4-118">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="60af4-118">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="60af4-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="60af4-119">See Also</span></span>


[<span data-ttu-id="60af4-120">Lync Server 2013 でインスタントメッセージング (IM) 用のファイル転送および URL フィルターを構成する</span><span class="sxs-lookup"><span data-stu-id="60af4-120">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[<span data-ttu-id="60af4-121">Lync Server 2013 で特定のサイトに対して新しいファイル転送フィルターを作成する</span><span class="sxs-lookup"><span data-stu-id="60af4-121">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[<span data-ttu-id="60af4-122">Lync Server 2013 での既定のファイル送信フィルターの変更</span><span class="sxs-lookup"><span data-stu-id="60af4-122">Modify the default file transfer filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[<span data-ttu-id="60af4-123">Lync Server 2013 で既定の URL フィルターを変更する</span><span class="sxs-lookup"><span data-stu-id="60af4-123">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

