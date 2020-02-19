---
title: 移行後に簡単な Url を変更する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Change simple URLs after migration
ms:assetid: addb0dc8-8324-42b1-9a00-f4bd14fdf5c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721844(v=OCS.15)
ms:contentKeyID: 49733777
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8e96c6a1d33c9c50208c7cdea628b2c4464a7b7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135414"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="change-simple-urls-after-migration"></a><span data-ttu-id="2e3ce-102">移行後に簡単な Url を変更する</span><span class="sxs-lookup"><span data-stu-id="2e3ce-102">Change simple URLs after migration</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2e3ce-103">_**トピックの最終更新日:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="2e3ce-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="2e3ce-104">Lync Server は、次の3つの簡単な Url をサポートします。</span><span class="sxs-lookup"><span data-stu-id="2e3ce-104">Lync Server supports three simple URLs:</span></span>

  - <span data-ttu-id="2e3ce-105">**Meet**は、サイトまたは組織内のすべての電話会議のベース URL として使用されます。</span><span class="sxs-lookup"><span data-stu-id="2e3ce-105">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="2e3ce-106">簡単な会議 URL を使用すると、会議に参加するためのリンクが覚えやすくなり、通知も配布も簡単になります。</span><span class="sxs-lookup"><span data-stu-id="2e3ce-106">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span>

  - <span data-ttu-id="2e3ce-107">**ダイヤル**インは、ダイヤルイン会議設定 web ページへのアクセスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="2e3ce-107">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="2e3ce-108">ダイヤルインの簡易 URL は、すべての会議出席依頼に含まれているため、会議にダイヤルインするユーザーは必要な電話番号と PIN 情報にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2e3ce-108">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span>

  - <span data-ttu-id="2e3ce-109">**管理者**は、Lync Server コントロールパネルにすばやくアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2e3ce-109">**Admin** enables quick access to the Lync Server Control Panel.</span></span> <span data-ttu-id="2e3ce-110">簡単な管理 URL は、組織内部の URL です。</span><span class="sxs-lookup"><span data-stu-id="2e3ce-110">The Admin simple URL is internal to your organization.</span></span>

<span data-ttu-id="2e3ce-111">Lync Server 2013 に移行した後、変更によって簡単な Url の DNS レコードと証明書に与える影響に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e3ce-111">After migrating to Lync Server 2013, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="2e3ce-112">従来の Lync Server 2010 ディレクターがトポロジで使用されている場合は、簡易 Url を変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2e3ce-112">If the legacy Lync Server 2010 Director remains in use in the topology, no changes to your simple URLs are required.</span></span> <span data-ttu-id="2e3ce-113">移行後に Lync Server 2010 ディレクターがトポロジから削除された場合は、簡単な URL の DNS レコードを更新して、Lync Server 2013 プールの1つをポイントする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e3ce-113">If the Lync Server 2010 Director is removed from the topology after migration, the simple URL DNS records must be updated to point to one of the Lync Server 2013 pools.</span></span> <span data-ttu-id="2e3ce-114">ただし、簡易 URL 名を変更する場合は必ず、各ディレクターおよびフロントエンド サーバーで Enable-CsComputer を実行して変更を登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e3ce-114">Whenever you change a simple URL name, however, you must run Enable-CsComputer on each Director and Front End Server to register the change.</span></span>

<div>

## <a name="changing-simple-urls-after-migration"></a><span data-ttu-id="2e3ce-115">移行後の簡易 Url の変更</span><span class="sxs-lookup"><span data-stu-id="2e3ce-115">Changing Simple URLs after Migration</span></span>

<span data-ttu-id="2e3ce-116">**簡単な会議 URL を更新するには**</span><span class="sxs-lookup"><span data-stu-id="2e3ce-116">**To update the Meet simple URL**</span></span>

1.  <span data-ttu-id="2e3ce-117">トポロジビルダーで、最上位ノードの [ **Lync Server**] を右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e3ce-117">In Topology Builder, right-click the top node **Lync Server**, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="2e3ce-118">左側のウィンドウで [**簡易 url** ] を選択し、[**会議の url:** ] の下の [url の**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e3ce-118">Select **Simple URLs** in the left pane, then below **Meeting URLs:** select the Meet URL and then click **Edit URL**.</span></span>

3.  <span data-ttu-id="2e3ce-119">URL を目的の値に更新し、[**OK**] をクリックして編集した URL を保存します。</span><span class="sxs-lookup"><span data-stu-id="2e3ce-119">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span>

<span data-ttu-id="2e3ce-120">**管理者の簡易 URL を更新するには**</span><span class="sxs-lookup"><span data-stu-id="2e3ce-120">**To update the Admin simple URL**</span></span>

1.  <span data-ttu-id="2e3ce-121">トポロジビルダーで、最上位ノードの [ **Lync Server**] を右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e3ce-121">In Topology Builder, right-click the top node **Lync Server**, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="2e3ce-122">[**簡易 url**の選択] 左側のウィンドウで、[**管理アクセス url** ] ボックスに、Lync Server 2013 コントロールパネルへの管理アクセスに使用する簡易 url を入力し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e3ce-122">Select **Simple URLs** in the left pane, then below **Administrative access URL** box, enter the simple URL you want for administrative access to Lync Server 2013 Control Panel, and then click **OK**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="2e3ce-123">管理 URL にできるだけ簡易 URL を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2e3ce-123">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="2e3ce-124">最も簡単なオプションは<STRONG> https://admin、です。</STRONG>&lt;ドメイン&gt;。</span><span class="sxs-lookup"><span data-stu-id="2e3ce-124">The simplest option is <STRONG>https://admin.</STRONG>&lt;domain&gt;.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2e3ce-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="2e3ce-125">See Also</span></span>


[<span data-ttu-id="2e3ce-126">Lync Server 2013 での簡単な Url の計画</span><span class="sxs-lookup"><span data-stu-id="2e3ce-126">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

