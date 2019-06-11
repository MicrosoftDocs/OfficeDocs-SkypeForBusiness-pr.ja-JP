---
title: 'Lync Server 2013: Office Web Apps サーバーの構成を検証する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Validating the configuration of Office Web Apps Server
ms:assetid: f6e8ecbf-305d-4a13-92d0-b61dbd82b0ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205393(v=OCS.15)
ms:contentKeyID: 48185859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35844ae2ae73937d6840e480dc57393b91d13eaf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848247"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-the-configuration-of-office-web-apps-server-in-lync-server-2013"></a><span data-ttu-id="ad6cf-102">Lync Server 2013 で Office Web Apps サーバーの構成を検証する</span><span class="sxs-lookup"><span data-stu-id="ad6cf-102">Validating the configuration of Office Web Apps Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad6cf-103">_**最終更新日:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="ad6cf-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="ad6cf-104">Office Web Apps サーバーをトポロジに追加した後で、そのトポロジが公開されると、Lync Server イベントログに2つの新しいイベントログイベントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ad6cf-104">After Office Web Apps Server has been added to the topology, and after that topology has been published, you should see two new event log events in the Lync Server event log.</span></span> <span data-ttu-id="ad6cf-105">最初に、LS データ MCU イベント (イベント ID 41034) を追加する必要があります。このイベントは、Office Web Apps サーバーが検出されたことを報告します。</span><span class="sxs-lookup"><span data-stu-id="ad6cf-105">First, an LS Data MCU event (event ID 41034) should be added; this event will report that the Office Web Apps Server has been discovered:</span></span>

<span data-ttu-id="ad6cf-106">**Web 会議サーバー Office Web Apps サーバーが検出され、PowerPoint コンテンツが有効になりました。**</span><span class="sxs-lookup"><span data-stu-id="ad6cf-106">**Web Conferencing Server Office Web Apps Server is discovered, PowerPoint content is enabled.**</span></span>

<span data-ttu-id="ad6cf-p102">これに加えて、Office Web Apps Server URL を報告する別の LS Data MCU イベント (イベント ID 41032) が表示されます。たとえば、次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="ad6cf-p102">In addition to that you should see another LS Data MCU event (event ID 41032) that reports back Office Web Apps Server URLs. For example, you should see something similar to this:</span></span>

<span data-ttu-id="ad6cf-109">**Web 会議サーバー Office Web Apps サーバー検出が成功しました。**</span><span class="sxs-lookup"><span data-stu-id="ad6cf-109">**Web Conferencing Server Office Web Apps Server discovery has succeeded.**</span></span>

<span data-ttu-id="ad6cf-110">**Office Web Apps サーバーの内部発表者ページ:https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**</span><span class="sxs-lookup"><span data-stu-id="ad6cf-110">**Office Web Apps Server internal presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**</span></span>

<span data-ttu-id="ad6cf-111">**Office Web Apps サーバーの内部出席者ページ:https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**</span><span class="sxs-lookup"><span data-stu-id="ad6cf-111">**Office Web Apps Server internal attendee page: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**</span></span>

<span data-ttu-id="ad6cf-112">**Office Web Apps サーバーの外部発表者ページ:https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**</span><span class="sxs-lookup"><span data-stu-id="ad6cf-112">**Office Web Apps Server external presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**</span></span>

<span data-ttu-id="ad6cf-113">**Office Web Apps サーバーの内部出席者ページ:https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**</span><span class="sxs-lookup"><span data-stu-id="ad6cf-113">**Office Web Apps Server internal attendee page: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**</span></span>

<span data-ttu-id="ad6cf-114">Office Web Apps サーバーの検出に失敗したことを示す、イベント ID が41033の LS データ MCU イベントが表示される場合。</span><span class="sxs-lookup"><span data-stu-id="ad6cf-114">If you see an LS Data MCU event with the event ID of 41033 that means that Office Web Apps Server discovery has failed.</span></span> <span data-ttu-id="ad6cf-115">その場合、Microsoft Lync Server 2013 は、新しく構成された Office Web Apps サーバーを検出するために必要な回数だけ試します。</span><span class="sxs-lookup"><span data-stu-id="ad6cf-115">In that case, Microsoft Lync Server 2013 will try as many times as needed to discover the newly-configured Office Web Apps Server.</span></span> <span data-ttu-id="ad6cf-116">検出プロセスが繰り返し失敗する場合は、トポロジドキュメントから Office Web Apps サーバーを削除し、更新されたトポロジを公開して、接続の問題が解決した後で、Office Web Apps サーバーをトポロジに追加してみます。</span><span class="sxs-lookup"><span data-stu-id="ad6cf-116">If the discovery process fails repeatedly you should remove Office Web Apps Server from your topology document, publish the updated topology, and then try adding Office Web Apps Server back to the topology after the connectivity issues have been resolved.</span></span>

<span data-ttu-id="ad6cf-117">Office Web Apps サーバーが正しく構成されていて、検出プロセスによって認識されている場合は、Microsoft Lync 2013 クライアントのペア間で PowerPoint プレゼンテーションを共有することで、Office Web Apps サーバーが正常に動作していることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="ad6cf-117">If Office Web Apps Server appears to be configured correctly and has been recognized by the discovery process you can verify that Office Web Apps Server is working as expected by sharing a PowerPoint presentation between a pair of Microsoft Lync 2013 clients.</span></span> <span data-ttu-id="ad6cf-118">ユーザー A が PowerPoint プレゼンテーションを読み込み、表示できる場合に、ユーザー B が会議に参加すると、そのプレゼンテーションが Office Web Apps サーバーで動作することを確認できます。</span><span class="sxs-lookup"><span data-stu-id="ad6cf-118">If User A can load and display the PowerPoint presentation and if User B can then join the meeting and see that presentation then Office Web Apps Server is working.</span></span>

<span data-ttu-id="ad6cf-119">Office Web Apps サーバーが正しく構成されているように見えても、PowerPoint プレゼンテーションを共有しようとすると、"サーバーの接続に問題が発生したため、一部の共有機能を利用できません" というエラーメッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="ad6cf-119">Even if Office Web Apps Server appears to be configured correctly, you could potentially receive the error message “Some sharing features are unavailable due to server connectivity issues” when you try sharing a PowerPoint presentation.</span></span> <span data-ttu-id="ad6cf-120">このエラーメッセージが表示された場合は、新しい Office Web Apps サーバーに関連付けられたフロントエンドサーバー (またはサーバー) を再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad6cf-120">If you receive that error message you should restart the Front End server (or servers) associated with the new Office Web Apps Server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

