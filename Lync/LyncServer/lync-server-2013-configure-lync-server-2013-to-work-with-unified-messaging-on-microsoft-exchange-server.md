---
title: 'Lync Server 2013: Microsoft Exchange Server でユニファイドメッセージングを使用するように Lync Server 2013 を構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server
ms:assetid: 1098ae4d-f57f-44f3-804e-39889d9fc14e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398193(v=OCS.15)
ms:contentKeyID: 48183430
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 043015fb30ca21a697a9758a5fbb4d916b006046
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146450"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server"></a><span data-ttu-id="14f14-102">Microsoft Exchange Server でユニファイドメッセージングを使用するように Lync Server 2013 を構成する</span><span class="sxs-lookup"><span data-stu-id="14f14-102">Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span data-ttu-id="14f14-103">_**トピックの最終更新日:** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="14f14-103">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="14f14-104">このステップを実行するには、Exchange UM 統合ユーティリティ (OcsUmUtil.exe) が必要です。</span><span class="sxs-lookup"><span data-stu-id="14f14-104">This step requires the Exchange UM Integration Utility (OcsUmUtil.exe).</span></span> <span data-ttu-id="14f14-105">このツールは、の Lync Server 2013 サーバーにあります。\\Program Files\\Common Files\\Microsoft Lync Server 2013\\サポートフォルダ。</span><span class="sxs-lookup"><span data-stu-id="14f14-105">This tool is located on the Lync Server 2013 server in the ..\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Support folder.</span></span>

<div>

## <a name="running-the-exchange-um-integration-utility"></a><span data-ttu-id="14f14-106">Exchange UM 統合ユーティリティの実行</span><span class="sxs-lookup"><span data-stu-id="14f14-106">Running the Exchange UM Integration Utility</span></span>

<span data-ttu-id="14f14-107">Exchange UM 統合ユーティリティは、次の特性を持つユーザー アカウントで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14f14-107">The Exchange UM Integration Utility must be run from a user account with the following characteristics:</span></span>

  - <span data-ttu-id="14f14-108">RTCUniversalServerAdmins グループおよび RtcUniversalUserAdmins グループ (Exchange Server ユニファイド メッセージングの設定を読み取るアクセス許可が割り当てられている) に属している。</span><span class="sxs-lookup"><span data-stu-id="14f14-108">Membership in the RTCUniversalServerAdmins and RtcUniversalUserAdmins groups (which includes permission to read Exchange Server Unified Messaging settings).</span></span>

  - <span data-ttu-id="14f14-109">指定された組織単位 (OU) コンテナーに連絡先オブジェクトを作成するための、ドメイン内のユーザー権限。</span><span class="sxs-lookup"><span data-stu-id="14f14-109">User rights within the domain to create contact objects in the specified organizational unit (OU) container.</span></span>

<span data-ttu-id="14f14-110">Exchange UM 統合ユーティリティを実行すると、以下のタスクが実行されます。</span><span class="sxs-lookup"><span data-stu-id="14f14-110">When you run the Exchange UM Integration Utility, it performs the following tasks:</span></span>

  - <span data-ttu-id="14f14-111">エンタープライズ VoIP ユーザーが使用する各自動応答番号とサブスクライバー アクセス番号の連絡先オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="14f14-111">Creates contact objects for each auto-attendant and subscriber access number to be used by Enterprise Voice users.</span></span>

  - <span data-ttu-id="14f14-112">各エンタープライズ Voip ダイヤルプランの名前が、対応するユニファイドメッセージング (UM) ダイヤルプランの電話のコンテキストに一致することを確認します。</span><span class="sxs-lookup"><span data-stu-id="14f14-112">Verifies that the name of each Enterprise Voice dial plan matches its corresponding unified messaging (UM) dial plan phone context.</span></span> <span data-ttu-id="14f14-113">この一致は、UM ダイヤルプランが Exchange 2010 Service Pack 1 (SP1) より*前*のバージョンの exchange 上で実行されている場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="14f14-113">This matching is necessary only if the UM dial plan is running on a version of Exchange *earlier* than Exchange 2010 Service Pack 1 (SP1).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="14f14-114">Exchange UM 統合ユーティリティを実行する前に、次の操作が完了していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="14f14-114">Before running the Exchange UM Integration Utility, be sure that you have done the following:</span></span>
> <ul>
> <li><p><span data-ttu-id="14f14-115">Exchange 製品のドキュメントで説明されているように、1つ以上の Exchange UM ダイヤルプランを作成します。</span><span class="sxs-lookup"><span data-stu-id="14f14-115">Create one or more Exchange UM dial plans, as described in the Exchange product documentation.</span></span></p>
> <p><span data-ttu-id="14f14-116">Microsoft Exchange Server 2010 について&quot;は、「UM ダイヤル&quot;プラン<a href="https://go.microsoft.com/fwlink/p/?linkid=186177">https://go.microsoft.com/fwlink/p/?linkId=186177</a>を作成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14f14-116">For Microsoft Exchange Server 2010, see &quot;Create a UM Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=186177">https://go.microsoft.com/fwlink/p/?linkId=186177</a>.</span></span></p>
> <p><span data-ttu-id="14f14-117">Microsoft Exchange Server 2007 Service Pack 1 (SP1) について&quot;は、「How to Create a ユニファイドメッセージング&quot; SIP <a href="https://go.microsoft.com/fwlink/p/?linkid=185771">https://go.microsoft.com/fwlink/p/?linkId=185771</a>URI ダイヤルプラン」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14f14-117">For Microsoft Exchange Server 2007 Service Pack 1 (SP1), see &quot;How to Create a Unified Messaging SIP URI Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=185771">https://go.microsoft.com/fwlink/p/?linkId=185771</a>.</span></span></p></li>
> <li><p><span data-ttu-id="14f14-118">「 <a href="lync-server-2013-create-a-dial-plan.md">Lync server 2013 でダイヤルプランを作成</a>する」の説明に従って、1つ以上の対応する lync server ダイヤルプランを作成します。</span><span class="sxs-lookup"><span data-stu-id="14f14-118">Create one or more corresponding Lync Server dial plans, as described in <a href="lync-server-2013-create-a-dial-plan.md">Create a dial plan in Lync Server 2013</a>.</span></span></p></li>
> <ul><li><span data-ttu-id="14f14-119">Microsoft Exchange Server 2010 SP1 より前のバージョンの Exchange を使用している場合は、対応する Exchange ユニファイドメッセージング (UM) SIP ダイヤルプランの完全修飾ドメイン名 (FQDN) を Lync Server 2013 ダイヤルプランの [<STRONG>簡易名</STRONG>] フィールドに入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14f14-119">If you are using a version of Exchange that is earlier than Microsoft Exchange Server 2010 SP1, you must enter the fully qualified domain name (FQDN) of the corresponding Exchange Unified Messaging (UM) SIP dial plan in the Lync Server 2013 dial plan <STRONG>Simple name</STRONG> field.</span></span> <span data-ttu-id="14f14-120">Microsoft Exchange Server 2010 SP1 または最新の service pack を使用している場合は、このダイヤルプラン名の一致は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="14f14-120">If you are using Microsoft Exchange Server 2010 SP1 or latest service pack, this dial plan name matching is not necessary.</span></span></li></ul>
> <li><span data-ttu-id="14f14-121">自動応答を作成し、サブスクライバー アクセス番号と自動応答番号の両方が E.164 形式であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="14f14-121">Create an auto-attendant and make sure that both the subscriber access number and auto-attendant number are in E.164 format.</span></span></li></ul>


<div>

## <a name="to-run-the-exchange-um-integration-utility"></a><span data-ttu-id="14f14-122">Exchange UM 統合ユーティリティを実行するには</span><span class="sxs-lookup"><span data-stu-id="14f14-122">To run the Exchange UM Integration Utility</span></span>

1.  <span data-ttu-id="14f14-123">フロントエンドサーバーで、コマンドプロンプトを開き、「 **cd% CommonProgramFiles%\\Microsoft Lync Server 2013\\サポート**」と入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="14f14-123">On a Front End Server, open a command prompt and type **cd %CommonProgramFiles%\\Microsoft Lync Server 2013\\Support**, and then press ENTER.</span></span>

2.  <span data-ttu-id="14f14-124">「**OcsUmUtil.exe**」と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="14f14-124">Type **OcsUmUtil.exe**, and then press ENTER.</span></span>

3.  <span data-ttu-id="14f14-125">**[データの読み込み]** をクリックして、信頼できるすべての Exchange フォレストを探します。</span><span class="sxs-lookup"><span data-stu-id="14f14-125">Click **Load Data** to find all trusted Exchange forests.</span></span>

4.  <span data-ttu-id="14f14-126">**[SIP ダイヤル プラン]** ボックスの一覧で、連絡先オブジェクトを作成する UM SIP ダイヤル プランを選択し、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="14f14-126">In the **SIP Dial Plans** list, select a UM SIP dial plan for which you want to create contact objects, and then click **Add**.</span></span>

5.  <span data-ttu-id="14f14-p104">**[連絡先]** ボックスで、既定の組織単位をそのまま使用するか、または **[参照]** をクリックして **[OU の選択]** を開始します。 **[OU の選択]** ボックスで、OU を選択して **[OK]** をクリックするか、または **[新しい OU の作成]** をクリックしてルートまたはドメイン内のその他の OU の下に新しい組織単位を作成し、**[OK]** をクリックします (たとえば、"OU=RTC Special Accounts,DC=fourthcoffee,DC=com")。</span><span class="sxs-lookup"><span data-stu-id="14f14-p104">In the **Contact** box, accept the default organizational unit, or click **Browse** to start the **OU Picker**. In the **OU Picker** box, you can select an OU and click **OK**, or you can click **Make New OU** to create a new organizational unit under the root or any other OU in the domain (for example, "OU=RTC Special Accounts,DC=fourthcoffee,DC=com"), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="14f14-129">選択または作成した OU の識別名 (DN) が <STRONG>[組織単位]</STRONG> ボックスに表示されます。</span><span class="sxs-lookup"><span data-stu-id="14f14-129">The distinguished name (DN) of the OU that you have selected or created is now displayed in the <STRONG>Organizational Unit</STRONG> box.</span></span>

    
    </div>

6.  <span data-ttu-id="14f14-130">既定のダイヤル プラン名をそのまま使用するか、作成する連絡先オブジェクトの新しい表示名を **[名前]** ボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="14f14-130">In the **Name** box, either accept the default dial plan name or type a new display name for the contact object that you are creating.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="14f14-131">たとえば、サブスクライバー アクセス連絡先オブジェクトを作成する場合は、名前を単に「Subscriber Access」とすることもできます。</span><span class="sxs-lookup"><span data-stu-id="14f14-131">For example, if you are creating a subscriber access contact object, you might simply name it Subscriber Access.</span></span>

    
    </div>

7.  <span data-ttu-id="14f14-132">**[SIP アドレス]** ボックスで、既定の SIP アドレスをそのまま使用するか、別の SIP アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="14f14-132">In the **SIP Address** box, either accept the default SIP address or type a new SIP address.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="14f14-133">別の SIP アドレスを入力する場合は、<STRONG>[SIP:]</STRONG>(コロンを含む "SIP:") で始める必要があります。</span><span class="sxs-lookup"><span data-stu-id="14f14-133">If you type a new SIP address, it must begin with <STRONG>SIP:</STRONG> (that is, "SIP:" including the colon).</span></span>

    
    </div>

8.  <span data-ttu-id="14f14-134">[**サーバーまたはプール**] の一覧で、連絡先オブジェクトを有効にする Standard Edition サーバーまたはフロントエンドプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="14f14-134">In the **Server or Pool** list, select the Standard Edition server or Front End pool in which the contact object is to be enabled.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="14f14-135">プールの場合は、できれば、エンタープライズ VoIP と Exchange UM を有効にしたユーザーを展開するプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="14f14-135">Preferably, the pool you select is the same one pool where users enabled for Enterprise Voice and Exchange UM are deployed.</span></span>

    
    </div>

9.  <span data-ttu-id="14f14-136">**[電話番号]** ボックスの一覧で、**[電話番号の入力]** または **[Exchange UM からのこのパイロット番号を使用]** をクリックし、電話番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="14f14-136">In the **Phone Number** list, select either **Enter phone number** or **Use this pilot number from Exchange UM** and then enter a phone number.</span></span>

10. <span data-ttu-id="14f14-137">**[連絡先の種類]** ボックスの一覧で作成する連絡先の種類を選択し、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="14f14-137">In the **Contact Type** list, select the contact type that you want to create, and then click **OK**.</span></span>

11. <span data-ttu-id="14f14-138">ステップ 1. ～ 10. を繰り返し、必要に応じて、追加の連絡先オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="14f14-138">Repeat steps 1 through 10 for additional contact objects that you want to create.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="14f14-p105">自動応答ごとに少なくとも 1 つの連絡先を作成してください。外部アクセスが必要な場合は、サブスクライバー アクセス連絡先が必要であり、DID (Direct Inward Dial) 番号を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14f14-p105">You should create at least one contact for each auto attendant. If you want external access, you also need a Subscriber Access contact and to specify Direct Inward Dial (DID) numbers.</span></span>

    
    </div>

</div>

<span data-ttu-id="14f14-p106">連絡先オブジェクトが作成されていることを確認するには、Active Directory ユーザーとコンピューターを開き、オブジェクトを作成した OU を選択します。作成したオブジェクトが詳細ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="14f14-p106">To verify that the contact objects have been created, open Active Directory Users and Computers and select the OU in which the objects were created. The contact objects should appear in the details pane.</span></span>

<span data-ttu-id="14f14-143"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="14f14-143"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

