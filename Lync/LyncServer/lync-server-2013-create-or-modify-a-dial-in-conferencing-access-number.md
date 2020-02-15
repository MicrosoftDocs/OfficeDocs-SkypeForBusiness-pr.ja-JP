---
title: 'Lync Server 2013: ダイヤルイン会議アクセス番号の作成または変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a dial-in conferencing access number
ms:assetid: 06f55c28-57f8-4d4e-8313-9740846796d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398126(v=OCS.15)
ms:contentKeyID: 48183304
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6406fe5c2f1183b39966902ee2fa5273f509bf2d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048928"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-dial-in-conferencing-access-number-in-lync-server-2013"></a><span data-ttu-id="cde2c-102">Lync Server 2013 でダイヤルイン会議アクセス番号を作成または変更する</span><span class="sxs-lookup"><span data-stu-id="cde2c-102">Create or modify a dial-in conferencing access number in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cde2c-103">_**トピックの最終更新日:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="cde2c-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="cde2c-104">ダイヤルイン会議アクセス番号を作成または変更する場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cde2c-104">Follow these steps if you want to create or modify a dial-in conferencing access number.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="cde2c-105">新しいダイヤルインアクセス番号を作成する前に、新しいダイヤルインアクセス番号に関連付けられているダイヤルプランにダイヤルイン会議の地域を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cde2c-105">Before you create a new dial-in access number, you must set a dial-in conferencing region in the dial plan that is associated with the new dial-in access number.</span></span> <span data-ttu-id="cde2c-106">複数のダイヤルプランで同じ地域を使用できます。</span><span class="sxs-lookup"><span data-stu-id="cde2c-106">Multiple dial plans can use the same region.</span></span>



</div>

<div>

## <a name="to-create-or-modify-a-dial-in-access-number"></a><span data-ttu-id="cde2c-107">ダイヤルインアクセス番号を作成または変更するには</span><span class="sxs-lookup"><span data-stu-id="cde2c-107">To create or modify a dial-in access number</span></span>

1.  <span data-ttu-id="cde2c-108">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="cde2c-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="cde2c-109">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="cde2c-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="cde2c-110">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cde2c-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="cde2c-111">左側のナビゲーション バーで [**会議**] をクリックし、[**ダイヤルイン アクセス番号**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cde2c-111">In the left navigation bar, click **Conferencing** and then click **Dial-in Access Number**.</span></span>

4.  <span data-ttu-id="cde2c-112">[**ダイヤルインアクセス番号**] ページで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="cde2c-112">On the **Dial-in Access Number** page, do one of the following:</span></span>
    
      - <span data-ttu-id="cde2c-113">[**新規**] をクリックして、**新しいダイヤルインアクセス番号**を開きます。</span><span class="sxs-lookup"><span data-stu-id="cde2c-113">Click **New** to open **New Dial-in Access Number**.</span></span>
    
      - <span data-ttu-id="cde2c-114">一覧でダイヤルインアクセス番号のいずれかをクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cde2c-114">Click one of the dial-in access numbers in the list, click **Edit**, and then click **Show details**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="cde2c-115">検索フィールドを使用して、ダイヤルインアクセス番号の一覧にある列の内容を検索しても、期待する結果が得られない場合があります。</span><span class="sxs-lookup"><span data-stu-id="cde2c-115">Using the search field to search for the contents of a column in the list of dial-in access numbers may not yield the results you expect.</span></span> <span data-ttu-id="cde2c-116">代わりに、目的の列でリストを並べ替えて、表示または変更するダイヤルインアクセス番号を識別します。</span><span class="sxs-lookup"><span data-stu-id="cde2c-116">Instead, sort the list by the column of interest to identify the dial-in access number you want to view or change.</span></span>

        
        </div>

5.  <span data-ttu-id="cde2c-117">[**表示番号**] に、公衆交換電話網 (PSTN) 電話ユーザーが会議に参加するためにダイヤルする電話番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="cde2c-117">In **Display number**, type the phone number that public switched telephone network (PSTN) phone users dial to join a conference.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cde2c-118">この番号は、会議出席依頼とダイヤルイン会議の設定 web ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="cde2c-118">This number is displayed in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>

    
    </div>

6.  <span data-ttu-id="cde2c-119">[**表示名**] に、ダイヤルインアクセス番号の説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="cde2c-119">In **Display name**, type a description for the dial-in access number.</span></span> <span data-ttu-id="cde2c-120">これは、Lync 検索結果のダイヤルインアクセス番号に関連付けられている名前です。</span><span class="sxs-lookup"><span data-stu-id="cde2c-120">This is the name that is associated with the dial-in access number in Lync search results.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cde2c-121">この名前は、ユーザーがアクセス番号を呼び出したときにクライアントに表示されます。</span><span class="sxs-lookup"><span data-stu-id="cde2c-121">This name is displayed in the client when a user calls the access number.</span></span>

    
    </div>

7.  <span data-ttu-id="cde2c-122">[**行 uri**] に、ダイヤルインアクセス番号の e.164 番号を、数字の前に + 記号を含め、スペースを除外して、TEL uri 形式で入力します。</span><span class="sxs-lookup"><span data-stu-id="cde2c-122">In **Line URI**, type the E.164 number of the dial-in access number in TEL URI format, including the + symbol before the number and excluding spaces.</span></span> <span data-ttu-id="cde2c-123">たとえば、tel: + 14255550200。</span><span class="sxs-lookup"><span data-stu-id="cde2c-123">For example, tel:+14255550200.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cde2c-124">同じ回線 URI を、別のダイヤルイン会議アクセス番号で再利用することはできません。</span><span class="sxs-lookup"><span data-stu-id="cde2c-124">The same Line URI cannot be reused by another dial-in conferencing access number.</span></span>

    
    </div>

8.  <span data-ttu-id="cde2c-125">[ **SIP URI**] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="cde2c-125">In **SIP URI**, do the following:</span></span>
    
      - <span data-ttu-id="cde2c-126">テキストボックスに、このダイヤルイン会議アクセス番号の一意の SIP URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="cde2c-126">In the text box, type a unique SIP URI for this dial-in conferencing access number.</span></span> <span data-ttu-id="cde2c-127">この SIP URI はさまざまな場所に表示されますが、これに制限はありません。これには、Communicator クライアントの呼び出し通知メッセージと以前のバージョンが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cde2c-127">This SIP URI is displayed in various locations including, but not limited to, call notification messages and previous versions of Communicator clients.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="cde2c-128">同じ SIP URI を、別のダイヤルイン会議アクセス番号で再利用することはできません。</span><span class="sxs-lookup"><span data-stu-id="cde2c-128">The same SIP URI cannot be reused by another dial-in conferencing access number.</span></span> <span data-ttu-id="cde2c-129">アクセス番号の作成後は、SIP URI を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="cde2c-129">The SIP URI cannot be modified after the access number is created.</span></span> <span data-ttu-id="cde2c-130">SIP URI を変更する唯一の方法は、アクセス番号を削除して再作成することです。</span><span class="sxs-lookup"><span data-stu-id="cde2c-130">The only way to change the SIP URI is to delete and recreate the access number.</span></span>

        
        </div>
    
      - <span data-ttu-id="cde2c-131">ドロップダウンリストボックスで、このダイヤルインアクセス番号をサポートする会議アテンダントアプリケーションのドメインをクリックします。</span><span class="sxs-lookup"><span data-stu-id="cde2c-131">In the drop-down list box, click the domain of the Conferencing Attendant application that supports this dial-in access number.</span></span>

9.  <span data-ttu-id="cde2c-132">[**プール**] で、このダイヤルインアクセス番号をサポートする会議アテンダントのインスタンスを実行しているプールをクリックします。</span><span class="sxs-lookup"><span data-stu-id="cde2c-132">In **Pool**, click the pool that is running the instance of Conferencing Attendant that supports this dial-in access number.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cde2c-133">アクセス番号の作成後にプールを変更する必要がある場合は、 <STRONG>Move-CsApplicationEndpoint</STRONG>コマンドレットを使用するか、またはアクセス番号を削除して再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cde2c-133">If you need to change the pool after you create the access number, you must use the <STRONG>Move-CsApplicationEndpoint</STRONG> cmdlet or delete and recreate the access number.</span></span>

    
    </div>

10. <span data-ttu-id="cde2c-134">[**第1言語**] で、このダイヤルインアクセス番号に対してプロンプトが再生される言語をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cde2c-134">In **Primary language**, click the language in which prompts are played for this dial-in access number.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cde2c-135">第1言語は、会議アテンダントが通話に応答するために使用する言語です。</span><span class="sxs-lookup"><span data-stu-id="cde2c-135">The primary language is the language that the Conferencing Attendant uses to answer the call.</span></span> <span data-ttu-id="cde2c-136">サポートされている言語は、[ダイヤルイン会議の設定] web ページに、各アクセス電話番号の横に表示されます。</span><span class="sxs-lookup"><span data-stu-id="cde2c-136">Supported languages are displayed alongside each access phone number on the Dial-in Conferencing Settings webpage.</span></span>

    
    </div>

11. <span data-ttu-id="cde2c-137">オプション[ **2 番目の言語 (最大4つ)**] で、[**追加**] をクリックして、このダイヤルインアクセス番号に対する発信者に対してサポートする1つまたは複数の追加の言語を選択し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cde2c-137">(Optional) In **Secondary languages (maximum of four)**, click **Add**, select one or more additional languages that you want to support for callers to this dial-in access number, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cde2c-138">各ダイヤルインアクセス番号に対して最大4つの第2言語を選択できます。</span><span class="sxs-lookup"><span data-stu-id="cde2c-138">You can choose up to four secondary languages for each dial-in access number.</span></span> <span data-ttu-id="cde2c-139">ユーザーは、会議にダイヤルインするときに、会議 ID を入力する前に第2言語を選択できます。</span><span class="sxs-lookup"><span data-stu-id="cde2c-139">Users can select a secondary language before entering the conference ID when they dial in to a conference.</span></span>

    
    </div>

12. <span data-ttu-id="cde2c-140">ダイヤルインアクセス番号の地域を追加するには、[**関連付けられている地域**] で [**追加**] をクリックし、このダイヤルインアクセス番号のダイヤルプランに関連付けられている1つまたは複数の地域をクリックして、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cde2c-140">To add a region for the dial-in access number, under **Associated regions**, click **Add**, click one or more regions that are associated with the dial plans for this dial-in access number, and then click **OK**.</span></span>

13. <span data-ttu-id="cde2c-141">ダイヤルインアクセス番号から地域を削除するには、[**関連付けられている**地域] で削除する地域をクリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cde2c-141">To delete a region from the dial-in access number, under **Associated regions**, click the region you want to delete, and then click **Remove**.</span></span>

14. <span data-ttu-id="cde2c-142">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cde2c-142">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

