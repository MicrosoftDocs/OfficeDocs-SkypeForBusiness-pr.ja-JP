---
title: 'Lync Server 2013: 通話管理機能の計画'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for call management features
ms:assetid: 5f557345-5a04-45d6-b274-c02dbfe41b33
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398421(v=OCS.15)
ms:contentKeyID: 48184298
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 206974500bd27c0cbecd902f9e87daf9a435c6dd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41754627"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-call-management-features-in-lync-server-2013"></a><span data-ttu-id="7e400-102">Lync Server 2013 の通話管理機能の計画</span><span class="sxs-lookup"><span data-stu-id="7e400-102">Planning for call management features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e400-103">_**最終更新日:** 2012-12-17_</span><span class="sxs-lookup"><span data-stu-id="7e400-103">_**Topic Last Modified:** 2012-12-17_</span></span>

<span data-ttu-id="7e400-104">エンタープライズ音声通話管理機能は、着信通話のルーティングと応答の方法を制御します。</span><span class="sxs-lookup"><span data-stu-id="7e400-104">Enterprise Voice call management features control how incoming calls are routed and answered.</span></span> <span data-ttu-id="7e400-105">Lync Server 2013 には、次のような通話管理機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="7e400-105">Lync Server 2013 provides the following call management features:</span></span>

  - <span data-ttu-id="7e400-106">**コール パーク**: VoIP ユーザーは、通話を一時的に保留し、同じ電話や別の電話で受けることができます。</span><span class="sxs-lookup"><span data-stu-id="7e400-106">**Call Park**:   Enables voice users to temporarily park a call and then pick it up from the same or another phone.</span></span>

  - <span data-ttu-id="7e400-107">**グループ ピックアップ**: VoIP ユーザーは、通話ピックアップ グループに割り当てられている他の VoIP ユーザーへの電話を受けることができます。</span><span class="sxs-lookup"><span data-stu-id="7e400-107">**Group Pickup**:   Enables voice users to pick up calls that are ringing for other voice users who are assigned to call pickup groups.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7e400-108">グループピックアップは、Lync Server 2013 の累積更新プログラムで、2013年2月に追加されています。</span><span class="sxs-lookup"><span data-stu-id="7e400-108">Group Pickup is new with Cumulative Updates for Lync Server 2013: February 2013.</span></span>

    
    </div>

  - <span data-ttu-id="7e400-109">**応答グループ**: ハント グループまたは対話型音声応答 (IVR) の質問と回答を使用して、着信通話をエージェントのグループにルーティングします。</span><span class="sxs-lookup"><span data-stu-id="7e400-109">**Response Group**:   Routes incoming calls to groups of agents by using hunt groups or interactive voice response (IVR) questions and answers.</span></span>

  - <span data-ttu-id="7e400-110">**お知らせ:**    割り当てられていない番号への通話に対してメッセージを再生するか、通話を別の場所またはその両方にルーティングします。</span><span class="sxs-lookup"><span data-stu-id="7e400-110">**Announcement:**    Plays a message for calls made to an unassigned number, or routes the call elsewhere, or both.</span></span>

<span data-ttu-id="7e400-111">エンタープライズ VoIP の展開を計画している場合、これらの通話管理機能のいずれかまたはすべてを実装するように選択できます。</span><span class="sxs-lookup"><span data-stu-id="7e400-111">If you plan to deploy Enterprise Voice, you can choose to implement any or all of these call management features.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7e400-112">このセクション中</span><span class="sxs-lookup"><span data-stu-id="7e400-112">In This Section</span></span>

  - [<span data-ttu-id="7e400-113">Lync Server 2013 でのコール パークの計画</span><span class="sxs-lookup"><span data-stu-id="7e400-113">Planning for Call Park in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-park.md)

  - [<span data-ttu-id="7e400-114">Lync Server 2013 でグループ通話のピックアップを計画する</span><span class="sxs-lookup"><span data-stu-id="7e400-114">Planning for Group Call Pickup in Lync Server 2013</span></span>](lync-server-2013-planning-for-group-call-pickup.md)

  - [<span data-ttu-id="7e400-115">Lync Server 2013 での応答グループの計画</span><span class="sxs-lookup"><span data-stu-id="7e400-115">Planning for response groups in Lync Server 2013</span></span>](lync-server-2013-planning-for-response-groups.md)

  - [<span data-ttu-id="7e400-116">Lync Server 2013 でのアナウンスの計画</span><span class="sxs-lookup"><span data-stu-id="7e400-116">Planning for announcements in Lync Server 2013</span></span>](lync-server-2013-planning-for-announcements.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

