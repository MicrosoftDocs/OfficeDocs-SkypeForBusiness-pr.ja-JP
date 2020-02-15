---
title: 'Lync Server 2013: 会議の要件の定義'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your requirements for conferencing
ms:assetid: 5c83e268-22bf-42b2-bac3-3237b5e02e03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204935(v=OCS.15)
ms:contentKeyID: 48184255
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 982643a33a2855075eac5372fa0140c3a69b39bd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42032452"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="6862a-102">Lync Server 2013 での会議の要件の定義</span><span class="sxs-lookup"><span data-stu-id="6862a-102">Defining your requirements for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6862a-103">_**トピックの最終更新日:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="6862a-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="6862a-p101">どの会議機能を展開するかを決定するときには、ユーザーに提供したい機能とネットワーク帯域幅の能力を考慮する必要があります。次に示す質問の一覧では、組織の要件に基づいて展開する必要のある会議機能を決定するための会議計画プロセスを辿ります。</span><span class="sxs-lookup"><span data-stu-id="6862a-p101">When you are determining which conferencing capabilities to deploy, you need to consider the features that you want available to your users and your network bandwidth capabilities. The following list of questions guides you through the conferencing planning process to determine what features of conferencing you should deploy, based on your organization’s requirements.</span></span>

  - <span data-ttu-id="6862a-106">**ドキュメントのコラボレーションやアプリケーション共有を含む Web 会議を有効にしますか。**</span><span class="sxs-lookup"><span data-stu-id="6862a-106">**Do you want to enable web conferencing, which includes document collaboration and application sharing?**</span></span>
    
    <span data-ttu-id="6862a-107">その場合は、Microsoft Lync Server 2013、計画ツール、またはトポロジビルダーでフロントエンドプール用の会議を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6862a-107">If so, you must enable conferencing for your Front End pool in the Microsoft Lync Server 2013, Planning Tool or in Topology Builder.</span></span> <span data-ttu-id="6862a-108">会議を有効にすると、Web 会議と音声ビデオ会議の両方が有効になります。</span><span class="sxs-lookup"><span data-stu-id="6862a-108">When you enable conferencing, you enable both web conferencing and A/V conferencing.</span></span>
    
    <span data-ttu-id="6862a-109">アプリケーション共有では、ドキュメントのコラボレーションよりも多くのネットワーク帯域幅を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6862a-109">Application sharing requires and uses more network bandwidth than document collaboration.</span></span> <span data-ttu-id="6862a-110">Lync Server 2013 には、各アプリケーション共有セッションを制御するための調整メカニズムが用意されています。</span><span class="sxs-lookup"><span data-stu-id="6862a-110">Lync Server 2013 provides a throttling mechanism to control each application sharing session.</span></span> <span data-ttu-id="6862a-111">既定では、セッションあたり 1.5 KB/秒に設定されます。</span><span class="sxs-lookup"><span data-stu-id="6862a-111">By default, this is set to 1.5 KB/second for each session.</span></span>
    
    <span data-ttu-id="6862a-112">アプリケーション共有は有効にせず、ドキュメントのコラボレーションを有効にする場合は、会議を有効にし、会議ポリシーを使用してアプリケーション共有を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="6862a-112">If you do not want to enable application sharing but you do want document collaboration, you can enable conferencing and use meeting policies to disable application sharing.</span></span> <span data-ttu-id="6862a-113">会議ポリシーの構成の詳細については、「 [Lync Server 2013 の会議ポリシー](lync-server-2013-conferencing-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6862a-113">For details about configuring meeting policies, see [Conferencing policies in Lync Server 2013](lync-server-2013-conferencing-policies.md).</span></span>
    
    <span data-ttu-id="6862a-114">ユーザーが PowerPoint プレゼンテーションを共有できるようにするには、Office Web Apps サーバーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6862a-114">To enable users to share PowerPoint presentations, you need to configure Office Web Apps Server.</span></span> <span data-ttu-id="6862a-115">Office Web Apps サーバーの構成の詳細については、「 [Office Web Apps server および Lync Server 2013 との統合の構成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6862a-115">For details about configuring Office Web Apps Server, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

  - <span data-ttu-id="6862a-116">**音声ビデオ会議を有効にしますか。**</span><span class="sxs-lookup"><span data-stu-id="6862a-116">**Do you want to enable A/V conferencing?**</span></span>
    
    <span data-ttu-id="6862a-117">その場合は、Lync Server 2013、計画ツール、またはトポロジビルダーで、フロントエンドプール用の会議を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6862a-117">If so, you must enable conferencing for your Front End pool in the Lync Server 2013, Planning Tool or in Topology Builder.</span></span> <span data-ttu-id="6862a-118">会議を有効にすると、Web 会議と音声ビデオ会議の両方が有効になります。</span><span class="sxs-lookup"><span data-stu-id="6862a-118">When you enable conferencing, you enable both web conferencing and A/V conferencing.</span></span>
    
    <span data-ttu-id="6862a-p107">音声ビデオ会議では、Web 会議 (ドキュメントのコラボレーションやアプリケーション共有を含む) よりも多くのネットワーク帯域幅を使用する必要があります。音声ビデオ会議は有効にせず、Web 会議を有効にする場合は、会議を有効にし、会議ポリシーを使用して音声ビデオ会議を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="6862a-p107">A/V conferencing requires and uses more network bandwidth than web conferencing (which includes document collaboration and application sharing). If you do not want to enable A/V conferencing but you do want to enable web conferencing, you can enable conferencing and use meeting policies to disable A/V conferences.</span></span>
    
    <span data-ttu-id="6862a-p108">電話会議を有効にして、ビデオ会議は無効にする場合は、音声ビデオ会議を有効にし、会議ポリシーを使用してビデオ会議を使用できないようにすることができます。 あるいは、音声ビデオ会議を有効にして、特定のユーザーだけが音声ビデオ会議を開始または音声ビデオ会議に参加できるようにすることが可能です。</span><span class="sxs-lookup"><span data-stu-id="6862a-p108">If you do want to enable audio conferences but not video conferences, you can enable A/V conferencing and use meeting policies to prevent video conferences. Alternatively, you can enable A/V conferencing and enable only certain users to start or participate in A/V conferences.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6862a-123">音声ビデオ会議を使用するためにエンタープライズ Voip は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="6862a-123">Enterprise Voice is not required for you to use A/V conferencing.</span></span> <span data-ttu-id="6862a-124">音声ビデオ会議を有効にすると、電話ソリューション用に PBX を使用していても、ユーザーはオーディオ デバイスがあればオーディオを会議に追加できます。</span><span class="sxs-lookup"><span data-stu-id="6862a-124">If you enable A/V conferencing, your users can add audio to their conferences if they have audio devices, even if you use a PBX for your telephone solution.</span></span>

    
    </div>

  - <span data-ttu-id="6862a-125">**PSTN 電話を使用している場合、ユーザーが会議のオーディオ部分に参加できるようにしますか。**</span><span class="sxs-lookup"><span data-stu-id="6862a-125">**Do you want to enable users to join the audio portion of conferences when using a PSTN phone?**</span></span>
    
    <span data-ttu-id="6862a-p110">その場合は、ダイヤルイン会議を展開して有効にする必要があります。 組織内と外部の両方の招待ユーザーが、PSTN 電話を使用して会議のオーディオ部分に参加できるようになります。</span><span class="sxs-lookup"><span data-stu-id="6862a-p110">If so, deploy and enable dial-in conferencing. Invited users, both inside and outside your organization, can then join the audio portion of conferences by using a PSTN phone.</span></span>

  - <span data-ttu-id="6862a-128">**Lync Server 2013 クライアントを使用している外部ユーザーが、有効にした会議の種類に参加できるようにしますか。**</span><span class="sxs-lookup"><span data-stu-id="6862a-128">**Do you want to enable external users with Lync Server 2013 clients to join the types of conferences that you have enabled?**</span></span>
    
    <span data-ttu-id="6862a-129">その場合は、エッジ サーバーを展開します。</span><span class="sxs-lookup"><span data-stu-id="6862a-129">If so, you should deploy Edge Servers.</span></span> <span data-ttu-id="6862a-130">会議への外部参加を許可することで、Lync Server 2013 への投資を最大限に活用できます。</span><span class="sxs-lookup"><span data-stu-id="6862a-130">By allowing external participation in meetings, you maximize your investment in Lync Server 2013.</span></span> <span data-ttu-id="6862a-131">たとえば、Lync Server 2013 を使用しているラップトップを使用しているユーザーは、自宅、空港、お客様のサイトなどのどこからでも会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="6862a-131">For example, users with laptops with Lync Server 2013 can join conferences from wherever they are—at home, in the airport, or at customer sites.</span></span>
    
    <span data-ttu-id="6862a-132">また、エッジ サーバーを展開していれば、顧客やベンダーなどの他の組織とフェデレーション関係を築くことができ、これらの組織のユーザーは、こちらのユーザーとより容易に共同作業を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="6862a-132">Additionally, with Edge Servers deployed you can create federated relationships with other organizations-such as your customers or vendors-and users from those organizations can more easily collaborate with your users.</span></span>
    
    <span data-ttu-id="6862a-133">エッジサーバーの展開の詳細については、「 [lync server 2013 での外部ユーザーアクセスの計画](lync-server-2013-planning-for-external-user-access.md)」および「 [lync server 2013 での外部ユーザーアクセスの展開](lync-server-2013-deploying-external-user-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6862a-133">For details about deploying Edge Servers, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span></span> <span data-ttu-id="6862a-134">Office Web Apps サーバーの外部アクセスを有効にする方法の詳細については、「 [Office Web Apps サーバーを、リバースプロキシサーバーを使用して Lync server 2013 で公開](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6862a-134">For details about enabling external access for Office Web Apps Server, see [Publishing Office Web Apps Server in Lync Server 2013 using a reverse proxy server](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md).</span></span>

  - <span data-ttu-id="6862a-135">**Lync Server 2013 会議に参加できるクライアントを制御しますか。**</span><span class="sxs-lookup"><span data-stu-id="6862a-135">**Do you want to control the clients that can join Lync Server 2013 meetings?**</span></span>
    
    <span data-ttu-id="6862a-136">その場合は、サポートするクライアントオプションのみが利用できるように、会議参加ページを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6862a-136">If so, you should configure the meeting join page so that only the client options that you want to support are available.</span></span> <span data-ttu-id="6862a-137">ユーザーがスケジュールされた会議に参加するためのリンクをクリックするたびに、Lync Server 2013 はクライアントがコンピューターに既にインストールされているかどうかを検出します。</span><span class="sxs-lookup"><span data-stu-id="6862a-137">Each time a user clicks a link to join a scheduled meeting, Lync Server 2013 detects whether a client is already installed on the computer.</span></span> <span data-ttu-id="6862a-138">次に、既定のクライアントを起動し、代替クライアントへのリンクが含まれている [ミーティング参加] ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="6862a-138">It then starts the default client and opens the meeting join page, which contains links for alternate clients.</span></span> <span data-ttu-id="6862a-139">会議参加ページには、Microsoft Lync Web App を使用するオプションが常に表示されます。</span><span class="sxs-lookup"><span data-stu-id="6862a-139">The meeting join page always contains the option to use Microsoft Lync Web App.</span></span> <span data-ttu-id="6862a-140">このオプションに加えて、Communicator の出席者と以前のバージョンのリンクを含めるかどうかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="6862a-140">In addition to this option, you can decide whether to include links for Attendee and previous versions of Communicator.</span></span> <span data-ttu-id="6862a-141">詳細については、「 [Lync Server 2013 での会議参加ページの構成](lync-server-2013-configuring-the-meeting-join-page.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6862a-141">For details, see [Configuring the meeting join page in Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6862a-142">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="6862a-142">In This Section</span></span>

  - [<span data-ttu-id="6862a-143">Lync Server 2013 での Web 会議の要件</span><span class="sxs-lookup"><span data-stu-id="6862a-143">Web conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-web-conferencing-requirements.md)

  - [<span data-ttu-id="6862a-144">Lync Server 2013 での音声ビデオ会議の要件</span><span class="sxs-lookup"><span data-stu-id="6862a-144">A/V conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-a-v-conferencing-requirements.md)

  - [<span data-ttu-id="6862a-145">Lync Server 2013 でのダイヤルイン会議の要件</span><span class="sxs-lookup"><span data-stu-id="6862a-145">Dial-in conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-requirements.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6862a-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="6862a-146">See Also</span></span>


[<span data-ttu-id="6862a-147">Lync Server 2013 での会議の計画</span><span class="sxs-lookup"><span data-stu-id="6862a-147">Planning for conferencing in Lync Server 2013</span></span>](lync-server-2013-planning-for-conferencing.md)  
[<span data-ttu-id="6862a-148">Lync Server 2013 での会議の展開チェックリスト</span><span class="sxs-lookup"><span data-stu-id="6862a-148">Deployment checklist for conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

