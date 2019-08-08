---
title: 移行後の簡易 URL の変更
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Change simple URLs after migration
ms:assetid: addb0dc8-8324-42b1-9a00-f4bd14fdf5c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721844(v=OCS.15)
ms:contentKeyID: 49733777
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 811296efc12badd61d148b7dbd60a3489e74a747
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36232871"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-simple-urls-after-migration"></a><span data-ttu-id="417d2-102">移行後の簡易 URL の変更</span><span class="sxs-lookup"><span data-stu-id="417d2-102">Change simple URLs after migration</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="417d2-103">_**最終更新日:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="417d2-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="417d2-104">Lync Server は、次の3つの簡単な Url をサポートします。</span><span class="sxs-lookup"><span data-stu-id="417d2-104">Lync Server supports three simple URLs:</span></span>

  - <span data-ttu-id="417d2-105">**会議**は、サイトまたは組織内のすべての会議のベース URL として使用されます。</span><span class="sxs-lookup"><span data-stu-id="417d2-105">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="417d2-106">[会議への参加] の [シンプル URL] を使用すると、会議に参加するためのリンクを簡単に理解して、簡単に連絡して配布することができます。</span><span class="sxs-lookup"><span data-stu-id="417d2-106">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span>

  - <span data-ttu-id="417d2-107">[**ダイヤル**イン] は、ダイヤルイン会議の設定の web ページにアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="417d2-107">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="417d2-108">ダイヤルインの簡易 URL は、会議にダイヤルインするユーザーが必要な電話番号と PIN 情報にアクセスできるように、すべての会議出席依頼に含まれています。</span><span class="sxs-lookup"><span data-stu-id="417d2-108">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span>

  - <span data-ttu-id="417d2-109">**管理者**が Lync Server コントロールパネルにすばやくアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="417d2-109">**Admin** enables quick access to the Lync Server Control Panel.</span></span> <span data-ttu-id="417d2-110">管理者の簡易 URL は、組織の内部にあります。</span><span class="sxs-lookup"><span data-stu-id="417d2-110">The Admin simple URL is internal to your organization.</span></span>

<span data-ttu-id="417d2-111">Lync Server 2013 に移行した後は、変更によって単純な Url の DNS レコードと証明書にどのような影響があるかを把握しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="417d2-111">After migrating to Lync Server 2013, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="417d2-112">従来の Lync Server 2010 ディレクターがトポロジで引き続き使用されている場合は、単純な Url への変更は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="417d2-112">If the legacy Lync Server 2010 Director remains in use in the topology, no changes to your simple URLs are required.</span></span> <span data-ttu-id="417d2-113">移行後に Lync Server 2010 ディレクターがトポロジから削除された場合は、Lync Server 2013 プールの1つをポイントするように、単純な URL の DNS レコードを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="417d2-113">If the Lync Server 2010 Director is removed from the topology after migration, the simple URL DNS records must be updated to point to one of the Lync Server 2013 pools.</span></span> <span data-ttu-id="417d2-114">ただし、単純な URL 名を変更する場合は必ず、各ディレクターとフロントエンドサーバーで [ユーザーの有効化] を実行して、変更を登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="417d2-114">Whenever you change a simple URL name, however, you must run Enable-CsComputer on each Director and Front End Server to register the change.</span></span>

<div>

## <a name="changing-simple-urls-after-migration"></a><span data-ttu-id="417d2-115">移行後に単純な Url を変更する</span><span class="sxs-lookup"><span data-stu-id="417d2-115">Changing Simple URLs after Migration</span></span>

<span data-ttu-id="417d2-116">**[シンプルの概要 URL を更新するには、**</span><span class="sxs-lookup"><span data-stu-id="417d2-116">**To update the Meet simple URL**</span></span>

1.  <span data-ttu-id="417d2-117">[トポロジビルダー] で、トップノードの**Lync サーバー**を右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="417d2-117">In Topology Builder, right-click the top node **Lync Server**, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="417d2-118">左側のウィンドウで [**単純な url** ] を選び、[会議 url] を選び**ます。** [会議 url] を選び、[ **url の編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="417d2-118">Select **Simple URLs** in the left pane, then below **Meeting URLs:** select the Meet URL and then click **Edit URL**.</span></span>

3.  <span data-ttu-id="417d2-119">URL を目的の値に更新し、[**OK**] をクリックして編集した URL を保存します。</span><span class="sxs-lookup"><span data-stu-id="417d2-119">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span>

<span data-ttu-id="417d2-120">**管理者の簡易 URL を更新するには**</span><span class="sxs-lookup"><span data-stu-id="417d2-120">**To update the Admin simple URL**</span></span>

1.  <span data-ttu-id="417d2-121">[トポロジビルダー] で、トップノードの**Lync サーバー**を右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="417d2-121">In Topology Builder, right-click the top node **Lync Server**, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="417d2-122">左側のウィンドウで [**単純な url** ] を選び、[**管理アクセス URL** ] ボックスに、Lync Server 2013 コントロールパネルへの管理アクセスに使用する単純な url を入力して、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="417d2-122">Select **Simple URLs** in the left pane, then below **Administrative access URL** box, enter the simple URL you want for administrative access to Lync Server 2013 Control Panel, and then click **OK**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="417d2-123">管理 URL には、できる限りシンプルな URL を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="417d2-123">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="417d2-124">最も簡単なオプションは<STRONG> https://adminです。</STRONG>&lt;ドメイン&gt;。</span><span class="sxs-lookup"><span data-stu-id="417d2-124">The simplest option is <STRONG>https://admin.</STRONG>&lt;domain&gt;.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="417d2-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="417d2-125">See Also</span></span>


[<span data-ttu-id="417d2-126">Lync Server 2013 での簡単な URL の計画</span><span class="sxs-lookup"><span data-stu-id="417d2-126">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

