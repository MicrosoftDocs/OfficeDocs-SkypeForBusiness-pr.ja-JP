---
title: 'Lync Server 2013: 既定のファイル転送フィルターを変更する'
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
ms.openlocfilehash: e8a0d9ade3fd750f5dc89526969bad7e39ad0f35
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756891"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-default-file-transfer-filter-in-lync-server-2013"></a><span data-ttu-id="6b0c4-102">Lync Server 2013 で既定のファイル転送フィルターを変更する</span><span class="sxs-lookup"><span data-stu-id="6b0c4-102">Modify the default file transfer filter in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6b0c4-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="6b0c4-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="6b0c4-104">Lync Server 2013 では、Lync Server 2013 の展開における次のファイル関連のアクティビティ中に、特定の種類のファイルをブロックするグローバルファイル転送フィルターが提供されています。</span><span class="sxs-lookup"><span data-stu-id="6b0c4-104">Lync Server 2013 provides a global file transfer filter that blocks specific types of files during the following file-related activities within your Lync Server 2013 deployment:</span></span>

  - <span data-ttu-id="6b0c4-105">インスタントメッセージング (IM) 会話中のファイル送信要求</span><span class="sxs-lookup"><span data-stu-id="6b0c4-105">File transfer requests during instant messaging (IM) conversations</span></span>

  - <span data-ttu-id="6b0c4-106">Office Live Meeting 2007 クライアントで配布資料機能を使用しているときにファイルのアップロードとダウンロードを行う</span><span class="sxs-lookup"><span data-stu-id="6b0c4-106">File uploads and downloads while using the handout feature in the Office Live Meeting 2007 client</span></span>

  - <span data-ttu-id="6b0c4-107">会議中のマルチメディア再生</span><span class="sxs-lookup"><span data-stu-id="6b0c4-107">Multimedia playback during conferences</span></span>

<span data-ttu-id="6b0c4-108">ブロックまたは許可するファイルの種類に応じて、Lync Server コントロールパネルを使用してグローバルフィルターを変更できます。</span><span class="sxs-lookup"><span data-stu-id="6b0c4-108">Depending on the types of files you want to block or allow, you can use Lync Server Control Panel to modify the global filter.</span></span> <span data-ttu-id="6b0c4-109">ファイル転送フィルターの詳細については、「 [Lync Server 2013 でインスタントメッセージング (IM) のためのファイル送信と URL フィルタリングを構成する](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b0c4-109">For details about file transfer filtering, see [Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span></span>

<div>

## <a name="to-modify-the-default-file-transfer-filter"></a><span data-ttu-id="6b0c4-110">既定のファイル転送フィルターを変更するには</span><span class="sxs-lookup"><span data-stu-id="6b0c4-110">To modify the default file transfer filter</span></span>

1.  <span data-ttu-id="6b0c4-111">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="6b0c4-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6b0c4-112">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="6b0c4-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6b0c4-113">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6b0c4-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6b0c4-114">左側のナビゲーションバーで、[ **IM とプレゼンス**] をクリックし、[**ファイルフィルター**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b0c4-114">In the left navigation bar, click **IM and Presence** and then click **File Filter**.</span></span>

4.  <span data-ttu-id="6b0c4-115">[**ファイルフィルター** ] ページで、**グローバル**フィルターをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b0c4-115">On the **File Filter** page, double-click the **Global** filter.</span></span>

5.  <span data-ttu-id="6b0c4-116">[**ファイルフィルターの編集**] で、[**ファイルフィルターを有効にする**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="6b0c4-116">In **Edit File Filter**, select the **Enable file filter** check box.</span></span>

6.  <span data-ttu-id="6b0c4-117">[**ファイル転送**] ドロップダウンリストボックスで、[**ブロック**する] または [**特定の種類のファイルをブロック**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b0c4-117">In the **File transfer** drop-down list box, click **Block All** or **Block specific file types**.</span></span>

7.  <span data-ttu-id="6b0c4-118">[**すべてブロック**] をクリックした場合は、手順9に進みます。</span><span class="sxs-lookup"><span data-stu-id="6b0c4-118">If you clicked **Block All**, skip to step 9.</span></span>

8.  <span data-ttu-id="6b0c4-119">[特定の**種類のファイルをブロック**する] をクリックした場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6b0c4-119">If you clicked **Block specific file types**, do the following:</span></span>
    
    1.  <span data-ttu-id="6b0c4-120">[**選択**] をクリックして、ブロックするファイルの種類の拡張子の既定のリストを変更します。</span><span class="sxs-lookup"><span data-stu-id="6b0c4-120">Click **Select** to modify the default list of file type extensions that you want to block.</span></span>
    
    2.  <span data-ttu-id="6b0c4-121">[ファイルの**種類の選択**] で、ブロックまたは削除するファイルの種類を [ファイルの**種類の拡張子**] の下にあるカテゴリから選びます。</span><span class="sxs-lookup"><span data-stu-id="6b0c4-121">In **Select File Type**, select the file types that you want to block or allow by adding or removing their extensions from the categories under **File type extensions**.</span></span>
    
    3.  <span data-ttu-id="6b0c4-122">ブロックするファイルの種類の拡張子が表示されない場合は、[**ファイルの種類の拡張子を追加する**] の下のテキストボックスに拡張子を入力し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b0c4-122">If you do not see the extension for a file type that you want to block, type the extension in the text box under **Add file type extensions to the list**, and then click **Add**.</span></span>
    
    4.  <span data-ttu-id="6b0c4-123">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b0c4-123">Click **OK**.</span></span>

9.  <span data-ttu-id="6b0c4-124">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b0c4-124">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6b0c4-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="6b0c4-125">See Also</span></span>


[<span data-ttu-id="6b0c4-126">Lync Server 2013 でのインスタントメッセージング (IM) のファイル転送と URL フィルタリングの構成</span><span class="sxs-lookup"><span data-stu-id="6b0c4-126">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[<span data-ttu-id="6b0c4-127">Lync Server 2013 で特定のサイト用の新しいファイル転送フィルターを作成する</span><span class="sxs-lookup"><span data-stu-id="6b0c4-127">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[<span data-ttu-id="6b0c4-128">Lync Server 2013 で新しい URL フィルターを作成して、IM 会話のハイパーリンクを処理する</span><span class="sxs-lookup"><span data-stu-id="6b0c4-128">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  


[<span data-ttu-id="6b0c4-129">Lync Server 2013 で既定の URL フィルターを変更する</span><span class="sxs-lookup"><span data-stu-id="6b0c4-129">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

