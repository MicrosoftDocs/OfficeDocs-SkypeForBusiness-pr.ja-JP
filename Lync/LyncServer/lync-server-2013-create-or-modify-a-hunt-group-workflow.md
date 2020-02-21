---
title: 'Lync Server 2013: ハントグループワークフローの作成または変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a hunt group workflow
ms:assetid: dcb9effb-5d12-4dee-80fc-ab9654222d5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205321(v=OCS.15)
ms:contentKeyID: 48185596
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e8fd10947bab25e522f35e9cd121a04abbb4a45
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203363"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-hunt-group-workflow-in-lync-server-2013"></a><span data-ttu-id="30edf-102">Lync Server 2013 でハントグループワークフローを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="30edf-102">Create or modify a hunt group workflow in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30edf-103">_**トピックの最終更新日:** 2013-09-11_</span><span class="sxs-lookup"><span data-stu-id="30edf-103">_**Topic Last Modified:** 2013-09-11_</span></span>

<span data-ttu-id="30edf-104">ハントグループワークフローを作成または変更するには、次のいずれかの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="30edf-104">Use one of the following procedures to create or modify a hunt group workflow.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="30edf-105">Lync Server 管理シェルまたは応答グループ構成ツールを使用して、ハントグループワークフローを作成および変更できます。</span><span class="sxs-lookup"><span data-stu-id="30edf-105">You can use Lync Server Management Shell or the Response Group Configuration Tool to create and modify hunt group workflows.</span></span> <span data-ttu-id="30edf-106">[Lync Server コントロールパネル] から応答グループ構成ツールにアクセスするか、次の URL を入力して web ブラウザーから直接 web ページを開くことによって、 <STRONG>https://</STRONG>&lt;webpoolfqdn&gt;<STRONG>/RgsConfig</STRONG>にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="30edf-106">You can access the Response Group Configuration Tool from Lync Server Control Panel, or by opening the webpage directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>



</div>

<div>

## <a name="to-use-response-group-configuration-tool-to-create-or-modify-a-hunt-group-workflow"></a><span data-ttu-id="30edf-107">応答グループ構成ツールを使用して、ハントグループワークフローを作成または変更するには</span><span class="sxs-lookup"><span data-stu-id="30edf-107">To use Response Group Configuration Tool to create or modify a hunt group workflow</span></span>

1.  <span data-ttu-id="30edf-108">RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="30edf-108">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="30edf-109">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="30edf-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="30edf-110">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30edf-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="30edf-111">左側のナビゲーション バーで、[**応答グループ**] をクリックし、[**ワークフロー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="30edf-111">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>

4.  <span data-ttu-id="30edf-112">[**ワークフロー**] ページで、[**ワークフローの作成または編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="30edf-112">On the **Workflow** page, click **Create or edit a workflow**.</span></span>

5.  <span data-ttu-id="30edf-113">**[サービスの選択**] 検索フィールドに、作成または変更するワークフローをホストする**ApplicationServer**サービスの名前の全体または一部を入力します。</span><span class="sxs-lookup"><span data-stu-id="30edf-113">In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service that hosts the workflow that you want to create or change.</span></span> <span data-ttu-id="30edf-114">表示されたサービスの一覧で、目的のサービスをクリックし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="30edf-114">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="30edf-115">応答グループ構成ツールが開きます。</span><span class="sxs-lookup"><span data-stu-id="30edf-115">The Response Group Configuration Tool opens.</span></span> <span data-ttu-id="30edf-116">次の URL を入力して、web ブラウザーから応答グループ構成ツールを直接開くこともできます。 <STRONG>https://</STRONG>&lt;webpoolfqdn&gt;<STRONG>/RgsConfig</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="30edf-116">You can also open the Response Group Configuration Tool directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>

    
    </div>

6.  <span data-ttu-id="30edf-117">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="30edf-117">Do one of the following:</span></span>
    
      - <span data-ttu-id="30edf-118">[**新規ワークフローの作成**] で、[**ハント グループ**] の横にある [作成] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="30edf-118">Under **Create a New Workflow**, next to **Hunt Group, click Create**.</span></span>
    
      - <span data-ttu-id="30edf-119">[**既存ワークフローの管理**] で変更するワークフローを見つけて、[**アクション**] の [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="30edf-119">Under **Manage an Existing Workflow**, locate the workflow you want to change, and then under **Action**, click **Edit**.</span></span>

7.  <span data-ttu-id="30edf-120">ユーザーがワークフローの呼び出しを開始できる状態になっている場合は、[**ワークフローのアクティブ化**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="30edf-120">If you are ready for users to start calling the workflow, select **Activate the workflow**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="30edf-p105">管理ワークフローを作成する場合は、[<STRONG>ワークフローのアクティブ化</STRONG>] を選択する必要があります。アクティブな管理ワークフローを保存した後、そのワークフローを変更したり、非アクティブ化したりできます。</span><span class="sxs-lookup"><span data-stu-id="30edf-p105">If you are to creating a managed workflow, you need to select <STRONG>Activate the workflow</STRONG>. After you save the active, managed workflow, you can then modify and deactivate it.</span></span>

    
    </div>

8.  <span data-ttu-id="30edf-123">フェデレーション ユーザーにグループへの通話を許可するには、[**フェデレーションを有効にする**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="30edf-123">To allow federated users to call the group, select the **Enable for federation** check box.</span></span> <span data-ttu-id="30edf-124">また、フェデレーション用に構成された応答グループアプリケーションに適用される外部アクセスポリシーも必要です。</span><span class="sxs-lookup"><span data-stu-id="30edf-124">You must also have an external access policy that applies to the Response Group application configured for federation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="30edf-125">グローバル外部アクセスポリシーは、応答グループアプリケーションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="30edf-125">The global external access policy applies to the Response Group application.</span></span> <span data-ttu-id="30edf-126">Lync Server コントロールパネルを使用するか、 <STRONG>get-csexternalaccesspolicy</STRONG>コマンドレットを使用して EnableOutsideAccess パラメーターを True に設定することによって、応答グループフェデレーションのグローバルポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="30edf-126">You can configure the global policy for response group federation by using Lync Server Control Panel or by using the <STRONG>Set-CsExternalAccessPolicy</STRONG> cmdlet to set the EnableOutsideAccess parameter to True.</span></span> <span data-ttu-id="30edf-127">グローバル ポリシー設定は、サイトやユーザー ポリシーに割り当てられていない限り、すべてのユーザーに適用されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="30edf-127">Keep in mind that global policy settings apply to all users unless they are assigned a site or user policy.</span></span> <span data-ttu-id="30edf-128">そのため、応答グループ向けにこの設定を変更する前に、フェデレーション設定が組織の要件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="30edf-128">Therefore, before changing this setting for response groups, make sure that the federation setting meets the requirements of your organization.</span></span> <span data-ttu-id="30edf-129">ポリシーをユーザーに適用する方法の詳細については、「 <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Lync Server 2013 の外部アクセスポリシーの管理</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30edf-129">For details about how policies apply to users, see <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage external access policy in Lync Server 2013</A>.</span></span> <span data-ttu-id="30edf-130">フェデレーション設定の詳細については、「 <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy">get-csexternalaccesspolicy</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30edf-130">For details about the federation setting, see <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy">Set-CsExternalAccessPolicy</A>.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="30edf-131">Lync Online でホストされているユーザーは、オンプレミスの展開でホストされている応答グループに電話をかけることはできません。</span><span class="sxs-lookup"><span data-stu-id="30edf-131">Users who are hosted in Lync Online can’t place calls to response groups that are hosted in an on-premise deployment.</span></span> <span data-ttu-id="30edf-132">これは、ハイブリッド展開とオンプレミス展開が Lync Online 展開とフェデレーションされている場合の両方で当てはまります。</span><span class="sxs-lookup"><span data-stu-id="30edf-132">This is true in both hybrid deployments and in cases where an on-premise deployment is federated with a Lync Online deployment.</span></span>

    
    </div>

9.  <span data-ttu-id="30edf-133">通話中、エージェントの ID を非表示にするには、[**エージェントの匿名性を有効にする**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="30edf-133">To hide the identity of agents during calls, select the **Enable agent anonymity** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="30edf-134">匿名呼び出しは、インスタントメッセージング (IM) またはビデオで開始することはできません。ただし、エージェントまたは発信者は、呼び出しが確立された後に IM とビデオを追加できます。</span><span class="sxs-lookup"><span data-stu-id="30edf-134">Anonymous calls cannot start with instant messaging (IM) or video, although the agent or the caller can add IM and video after the call is established.</span></span> <span data-ttu-id="30edf-135">匿名エージェントは、通話を保留にしたり、通話を転送したり (ブラインドおよび提案転送の両方) したり、通話をパークおよび取得したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="30edf-135">An anonymous agent can also put calls on hold, transfer calls (both blind and consultative transfers), and park and retrieve calls.</span></span> <span data-ttu-id="30edf-136">匿名呼び出しでは、会議、アプリケーション共有とデスクトップ共有、ファイル転送、ホワイトボードとデータコラボレーション、通話記録はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="30edf-136">Anonymous calls do not support conferencing, application sharing and desktop sharing, file transfer, whiteboarding and data collaboration, and call recording.</span></span> <span data-ttu-id="30edf-137">Lync VDI プラグインを使用するエージェントは、匿名で着信呼び出しを受信できますが、匿名で発信呼び出しを行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="30edf-137">Agents using the Lync VDI Plugin can receive incoming calls anonymously, but they cannot make outgoing calls anonymously.</span></span>

    
    </div>

10. <span data-ttu-id="30edf-138">[**通話を受けるグループのアドレスを入力します**] に、ワークフローへの通話に応答するグループのプライマリ SIP Uniform Resource Identifier (URI) アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="30edf-138">Under **Enter the address of the group that will receive the calls**, type the primary SIP uniform resource identifier (URI) address of the group that will answer calls to the workflow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="30edf-139">ワークフローのプライマリ URI は、ワークフローがどのように識別され、参照されるかを示しています。</span><span class="sxs-lookup"><span data-stu-id="30edf-139">The primary URI for a workflow is how the workflow is identified and referenced.</span></span> <span data-ttu-id="30edf-140">入力した SIP URI は、Active Directory ドメインサービスの連絡先オブジェクトとして作成されます。</span><span class="sxs-lookup"><span data-stu-id="30edf-140">The SIP URI that you enter is created as a contact object in Active Directory Domain Services.</span></span> <span data-ttu-id="30edf-141">URI を作成するには、オブジェクトが Active Directory 内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="30edf-141">To create the URI, the object must be unique in Active Directory.</span></span>

    
    </div>

11. <span data-ttu-id="30edf-142">ワークフローで表示する名前を [**表示名**] に入力します (例: 販売応答グループ)。</span><span class="sxs-lookup"><span data-stu-id="30edf-142">In **Display name**, type the name that you want to display for the workflow (for example, Sales Response Group).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="30edf-143">[表示名] に&lt;"" また&gt;は "" 文字を含めないでください。</span><span class="sxs-lookup"><span data-stu-id="30edf-143">Do not include the "&lt;" or "&gt;" characters in the display name.</span></span> <span data-ttu-id="30edf-144">次の表示名は、予約されているため、使用しないでください。 <STRONG>Rg プレゼンス監視</STRONG>または<STRONG>アナウンスサービス</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="30edf-144">Do not use the following display names because they are reserved: <STRONG>RGS Presence Watcher</STRONG> or <STRONG>Announcement Service</STRONG>.</span></span>

    
    </div>

12. <span data-ttu-id="30edf-145">**[電話番号]** に、応答グループの回線 URI を入力します (入力例 +14255550165)。</span><span class="sxs-lookup"><span data-stu-id="30edf-145">Under **Telephone number**, type the line URI for the response group (for example, +14255550165).</span></span>

13. <span data-ttu-id="30edf-146">[**表示番号**] に、応答グループを表示する番号を入力します (入力例 +1 (425) 555-0165)。</span><span class="sxs-lookup"><span data-stu-id="30edf-146">In **Display number**, type the number as you want it to appear for the response group (for example, +1 (425) 555-0165).</span></span>

14. <span data-ttu-id="30edf-147">オプション[**説明**] に、Lync クライアントの連絡先カードに表示するワークフローの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="30edf-147">(Optional) In **Description**, type a description for the workflow as you want it to appear on the contact card in Lync client.</span></span>

15. <span data-ttu-id="30edf-148">このワークフローを応答グループのマネージャーが管理する場合は、[**ワークフローの種類**] で [**管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="30edf-148">In **Workflow Type**, select **Managed** if this workflow will be managed by a Response Group Manager.</span></span> <span data-ttu-id="30edf-149">ワークフローを応答グループのマネージャーに割り当てるには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="30edf-149">Do the following to assign Response Group Managers to the workflow:</span></span>
    
    1.  <span data-ttu-id="30edf-150">このワークフローのマネージャーの SIP URI を入力し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="30edf-150">Type the SIP URI of a manager for this workflow, and click **Add**.</span></span>
    
    2.  <span data-ttu-id="30edf-151">ワークフローに追加するマネージャーの SIP URI を入力し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="30edf-151">Type the SIP URI of additional managers to add to the workflow, and click **Add**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="30edf-p113">応答グループのマネージャーに指定されているすべてのユーザーに CsResponseGroupManager ロールを割り当てる必要があります。このロールが割り当てられていない場合、ユーザーは応答グループを管理できません。</span><span class="sxs-lookup"><span data-stu-id="30edf-p113">Every user who is designated as a manager of a response group must be assigned the CsResponseGroupManager role. If users are not assigned this role, they cannot manage response groups.</span></span>

    
    </div>

16. <span data-ttu-id="30edf-154">**[ステップ 2 言語の選択]** で、音声認識と音声合成で使用する言語をクリックします。</span><span class="sxs-lookup"><span data-stu-id="30edf-154">Under **Step 2 Select a Language**, click the language that you want to use for speech recognition and text-to-speech.</span></span>

17. <span data-ttu-id="30edf-155">開始メッセージを構成する場合は、**[ステップ 3 開始メッセージの構成]** で **[開始メッセージを再生する]** チェック ボックスをオンにして、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="30edf-155">If you want to configure a welcome message, under **Step 3 Configure a Welcome Message**, select the **Play a welcome message** check box, and then do one of the following:</span></span>
    
      - <span data-ttu-id="30edf-156">発信者用の音声に変換される開始メッセージをテキストとして入力するには、[**音声合成を使用する**] をクリックして、テキスト ボックスに開始メッセージを入力します。</span><span class="sxs-lookup"><span data-stu-id="30edf-156">To enter the welcome message as text that is converted to speech for callers, click **Use text-to-speech**, and then type the welcome message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="30edf-p114">入力するテキストに HTML タグを含めないでください。HTML タグを含めると、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="30edf-p114">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="30edf-p115">開始メッセージに Wave (.wav) または Windows Media オーディオ (.wma) ファイルの録音を使用するには、**[録音を選択する]** をクリックします。 新しいオーディオ ファイルをアップロードする場合は、**[録音]** リンクをクリックしてください。 新しいブラウザー ウィンドウで **[参照]** をクリックし、使用するオーディオ ファイルを選択して、**[開く]** をクリックします。 **[アップロード]** をクリックしてオーディオ ファイルを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="30edf-p115">To use a wave (.wav) or Windows Media audio (.wma) file recording for the welcome message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the audio file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="30edf-163">ユーザーが指定したすべてのオーディオ ファイルは、特定の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="30edf-163">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="30edf-164">サポートされているファイル形式の詳細については、「 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 の応答グループの技術要件</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30edf-164">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

18. <span data-ttu-id="30edf-165">**[ステップ 4 営業時間の指定]** の **[タイム ゾーン]** で、ワークフローのタイム ゾーンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="30edf-165">Under **Step 4 Specify Your Business Hours**, in **Your time zone**, click the time zone for the workflow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="30edf-p117">このタイム ゾーンは、ワークフローの発信者とエージェントの所在地のタイム ゾーンです。 これを使用して、始業時間と終業時間が計算されます。 たとえば、北アメリカ東部標準時を使用するようにワークフローが構成されており、ワークフローで始業が午前 7:00、終業が午後 11:00 にスケジュールされている場合は、東部標準時の 7:00 と 23:00 がそれぞれ始業時刻と終業時刻になります (時間は 24 時間表記で入力する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="30edf-p117">The time zone is the time zone where the callers and agents of the workflow reside. It is used to calculate the open and close hours. For example, if the workflow is configured to use the North American Eastern Time zone and the workflow is scheduled to open at 7:00 A.M. and close at 11:00 P.M., the open and close times are assumed to be 7:00 Eastern Time and 23:00 Eastern Time respectively. (You must enter the times in 24-hour time notation.)</span></span>

    
    </div>

19. <span data-ttu-id="30edf-171">次のいずれかの操作を実行して、使用する営業時間スケジュールの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="30edf-171">Select the type of business hours schedule you want to use by doing one of the following:</span></span>
    
      - <span data-ttu-id="30edf-172">事前に定義した営業時間スケジュールを使用するには、[**事前設定したスケジュールを使用する**] をクリックして、ドロップダウン リストから使用するスケジュールを選択します。</span><span class="sxs-lookup"><span data-stu-id="30edf-172">To use a predefined schedule of business hours, click **Use a preset schedule**, and then select the schedule you want to use from the drop-down list.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="30edf-173">このオプションを選択できるようにするには、あらかじめ少なくとも 1 つの事前設定スケジュールを定義しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="30edf-173">You must have defined at least one preset schedule previously to be able to select this option.</span></span> <span data-ttu-id="30edf-174"><STRONG>New-CSRgsHoursOfBusiness</STRONG> コマンドレットを使用して事前設定スケジュールを定義します。</span><span class="sxs-lookup"><span data-stu-id="30edf-174">You define preset schedules by using the <STRONG>New-CSRgsHoursOfBusiness</STRONG> cmdlet.</span></span> <span data-ttu-id="30edf-175">詳細については、「 <A href="lync-server-2013-optional-define-response-group-business-hours.md">Lync Server 2013 で応答グループの営業時間を定義する (オプション)</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30edf-175">For details, see <A href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Define Response Group business hours in Lync Server 2013</A>.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="30edf-176">事前設定したスケジュールを選択すると、応答グループの対応日時で、[<STRONG>曜日</STRONG>]、[<STRONG>始業</STRONG>]、[<STRONG>終業</STRONG>] が自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="30edf-176">When you select a preset schedule, <STRONG>Day</STRONG>, <STRONG>Open</STRONG>, and <STRONG>Close</STRONG> are automatically filled with the days and hours that the response group is available.</span></span>

        
        </div>
    
      - <span data-ttu-id="30edf-177">このワークフローのみに適用するカスタム スケジュールを使用するには、[**カスタム スケジュールを使用する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="30edf-177">To use a custom schedule that applies only to this workflow, click **Use a custom schedule**.</span></span>

20. <span data-ttu-id="30edf-178">このワークフロー用のカスタム スケジュールを作成する場合は、応答グループが対応可能な曜日のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="30edf-178">If you are creating a custom schedule for this workflow, click the check boxes for the days of the week that the response group is available.</span></span>

21. <span data-ttu-id="30edf-179">カスタム スケジュールを作成する場合は、応答グループが対応可能な各曜日の **[始業]** 時間と **[終業]** 時間を入力します。</span><span class="sxs-lookup"><span data-stu-id="30edf-179">If you are creating a custom schedule, type the **Open** and **Close** hours for each day of the week that the response group available.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="30edf-p119"><STRONG>[始業]</STRONG> 時間と <STRONG>[終業]</STRONG> 時間は 24 時間表記で入力する必要があります。 たとえば、職場の営業時間が営業日の 9 ～ 5 時までで、昼休みのために正午にオフィスを一度閉める場合、営業時間は <STRONG>[始業]</STRONG> 9:00、<STRONG>[終業]</STRONG> 12:00、<STRONG>[始業]</STRONG> 13:00、<STRONG>[終業]</STRONG> 17:00 として指定します。</span><span class="sxs-lookup"><span data-stu-id="30edf-p119">The <STRONG>Open</STRONG> and <STRONG>Close</STRONG> hours must be in 24-hour time notation. For example, if your office works a 9-to-5 work day and closes at noon for lunch, the business hours are specified as <STRONG>Open</STRONG> 9:00, <STRONG>Close</STRONG> 12:00, <STRONG>Open</STRONG> 13:00, and <STRONG>Close</STRONG> 17:00.</span></span>

    
    </div>

22. <span data-ttu-id="30edf-182">営業時間外にメッセージを再生するには、[**応答グループの営業時間外にメッセージを再生する**] チェック ボックスをオンにしてから、次のいずれかの操作を実行して再生するメッセージを指定します。</span><span class="sxs-lookup"><span data-stu-id="30edf-182">If you want to play a message when the office is not open, select the **Play a message when the response group is outside of business hours** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="30edf-183">発信者用に音声に変換されるメッセージをテキストとして入力するには、[**音声合成を使用する**] をクリックして、テキスト ボックスにメッセージを入力します。</span><span class="sxs-lookup"><span data-stu-id="30edf-183">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="30edf-p120">入力するテキストに HTML タグを含めないでください。HTML タグを含めると、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="30edf-p120">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="30edf-p121">メッセージにオーディオ ファイルの録音を使用するには、[**録音を選択する**] をクリックします。新しいオーディオ ファイルをアップロードする場合は、[**録音**] リンクをクリックしてください。新しいブラウザー ウィンドウで [**参照**] をクリックし、使用するファイルを選択して、[**開く**] をクリックします。[**アップロード**] をクリックしてオーディオ ファイルを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="30edf-p121">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="30edf-190">ユーザーが指定したすべてのオーディオ ファイルは、特定の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="30edf-190">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="30edf-191">サポートされているオーディオファイル形式の詳細については、「 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 の応答グループの技術要件</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30edf-191">For details about supported audio file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

23. <span data-ttu-id="30edf-192">メッセージが構成されている場合は、メッセージ再生後の通話の処理方法を次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="30edf-192">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="30edf-193">通話を終了するには、[**終話**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="30edf-193">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="30edf-194">通話をボイス メールに転送するには、[**ボイス メールに転送**] をクリックして、ボイス メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="30edf-194">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="30edf-195">ボイス\<メールアドレスの形式は username\>@\<domainName\> (たとえば、bob@contoso.com) です。</span><span class="sxs-lookup"><span data-stu-id="30edf-195">The format for the voice mail address is \<username\>@\<domainName\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="30edf-196">通話を別のユーザーに転送するには、[**SIP URI に転送**] をクリックして、ユーザー アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="30edf-196">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="30edf-197">ユーザー \<アドレスの形式は username\>@\<domainName\>です。</span><span class="sxs-lookup"><span data-stu-id="30edf-197">The format for the user address is \<username\>@\<domainName\>.</span></span>
    
      - <span data-ttu-id="30edf-198">通話を別の電話番号に転送するには、[**電話番号に転送**] をクリックして、電話番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="30edf-198">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="30edf-199">電話番号の形式は、domainName \<\>@\<\>の番号です (たとえば、+ 14255550121@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="30edf-199">The format for the telephone number is \<number\>@\<domainName\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="30edf-200">発信者は、ドメイン名を使用して適切な宛先にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="30edf-200">The domain name is used to route the caller to the correct destination.</span></span>

24. <span data-ttu-id="30edf-201">[**ステップ 5 休日の指定**] で、応答グループが営業しない日を定義する、1 つまたは複数の休日セットのチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="30edf-201">Under **Step 5 Specify Your Holidays**, click the check boxes for one or more sets of holidays that define the days when the response group is closed for business.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="30edf-202">ワークフローを構成する前に、休日および休日セットを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="30edf-202">You need to define holidays and holiday sets before you configure the workflow.</span></span> <span data-ttu-id="30edf-203">休日および休日セットを定義するには、<STRONG>New-CsRgsHoliday</STRONG> コマンドレットおよび <STRONG>New-CsRgsHolidaySet</STRONG> コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="30edf-203">Use the <STRONG>New-CsRgsHoliday</STRONG> and <STRONG>New-CsRgsHolidaySet</STRONG> cmdlets to define holidays and holiday sets.</span></span> <span data-ttu-id="30edf-204">詳細については、「 <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">Lync Server 2013 で応答グループの休日セットを定義する (オプション)</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30edf-204">For details, see <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Optional) Define Response Group holiday sets in Lync Server 2013</A>.</span></span>

    
    </div>

25. <span data-ttu-id="30edf-205">休日にメッセージを再生するには、[**休日にメッセージを再生する**] チェック ボックスをオンにしてから、次のいずれかの操作を実行して再生するメッセージを指定します。</span><span class="sxs-lookup"><span data-stu-id="30edf-205">If you want to play a message on holidays, select the **Play a message during holidays** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="30edf-206">発信者用に音声に変換されるメッセージをテキストとして入力するには、[**音声合成を使用する**] をクリックして、テキスト ボックスにメッセージを入力します。</span><span class="sxs-lookup"><span data-stu-id="30edf-206">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="30edf-p127">入力するテキストに HTML タグを含めないでください。HTML タグを含めると、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="30edf-p127">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="30edf-p128">メッセージにオーディオ ファイルの録音を使用するには、[**録音を選択する**] をクリックします。新しいオーディオ ファイルをアップロードする場合は、[**録音**] リンクをクリックしてください。新しいブラウザー ウィンドウで [**参照**] をクリックし、使用するファイルを選択して、[**開く**] をクリックします。[**アップロード**] をクリックしてオーディオ ファイルを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="30edf-p128">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="30edf-213">ユーザーが指定したすべてのオーディオ ファイルは、特定の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="30edf-213">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="30edf-214">サポートされているオーディオファイル形式の詳細については、「 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 の応答グループの技術要件</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30edf-214">For details about supported audio file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

26. <span data-ttu-id="30edf-215">メッセージが構成されている場合は、メッセージ再生後の通話の処理方法を次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="30edf-215">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="30edf-216">通話を終了するには、[**終話**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="30edf-216">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="30edf-217">通話をボイス メールに転送するには、[**ボイス メールに転送**] をクリックして、ボイス メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="30edf-217">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="30edf-218">ボイス\<メールアドレスの形式は username\>@\<domainName\> (たとえば、bob@contoso.com) です。</span><span class="sxs-lookup"><span data-stu-id="30edf-218">The format for the voice mail address is \<username\>@\<domainName\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="30edf-219">通話を別のユーザーに転送するには、[**SIP URI に転送**] をクリックして、ユーザー アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="30edf-219">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="30edf-220">ユーザー \<アドレスの形式は username\>@\<domainName\>です。</span><span class="sxs-lookup"><span data-stu-id="30edf-220">The format for the user address is \<username\>@\<domainName\>.</span></span>
    
      - <span data-ttu-id="30edf-221">通話を別の電話番号に転送するには、[**電話番号に転送**] をクリックして、電話番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="30edf-221">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="30edf-222">電話番号の形式は、domainName \<\>@\<\>の番号です (たとえば、+ 14255550121@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="30edf-222">The format for the telephone number is \<number\>@\<domainName\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="30edf-223">発信者は、ドメイン名を使用して適切な宛先にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="30edf-223">The domain name is used to route the caller to the correct destination.</span></span>

27. <span data-ttu-id="30edf-224">**[ステップ 6 キューの構成]** の **[通話を受け取るキューを選択します]** で、エージェントが応答可能になるまで発信者を保留するキューを選択します。</span><span class="sxs-lookup"><span data-stu-id="30edf-224">Under **Step 6 Configure a Queue**, in **Select the queue that will receive the calls**, select the queue that you want to hold callers until an agent becomes available.</span></span>

28. <span data-ttu-id="30edf-225">**[ステップ 7 保留音の構成]** で次のいずれかの操作を実行して、発信者がエージェントの応答を待機しているときの保留音を選択します。</span><span class="sxs-lookup"><span data-stu-id="30edf-225">Under **Step 7 Configure Music on Hold**, choose the music you want callers to listen to while waiting for an agent by doing one of the following:</span></span>
    
      - <span data-ttu-id="30edf-226">既定の保留音の録音を使用するには、**[既定値を使用する]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="30edf-226">To use the default music-on-hold recording, click **Use default**.</span></span>
    
      - <span data-ttu-id="30edf-p133">保留音にオーディオ ファイルの録音を使用するには、**[音楽ファイルを選択する]** をクリックします。 新しいオーディオ ファイルをアップロードする場合は、**[音楽ファイル]** リンクをクリックします。新しいブラウザー ウィンドウで **[参照]** をクリックし、使用するファイルを選択して、**[開く]** をクリックします。 **[アップロード]** をクリックしてオーディオ ファイルを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="30edf-p133">To use an audio file recording for the music on hold, click **Select a music file**. If you want to upload a new audio file, click the **a music file** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="30edf-231">ユーザーが指定するすべてのオーディオ ファイルは、特定の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="30edf-231">All user provided audio files must meet certain requirements.</span></span> <span data-ttu-id="30edf-232">サポートされているオーディオファイル形式の詳細については、「 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 の応答グループの技術要件</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30edf-232">For details about supported audio file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

29. <span data-ttu-id="30edf-233">[**展開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="30edf-233">Click **Deploy**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-hunt-group-workflow"></a><span data-ttu-id="30edf-234">Windows PowerShell を使用して、ハントグループワークフローを作成または変更するには</span><span class="sxs-lookup"><span data-stu-id="30edf-234">To use Windows PowerShell to create or modify a hunt group workflow</span></span>

1.  <span data-ttu-id="30edf-235">RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="30edf-235">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="30edf-236">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="30edf-236">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="30edf-237">開始メッセージに対して再生されるプロンプトを作成し、変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="30edf-237">Create the prompt to be played for the welcome message, and save it in a variable.</span></span> <span data-ttu-id="30edf-238">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="30edf-238">At the command line, run:</span></span>
    
        $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    <span data-ttu-id="30edf-239">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="30edf-239">For example:</span></span>
    
        $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "Welcome to Contoso. Please wait for an available agent."
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="30edf-240">プロンプトにオーディオ ファイルを使用するには、<STRONG>Import-CsRgsAudioFile</STRONG> コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="30edf-240">To use an audio file for the prompt, use the <STRONG>Import-CsRgsAudioFile</STRONG> cmdlet.</span></span> <span data-ttu-id="30edf-241">詳細については、「 <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">import-csrgsaudiofile</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30edf-241">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="30edf-242">呼び出しが送信されるキューまたは質問の id を取得します。</span><span class="sxs-lookup"><span data-stu-id="30edf-242">Get the identity of the queue or question where the calls will be directed.</span></span> <span data-ttu-id="30edf-243">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="30edf-243">At the command line, run:</span></span>
    
        $qid = (Get-CsRgsQueue -Name "Help Desk").Identity
    
    <span data-ttu-id="30edf-244">キューの作成の詳細については、「 [New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30edf-244">For details about creating the queue, see [New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue).</span></span>

5.  <span data-ttu-id="30edf-245">営業時間中にワークフローが開かれたときに実行される既定のアクションを定義し、それを変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="30edf-245">Define the default action to be taken when a workflow is opened during business hours, and save it in a variable.</span></span> <span data-ttu-id="30edf-246">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="30edf-246">At the command line, run:</span></span>
    
        $actionWM = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken> -QueueID $qid
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="30edf-247">ハントグループワークフローでは、既定のアクションで呼び出しをキューに送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="30edf-247">For hunt group workflows, the default action must direct the call to a queue.</span></span> <span data-ttu-id="30edf-248">このパラメーターは、アクティブなワークフローでは必須です。</span><span class="sxs-lookup"><span data-stu-id="30edf-248">This is parameter is required for active workflows.</span></span> <span data-ttu-id="30edf-249">非アクティブなワークフローには必要ありません。</span><span class="sxs-lookup"><span data-stu-id="30edf-249">It is not required for inactive workflows.</span></span>

    
    </div>
    
    <span data-ttu-id="30edf-250">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="30edf-250">For example:</span></span>
    
        $actionWM = New-CsRgsCallAction -Prompt $promptWM -Action TransferToQueue -QueueID $qid.Identity

6.  <span data-ttu-id="30edf-251">営業時間および休日を定義する場合は、ワークフローを作成または変更する前に、それらを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="30edf-251">If you want to define business hours and holidays, you need to create them before you create or modify the workflow.</span></span> <span data-ttu-id="30edf-252">詳細については、「lync server 2013 で応答グループの[営業時間を定義する (オプション)](lync-server-2013-optional-define-response-group-business-hours.md) 」および「 [lync Server 2013 で応答グループの休日セットを定義](lync-server-2013-optional-define-response-group-holiday-sets.md)する (オプション)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30edf-252">For details, see [(Optional) Define Response Group business hours in Lync Server 2013](lync-server-2013-optional-define-response-group-business-hours.md) and [(Optional) Define Response Group holiday sets in Lync Server 2013](lync-server-2013-optional-define-response-group-holiday-sets.md).</span></span>

7.  <span data-ttu-id="30edf-253">営業時間外または休日に受信された通話のプロンプトを表示する場合は、**新しい-CsRgsPrompt**コマンドレットを使用してプロンプトを定義し、**新しい-CsRgsCallAction**を使用して、プロンプトの後に実行するアクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="30edf-253">If you want to have prompts for calls that are received out of business hours or on holidays, use the **New-CsRgsPrompt** cmdlet to define the prompt, and use the **New-CsRgsCallAction** to define the action to be taken after the prompt.</span></span> <span data-ttu-id="30edf-254">詳細については、「 [new-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt) 」および「 [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30edf-254">For details, see [New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt) and [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction).</span></span>

8.  <span data-ttu-id="30edf-255">Lync Server 応答グループサービスのサービス名を取得し、変数に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="30edf-255">Retrieve the service name for the Lync Server Response Group service and assign it to a variable.</span></span> <span data-ttu-id="30edf-256">コマンドで、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="30edf-256">At the command, run:</span></span>
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;

9.  <span data-ttu-id="30edf-257">ワークフローを作成または変更します。</span><span class="sxs-lookup"><span data-stu-id="30edf-257">Create or modify the workflow.</span></span> <span data-ttu-id="30edf-258">ワークフローを作成するには、**新しい-CsRgsWorkflow**を使用します。</span><span class="sxs-lookup"><span data-stu-id="30edf-258">To create a workflow, use **New-CsRgsWorkflow**.</span></span> <span data-ttu-id="30edf-259">ワークフローを変更するには、 **Set-CsRgsWorkflow**を使用します。</span><span class="sxs-lookup"><span data-stu-id="30edf-259">To modify a workflow, use **Set-CsRgsWorkflow**.</span></span> <span data-ttu-id="30edf-260">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="30edf-260">At the command line, type:</span></span>
    
        $workflowHG = New-CsRgsWorkflow -Parent <service ID for the Response Group service> -Name "<hunt group name>" [-Description "<hunt group description>"] -PrimaryUri "<SIP address for the workflow>" [-LineUri "<Phone number for the workflow>"] [-DisplayNumber "<Phone number displayed in Lync>"] [-Active <$true | $false>] [-Anonymous <$true | $false>] [-DefaultAction <variable from preceding step>] [-EnabledForFederation <$true | $false>] [-Managed <$true | $false>] [-MangersByUri <SIP addresses for Response Group Managers who can manage the workflow>]
    
    <span data-ttu-id="30edf-261">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="30edf-261">For example:</span></span>
    
        $workflowHG = New-CsRgsWorkflow -Parent $serviceID -Name "Human Resources" -Description "Human Resources workflow" -PrimaryUri "sip:humanresources@contoso.com" -LineUri "TEL:+14255551219" -DisplayNumber "555-1219" -Active $true -Anonymous $true -DefaultAction $actionWM -EnabledForFederation $false -Managed $true -ManagersByUri "sip:bob@contoso.com", "mindy@contoso.com"
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="30edf-262">ワークフローの管理者として指定されているすべてのユーザーに CsResponseGroupManager ロールを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="30edf-262">All users who are designated managers for workflows must be assigned the CsResponseGroupManager role.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="30edf-263">追加のオプションのパラメーターの詳細については、「 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow">New-csrgsworkflow</A>または<A href="https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow">Set-csrgsworkflow</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30edf-263">For details about additional optional parameters, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow">New-CsRgsWorkflow</A> or <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow">Set-CsRgsWorkflow</A></span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="30edf-264">関連項目</span><span class="sxs-lookup"><span data-stu-id="30edf-264">See Also</span></span>


[<span data-ttu-id="30edf-265">オプションLync Server 2013 で応答グループの休日セットを定義する</span><span class="sxs-lookup"><span data-stu-id="30edf-265">(Optional) Define Response Group holiday sets in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-holiday-sets.md)  


[<span data-ttu-id="30edf-266">オプションLync Server 2013 で応答グループの営業時間を定義する</span><span class="sxs-lookup"><span data-stu-id="30edf-266">(Optional) Define Response Group business hours in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-business-hours.md)  


[<span data-ttu-id="30edf-267">New-CsRgsWorkflow</span><span class="sxs-lookup"><span data-stu-id="30edf-267">New-CsRgsWorkflow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow)  
[<span data-ttu-id="30edf-268">Set-CsRgsWorkflow</span><span class="sxs-lookup"><span data-stu-id="30edf-268">Set-CsRgsWorkflow</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow)  
[<span data-ttu-id="30edf-269">New-CsRgsPrompt</span><span class="sxs-lookup"><span data-stu-id="30edf-269">New-CsRgsPrompt</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt)  
[<span data-ttu-id="30edf-270">New-CsRgsCallAction</span><span class="sxs-lookup"><span data-stu-id="30edf-270">New-CsRgsCallAction</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

