---
title: 'Lync Server 2013: 特定のサイト用の新しいファイル転送フィルターを作成する'
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
ms.openlocfilehash: edaf0afabff9d212cdd3b5353a8e54840979f827
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740407"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-new-file-transfer-filter-in-lync-server-2013-for-a-specific-site"></a><span data-ttu-id="a12a6-102">Lync Server 2013 で特定のサイト用の新しいファイル転送フィルターを作成する</span><span class="sxs-lookup"><span data-stu-id="a12a6-102">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a12a6-103">_**最終更新日:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="a12a6-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="a12a6-104">グローバルファイル転送フィルターの変更に加えて、Lync Server 2013 展開内の特定のサイト用のカスタムファイル転送フィルターを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="a12a6-104">In addition to modifying the global file transfer filter, you can configure custom file transfer filters for specific sites within your Lync Server 2013 deployment.</span></span> <span data-ttu-id="a12a6-105">ファイル転送フィルターの詳細については、「 [Lync Server 2013 でインスタントメッセージング (IM) のためのファイル送信と URL フィルタリングを構成する](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a12a6-105">For details about file transfer filtering, see [Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span></span>

<div>

## <a name="to-create-a-file-transfer-filter-for-a-specific-site"></a><span data-ttu-id="a12a6-106">特定のサイトのファイル転送フィルターを作成するには</span><span class="sxs-lookup"><span data-stu-id="a12a6-106">To create a file transfer filter for a specific site</span></span>

1.  <span data-ttu-id="a12a6-107">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="a12a6-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a12a6-108">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="a12a6-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a12a6-109">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a12a6-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a12a6-110">左側のナビゲーションバーで、[ **IM とプレゼンス**] をクリックし、[**ファイルフィルター**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a12a6-110">In the left navigation bar, click **IM and Presence** and then click **File Filter**.</span></span>

4.  <span data-ttu-id="a12a6-111">[**ファイルフィルター** ] ページで、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a12a6-111">On the **File Filter** page, click **New**.</span></span>

5.  <span data-ttu-id="a12a6-112">[**サイトの選択**] ダイアログボックスで、ファイル転送フィルターを作成するサイトをクリックし、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a12a6-112">In the **Select a Site** dialog box, click the site for which you want to create the file transfer filter, and then click **OK**.</span></span>

6.  <span data-ttu-id="a12a6-113">**新しいファイルフィルター**で、[**ファイルフィルターを有効にする**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="a12a6-113">In **New File Filter**, click the **Enable file filter** check box.</span></span>

7.  <span data-ttu-id="a12a6-114">[**ファイル転送**] ドロップダウンリストボックスで、[**ブロック**する] または [**特定の種類のファイルをブロック**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a12a6-114">In **File transfer** drop-down list box, click **Block All** or **Block specific file types**.</span></span>

8.  <span data-ttu-id="a12a6-115">[**すべてブロック**] をクリックした場合は、手順10に進みます。</span><span class="sxs-lookup"><span data-stu-id="a12a6-115">If you clicked **Block All**, skip to step 10.</span></span>

9.  <span data-ttu-id="a12a6-116">[特定の**種類のファイルをブロック**する] をクリックした場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a12a6-116">If you clicked **Block specific file types**, do the following:</span></span>
    
    1.  <span data-ttu-id="a12a6-117">[**選択**] をクリックして、ブロックするファイルの種類の拡張子の既定のリストを変更します。</span><span class="sxs-lookup"><span data-stu-id="a12a6-117">Click **Select** to modify the default list of file type extensions that you want to block.</span></span>
    
    2.  <span data-ttu-id="a12a6-118">[ファイルの**種類の選択**] ダイアログボックスで、[ファイルの種類の**拡張子**] の下にあるカテゴリの拡張子を追加または削除して、ブロックまたは許可するファイルの種類を選びます。</span><span class="sxs-lookup"><span data-stu-id="a12a6-118">In the **Select File Type** dialog box, select the file types that you want to block or allow by adding or removing their extensions from the categories under **File type extensions**.</span></span>
    
    3.  <span data-ttu-id="a12a6-119">ブロックするファイルの種類の拡張子が表示されない場合は、[**ファイルの種類の拡張子を追加する**] の下のテキストボックスに拡張子を入力し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a12a6-119">If you do not see the extension for a file type that you want to block, type the extension in the text box under **Add file type extensions to the list**, and then click **Add**.</span></span>
    
    4.  <span data-ttu-id="a12a6-120">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a12a6-120">Click **OK**.</span></span>

10. <span data-ttu-id="a12a6-121">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a12a6-121">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a12a6-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="a12a6-122">See Also</span></span>


[<span data-ttu-id="a12a6-123">Lync Server 2013 でのインスタントメッセージング (IM) のファイル転送と URL フィルタリングの構成</span><span class="sxs-lookup"><span data-stu-id="a12a6-123">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[<span data-ttu-id="a12a6-124">Lync Server 2013 で新しい URL フィルターを作成して、IM 会話のハイパーリンクを処理する</span><span class="sxs-lookup"><span data-stu-id="a12a6-124">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  
[<span data-ttu-id="a12a6-125">Lync Server 2013 で既定のファイル転送フィルターを変更する</span><span class="sxs-lookup"><span data-stu-id="a12a6-125">Modify the default file transfer filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[<span data-ttu-id="a12a6-126">Lync Server 2013 で既定の URL フィルターを変更する</span><span class="sxs-lookup"><span data-stu-id="a12a6-126">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

