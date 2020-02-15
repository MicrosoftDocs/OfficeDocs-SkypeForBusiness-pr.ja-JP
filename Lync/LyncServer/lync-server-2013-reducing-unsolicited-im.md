---
title: 'Lync Server 2013: 要請していない IM の削減'
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
ms.openlocfilehash: 5574930d6474a75ca4a35219df7cd2e3e2431b15
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050129"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reducing-unsolicited-im-for-lync-server-2013"></a><span data-ttu-id="c1206-102">Lync Server 2013 の未承諾 IM の削減</span><span class="sxs-lookup"><span data-stu-id="c1206-102">Reducing unsolicited IM for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c1206-103">_**トピックの最終更新日:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="c1206-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="c1206-104">インテリジェント IM フィルターアプリケーションは、ユーザーの利便性を最小限に抑えながら、最も一般的なウイルスに対して Microsoft Lync Server 2013 の展開を保護するのに役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="c1206-104">The Intelligent IM Filter application helps protect your Microsoft Lync Server 2013 deployment against the most common viruses with minimal degradation to the user experience.</span></span> <span data-ttu-id="c1206-105">インテリジェント IM フィルターには、以下の機能があります。</span><span class="sxs-lookup"><span data-stu-id="c1206-105">The Intelligent IM Filter provides the following:</span></span>

  - <span data-ttu-id="c1206-106">拡張 URL フィルター</span><span class="sxs-lookup"><span data-stu-id="c1206-106">Enhanced URL filtering</span></span>

  - <span data-ttu-id="c1206-107">拡張ファイル送信フィルター</span><span class="sxs-lookup"><span data-stu-id="c1206-107">Enhanced file transfer filtering</span></span>

<span data-ttu-id="c1206-p102">インテリジェント IM フィルターを使用して、企業ファイアウォールの外側にある未知のエンドポイントから送信された、要求していないか損害を与える可能性のあるインスタント メッセージを禁止するようにフィルターを構成します。フィルターを構成するには、禁止する対象 (たとえば、ハイパーリンクや特定の拡張子のファイルを含むインスタント メッセージ) を判断するための基準を指定します。</span><span class="sxs-lookup"><span data-stu-id="c1206-p102">Use Intelligent IM Filter to configure filters to block unsolicited or potentially harmful instant messages from unknown endpoints outside the corporate firewall. You configure filters by specifying the criteria to be used to determine what should be blocked, such as instant messages containing hyperlinks and files with specific extensions.</span></span>

<span data-ttu-id="c1206-110">インテリジェント IM メッセージフィルターアプリケーションを展開する前に、1つの Lync Server 2013 サーバーから別のサーバーにメッセージをルーティングするときのフィルターオプションの適用方法を理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="c1206-110">Before you deploy the Intelligent IM Message Filter application, you should understand how filtering options are applied when messages are routed from one Lync Server 2013 server to another.</span></span> <span data-ttu-id="c1206-111">これらのサーバーが 1 つの組織内に配置されている場合も、組織の境界を越えて配置されている場合も、フィルター オプションが適用される方法は一貫しています。</span><span class="sxs-lookup"><span data-stu-id="c1206-111">The way these filtering options are applied is consistent, regardless of whether the servers are located in a single organization or across organizational boundaries.</span></span> <span data-ttu-id="c1206-112">この一貫性は、カスタマイズされた通知や警告テキストがメッセージに挿入され、サーバー間で送信される方法に適用されます。</span><span class="sxs-lookup"><span data-stu-id="c1206-112">This consistency applies to the way that the customized notice, and warning texts are inserted into messages and sent across servers.</span></span>

<span data-ttu-id="c1206-113">推奨されるフィルター処理オプションは、ハイパーリンクを含むインスタントメッセージを許可するが、インテリジェント IM フィルターでリンクを無効にするには、その前にアンダースコアを挿入する必要があることです。</span><span class="sxs-lookup"><span data-stu-id="c1206-113">The recommended filtering option is to allow instant messages with hyperlinks but require the Intelligent IM Filter to disable the link by inserting an underscore before it.</span></span> <span data-ttu-id="c1206-114">このオプションを選択すると、ハイパーリンクを含む各インスタントメッセージの冒頭に表示されるユーザーに対して通知を作成するオプションが追加されます。</span><span class="sxs-lookup"><span data-stu-id="c1206-114">If you choose this option, you have the additional option of composing a notice to users that appears at the beginning of each instant message that contains a hyperlink.</span></span>

<span data-ttu-id="c1206-115">2番目のフィルターオプションは、未変更のハイパーリンクを含むインスタントメッセージを許可することです。</span><span class="sxs-lookup"><span data-stu-id="c1206-115">A second filtering option is to allow instant messages with unmodified hyperlinks.</span></span> <span data-ttu-id="c1206-116">このオプションを選択した場合は、各メッセージに挿入されたユーザーに対して警告を作成するための追加のオプション (推奨) があります。</span><span class="sxs-lookup"><span data-stu-id="c1206-116">If you choose this option, you have the additional option (recommended) of composing a warning to users that is inserted in each message.</span></span>

<span data-ttu-id="c1206-117">3番目のオプションは、ハイパーリンクを含むすべてのインスタントメッセージをブロックすることです。</span><span class="sxs-lookup"><span data-stu-id="c1206-117">A third option is to block all instant messages that contain hyperlinks.</span></span> <span data-ttu-id="c1206-118">このオプションを選択すると、サーバーはユーザーに警告を送信します。</span><span class="sxs-lookup"><span data-stu-id="c1206-118">If you choose this option, the server sends a warning to the user.</span></span> <span data-ttu-id="c1206-119">この警告を記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c1206-119">You must write this warning.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

