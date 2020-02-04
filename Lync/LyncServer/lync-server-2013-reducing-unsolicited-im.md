---
title: 'Lync Server 2013: 未承諾 IM の削減'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reducing unsolicited IM for Lync Server 2013
ms:assetid: d2998708-e699-4465-a918-e1d9ea4c49c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518335(v=OCS.15)
ms:contentKeyID: 62625493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0f8326d6fa9f85b202e0ea2dcbe3fed63a723aa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724453"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reducing-unsolicited-im-for-lync-server-2013"></a><span data-ttu-id="8ee08-102">Lync Server 2013 での未承諾 IM の削減</span><span class="sxs-lookup"><span data-stu-id="8ee08-102">Reducing unsolicited IM for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ee08-103">_**最終更新日:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="8ee08-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="8ee08-104">インテリジェント IM フィルターアプリケーションは、ユーザーエクスペリエンスの低下を最小限に抑えて、Microsoft Lync Server 2013 の展開を最も一般的なウイルスと保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8ee08-104">The Intelligent IM Filter application helps protect your Microsoft Lync Server 2013 deployment against the most common viruses with minimal degradation to the user experience.</span></span> <span data-ttu-id="8ee08-105">インテリジェント IM フィルターでは、次の機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="8ee08-105">The Intelligent IM Filter provides the following:</span></span>

  - <span data-ttu-id="8ee08-106">強化された URL フィルター</span><span class="sxs-lookup"><span data-stu-id="8ee08-106">Enhanced URL filtering</span></span>

  - <span data-ttu-id="8ee08-107">拡張されたファイル転送フィルター機能</span><span class="sxs-lookup"><span data-stu-id="8ee08-107">Enhanced file transfer filtering</span></span>

<span data-ttu-id="8ee08-108">インテリジェント IM フィルターを使用して、組織外のエンドポイントからの不要または有害なインスタントメッセージをブロックするようにフィルターを設定します。</span><span class="sxs-lookup"><span data-stu-id="8ee08-108">Use Intelligent IM Filter to configure filters to block unsolicited or potentially harmful instant messages from unknown endpoints outside the corporate firewall.</span></span> <span data-ttu-id="8ee08-109">フィルターを設定するには、ハイパーリンクを含むインスタントメッセージや特定の拡張子のファイルなど、ブロックする必要があるものを決定するために使用する条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="8ee08-109">You configure filters by specifying the criteria to be used to determine what should be blocked, such as instant messages containing hyperlinks and files with specific extensions.</span></span>

<span data-ttu-id="8ee08-110">インテリジェント IM メッセージフィルターアプリケーションを展開する前に、メッセージが Lync Server 2013 サーバー間でルーティングされるときのフィルターオプションの適用方法を理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ee08-110">Before you deploy the Intelligent IM Message Filter application, you should understand how filtering options are applied when messages are routed from one Lync Server 2013 server to another.</span></span> <span data-ttu-id="8ee08-111">これらのフィルターオプションの適用方法は、サーバーが1つの組織内に配置されているか、組織の境界を超えているかに関係なく一貫しています。</span><span class="sxs-lookup"><span data-stu-id="8ee08-111">The way these filtering options are applied is consistent, regardless of whether the servers are located in a single organization or across organizational boundaries.</span></span> <span data-ttu-id="8ee08-112">この一貫性は、カスタマイズされた通知や警告テキストがメッセージに挿入され、サーバー間で送信される方法に適用されます。</span><span class="sxs-lookup"><span data-stu-id="8ee08-112">This consistency applies to the way that the customized notice, and warning texts are inserted into messages and sent across servers.</span></span>

<span data-ttu-id="8ee08-113">推奨されるフィルターオプションは、ハイパーリンクを使用してインスタントメッセージを許可することですが、インテリジェント IM フィルターを使用して、リンクを無効にするには、その前にアンダースコアを挿入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ee08-113">The recommended filtering option is to allow instant messages with hyperlinks but require the Intelligent IM Filter to disable the link by inserting an underscore before it.</span></span> <span data-ttu-id="8ee08-114">このオプションを選ぶと、ハイパーリンクが設定されている各インスタントメッセージの先頭に表示されるユーザーへの通知を作成するオプションが追加されます。</span><span class="sxs-lookup"><span data-stu-id="8ee08-114">If you choose this option, you have the additional option of composing a notice to users that appears at the beginning of each instant message that contains a hyperlink.</span></span>

<span data-ttu-id="8ee08-115">2番目のフィルターオプションは、ハイパーリンクを変更せずにインスタントメッセージを送信できるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="8ee08-115">A second filtering option is to allow instant messages with unmodified hyperlinks.</span></span> <span data-ttu-id="8ee08-116">このオプションを選択すると、各メッセージに挿入されたユーザーに警告を作成するための追加オプション (推奨) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8ee08-116">If you choose this option, you have the additional option (recommended) of composing a warning to users that is inserted in each message.</span></span>

<span data-ttu-id="8ee08-117">3番目のオプションは、ハイパーリンクを含むすべてのインスタントメッセージをブロックすることです。</span><span class="sxs-lookup"><span data-stu-id="8ee08-117">A third option is to block all instant messages that contain hyperlinks.</span></span> <span data-ttu-id="8ee08-118">このオプションを選択すると、サーバーはユーザーに警告を送信します。</span><span class="sxs-lookup"><span data-stu-id="8ee08-118">If you choose this option, the server sends a warning to the user.</span></span> <span data-ttu-id="8ee08-119">この警告は、作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ee08-119">You must write this warning.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

