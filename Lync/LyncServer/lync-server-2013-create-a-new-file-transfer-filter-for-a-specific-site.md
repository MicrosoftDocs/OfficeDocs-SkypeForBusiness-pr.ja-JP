---
title: 'Lync Server 2013: 特定のサイト用の新しいファイル送信フィルターの作成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a new file transfer filter for a specific site
ms:assetid: d0006487-5217-491c-b730-e6c551cd9825
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182589(v=OCS.15)
ms:contentKeyID: 48185577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a374cb234567c5aeb44ce6071f6e67559c5159ec
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144974"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-new-file-transfer-filter-in-lync-server-2013-for-a-specific-site"></a><span data-ttu-id="e8df5-102">Lync Server 2013 で特定のサイトに対して新しいファイル転送フィルターを作成する</span><span class="sxs-lookup"><span data-stu-id="e8df5-102">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8df5-103">_**トピックの最終更新日:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="e8df5-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="e8df5-104">グローバルファイル転送フィルターを変更するだけでなく、Lync Server 2013 展開内の特定のサイトに対してカスタムファイル転送フィルターを構成できます。</span><span class="sxs-lookup"><span data-stu-id="e8df5-104">In addition to modifying the global file transfer filter, you can configure custom file transfer filters for specific sites within your Lync Server 2013 deployment.</span></span> <span data-ttu-id="e8df5-105">ファイル転送フィルターの詳細については、「 [Lync Server 2013 でインスタントメッセージング (IM) のファイル転送と URL フィルターを構成する](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8df5-105">For details about file transfer filtering, see [Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span></span>

<div>

## <a name="to-create-a-file-transfer-filter-for-a-specific-site"></a><span data-ttu-id="e8df5-106">特定のサイトに対してファイル送信フィルタを作成するには</span><span class="sxs-lookup"><span data-stu-id="e8df5-106">To create a file transfer filter for a specific site</span></span>

1.  <span data-ttu-id="e8df5-107">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="e8df5-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e8df5-108">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="e8df5-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e8df5-109">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8df5-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e8df5-110">左側のナビゲーション バーで [**IM とプレゼンス**] をクリックし、[**ファイル フィルター**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e8df5-110">In the left navigation bar, click **IM and Presence** and then click **File Filter**.</span></span>

4.  <span data-ttu-id="e8df5-111">[**ファイル フィルタ**] ページで [**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e8df5-111">On the **File Filter** page, click **New**.</span></span>

5.  <span data-ttu-id="e8df5-112">[**サイトの選択**] ダイアログ ボックスで、ファイル送信フィルタを作成するサイトをクリックしてから、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e8df5-112">In the **Select a Site** dialog box, click the site for which you want to create the file transfer filter, and then click **OK**.</span></span>

6.  <span data-ttu-id="e8df5-113">[**新しいファイル フィルタ**] で、[**ファイル フィルタを有効にする**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="e8df5-113">In **New File Filter**, click the **Enable file filter** check box.</span></span>

7.  <span data-ttu-id="e8df5-114">[**ファイル送信**] ドロップダウン リスト ボックスで、[**すべて禁止**] または [**特定の種類のファイルを禁止**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e8df5-114">In **File transfer** drop-down list box, click **Block All** or **Block specific file types**.</span></span>

8.  <span data-ttu-id="e8df5-115">[**すべて禁止**] をクリックした場合は、ステップ 10 へ進みます。</span><span class="sxs-lookup"><span data-stu-id="e8df5-115">If you clicked **Block All**, skip to step 10.</span></span>

9.  <span data-ttu-id="e8df5-116">[**特定の種類のファイルを禁止する**] をクリックした場合は、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="e8df5-116">If you clicked **Block specific file types**, do the following:</span></span>
    
    1.  <span data-ttu-id="e8df5-117">[**選択**] をクリックして、禁止する種類のファイル拡張子の既定の一覧を変更します。</span><span class="sxs-lookup"><span data-stu-id="e8df5-117">Click **Select** to modify the default list of file type extensions that you want to block.</span></span>
    
    2.  <span data-ttu-id="e8df5-118">[**ファイルの種類を選択**] ダイアログ ボックスで、[**ファイル拡張子**] の下のカテゴリから拡張子を追加するか削除して、禁止または許可するファイルの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="e8df5-118">In the **Select File Type** dialog box, select the file types that you want to block or allow by adding or removing their extensions from the categories under **File type extensions**.</span></span>
    
    3.  <span data-ttu-id="e8df5-119">禁止する種類のファイルの拡張子が見当たらない場合は、[**ファイルの拡張子を一覧に追加**] のテキスト ボックスに拡張子を入力して、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e8df5-119">If you do not see the extension for a file type that you want to block, type the extension in the text box under **Add file type extensions to the list**, and then click **Add**.</span></span>
    
    4.  <span data-ttu-id="e8df5-120">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e8df5-120">Click **OK**.</span></span>

10. <span data-ttu-id="e8df5-121">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e8df5-121">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e8df5-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="e8df5-122">See Also</span></span>


[<span data-ttu-id="e8df5-123">Lync Server 2013 でインスタントメッセージング (IM) 用のファイル転送および URL フィルターを構成する</span><span class="sxs-lookup"><span data-stu-id="e8df5-123">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[<span data-ttu-id="e8df5-124">IM 会話でのハイパーリンクを処理するために Lync Server 2013 で新しい URL フィルターを作成する</span><span class="sxs-lookup"><span data-stu-id="e8df5-124">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  
[<span data-ttu-id="e8df5-125">Lync Server 2013 での既定のファイル送信フィルターの変更</span><span class="sxs-lookup"><span data-stu-id="e8df5-125">Modify the default file transfer filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[<span data-ttu-id="e8df5-126">Lync Server 2013 で既定の URL フィルターを変更する</span><span class="sxs-lookup"><span data-stu-id="e8df5-126">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

