---
title: 'Lync Server 2013: Lync Room System 管理 Web ポータルの展開'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying the Lync Room System Administrative Web Portal
ms:assetid: ecba5b36-632e-40b9-9c2e-ab825baf7a46
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436324(v=OCS.15)
ms:contentKeyID: 56737621
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7f62a5c7fde401452744abba5f4b6dfec175da2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740807"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="96efb-102">Deploying the Lync Room System Administrative Web Portal in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="96efb-102">Deploying the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96efb-103">_**最終更新日:** 2015-05-04_</span><span class="sxs-lookup"><span data-stu-id="96efb-103">_**Topic Last Modified:** 2015-05-04_</span></span>

<span data-ttu-id="96efb-104">Microsoft Lync Server 2013 Lync Room System (LRS) 管理 Web ポータルは、Lync Room System 会議室を管理するために組織が使用できる web ポータルです。</span><span class="sxs-lookup"><span data-stu-id="96efb-104">The Microsoft Lync Server 2013 Lync Room System (LRS) Administrative Web Portal is a web portal that organizations can use to maintain their Lync Room System conference rooms.</span></span> <span data-ttu-id="96efb-105">管理者は、LRS 管理 Web ポータルを使用して、接続されているオーディオ/ビデオデバイスを監視するなどして、LRS の正常性を監視することができます。</span><span class="sxs-lookup"><span data-stu-id="96efb-105">Administrators can use the LRS Administrative Web Portal to monitor LRS health, for example by monitoring audio/video devices that are connected.</span></span> <span data-ttu-id="96efb-106">このポータルでは、管理者はリモートで診断情報を収集して、会議室の正常性を監視することができます。</span><span class="sxs-lookup"><span data-stu-id="96efb-106">With this portal, administrators can remotely collect diagnostic information to monitor conference room health.</span></span>

<span data-ttu-id="96efb-107">LRS 管理 Web ポータルは、すべての Lync フロントエンドサーバーに展開されます。</span><span class="sxs-lookup"><span data-stu-id="96efb-107">The LRS Administrative Web Portal is deployed on every Lync Front End Server.</span></span> <span data-ttu-id="96efb-108">このガイドでは、LRS 管理 Web ポータルをインストールして構成する方法について管理者向けの手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="96efb-108">This guide provides instructions for administrators about how to install and configure the LRS Administrative Web Portal.</span></span> <span data-ttu-id="96efb-109">Lync Server の管理について理解している管理者、および Lync Server トポロジを変更する管理者ユーザーの権限を持つ管理者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="96efb-109">It is intended for administrators who have knowledge of Lync Server administration, and who have administrator user rights to modify the Lync Server topology.</span></span>

<span data-ttu-id="96efb-110">LRS 管理 Web ポータルがサーバーに展開されると、管理者は、自分のコンピューターまたはノート pc からサイトにログオンして、すべての LRS 室の状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="96efb-110">After LRS Administrative Web Portal is deployed on the server, administrators can check the status of all LRS rooms by logging on to the site from their own computers or laptops.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="96efb-111">LRS 管理 Web ポータルを Microsoft Lync Server 2013 の展開にインストールする場合は、 <A href="http://go.microsoft.com/fwlink/p/?linkid=544806">Lync server 2013 の Microsoft Lync Room System 管理 Web ポータル</A>を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="96efb-111">When you install the LRS Administrative Web Portal in a Microsoft Lync Server 2013 deployment, you should use the <A href="http://go.microsoft.com/fwlink/p/?linkid=544806">Microsoft Lync Room System Administrative Web Portal for Lync Server 2013</A>.</span></span><BR><span data-ttu-id="96efb-112">LRS 管理 Web ポータルの新しいバージョンは、Skype for Business Server 2015 で使用できますが、Skype for Business Server 2015 を展開していない場合は、そのバージョンをインストールしないでください。</span><span class="sxs-lookup"><span data-stu-id="96efb-112">A new version of the LRS Administrative Web Portal is available for Skype for Business Server 2015, but you should not install that version unless you have deployed Skype for Business Server 2015.</span></span> <span data-ttu-id="96efb-113"><A href="http://go.microsoft.com/fwlink/?linkid=544807">Skype For Business Server 2015 の Microsoft Lync Room System 管理 Web ポータル</A>をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="96efb-113">Download the <A href="http://go.microsoft.com/fwlink/?linkid=544807">Microsoft Lync Room System Administrative Web Portal for Skype for Business Server 2015</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="96efb-114">このセクション中</span><span class="sxs-lookup"><span data-stu-id="96efb-114">In This Section</span></span>

[<span data-ttu-id="96efb-115">Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal</span><span class="sxs-lookup"><span data-stu-id="96efb-115">Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal</span></span>](lync-server-2013-configuring-your-environment-for-the-lync-room-system-administrative-web-portal.md)

[<span data-ttu-id="96efb-116">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="96efb-116">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>](lync-server-2013-installing-the-lync-room-system-administrative-web-portal.md)

[<span data-ttu-id="96efb-117">Using the Lync Room System Administrative Web Portal in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="96efb-117">Using the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>](lync-server-2013-using-the-lync-room-system-administrative-web-portal.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="96efb-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="96efb-118">See Also</span></span>


[<span data-ttu-id="96efb-119">Lync Server 2013 での電話会議の展開</span><span class="sxs-lookup"><span data-stu-id="96efb-119">Deploying conferencing in Lync Server 2013</span></span>](lync-server-2013-deploying-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

