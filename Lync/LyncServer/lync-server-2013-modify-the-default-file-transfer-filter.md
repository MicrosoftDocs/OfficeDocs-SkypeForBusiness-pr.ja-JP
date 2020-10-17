---
title: 'Lync Server 2013: 既定のファイル送信フィルターの変更'
description: 'Lync Server 2013: 既定のファイル送信フィルターを変更します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the default file transfer filter
ms:assetid: 791774a2-0bb6-4b5b-aeb0-ff69abb170f4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521017(v=OCS.15)
ms:contentKeyID: 48184584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8091dfebea87b793c56b9a670cfeeeab15ce6c44
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566933"
---
# <a name="modify-the-default-file-transfer-filter-in-lync-server-2013"></a><span data-ttu-id="33aa3-103">Lync Server 2013 での既定のファイル送信フィルターの変更</span><span class="sxs-lookup"><span data-stu-id="33aa3-103">Modify the default file transfer filter in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33aa3-104">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="33aa3-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="33aa3-105">Lync Server 2013 には、Lync Server 2013 展開内の次のファイル関連アクティビティで特定の種類のファイルをブロックするグローバルファイル転送フィルターが用意されています。</span><span class="sxs-lookup"><span data-stu-id="33aa3-105">Lync Server 2013 provides a global file transfer filter that blocks specific types of files during the following file-related activities within your Lync Server 2013 deployment:</span></span>

  - <span data-ttu-id="33aa3-106">インスタント メッセージング (IM) 会話中のファイル転送要求</span><span class="sxs-lookup"><span data-stu-id="33aa3-106">File transfer requests during instant messaging (IM) conversations</span></span>

  - <span data-ttu-id="33aa3-107">Office Live Meeting 2007 クライアントの配布資料機能使用中のファイル アップロードおよびダウンロード</span><span class="sxs-lookup"><span data-stu-id="33aa3-107">File uploads and downloads while using the handout feature in the Office Live Meeting 2007 client</span></span>

  - <span data-ttu-id="33aa3-108">会議中のマルチメディア再生</span><span class="sxs-lookup"><span data-stu-id="33aa3-108">Multimedia playback during conferences</span></span>

<span data-ttu-id="33aa3-109">禁止または許可するファイルの種類に応じて、Lync Server コントロールパネルを使用してグローバルフィルターを変更できます。</span><span class="sxs-lookup"><span data-stu-id="33aa3-109">Depending on the types of files you want to block or allow, you can use Lync Server Control Panel to modify the global filter.</span></span> <span data-ttu-id="33aa3-110">ファイル転送フィルターの詳細については、「 [Lync Server 2013 でインスタントメッセージング (IM) のファイル転送と URL フィルターを構成する](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33aa3-110">For details about file transfer filtering, see [Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span></span>

<div>

## <a name="to-modify-the-default-file-transfer-filter"></a><span data-ttu-id="33aa3-111">既定のファイル送信フィルターを変更するには</span><span class="sxs-lookup"><span data-stu-id="33aa3-111">To modify the default file transfer filter</span></span>

1.  <span data-ttu-id="33aa3-112">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="33aa3-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="33aa3-113">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="33aa3-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="33aa3-114">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33aa3-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="33aa3-115">左側のナビゲーション バーで [**IM とプレゼンス**] をクリックし、[**ファイル フィルター**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33aa3-115">In the left navigation bar, click **IM and Presence** and then click **File Filter**.</span></span>

4.  <span data-ttu-id="33aa3-116">[**ファイル フィルター**] ページで、[**グローバル**] フィルターをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="33aa3-116">On the **File Filter** page, double-click the **Global** filter.</span></span>

5.  <span data-ttu-id="33aa3-117">[**ファイル フィルターの編集**] で、[**ファイル フィルターを有効にする**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="33aa3-117">In **Edit File Filter**, select the **Enable file filter** check box.</span></span>

6.  <span data-ttu-id="33aa3-118">[**ファイル転送**] ドロップダウン リストで、[**すべて禁止**] または [**特定の種類のファイルを禁止する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33aa3-118">In the **File transfer** drop-down list box, click **Block All** or **Block specific file types**.</span></span>

7.  <span data-ttu-id="33aa3-119">[**すべて禁止**] をクリックした場合は、ステップ 9 へ進みます。</span><span class="sxs-lookup"><span data-stu-id="33aa3-119">If you clicked **Block All**, skip to step 9.</span></span>

8.  <span data-ttu-id="33aa3-120">[**特定の種類のファイルを禁止する**] をクリックした場合は、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="33aa3-120">If you clicked **Block specific file types**, do the following:</span></span>
    
    1.  <span data-ttu-id="33aa3-121">[**選択**] をクリックして、禁止する種類のファイル拡張子の既定の一覧を変更します。</span><span class="sxs-lookup"><span data-stu-id="33aa3-121">Click **Select** to modify the default list of file type extensions that you want to block.</span></span>
    
    2.  <span data-ttu-id="33aa3-122">[**ファイルの種類を選択**] の [**ファイルの種類の拡張子**] で、カテゴリの拡張子を追加または削除して、禁止または許可するファイルの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="33aa3-122">In **Select File Type**, select the file types that you want to block or allow by adding or removing their extensions from the categories under **File type extensions**.</span></span>
    
    3.  <span data-ttu-id="33aa3-123">禁止する種類のファイルの拡張子が見当たらない場合は、[**ファイルの拡張子を一覧に追加**] のテキスト ボックスに拡張子を入力して、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33aa3-123">If you do not see the extension for a file type that you want to block, type the extension in the text box under **Add file type extensions to the list**, and then click **Add**.</span></span>
    
    4.  <span data-ttu-id="33aa3-124">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33aa3-124">Click **OK**.</span></span>

9.  <span data-ttu-id="33aa3-125">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33aa3-125">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="33aa3-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="33aa3-126">See Also</span></span>


[<span data-ttu-id="33aa3-127">Lync Server 2013 でインスタントメッセージング (IM) 用のファイル転送および URL フィルターを構成する</span><span class="sxs-lookup"><span data-stu-id="33aa3-127">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[<span data-ttu-id="33aa3-128">Lync Server 2013 で特定のサイトに対して新しいファイル転送フィルターを作成する</span><span class="sxs-lookup"><span data-stu-id="33aa3-128">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[<span data-ttu-id="33aa3-129">IM 会話でのハイパーリンクを処理するために Lync Server 2013 で新しい URL フィルターを作成する</span><span class="sxs-lookup"><span data-stu-id="33aa3-129">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  


[<span data-ttu-id="33aa3-130">Lync Server 2013 で既定の URL フィルターを変更する</span><span class="sxs-lookup"><span data-stu-id="33aa3-130">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

