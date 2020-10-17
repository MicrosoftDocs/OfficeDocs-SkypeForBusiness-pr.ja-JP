---
title: 'Lync Server 2013: Lync Room System 管理 Web ポータルの展開'
description: 'Lync Server 2013: Lync Room System 管理 Web ポータルの展開'
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
ms.openlocfilehash: e67723b3ddf3f452c53411e560420bb0b043128e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565983"
---
# <a name="deploying-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="d6dc6-103">Lync Server 2013 での Lync Room System 管理 Web ポータルの展開</span><span class="sxs-lookup"><span data-stu-id="d6dc6-103">Deploying the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6dc6-104">_**トピックの最終更新日:** 2015-05-04_</span><span class="sxs-lookup"><span data-stu-id="d6dc6-104">_**Topic Last Modified:** 2015-05-04_</span></span>

<span data-ttu-id="d6dc6-105">Microsoft Lync Server 2013 Lync Room System (LRS) 管理 Web ポータルは、組織が Lync Room System の会議室を維持するために使用できる web ポータルです。</span><span class="sxs-lookup"><span data-stu-id="d6dc6-105">The Microsoft Lync Server 2013 Lync Room System (LRS) Administrative Web Portal is a web portal that organizations can use to maintain their Lync Room System conference rooms.</span></span> <span data-ttu-id="d6dc6-106">管理者は、LRS 管理 Web ポータルを使用して、接続されているオーディオ/ビデオデバイスを監視するなど、LRS の正常性を監視できます。</span><span class="sxs-lookup"><span data-stu-id="d6dc6-106">Administrators can use the LRS Administrative Web Portal to monitor LRS health, for example by monitoring audio/video devices that are connected.</span></span> <span data-ttu-id="d6dc6-107">このポータルを使用すると、管理者はリモートで診断情報を収集して、会議室の状態を監視できます。</span><span class="sxs-lookup"><span data-stu-id="d6dc6-107">With this portal, administrators can remotely collect diagnostic information to monitor conference room health.</span></span>

<span data-ttu-id="d6dc6-108">LRS 管理 Web ポータルは、すべての Lync フロントエンドサーバーに展開されます。</span><span class="sxs-lookup"><span data-stu-id="d6dc6-108">The LRS Administrative Web Portal is deployed on every Lync Front End Server.</span></span> <span data-ttu-id="d6dc6-109">このガイドでは、LRS 管理 Web ポータルをインストールして構成する方法に関する管理者向けの手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="d6dc6-109">This guide provides instructions for administrators about how to install and configure the LRS Administrative Web Portal.</span></span> <span data-ttu-id="d6dc6-110">これは、Lync Server の管理について理解している管理者と、Lync Server トポロジを変更する管理者のユーザー権限を持つ管理者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="d6dc6-110">It is intended for administrators who have knowledge of Lync Server administration, and who have administrator user rights to modify the Lync Server topology.</span></span>

<span data-ttu-id="d6dc6-111">LRS 管理 Web ポータルがサーバーに展開されると、管理者は自分のコンピューターまたはラップトップからサイトにログオンすることによって、すべての LRS ルームの状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="d6dc6-111">After LRS Administrative Web Portal is deployed on the server, administrators can check the status of all LRS rooms by logging on to the site from their own computers or laptops.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d6dc6-112">LRS 管理 Web ポータルを Microsoft Lync Server 2013 の展開にインストールする場合は、 <A href="https://go.microsoft.com/fwlink/p/?linkid=544806">Lync server 2013 の Microsoft Lync Room System 管理 Web ポータル</A>を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6dc6-112">When you install the LRS Administrative Web Portal in a Microsoft Lync Server 2013 deployment, you should use the <A href="https://go.microsoft.com/fwlink/p/?linkid=544806">Microsoft Lync Room System Administrative Web Portal for Lync Server 2013</A>.</span></span><BR><span data-ttu-id="d6dc6-113">LRS 管理 Web ポータルの新しいバージョンが Skype for Business Server 2015 で利用可能ですが、Skype for business Server 2015 を展開していない限り、このバージョンはインストールしないでください。</span><span class="sxs-lookup"><span data-stu-id="d6dc6-113">A new version of the LRS Administrative Web Portal is available for Skype for Business Server 2015, but you should not install that version unless you have deployed Skype for Business Server 2015.</span></span> <span data-ttu-id="d6dc6-114">Skype for <A href="https://go.microsoft.com/fwlink/?linkid=544807">Business Server 2015 用の Microsoft Lync Room System 管理 Web ポータルを</A>ダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="d6dc6-114">Download the <A href="https://go.microsoft.com/fwlink/?linkid=544807">Microsoft Lync Room System Administrative Web Portal for Skype for Business Server 2015</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d6dc6-115">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d6dc6-115">In This Section</span></span>

[<span data-ttu-id="d6dc6-116">Lync Room System 管理 Web ポータル用に Lync Server 2013 環境を構成する</span><span class="sxs-lookup"><span data-stu-id="d6dc6-116">Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal</span></span>](lync-server-2013-configuring-your-environment-for-the-lync-room-system-administrative-web-portal.md)

[<span data-ttu-id="d6dc6-117">Lync Server 2013 での Lync Room System 管理 Web ポータルのインストール</span><span class="sxs-lookup"><span data-stu-id="d6dc6-117">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>](lync-server-2013-installing-the-lync-room-system-administrative-web-portal.md)

[<span data-ttu-id="d6dc6-118">Lync Server 2013 での Lync Room System 管理 Web ポータルの使用</span><span class="sxs-lookup"><span data-stu-id="d6dc6-118">Using the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>](lync-server-2013-using-the-lync-room-system-administrative-web-portal.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d6dc6-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="d6dc6-119">See Also</span></span>


[<span data-ttu-id="d6dc6-120">Lync Server 2013 での会議の展開</span><span class="sxs-lookup"><span data-stu-id="d6dc6-120">Deploying conferencing in Lync Server 2013</span></span>](lync-server-2013-deploying-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

