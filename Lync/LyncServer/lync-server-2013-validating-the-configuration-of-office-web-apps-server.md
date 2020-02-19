---
title: 'Lync Server 2013: Office Web Apps サーバーの構成の検証'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating the configuration of Office Web Apps Server
ms:assetid: f6e8ecbf-305d-4a13-92d0-b61dbd82b0ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205393(v=OCS.15)
ms:contentKeyID: 48185859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c1cabdf03250a056c2fedaeb41e1f6839aea75a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42113410"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="validating-the-configuration-of-office-web-apps-server-in-lync-server-2013"></a><span data-ttu-id="d80ff-102">Lync Server 2013 での Office Web Apps サーバーの構成の検証</span><span class="sxs-lookup"><span data-stu-id="d80ff-102">Validating the configuration of Office Web Apps Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d80ff-103">_**トピックの最終更新日:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="d80ff-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="d80ff-104">Office Web Apps サーバーをトポロジに追加した後、そのトポロジが公開された後、Lync Server イベントログに2つの新しいイベントログイベントが表示されるはずです。</span><span class="sxs-lookup"><span data-stu-id="d80ff-104">After Office Web Apps Server has been added to the topology, and after that topology has been published, you should see two new event log events in the Lync Server event log.</span></span> <span data-ttu-id="d80ff-105">最初に、LS データ MCU イベント (イベント ID 41034) を追加する必要があります。このイベントは、Office Web Apps サーバーが検出されたことを報告します。</span><span class="sxs-lookup"><span data-stu-id="d80ff-105">First, an LS Data MCU event (event ID 41034) should be added; this event will report that the Office Web Apps Server has been discovered:</span></span>

<span data-ttu-id="d80ff-106">**Web 会議サーバー Office Web Apps サーバーが検出され、PowerPoint コンテンツが有効になっています。**</span><span class="sxs-lookup"><span data-stu-id="d80ff-106">**Web Conferencing Server Office Web Apps Server is discovered, PowerPoint content is enabled.**</span></span>

<span data-ttu-id="d80ff-p102">これに加えて、Office Web Apps Server URL を報告する別の LS Data MCU イベント (イベント ID 41032) が表示されます。たとえば、次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="d80ff-p102">In addition to that you should see another LS Data MCU event (event ID 41032) that reports back Office Web Apps Server URLs. For example, you should see something similar to this:</span></span>

<span data-ttu-id="d80ff-109">**Web 会議サーバー Office Web Apps サーバーの検出が成功しました。**</span><span class="sxs-lookup"><span data-stu-id="d80ff-109">**Web Conferencing Server Office Web Apps Server discovery has succeeded.**</span></span>

<span data-ttu-id="d80ff-110">**Office Web Apps サーバー内部発表者ページ:https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**</span><span class="sxs-lookup"><span data-stu-id="d80ff-110">**Office Web Apps Server internal presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**</span></span>

<span data-ttu-id="d80ff-111">**Office Web Apps サーバーの内部出席者ページ:https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**</span><span class="sxs-lookup"><span data-stu-id="d80ff-111">**Office Web Apps Server internal attendee page: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**</span></span>

<span data-ttu-id="d80ff-112">**Office Web Apps サーバーの外部発表者ページ:https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**</span><span class="sxs-lookup"><span data-stu-id="d80ff-112">**Office Web Apps Server external presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**</span></span>

<span data-ttu-id="d80ff-113">**Office Web Apps サーバーの内部出席者ページ:https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**</span><span class="sxs-lookup"><span data-stu-id="d80ff-113">**Office Web Apps Server internal attendee page: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**</span></span>

<span data-ttu-id="d80ff-114">イベント ID が 41033 の LS Data MCU イベントが表示された場合、Office Web Apps Server の検出が失敗したことを意味します。</span><span class="sxs-lookup"><span data-stu-id="d80ff-114">If you see an LS Data MCU event with the event ID of 41033 that means that Office Web Apps Server discovery has failed.</span></span> <span data-ttu-id="d80ff-115">その場合、Microsoft Lync Server 2013 は、新しく構成された Office Web Apps サーバーを検出するために必要な回数だけ試行します。</span><span class="sxs-lookup"><span data-stu-id="d80ff-115">In that case, Microsoft Lync Server 2013 will try as many times as needed to discover the newly-configured Office Web Apps Server.</span></span> <span data-ttu-id="d80ff-116">検出プロセスが繰り返し失敗する場合、Office Web Apps Server をトポロジー ドキュメントから削除し、更新されたトポロジーを公開し、接続の問題が解決された後に Office Web Apps Server をトポロジーに再度追加します。</span><span class="sxs-lookup"><span data-stu-id="d80ff-116">If the discovery process fails repeatedly you should remove Office Web Apps Server from your topology document, publish the updated topology, and then try adding Office Web Apps Server back to the topology after the connectivity issues have been resolved.</span></span>

<span data-ttu-id="d80ff-117">Office Web Apps サーバーが正しく構成されており、探索プロセスで認識されている場合は、Microsoft Lync 2013 クライアントのペア間で PowerPoint プレゼンテーションを共有することによって、Office Web Apps サーバーが正常に機能していることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="d80ff-117">If Office Web Apps Server appears to be configured correctly and has been recognized by the discovery process you can verify that Office Web Apps Server is working as expected by sharing a PowerPoint presentation between a pair of Microsoft Lync 2013 clients.</span></span> <span data-ttu-id="d80ff-118">ユーザー A が PowerPoint プレゼンテーションを読み込んで表示でき、ユーザー B が会議に参加してそのプレゼンテーションを表示できる場合、Office Web Apps Server は機能しています。</span><span class="sxs-lookup"><span data-stu-id="d80ff-118">If User A can load and display the PowerPoint presentation and if User B can then join the meeting and see that presentation then Office Web Apps Server is working.</span></span>

<span data-ttu-id="d80ff-p105">Office Web Apps Server が正しく構成されているような場合でも、PowerPoint プレゼンテーションを共有する際に「サーバーの接続問題により、一部の共有機能が使用できません」というエラー メッセージを受け取ることがあります。このエラー メッセージを受け取った場合、新しい Office Web Apps Server に関連したフロントエンド サーバー (場合によっては複数) を再起動します。</span><span class="sxs-lookup"><span data-stu-id="d80ff-p105">Even if Office Web Apps Server appears to be configured correctly, you could potentially receive the error message “Some sharing features are unavailable due to server connectivity issues” when you try sharing a PowerPoint presentation. If you receive that error message you should restart the Front End server (or servers) associated with the new Office Web Apps Server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

