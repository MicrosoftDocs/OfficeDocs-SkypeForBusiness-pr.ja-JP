---
title: 'Lync Server 2013: 発信者番号のプレゼンテーション'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Caller ID presentation
ms:assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204980(v=OCS.15)
ms:contentKeyID: 48184425
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f8feb08297b5588e790917a346557e5e6434930
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198540"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="caller-id-presentation-in-lync-server-2013"></a><span data-ttu-id="3306a-102">Lync Server 2013 の発信者番号のプレゼンテーション</span><span class="sxs-lookup"><span data-stu-id="3306a-102">Caller ID presentation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3306a-103">_**トピックの最終更新日:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="3306a-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="3306a-104">Lync Server 2010 では、発信者の電話番号 (と呼ばれる電話番号) は、トランクピア (つまり、関連付けられたゲートウェイ、構内交換機 (PBX)、または SIP トランク) で必要とされるローカルのダイヤル形式に変換できます。</span><span class="sxs-lookup"><span data-stu-id="3306a-104">With Lync Server 2010, the called party’s phone number (that is, the phone number called) can be translated from E.164 format to the local dialing format that is required by the trunk peer (that is, the associated gateway, private branch exchange (PBX), or SIP trunk).</span></span> <span data-ttu-id="3306a-105">これを行うためには、トランク ピアへのルーティングの前に要求 URI を変換する変換ルールを 1 つ以上定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3306a-105">To do this, you must define one or more translation rules to translate the Request URI before routing it to the trunk peer.</span></span>

<span data-ttu-id="3306a-106">Lync Server 2013 では、発信者の電話番号 (発信者の発信元の電話番号) を e.164 形式から、トランクピアに必要なローカルのダイヤル形式に変換するオプションも導入されています。</span><span class="sxs-lookup"><span data-stu-id="3306a-106">Lync Server 2013 introduces the option to also translate the calling party’s phone number (that is, the phone number that the caller is calling from) from E.164 format to the local dialing format that is required by the trunk peer.</span></span> <span data-ttu-id="3306a-107">たとえば、ダイヤル文字列の冒頭から +44 を取り除いて 0114 に置き換える変換ルールを記述できます。</span><span class="sxs-lookup"><span data-stu-id="3306a-107">For example, you can write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="3306a-108">**Lync Server コントロールパネルを使用して発信者番号を構成するには**</span><span class="sxs-lookup"><span data-stu-id="3306a-108">**To configure Caller ID by using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="3306a-109">RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="3306a-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="3306a-110">詳細については、「 [Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3306a-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="3306a-111">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="3306a-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3306a-112">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3306a-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3306a-113">左側のナビゲーション バーで [**音声のルーティング**] をクリックし、[**トランク構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3306a-113">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

4.  <span data-ttu-id="3306a-114">[**トランク構成**] ページで、既存のトランク (たとえば [**グローバル**] トランク) をダブルクリックして [**編集トランク構成**] ダイアログ ボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="3306a-114">On the **Trunk Configuration** page, double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>

5.  <span data-ttu-id="3306a-115">発信者番号のプレゼンテーションを構成するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="3306a-115">To configure caller ID presentation:</span></span>
    
      - <span data-ttu-id="3306a-116">エンタープライズ VoIP 展開で利用できるすべての変換ルールの一覧から 1 つ以上のルールを選択するには、**[選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3306a-116">To choose one or more rules from a list of all translation rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="3306a-117">[**発信者番号の変換ルール**] で、トランクに関連付けるルールをクリックし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3306a-117">In **Calling number translation rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="3306a-118">新しい変換ルールを定義してトランクに関連付ける場合は、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3306a-118">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="3306a-119">新しいルールの定義の詳細については、「展開」のドキュメントの「 [Lync Server 2013 で変換ルールを定義](lync-server-2013-defining-translation-rules.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3306a-119">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="3306a-120">既にトランクに関連付けられている変換ルールを編集するには、ルールの名前をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3306a-120">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="3306a-121">詳細については、「展開」のドキュメントの「 [Lync Server 2013 で変換ルールを定義](lync-server-2013-defining-translation-rules.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3306a-121">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="3306a-122">既存の変換ルールをコピーしてそれを基に新しいルールを定義するには、ルールの名前をクリックして [**コピー**] をクリックし、[**貼り付け**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3306a-122">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="3306a-123">詳細については、「 [Lync Server 2013 で変換ルールを定義](lync-server-2013-defining-translation-rules.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3306a-123">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="3306a-124">トランクから変換ルールを削除するには、ルールの名前を選択状態にし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3306a-124">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="3306a-125">関連付けられたトランク ピアに対して変換ルールを構成している場合は、2 つのルールが競合する危険があるため、変換ルールをトランクに関連付けないでください。</span><span class="sxs-lookup"><span data-stu-id="3306a-125">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

