---
title: 'Lync Server 2013: ダイヤルイン会議アクセス番号の作成または変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a dial-in conferencing access number
ms:assetid: 06f55c28-57f8-4d4e-8313-9740846796d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398126(v=OCS.15)
ms:contentKeyID: 48183304
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8372c8117f2e33594ae59b3eff15c6d7eee96ba6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833803"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-dial-in-conferencing-access-number-in-lync-server-2013"></a><span data-ttu-id="d0849-102">Lync Server 2013 でのダイヤルイン会議アクセス番号の作成または変更</span><span class="sxs-lookup"><span data-stu-id="d0849-102">Create or modify a dial-in conferencing access number in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0849-103">_**最終更新日:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="d0849-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="d0849-104">ダイヤルイン会議アクセス番号を作成または変更する場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d0849-104">Follow these steps if you want to create or modify a dial-in conferencing access number.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d0849-105">新しいダイヤルインアクセス番号を作成する前に、新しいダイヤルインアクセス番号に関連付けられているダイヤルプランでダイヤルイン会議領域を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0849-105">Before you create a new dial-in access number, you must set a dial-in conferencing region in the dial plan that is associated with the new dial-in access number.</span></span> <span data-ttu-id="d0849-106">複数のダイヤルプランで同じ地域を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d0849-106">Multiple dial plans can use the same region.</span></span>



</div>

<div>

## <a name="to-create-or-modify-a-dial-in-access-number"></a><span data-ttu-id="d0849-107">ダイヤルインアクセス番号を作成または変更するには</span><span class="sxs-lookup"><span data-stu-id="d0849-107">To create or modify a dial-in access number</span></span>

1.  <span data-ttu-id="d0849-108">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="d0849-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d0849-109">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="d0849-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d0849-110">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d0849-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d0849-111">左側のナビゲーション バーで [**会議**] をクリックし、[**ダイヤルイン アクセス番号**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0849-111">In the left navigation bar, click **Conferencing** and then click **Dial-in Access Number**.</span></span>

4.  <span data-ttu-id="d0849-112">[**ダイヤルイン アクセス番号**] ページで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d0849-112">On the **Dial-in Access Number** page, do one of the following:</span></span>
    
      - <span data-ttu-id="d0849-113">[**新規**] をクリックして、[**新規ダイヤルイン アクセス番号**] を開きます。</span><span class="sxs-lookup"><span data-stu-id="d0849-113">Click **New** to open **New Dial-in Access Number**.</span></span>
    
      - <span data-ttu-id="d0849-114">リストでダイヤルイン アクセス番号のいずれかをクリックして、[**編集**] をクリックし、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0849-114">Click one of the dial-in access numbers in the list, click **Edit**, and then click **Show details**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="d0849-p103">検索フィールドを使用してダイヤルイン アクセス番号のリストの列の内容を検索しても、結果が予想どおりにならない場合があります。代わりに、対象の列を基にしてリストを並べ替えて、表示または変更するダイヤルイン アクセス番号を特定してください。</span><span class="sxs-lookup"><span data-stu-id="d0849-p103">Using the search field to search for the contents of a column in the list of dial-in access numbers may not yield the results you expect. Instead, sort the list by the column of interest to identify the dial-in access number you want to view or change.</span></span>

        
        </div>

5.  <span data-ttu-id="d0849-117">[**表示番号**] に、公衆交換電話網 (PSTN) 電話を使用するユーザーが会議に参加するときにダイヤルする、電話番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="d0849-117">In **Display number**, type the phone number that public switched telephone network (PSTN) phone users dial to join a conference.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d0849-118">この番号は、会議出席依頼とダイヤルイン会議設定 Web ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d0849-118">This number is displayed in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>

    
    </div>

6.  <span data-ttu-id="d0849-119">[**表示名**] に、ダイヤルイン アクセス番号の説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="d0849-119">In **Display name**, type a description for the dial-in access number.</span></span> <span data-ttu-id="d0849-120">これは、Lync 検索結果のダイヤルインアクセス番号と関連付けられた名前です。</span><span class="sxs-lookup"><span data-stu-id="d0849-120">This is the name that is associated with the dial-in access number in Lync search results.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d0849-121">この名前は、ユーザーがアクセス番号を呼び出すとき、クライアントで表示されます。</span><span class="sxs-lookup"><span data-stu-id="d0849-121">This name is displayed in the client when a user calls the access number.</span></span>

    
    </div>

7.  <span data-ttu-id="d0849-p105">[**回線 URI**] に、ダイヤルイン アクセス番号の E.164 番号を、電話番号の前に + 記号を付加し、スペースを含めない電話 URI 形式で入力します。たとえば、tel:+14255550200 のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d0849-p105">In **Line URI**, type the E.164 number of the dial-in access number in TEL URI format, including the + symbol before the number and excluding spaces. For example, tel:+14255550200.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d0849-124">同じ回線 URI を、別のダイヤルイン会議アクセス番号で再利用することはできません。</span><span class="sxs-lookup"><span data-stu-id="d0849-124">The same Line URI cannot be reused by another dial-in conferencing access number.</span></span>

    
    </div>

8.  <span data-ttu-id="d0849-125">[**SIP URI**] で、次の操作を行ってください。</span><span class="sxs-lookup"><span data-stu-id="d0849-125">In **SIP URI**, do the following:</span></span>
    
      - <span data-ttu-id="d0849-126">テキスト ボックスで、このダイヤルイン会議アクセス番号の一意の SIP URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="d0849-126">In the text box, type a unique SIP URI for this dial-in conferencing access number.</span></span> <span data-ttu-id="d0849-127">この SIP URI は、さまざまな場所に表示されます。これには、通話通知メッセージや以前のバージョンの Communicator クライアントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d0849-127">This SIP URI is displayed in various locations including, but not limited to, call notification messages and previous versions of Communicator clients.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="d0849-p107">同じ SIP URI を、別のダイヤルイン会議アクセス番号で再利用することはできません。SIP URI を、アクセス番号の作成後に変更することはできません。SIP URI を変更する唯一の方法は、アクセス番号を削除して再作成することです。</span><span class="sxs-lookup"><span data-stu-id="d0849-p107">The same SIP URI cannot be reused by another dial-in conferencing access number. The SIP URI cannot be modified after the access number is created. The only way to change the SIP URI is to delete and recreate the access number.</span></span>

        
        </div>
    
      - <span data-ttu-id="d0849-131">ドロップダウンリストボックスで、ダイヤルインアクセス番号をサポートする会議アテンダントアプリケーションのドメインをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0849-131">In the drop-down list box, click the domain of the Conferencing Attendant application that supports this dial-in access number.</span></span>

9.  <span data-ttu-id="d0849-132">[**プール**] で、このダイヤルイン アクセス番号をサポートする会議アテンダントのインスタンスを実行するプールをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0849-132">In **Pool**, click the pool that is running the instance of Conferencing Attendant that supports this dial-in access number.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d0849-133">アクセス番号の作成後にプールを変更する必要がある場合は、<STRONG>Move-CsApplicationEndpoint</STRONG> コマンドレットを使用するか、またはアクセス番号をいったん削除して作成し直す必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0849-133">If you need to change the pool after you create the access number, you must use the <STRONG>Move-CsApplicationEndpoint</STRONG> cmdlet or delete and recreate the access number.</span></span>

    
    </div>

10. <span data-ttu-id="d0849-134">[**第 1 言語**] で、このダイヤルイン アクセス番号の案内を再生するときに使用される言語をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0849-134">In **Primary language**, click the language in which prompts are played for this dial-in access number.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d0849-p108">第 1 言語とは、会議アテンダントが着信への応答に使用する言語のことです。サポートされている言語は、各アクセス電話番号と共に、ダイヤルイン会議の設定 Web ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d0849-p108">The primary language is the language that the Conferencing Attendant uses to answer the call. Supported languages are displayed alongside each access phone number on the Dial-in Conferencing Settings webpage.</span></span>

    
    </div>

11. <span data-ttu-id="d0849-137">(オプション) [**第 2 言語 (4 つまで)**] で、[**追加**] をクリックして、このダイヤルイン アクセス番号への発信者用にサポートする 1 つ以上の追加言語を選択し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0849-137">(Optional) In **Secondary languages (maximum of four)**, click **Add**, select one or more additional languages that you want to support for callers to this dial-in access number, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d0849-p109">ダイヤルイン アクセス番号ごとに最大 4 つの第 2 言語を選択できます。ユーザーは、会議にダイヤルインする際に会議 ID を入力する前に、第 2 言語を選択できます。</span><span class="sxs-lookup"><span data-stu-id="d0849-p109">You can choose up to four secondary languages for each dial-in access number. Users can select a secondary language before entering the conference ID when they dial in to a conference.</span></span>

    
    </div>

12. <span data-ttu-id="d0849-140">ダイヤルインアクセス番号の領域を追加するには、[**関連付けられた地域**] の [**追加**] をクリックし、このダイヤルインアクセス番号のダイヤルプランに関連付けられている1つ以上の領域をクリックして、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0849-140">To add a region for the dial-in access number, under **Associated regions**, click **Add**, click one or more regions that are associated with the dial plans for this dial-in access number, and then click **OK**.</span></span>

13. <span data-ttu-id="d0849-141">ダイヤルイン アクセス番号から地域を削除するには、[**関連付けられている地域**] で削除する地域をクリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0849-141">To delete a region from the dial-in access number, under **Associated regions**, click the region you want to delete, and then click **Remove**.</span></span>

14. <span data-ttu-id="d0849-142">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0849-142">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

