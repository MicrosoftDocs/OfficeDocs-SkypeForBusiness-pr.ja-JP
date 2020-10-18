---
title: 'Lync Server 2013: 新しいクライアントバージョンポリシールールを作成または変更する'
description: 'Lync Server 2013: 新しいクライアントバージョンポリシールールを作成または変更します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a new client version policy rule
ms:assetid: 6f879d99-8401-41e0-a562-195c890d63ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898478(v=OCS.15)
ms:contentKeyID: 50873758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11ebcf17d5cb14fd519fba8ad36be10894fabdb9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574623"
---
# <a name="create-or-modify-a-new-client-version-policy-rule-in-lync-server-2013"></a><span data-ttu-id="16c22-103">Lync Server 2013 で新しいクライアントバージョンポリシールールを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="16c22-103">Create or modify a new client version policy rule in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16c22-104">_**トピックの最終更新日:** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="16c22-104">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="16c22-105">クライアントバージョンポリシールールは、ユーザーが特定のクライアントおよびクライアントバージョンでログオンしようとしたときに実行する必要のあるアクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="16c22-105">Client version policy rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span> <span data-ttu-id="16c22-106">Lync Server 2013 コントロールパネルから、クライアントバージョンポリシーの個々のルールを作成または変更することができます。</span><span class="sxs-lookup"><span data-stu-id="16c22-106">You can create or modify individual rules for a client version policy from Lync Server 2013 Control Panel.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="16c22-107">規則は優先順位に従って一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="16c22-107">Rules are listed in order of precedence.</span></span> <span data-ttu-id="16c22-108">たとえば、バージョン1.5 を実行しているクライアントの接続を許可するルールがあり、その後に2.0 より前のバージョンを実行しているクライアントをブロックするルールがある場合は、最初のルールが優先され、バージョン1.5 を実行しているクライアントは接続を許可されます。</span><span class="sxs-lookup"><span data-stu-id="16c22-108">For example, if you have a rule that allows clients running version 1.5 to connect, followed by a rule that blocks clients running a version earlier than 2.0, the first rule takes precedence, and clients running version 1.5 are allowed to connect.</span></span>



</div>

<div>

## <a name="to-create-or-modify-client-version-policy-rules-with-lync-server-control-panel"></a><span data-ttu-id="16c22-109">Lync Server コントロールパネルを使用してクライアントバージョンポリシールールを作成または変更するには</span><span class="sxs-lookup"><span data-stu-id="16c22-109">To create or modify client version policy rules with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="16c22-110">Lync server コントロールパネルを使用して[、Lync server 2013 で新しいクライアントバージョンポリシーを作成または変更](lync-server-2013-create-or-modify-a-new-client-version-policy.md)します。</span><span class="sxs-lookup"><span data-stu-id="16c22-110">[Create or modify a new client version policy in Lync Server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy.md) with Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="16c22-111">[ **クライアントバージョンポリシーの編集** ] ページで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="16c22-111">On the **Edit Client Version Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="16c22-112">[ **新規** ] をクリックして、新しいクライアントバージョンルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="16c22-112">Click **New** to create a new client version rule.</span></span>
    
      - <span data-ttu-id="16c22-113">一覧から定義済みのクライアントの種類のいずれかをクリックし、[ **詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="16c22-113">Click one of the defined client types in the list, and then click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="16c22-114">ワイルドカードを使用して、クライアントの種類を指定できます。</span><span class="sxs-lookup"><span data-stu-id="16c22-114">You can use wildcards to indicate the client type.</span></span>

    
    </div>

3.  <span data-ttu-id="16c22-115">[ **ユーザーエージェント**] で、クライアントの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="16c22-115">In **User agent**, select a client type.</span></span>

4.  <span data-ttu-id="16c22-116">[ **バージョン番号**] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="16c22-116">Under **Version number**, do the following:</span></span>
    
      - <span data-ttu-id="16c22-117">[ **メジャーバージョン**] に、クライアントのメジャーリリースに対応する番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="16c22-117">In **Major version**, type the number that corresponds to the major release of the client.</span></span>
    
      - <span data-ttu-id="16c22-118">[ **マイナーバージョン**] に、クライアントのマイナーリリースに対応する番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="16c22-118">In **Minor version**, type the number that corresponds to the minor release of the client.</span></span>
    
      - <span data-ttu-id="16c22-119">[ **ビルド**] に、クライアントのメジャーおよびマイナーリリースに対応する番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="16c22-119">In **Build**, type the number that corresponds to the major and minor release of the client.</span></span>
    
      - <span data-ttu-id="16c22-120">[ **更新**] に、更新されたクライアントのリリースに対応する番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="16c22-120">In **Update**, type the number that corresponds to the updated release of the client.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="16c22-121">ワイルドカードを使用してクライアントバージョン番号を示すことができます。</span><span class="sxs-lookup"><span data-stu-id="16c22-121">You can use wildcards to indicate the client version number.</span></span>

    
    </div>

5.  <span data-ttu-id="16c22-122">前の手順で指定したクライアントバージョンに一致する操作を指定するには、[ **比較操作**] で、次のいずれかをクリックします。</span><span class="sxs-lookup"><span data-stu-id="16c22-122">To specify the matching operation for the client version you specified in the preceding steps, in **Comparison operation**, click one of the following:</span></span>
    
      - <span data-ttu-id="16c22-123">**同じ**</span><span class="sxs-lookup"><span data-stu-id="16c22-123">**Same as**</span></span>
    
      - <span data-ttu-id="16c22-124">**異なる**</span><span class="sxs-lookup"><span data-stu-id="16c22-124">**Is not**</span></span>
    
      - <span data-ttu-id="16c22-125">**より新しい**</span><span class="sxs-lookup"><span data-stu-id="16c22-125">**Newer than**</span></span>
    
      - <span data-ttu-id="16c22-126">**以上**</span><span class="sxs-lookup"><span data-stu-id="16c22-126">**Newer than or same as**</span></span>
    
      - <span data-ttu-id="16c22-127">**より古い**</span><span class="sxs-lookup"><span data-stu-id="16c22-127">**Older than**</span></span>
    
      - <span data-ttu-id="16c22-128">**以前**</span><span class="sxs-lookup"><span data-stu-id="16c22-128">**Older than or same as**</span></span>

6.  <span data-ttu-id="16c22-129">前の手順の条件が満たされたときに実行するアクションを指定するには、[ **アクション**] で次のいずれかをクリックします。</span><span class="sxs-lookup"><span data-stu-id="16c22-129">To specify the action to perform when the criteria in the preceding steps are met, click one of the following in **Action**:</span></span>
    
      - <span data-ttu-id="16c22-130">クライアントのログオンを許可するには、[ **許可**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="16c22-130">To allow the client to log on, click **Allow**.</span></span>
    
      - <span data-ttu-id="16c22-131">クライアントが Windows Server Update Service または Microsoft Update からの更新を送受信できるようにするには、[ **許可およびアップグレード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="16c22-131">To allow the client to log on and receive updates from Windows Server Update Service or Microsoft Update, click **Allow and Upgrade**.</span></span> <span data-ttu-id="16c22-132">このアクションは、ユーザーエージェント **OC** が選択されている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="16c22-132">This action is available only when user agent **OC** is selected.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="16c22-133">このアクションを選択すると、ユーザーが次回 Lync 2013 にサインインしたときに通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="16c22-133">Selecting this action causes a notification to appear the next time users sign in to Lync 2013.</span></span> <span data-ttu-id="16c22-134">この通知では、更新プログラムがある場合、Windows Server Update Service または Microsoft Update にまだリリースされていなくても、更新プログラムを利用できることが伝えられます。</span><span class="sxs-lookup"><span data-stu-id="16c22-134">The notification states that an update is available, even if updates have not yet been released to Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="16c22-135">混乱を避けるため、このアクションは更新プログラムが利用できるようになった後でのみ選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="16c22-135">To avoid confusion, you should choose this action only after updates become available.</span></span>

        
        </div>
    
      - <span data-ttu-id="16c22-136">クライアントがログオンして、別のクライアントバージョンをダウンロードする場所に関するメッセージを表示できるようにするには、[ **URL を使用**して許可する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="16c22-136">To allow the client to log on and display a message about where to download another client version, click **Allow with URL**.</span></span> <span data-ttu-id="16c22-137">この手順の後半で、URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="16c22-137">You specify the URL later in this procedure.</span></span>
    
      - <span data-ttu-id="16c22-138">クライアントのログオンを禁止するには、[ **ブロック**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="16c22-138">To prevent the client from logging on, click **Block**.</span></span>
    
      - <span data-ttu-id="16c22-139">クライアントが Windows Server Update Service または Microsoft Update からの更新プログラムを受信できるようにするには、クライアントのログオンを禁止し、[ **ブロックとアップグレード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="16c22-139">To prevent the client from logging on and allow the client to receive updates from Windows Server Update Service or Microsoft Update, click **Block and Upgrade**.</span></span> <span data-ttu-id="16c22-140">このアクションは、ユーザーエージェント **OC** が選択されている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="16c22-140">This action is available only when user agent **OC** is selected.</span></span>
    
      - <span data-ttu-id="16c22-141">クライアントのログオンを禁止し、別のクライアントバージョンをダウンロードする場所についてのメッセージを表示するには、[ **URL を使用**してブロックする] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="16c22-141">To prevent the client from logging on and display a message about where to download another client version, click **Block with URL**.</span></span> <span data-ttu-id="16c22-142">この手順の後半で、URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="16c22-142">You specify the URL later in this procedure.</span></span>

7.  <span data-ttu-id="16c22-143">オプション前の手順で [URL を使用し **て許可** する] または [ **ブロックを url でブロック** する] をクリックした場合は、[ **url**] にメッセージに含めるクライアントのダウンロード url を入力します。</span><span class="sxs-lookup"><span data-stu-id="16c22-143">(Optional) If you clicked **Allow with URL** or **Block with URL** in the previous step, type the client download URL to include in the message in **URL**.</span></span>

8.  <span data-ttu-id="16c22-144">[ **OK**] をクリックし、[ **確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="16c22-144">Click **OK**, and then click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

