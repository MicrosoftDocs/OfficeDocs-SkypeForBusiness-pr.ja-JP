---
title: 'Lync Server 2013: 既定の URL フィルターの変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the default URL filter
ms:assetid: 80a472b3-054e-45a6-80fc-9ee2bda28ee6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182544(v=OCS.15)
ms:contentKeyID: 48184653
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15511ea6b48697cddfebc40c671880a14a545557
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051319"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-default-url-filter-in-lync-server-2013"></a><span data-ttu-id="0d5e4-102">Lync Server 2013 で既定の URL フィルターを変更する</span><span class="sxs-lookup"><span data-stu-id="0d5e4-102">Modify the default URL filter in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d5e4-103">_**トピックの最終更新日:** 2012-06-26_</span><span class="sxs-lookup"><span data-stu-id="0d5e4-103">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="0d5e4-104">インスタントメッセージング (IM) フィルターを使用することにより、lync server 2013 は、Lync Server 2013 展開全体でユーザー間の IM 会話に含まれる特定の Url をブロックするグローバル URL フィルターを提供します。</span><span class="sxs-lookup"><span data-stu-id="0d5e4-104">By using the instant messaging (IM) filter, Lync Server 2013 provides a global URL filter that blocks specific URLs contained in IM conversations among users throughout your Lync Server 2013 deployment.</span></span> <span data-ttu-id="0d5e4-105">Lync Server コントロールパネルを使用すると、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="0d5e4-105">By using Lync Server Control Panel, you can do the following:</span></span>

  - <span data-ttu-id="0d5e4-106">インスタント メッセージ会話内のすべての URL またはその一部を禁止します。</span><span class="sxs-lookup"><span data-stu-id="0d5e4-106">Block all or a subset of URLs in instant message conversations.</span></span>

  - <span data-ttu-id="0d5e4-p102">すべての URL を許可します。 オプションで、URL を含む各インスタント メッセージの先頭に挿入する通知を作成できます。</span><span class="sxs-lookup"><span data-stu-id="0d5e4-p102">Allow all URLs. As an option, you can create a notice that is inserted at the beginning of each instant message that contains a URL.</span></span>

  - <span data-ttu-id="0d5e4-109">特定の URL を許可し、URL を含む各インスタント メッセージに警告を入れます。</span><span class="sxs-lookup"><span data-stu-id="0d5e4-109">Allow specific URLs and include a warning with each instant message that contains a URL.</span></span>

<span data-ttu-id="0d5e4-110">また、特定の種類のファイルを含む URL を禁止することや、サーバーのローカル イントラネット ゾーン (イントラネット URL) 内の URL のサーバー通過を許可し、インターネット URL のみを禁止することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="0d5e4-110">In addition, you can choose to block URLs that contain specific file types, or block only Internet URLs by allowing URLs that are within the server’s local intranet zone — intranet URLs — to pass through the server.</span></span> <span data-ttu-id="0d5e4-111">URL フィルターの詳細については、「 [Lync Server 2013 でインスタントメッセージング (IM) のファイル転送と url フィルターを構成する](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d5e4-111">For details about URL filtering, see [Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="0d5e4-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="0d5e4-112">See Also</span></span>


[<span data-ttu-id="0d5e4-113">Lync Server 2013 でインスタントメッセージング (IM) 用のファイル転送および URL フィルターを構成する</span><span class="sxs-lookup"><span data-stu-id="0d5e4-113">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[<span data-ttu-id="0d5e4-114">Lync Server 2013 で特定のサイトに対して新しいファイル転送フィルターを作成する</span><span class="sxs-lookup"><span data-stu-id="0d5e4-114">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[<span data-ttu-id="0d5e4-115">IM 会話でのハイパーリンクを処理するために Lync Server 2013 で新しい URL フィルターを作成する</span><span class="sxs-lookup"><span data-stu-id="0d5e4-115">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  
[<span data-ttu-id="0d5e4-116">Lync Server 2013 での既定のファイル送信フィルターの変更</span><span class="sxs-lookup"><span data-stu-id="0d5e4-116">Modify the default file transfer filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-file-transfer-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

