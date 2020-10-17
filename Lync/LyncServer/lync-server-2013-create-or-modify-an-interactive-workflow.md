---
title: 'Lync Server 2013: 対話ワークフローを作成または変更する'
description: 'Lync Server 2013: 対話ワークフローを作成または変更します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify an interactive workflow
ms:assetid: bc7bb1bc-bf6a-4636-ae93-c56fa22613fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205213(v=OCS.15)
ms:contentKeyID: 48185260
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 470a073322c48c351dbfdfb24ce376731b3e7512
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546993"
---
# <a name="create-or-modify-an-interactive-workflow-in-lync-server-2013"></a><span data-ttu-id="203a6-103">Lync Server 2013 での対話ワークフローの作成または変更</span><span class="sxs-lookup"><span data-stu-id="203a6-103">Create or modify an interactive workflow in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="203a6-104">_**トピックの最終更新日:** 2013-09-11_</span><span class="sxs-lookup"><span data-stu-id="203a6-104">_**Topic Last Modified:** 2013-09-11_</span></span>

<span data-ttu-id="203a6-105">対話ワークフローを作成または変更するには、以下のいずれかの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="203a6-105">Use one of the following procedures to create or modify an interactive workflow.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="203a6-106">Lync Server 管理シェルまたは応答グループ構成ツールを使用して、対話型ワークフローを作成および変更できます。</span><span class="sxs-lookup"><span data-stu-id="203a6-106">You can use Lync Server Management Shell or the Response Group Configuration Tool to create and modify interactive workflows.</span></span> <span data-ttu-id="203a6-107">[Lync Server コントロールパネル] から応答グループ構成ツールにアクセスするか、次の URL を入力して web ブラウザーから直接 web ページを開くことによって、 <STRONG>Https://</STRONG> &lt; webpoolfqdn &gt; <STRONG>/RgsConfig</STRONG>にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="203a6-107">You can access the Response Group Configuration Tool from Lync Server Control Panel, or by opening the webpage directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>



</div>

<div>

## <a name="to-use-response-group-configuration-tool-to-create-or-modify-an-interactive-workflow"></a><span data-ttu-id="203a6-108">応答グループ構成ツールを使用して対話ワークフローを作成または変更するには</span><span class="sxs-lookup"><span data-stu-id="203a6-108">To use Response Group Configuration Tool to create or modify an Interactive workflow</span></span>

1.  <span data-ttu-id="203a6-109">RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="203a6-109">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="203a6-110">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="203a6-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="203a6-111">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="203a6-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="203a6-112">左側のナビゲーション バーで、[**応答グループ**] をクリックし、[**ワークフロー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="203a6-112">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>

4.  <span data-ttu-id="203a6-113">[**ワークフロー**] ページで、[**ワークフローの作成または編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="203a6-113">On the **Workflow** page, click **Create or edit a workflow**.</span></span>

5.  <span data-ttu-id="203a6-114">[**サービスの選択**] 検索フィールドに、作成または変更するワークフローをホストする **ApplicationServer** サービスの名前または名前の一部を入力します。</span><span class="sxs-lookup"><span data-stu-id="203a6-114">In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service that hosts the workflow that you want to create or modify.</span></span> <span data-ttu-id="203a6-115">表示されたサービスの一覧で、目的のサービスをクリックし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="203a6-115">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="203a6-116">応答グループ構成ツールが開きます。</span><span class="sxs-lookup"><span data-stu-id="203a6-116">The Response Group Configuration Tool opens.</span></span> <span data-ttu-id="203a6-117">次の URL を入力して、web ブラウザーから応答グループ構成ツールを直接開くこともできます。 <STRONG>Https://</STRONG> &lt; webpoolfqdn &gt; <STRONG>/RgsConfig</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="203a6-117">You can also open the Response Group Configuration Tool directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>

    
    </div>

6.  <span data-ttu-id="203a6-118">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="203a6-118">Do one of the following:</span></span>
    
      - <span data-ttu-id="203a6-119">[**新規ワークフローの作成**] の [**対話型**] の横にある [**作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="203a6-119">Under **Create a New Workflow**, next to **Interactive**, click **Create**.</span></span>
    
      - <span data-ttu-id="203a6-120">[**既存ワークフローの管理**] で変更するワークフローを見つけて、[**アクション**] の [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="203a6-120">Under **Manage an Existing Workflow**, locate the workflow you want to change, and then under **Action**, click **Edit**.</span></span>

7.  <span data-ttu-id="203a6-121">ユーザーがワークフローへの通話を開始できる状態ではない場合は、[**ワークフローのアクティブ化**] チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="203a6-121">If you are not ready for users to start calling the workflow, clear the **Activate the workflow** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="203a6-p105">管理ワークフローを作成する場合は、[<STRONG>ワークフローのアクティブ化</STRONG>] を選択する必要があります。アクティブな管理ワークフローを保存した後、そのワークフローを変更したり、非アクティブ化したりできます。</span><span class="sxs-lookup"><span data-stu-id="203a6-p105">If you are to creating a managed workflow, you need to select <STRONG>Activate the workflow</STRONG>. After you save the active, managed workflow, you can then modify and deactivate it.</span></span>

    
    </div>

8.  <span data-ttu-id="203a6-124">フェデレーション ユーザーにグループへの通話を許可するには、[**フェデレーションを有効にする**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="203a6-124">To allow federated users to call the group, select the **Enable for federation** check box.</span></span> <span data-ttu-id="203a6-125">また、フェデレーション用に構成された応答グループアプリケーションに適用される外部アクセスポリシーも必要です。</span><span class="sxs-lookup"><span data-stu-id="203a6-125">You must also have an external access policy that applies to the Response Group application configured for federation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="203a6-126">グローバル外部アクセスポリシーは、応答グループアプリケーションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="203a6-126">The global external access policy applies to the Response Group application.</span></span> <span data-ttu-id="203a6-127">Lync Server コントロールパネルを使用するか、 <STRONG>get-csexternalaccesspolicy</STRONG> コマンドレットを使用して EnableOutsideAccess パラメーターを True に設定することによって、応答グループフェデレーションのグローバルポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="203a6-127">You can configure the global policy for response group federation by using Lync Server Control Panel or by using the <STRONG>Set-CsExternalAccessPolicy</STRONG> cmdlet to set the EnableOutsideAccess parameter to True.</span></span> <span data-ttu-id="203a6-128">グローバル ポリシー設定は、サイトやユーザー ポリシーに割り当てられていない限り、すべてのユーザーに適用されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="203a6-128">Keep in mind that global policy settings apply to all users unless they are assigned a site or user policy.</span></span> <span data-ttu-id="203a6-129">そのため、応答グループ向けにこの設定を変更する前に、フェデレーション設定が組織の要件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="203a6-129">Therefore, before changing this setting for response groups, make sure that the federation setting meets the requirements of your organization.</span></span> <span data-ttu-id="203a6-130">ポリシーをユーザーに適用する方法の詳細については、「 <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Lync Server 2013 の外部アクセスポリシーの管理</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="203a6-130">For details about how policies apply to users, see <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage external access policy in Lync Server 2013</A>.</span></span> <span data-ttu-id="203a6-131">フェデレーション設定の詳細については、「 <STRONG>get-csexternalaccesspolicy</STRONG> 」の「Lync Server Management Shell」のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="203a6-131">For details about the federation setting, see <STRONG>Set-CsExternalAccessPolicy</STRONG> in Lync Server Management Shell documentation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="203a6-132">Lync Online でホストされているユーザーは、オンプレミスの展開でホストされている応答グループに電話をかけることはできません。</span><span class="sxs-lookup"><span data-stu-id="203a6-132">Users who are hosted in Lync Online can’t place calls to response groups that are hosted in an on-premise deployment.</span></span> <span data-ttu-id="203a6-133">これは、ハイブリッド展開とオンプレミス展開が Lync Online 展開とフェデレーションされている場合の両方で当てはまります。</span><span class="sxs-lookup"><span data-stu-id="203a6-133">This is true in both hybrid deployments and in cases where an on-premise deployment is federated with a Lync Online deployment.</span></span>

    
    </div>

9.  <span data-ttu-id="203a6-134">通話中、エージェントの ID を非表示にするには、[**エージェントの匿名性を有効にする**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="203a6-134">To hide the identity of agents during calls, select the **Enable agent anonymity** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="203a6-135">匿名呼び出しは、インスタントメッセージング (IM) またはビデオで開始することはできません。ただし、エージェントまたは発信者は、呼び出しが確立された後に IM とビデオを追加できます。</span><span class="sxs-lookup"><span data-stu-id="203a6-135">Anonymous calls cannot start with instant messaging (IM) or video, although the agent or the caller can add IM and video after the call is established.</span></span> <span data-ttu-id="203a6-136">匿名エージェントは、通話を保留にしたり、通話を転送したり (ブラインドおよび提案転送の両方) したり、通話をパークおよび取得したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="203a6-136">An anonymous agent can also put calls on hold, transfer calls (both blind and consultative transfers), and park and retrieve calls.</span></span> <span data-ttu-id="203a6-137">匿名呼び出しでは、会議、アプリケーション共有とデスクトップ共有、ファイル転送、ホワイトボードとデータコラボレーション、通話記録はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="203a6-137">Anonymous calls do not support conferencing, application sharing and desktop sharing, file transfer, whiteboarding and data collaboration, and call recording.</span></span> <span data-ttu-id="203a6-138">Lync VDI プラグインを使用するエージェントは、匿名で着信呼び出しを受信できますが、匿名で発信呼び出しを行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="203a6-138">Agents using the Lync VDI Plugin can receive incoming calls anonymously, but they cannot make outgoing calls anonymously.</span></span>

    
    </div>

10. <span data-ttu-id="203a6-139">[**通話を受けるグループのアドレスを入力します**] に、ワークフローへの通話に応答するグループのプライマリ SIP Uniform Resource Identifier (URI) アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="203a6-139">Under **Enter the address of the group that will receive the calls**, type the primary SIP uniform resource identifier (URI) address of the group that will answer calls to the workflow.</span></span>

11. <span data-ttu-id="203a6-140">[**表示名**] に、ワークフローを表示する名前を入力します (入力例: Sales IVR Response Group)。</span><span class="sxs-lookup"><span data-stu-id="203a6-140">In **Display name**, type the name that you want to display for the workflow (for example, Sales IVR Response Group).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="203a6-141">[ &lt; 表示名] に "" または "" 文字を含めないでください &gt; 。</span><span class="sxs-lookup"><span data-stu-id="203a6-141">Do not include the "&lt;" or "&gt;" characters in the display name.</span></span> <span data-ttu-id="203a6-142">次の表示名は、予約されているため、使用しないでください。 RG プレゼンス監視またはアナウンスサービス。</span><span class="sxs-lookup"><span data-stu-id="203a6-142">Do not use the following display names because they are reserved: RGS Presence Watcher or Announcement Service.</span></span>

    
    </div>

12. <span data-ttu-id="203a6-143">[**電話番号**] に、応答グループの回線 URI を入力します (入力例 +14255550165)。</span><span class="sxs-lookup"><span data-stu-id="203a6-143">In **Telephone number**, type the line URI for the response group (for example, +14255550165).</span></span>

13. <span data-ttu-id="203a6-144">[**表示番号**] に、応答グループを表示する番号を入力します (入力例 +1 (425) 555-0165)。</span><span class="sxs-lookup"><span data-stu-id="203a6-144">In **Display number**, type the number as you want it to appear for the response group (for example, +1 (425) 555-0165).</span></span>

14. <span data-ttu-id="203a6-145">オプション[ **説明**] に、Lync クライアントの連絡先カードに表示するワークフローの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="203a6-145">(Optional) In **Description**, type a description for the workflow that you want to appear on the contact card in the Lync client.</span></span>

15. <span data-ttu-id="203a6-146">このワークフローを応答グループのマネージャーが管理する場合は、[**ワークフローの種類**] で [**管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="203a6-146">In **Workflow Type**, select **Managed** if this workflow will be managed by a Response Group Manager.</span></span> <span data-ttu-id="203a6-147">ワークフローを応答グループのマネージャーに割り当てるには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="203a6-147">Do the following to assign Response Group Managers to the workflow:</span></span>
    
    1.  <span data-ttu-id="203a6-148">このワークフローのマネージャーの SIP URI を入力して、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="203a6-148">Type the SIP URI of a manager for this workflow, and click **Add**..</span></span>
    
    2.  <span data-ttu-id="203a6-149">ワークフローに追加するマネージャーの SIP URI を入力して、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="203a6-149">Type the SIP URI of additional managers to add to the workflow, and click **Add**..</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="203a6-p112">応答グループのマネージャーに指定されているすべてのユーザーに CsResponseGroupManager ロールを割り当てる必要があります。このロールが割り当てられていない場合、ユーザーは応答グループを管理できません。</span><span class="sxs-lookup"><span data-stu-id="203a6-p112">Every user who is designated as a manager of a response group must be assigned the CsResponseGroupManager role. If users are not assigned this role, they cannot manage response groups.</span></span>

    
    </div>

16. <span data-ttu-id="203a6-152">[**ステップ 2 言語の選択**] で、音声認識と音声合成で使用する言語をクリックします。</span><span class="sxs-lookup"><span data-stu-id="203a6-152">Under **Step 2 Select a Language**, click the language to use for speech recognition and text-to-speech.</span></span>

17. <span data-ttu-id="203a6-153">開始メッセージを構成する場合は、[**ステップ 3 開始メッセージの構成**] で [**開始メッセージを再生する**] チェック ボックスをオンにして、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="203a6-153">If you want to configure a welcome message, under **Step 3 Configure a Welcome Message**, select the **Play a welcome message** check box, and then do one of the following:</span></span>
    
      - <span data-ttu-id="203a6-154">発信者用の音声に変換される開始メッセージをテキストとして入力するには、[**音声合成を使用する**] をクリックして、テキスト ボックスに開始メッセージを入力します。</span><span class="sxs-lookup"><span data-stu-id="203a6-154">To enter the welcome message as text that is converted to speech for callers, click **Use text-to-speech**, and then type the welcome message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="203a6-p113">入力するテキストに HTML タグを含めないでください。HTML タグを含めると、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="203a6-p113">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="203a6-p114">開始メッセージに Wave または Windows Media オーディオ ファイルの録音を使用するには、[**録音を選択する**] をクリックします。新しいオーディオ ファイルをアップロードする場合は、[**録音**] リンクをクリックしてください。新しいブラウザー ウィンドウで [**参照**] をクリックし、使用するオーディオ ファイルを選択して、[**開く**] をクリックします。[**アップロード**] をクリックしてオーディオ ファイルを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="203a6-p114">To use a Wave or Windows Media Audio file recording for the welcome message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the audio file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="203a6-161">ユーザーが指定したすべてのオーディオ ファイルは、特定の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="203a6-161">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="203a6-162">サポートされているファイル形式の詳細については、「 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 の応答グループの技術要件</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="203a6-162">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

18. <span data-ttu-id="203a6-163">[**ステップ 4 営業時間の指定**] の [**タイム ゾーン**] ボックスで、ワークフローのタイム ゾーンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="203a6-163">Under **Step 4 Specify Your Business Hours**, in the **Your time zone** box, click the time zone of the workflow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="203a6-p116">このタイム ゾーンは、ワークフローの発信者とエージェントの所在地のタイム ゾーンです。 これを使用して、始業時間と終業時間が計算されます。 たとえば、北アメリカ東部標準時を使用するようにワークフローが構成されており、ワークフローで始業が午前 7:00、終業が11:00:00 にスケジュールされている場合は、東部標準時の 7:00 と 23:00 がそれぞれ始業時刻と終業時刻になります  (時間は 24 時間表記で入力する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="203a6-p116">The time zone is the time zone where the callers and agents of the workflow reside. It is used to calculate the open and close hours. For example, if the workflow is configured to use the North American Eastern Time zone and the workflow is scheduled to open at 7:00 A.M. and close at 11:00 P.M., the open and close times are assumed to be 7:00 Eastern Time and 11:00 Eastern Time respectively. (You must enter the times in 24-hour time notation.)</span></span>

    
    </div>

19. <span data-ttu-id="203a6-169">次のいずれかの操作を実行して、使用する営業時間スケジュールの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="203a6-169">Select the type of business hours schedule you want to use by doing one of the following:</span></span>
    
      - <span data-ttu-id="203a6-170">事前に定義した営業時間スケジュールを使用するには、[**事前設定したスケジュールを使用する**] をクリックして、ドロップダウン リストから使用するスケジュールを選択します。</span><span class="sxs-lookup"><span data-stu-id="203a6-170">To use a predefined schedule of business hours, click **Use a preset schedule**, and then select the schedule you want to use from the drop-down list.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="203a6-171">このオプションを選択できるようにするには、あらかじめ少なくとも 1 つの事前設定スケジュールを定義しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="203a6-171">You must have defined at least one preset schedule previously to be able to select this option.</span></span> <span data-ttu-id="203a6-172"><STRONG>New-CSRgsHoursOfBusiness</STRONG> コマンドレットを使用して事前設定スケジュールを定義します。</span><span class="sxs-lookup"><span data-stu-id="203a6-172">You define preset schedules by using the <STRONG>New-CSRgsHoursOfBusiness</STRONG> cmdlet.</span></span> <span data-ttu-id="203a6-173">詳細については、「 <A href="lync-server-2013-optional-define-response-group-business-hours.md">Lync Server 2013 で応答グループの営業時間を定義する (オプション)</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="203a6-173">For details, see <A href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Define Response Group business hours in Lync Server 2013</A>.</span></span> <span data-ttu-id="203a6-174">事前設定したスケジュールを選択すると、応答グループの対応日時で、[<STRONG>曜日</STRONG>]、[<STRONG>始業</STRONG>]、[<STRONG>終業</STRONG>] が自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="203a6-174">When you select a preset schedule, <STRONG>Day</STRONG>, <STRONG>Open</STRONG>, and <STRONG>Close</STRONG> are automatically filled with the days and hours that the response group is available.</span></span>

        
        </div>
    
      - <span data-ttu-id="203a6-175">このワークフローのみに適用するカスタム スケジュールを使用するには、[**カスタム スケジュールを使用する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="203a6-175">To use a custom schedule that applies only to this workflow, click **Use a custom schedule**.</span></span>

20. <span data-ttu-id="203a6-176">このワークフロー用のカスタム スケジュールを作成する場合は、応答グループが対応可能な曜日のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="203a6-176">If you are creating a custom schedule for this workflow, click the check boxes for the days of the week that the response group is available.</span></span>

21. <span data-ttu-id="203a6-177">カスタム スケジュールを作成する場合は、応答グループが対応可能な [**始業**] 時間と [**終業**] 時間を入力します。</span><span class="sxs-lookup"><span data-stu-id="203a6-177">If you are creating a custom schedule, type the **Open** and **Close** hours when the response group available.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="203a6-p118">[<STRONG>始業</STRONG>] 時間と [<STRONG>終業</STRONG>] 時間は 24 時間表記で入力する必要があります。 たとえば、職場の営業時間が営業日の 9 ～ 5 時までで、昼休みのために正午にオフィスを一度閉める場合、営業時間は [<STRONG>始業</STRONG>] 9:00、[<STRONG>終業</STRONG>] 12:00、[<STRONG>始業</STRONG>] 13:00、[<STRONG>終業</STRONG>] 17:00 として指定します。</span><span class="sxs-lookup"><span data-stu-id="203a6-p118">The <STRONG>Open</STRONG> and <STRONG>Close</STRONG> hours must be in 24-hour time notation. For example, if your office works a 9-to-5 work day and closes at noon for lunch, the business hours are specified as <STRONG>Open</STRONG> 9:00, <STRONG>Close</STRONG> 12:00, <STRONG>Open</STRONG> 13:00, and <STRONG>Close</STRONG> 17:00.</span></span>

    
    </div>

22. <span data-ttu-id="203a6-180">営業時間外にメッセージを再生するには、[**応答グループの営業時間外にメッセージを再生する**] チェック ボックスをオンにしてから、次のいずれかの操作を実行して再生するメッセージを指定します。</span><span class="sxs-lookup"><span data-stu-id="203a6-180">If you want to play a message when the office is not open, select the **Play a message when the response group is outside of business hours** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="203a6-181">発信者用に音声に変換されるメッセージをテキストとして入力するには、[**音声合成を使用する**] をクリックして、テキスト ボックスにメッセージを入力します。</span><span class="sxs-lookup"><span data-stu-id="203a6-181">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="203a6-p119">入力するテキストに HTML タグを含めないでください。HTML タグを含めると、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="203a6-p119">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="203a6-p120">メッセージにオーディオ ファイルの録音を使用するには、[**録音を選択する**] をクリックします。新しいオーディオ ファイルをアップロードする場合は、[**録音**] リンクをクリックしてください。新しいブラウザー ウィンドウで [**参照**] をクリックし、使用するファイルを選択して、[**開く**] をクリックします。[**アップロード**] をクリックしてオーディオ ファイルを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="203a6-p120">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="203a6-188">ユーザーが指定したすべてのオーディオ ファイルは、特定の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="203a6-188">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="203a6-189">サポートされているファイル形式の詳細については、「 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 の応答グループの技術要件</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="203a6-189">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

23. <span data-ttu-id="203a6-190">メッセージが構成されている場合は、メッセージ再生後の通話の処理方法を次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="203a6-190">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="203a6-191">通話を終了するには、[**終話**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="203a6-191">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="203a6-192">通話をボイス メールに転送するには、[**ボイス メールに転送**] をクリックして、ボイス メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="203a6-192">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="203a6-193">ボイスメールアドレスの形式は次のようになり \<username\> @ \<domainname\> ます (たとえば、bob@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="203a6-193">The format for the voice mail address is \<username\>@\<domainname\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="203a6-194">通話を別のユーザーに転送するには、[**SIP URI に転送**] をクリックして、ユーザー アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="203a6-194">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="203a6-195">ユーザーアドレスの形式は \<username\> @ \<domainname\> です。</span><span class="sxs-lookup"><span data-stu-id="203a6-195">The format for the user address is \<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="203a6-196">通話を別の電話番号に転送するには、[**電話番号に転送**] をクリックして、電話番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="203a6-196">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="203a6-197">電話番号の形式は次のようになり \<number\> @ \<domainname\> ます (たとえば、+ 14255550121@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="203a6-197">The format for the telephone number is \<number\>@\<domainname\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="203a6-198">発信者は、ドメイン名を使用して適切な宛先にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="203a6-198">The domain name is used to route the caller to the correct destination.</span></span>

24. <span data-ttu-id="203a6-199">[**ステップ 5 休日の指定**] で、応答グループが営業しない日を定義する、1 つまたは複数の休日セットのチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="203a6-199">Under **Step 5 Specify Your Holidays**, click the check boxes for one or more sets of holidays that define the days when the response group is closed for business.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="203a6-200">ワークフローを構成する前に、休日および休日セットを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="203a6-200">You need to define holidays and holiday sets before you configure the workflow.</span></span> <span data-ttu-id="203a6-201">休日および休日セットを定義するには、<STRONG>New-CsRgsHoliday</STRONG> コマンドレットおよび <STRONG>New-CsRgsHolidaySet</STRONG> コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="203a6-201">Use the <STRONG>New-CsRgsHoliday</STRONG> and <STRONG>New-CsRgsHolidaySet</STRONG> cmdlets to define holidays and holiday sets.</span></span> <span data-ttu-id="203a6-202">詳細については、「 <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">Lync Server 2013 で応答グループの休日セットを定義する (オプション)</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="203a6-202">For details, see <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Optional) Define Response Group holiday sets in Lync Server 2013</A>.</span></span>

    
    </div>

25. <span data-ttu-id="203a6-203">休日にメッセージを再生するには、[**休日にメッセージを再生する**] チェック ボックスをオンにしてから、次のいずれかの操作を実行して再生するメッセージを指定します。</span><span class="sxs-lookup"><span data-stu-id="203a6-203">If you want to play a message on holidays, select the **Play a message during holidays** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="203a6-204">発信者用に音声に変換されるメッセージをテキストとして入力するには、[**音声合成を使用する**] をクリックして、テキスト ボックスにメッセージを入力します。</span><span class="sxs-lookup"><span data-stu-id="203a6-204">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="203a6-p126">入力するテキストに HTML タグを含めないでください。HTML タグを含めると、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="203a6-p126">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="203a6-p127">メッセージにオーディオ ファイルの録音を使用するには、[**録音を選択する**] をクリックします。新しいオーディオ ファイルをアップロードする場合は、[**録音**] リンクをクリックしてください。新しいブラウザー ウィンドウで [**参照**] をクリックし、使用するファイルを選択して、[**開く**] をクリックします。[**アップロード**] をクリックしてオーディオ ファイルを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="203a6-p127">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="203a6-211">ユーザーが指定したすべてのオーディオ ファイルは、特定の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="203a6-211">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="203a6-212">サポートされているオーディオファイル形式の詳細については、「 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 の応答グループの技術要件</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="203a6-212">For details about supported audio file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

26. <span data-ttu-id="203a6-213">メッセージが構成されている場合は、メッセージ再生後の通話の処理方法を次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="203a6-213">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="203a6-214">通話を終了するには、[**終話**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="203a6-214">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="203a6-215">通話をボイス メールに転送するには、[**ボイス メールに転送**] をクリックして、ボイス メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="203a6-215">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="203a6-216">ボイスメールアドレスの形式は次のようになり \<username\> @ \<domainname\> ます (たとえば、bob@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="203a6-216">The format for the voice mail address is \<username\>@\<domainname\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="203a6-217">通話を別のユーザーに転送するには、[**SIP URI に転送**] をクリックして、ユーザー アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="203a6-217">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="203a6-218">ユーザーアドレスの形式は \<username\> @ \<domainname\> です。</span><span class="sxs-lookup"><span data-stu-id="203a6-218">The format for the user address is \<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="203a6-219">通話を別の電話番号に転送するには、[**電話番号に転送**] をクリックして、電話番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="203a6-219">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="203a6-220">電話番号の形式は次のようになり \<number\> @ \<domainname\> ます (たとえば、+ 14255550121@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="203a6-220">The format for the telephone number is \<number\>@\<domainname\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="203a6-221">発信者は、ドメイン名を使用して適切な宛先にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="203a6-221">The domain name is used to route the caller to the correct destination.</span></span>

27. <span data-ttu-id="203a6-222">[**ステップ 6 保留音の構成**] で、次のいずれかの操作を実行して、発信者がエージェントの応答を待機しているときの保留音を選択します。</span><span class="sxs-lookup"><span data-stu-id="203a6-222">Under **Step 6 Configure Music on Hold**, choose what you want callers to listen to while waiting for an agent by doing one of the following:</span></span>
    
      - <span data-ttu-id="203a6-223">既定の保留音の録音を使用する場合は、[**既定値を使用する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="203a6-223">To use the default music on-hold recording, click **Use default**.</span></span>
    
      - <span data-ttu-id="203a6-p132">保留音にオーディオ ファイルの録音を使用するには、[**音楽ファイルを選択する**] をクリックします。 新しいオーディオ ファイルをアップロードする場合は、[**音楽ファイル**] リンクをクリックします。新しいブラウザー ウィンドウで [**参照**] をクリックし、使用するファイルを選択して、[**開く**] をクリックします。[**アップロード**] をクリックしてオーディオ ファイルを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="203a6-p132">To use an audio file recording for the on-hold music, click **Select a music file**. If you want to upload a new audio file, click the **a music file** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="203a6-228">ユーザーが指定したすべてのオーディオ ファイルは、特定の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="203a6-228">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="203a6-229">サポートされているファイル形式の詳細については、「 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 の応答グループの技術要件</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="203a6-229">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

28. <span data-ttu-id="203a6-230">[**ステップ 7 対話型音声応答の構成**] の [**ユーザーには、次のテキストまたは録音メッセージを再生します**] という見出しの下で、次のように発信者に対する質問を指定します。</span><span class="sxs-lookup"><span data-stu-id="203a6-230">Under **Step 7 Configure Interactive Voice Response**, under the **The user will hear the following text or recorded message** heading, specify the question to ask callers as follows:</span></span>
    
      - <span data-ttu-id="203a6-231">質問をテキスト形式で入力するには、[**音声合成を使用する**] をクリックして、テキスト ボックスに質問を入力します。</span><span class="sxs-lookup"><span data-stu-id="203a6-231">To enter the question in text format, click **Use text-to-speech**, and type the question in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="203a6-p134">入力するテキストに HTML タグを含めないでください。HTML タグを含めると、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="203a6-p134">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="203a6-234">"#" 記号は、音声合成エンジンによって "番号" という語に変換されます。</span><span class="sxs-lookup"><span data-stu-id="203a6-234">The "#" symbol is translated by the text-to-speech engine as the word "number".</span></span> <span data-ttu-id="203a6-235"># キーを示す必要がある場合は、記号ではなく、キーの名前を質問に使用してください。</span><span class="sxs-lookup"><span data-stu-id="203a6-235">If you need to refer to the # key, you should use the key name, rather than the symbol, in your prompt.</span></span> <span data-ttu-id="203a6-236">たとえば、「営業部門をご希望の場合は、シャープを押してください」とします。</span><span class="sxs-lookup"><span data-stu-id="203a6-236">For example, "To talk to sales, press the pound key."</span></span>

        
        </div>
    
      - <span data-ttu-id="203a6-p136">質問を含む録音済みのオーディオ ファイルを使用する場合は、[**録音を選択する**] をクリックし、[**録音**] リンクをクリックしてファイルをアップロードします。 新しいブラウザー ウィンドウで [**参照**] をクリックし、オーディオ ファイルを選択して、[**開く**] をクリックします。 [**アップロード**] をクリックしてファイルを読み込んでから、必要な場合はテキスト ボックスに質問を入力します (これにより、質問と発信者の応答が応答エージェントに転送されます)。</span><span class="sxs-lookup"><span data-stu-id="203a6-p136">To use a prerecorded audio file that contains the question, click **Select a recording**, and then click the **a recording** link to upload the file. In the new browser window, click **Browse**, select the audio file, and then click **Open**. Click **Upload** to load the file, and then optionally you can type the question in the text box (this enables the question, and the caller’s response, to be forwarded to the responding agent).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="203a6-240">ユーザーが指定したすべてのオーディオ ファイルは、特定の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="203a6-240">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="203a6-241">サポートされているファイル形式の詳細については、「 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 の応答グループの技術要件</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="203a6-241">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

29. <span data-ttu-id="203a6-242">[**応答 1**] で次の操作を実行して、質問に対する 1 つ目の回答を指定します。</span><span class="sxs-lookup"><span data-stu-id="203a6-242">Under **Response 1**, specify the first possible answer to the question by doing the following:</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="203a6-p138">いずれの音声応答にも引用符 (") を使用しないでください。 引用符は IVR が失敗する原因になります。</span><span class="sxs-lookup"><span data-stu-id="203a6-p138">Do not use quotation marks (") in any voice responses. Quotation marks cause the IVR to fail.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="203a6-245">発信者が音声、英数字のキーパッド入力、または両方を使用して回答できるようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="203a6-245">You can choose to allow callers to answer using speech, alphanumeric keypad input, or both.</span></span>

    
    </div>
    
      - <span data-ttu-id="203a6-246">発信者が音声で応答できるようにする場合は、[**音声応答の入力**] に応答を入力します。</span><span class="sxs-lookup"><span data-stu-id="203a6-246">If you want to allow the caller to respond using speech, enter the answer in **Enter a voice response**.</span></span>
    
      - <span data-ttu-id="203a6-247">発信者がキーパッドのキー入力で応答できるようにする場合は、[**数字**] で、目的のキーパッドの数字をクリックします。</span><span class="sxs-lookup"><span data-stu-id="203a6-247">If you want to allow the caller to respond by pressing a key on the keypad, in **Digit**, click the keypad digit.</span></span>

30. <span data-ttu-id="203a6-248">次のように、発信者をキューにルーティングするか、もう 1 つ質問するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="203a6-248">Specify whether to route the caller to a queue, or to ask another question as follows:</span></span>
    
      - <span data-ttu-id="203a6-249">発信者をキューにルーティングするには [**キューに送る**] をクリックし、[**キューの選択**] で使用するキューをクリックします。</span><span class="sxs-lookup"><span data-stu-id="203a6-249">To route the caller to a queue, click **Send to a queue**, and in **Select a queue**, click the queue that you want to use.</span></span>
    
      - <span data-ttu-id="203a6-p139">もう 1 つ質問をするには、[**もう 1 つ質問する**] をクリックしてから、[**音声合成を使用する**] をクリックして質問を入力するか、[**録音を選択する**] をクリックします。 このセクションにある応答グループを使用して、追加の質問に対する最大 4 つの応答と、各応答で使用するキューを指定します。 3 番目または 4 番目の応答を指定するには、[**応答 3**] チェック ボックスまたは [**応答 4**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="203a6-p139">To ask another question, click **Ask another question**, and then click **Use text-to-speech** and type the question, or click **Select a recording**. Use the response groupings in this section to specify up to four possible responses to the additional question and the queue to use for each response. To specify a third or fourth possible response, click the **Response 3** check box or the **Response 4** check box.</span></span>

31. <span data-ttu-id="203a6-p140">手順 28 と 29 を繰り返して応答と各応答に対するアクションを指定し、元の質問に対する回答を最大 3 つ追加します。 3 番目または 4 番目の回答を指定するには、[**応答 3**] チェック ボックスまたは [**応答 4**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="203a6-p140">Specify up to three more possible answers to the original question by repeating steps 28 and 29 to specify the possible responses and the action to take for each response. To specify a third or fourth possible answer, click the **Response 3** check box or the **Response 4** check box.</span></span>

32. <span data-ttu-id="203a6-255">[**展開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="203a6-255">Click **Deploy**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-an-interactive-workflow"></a><span data-ttu-id="203a6-256">Windows PowerShell を使用して対話ワークフローを作成または変更するには</span><span class="sxs-lookup"><span data-stu-id="203a6-256">To use Windows PowerShell to create or modify an Interactive workflow</span></span>

1.  <span data-ttu-id="203a6-257">RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="203a6-257">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="203a6-258">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="203a6-258">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="203a6-p141">応答グループ サービスのサービス名を取得して変数に割り当てます。コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="203a6-p141">Retrieve the service name for the Response Group service and assign it to a variable. At the command line, run:</span></span>
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;

4.  <span data-ttu-id="203a6-p142">対話ワークフローには、2 つ以上のキューと 2 つ以上のエージェント グループが必要です。まず、エージェント グループを作成します。次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="203a6-p142">An interactive workflow requires two or more queues and two or more agent groups. First, create the agent groups. Run:</span></span>
    
        $AGSupport = New-CsRgsAgentGroup -Parent $serviceId -Name "Technical Support" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:agent1@contoso.com", "sip:agent2@contoso.com")]
        $AGSales = New-CsRgsAgentGroup -Parent $serviceId -Name "Sales Team" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:bob@contoso.com", "sip:alice@contoso.com")]

5.  <span data-ttu-id="203a6-p143">キューを作成します。次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="203a6-p143">Create the queues. Run:</span></span>
    
        $QSupport = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Support" -AgentGroupIDList($AG-Support.Identity)
        $QSales = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Sales" -AgentGroupIDList($AG-Sales.Identity)

6.  <span data-ttu-id="203a6-p144">応答グループ プロンプトを作成します。次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="203a6-p144">Create the first response group prompt. Run:</span></span>
    
        $SupportPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please be patient while we connect you with Contoso Technical Support."

7.  <span data-ttu-id="203a6-p145">次に、プロンプトの後に実行するアクションを作成します。次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="203a6-p145">Then create the action to be performed after the prompt. Run:</span></span>
    
        $SupportAction = New-CsRgsCallAction -Prompt $SupportPrompt -Action TransferToQueue -QueueID $QSupport.Identity

8.  <span data-ttu-id="203a6-p146">最初の応答グループ回答を作成します。次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="203a6-p146">Create the first response group answer. Run:</span></span>
    
        $SupportAnswer = New-CsRgsAnswer -Action $SupportAction [-DtmfResponse 1]

9.  <span data-ttu-id="203a6-p147">2 番目のプロンプト、通話アクション、および回答を作成します。まず、プロンプトを作成します。次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="203a6-p147">Now create the second prompt, call action, and answer. First create the prompt. Run:</span></span>
    
        $SalesPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please hold while we connect you with Contoso Sales."

10. <span data-ttu-id="203a6-p148">2 番目の通話アクションを作成します。次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="203a6-p148">Create the second call action. Run:</span></span>
    
        $SalesAction = New-CsRgsCallAction -Prompt $SalesPrompt -Action TransferToQueue -QueueID $QSales.Identity

11. <span data-ttu-id="203a6-p149">2 番目の応答グループ回答を作成します。次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="203a6-p149">Create the second response group answer. Run:</span></span>
    
        $SalesAnswer = New-CsRgsAnswer -Action $SalesAction [-DtmfResponse 2]

12. <span data-ttu-id="203a6-p150">最上位のプロンプトを作成します。次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="203a6-p150">Create the top-level prompt. Run:</span></span>
    
        $TopLevelPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Thank you for calling Contoso. For Technical Support, press 1. For a Sales Representative, press 2."

13. <span data-ttu-id="203a6-p151">最上位の質問を作成します。次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="203a6-p151">Create the top-level question. Run:</span></span>
    
        $TopLevelQuestion = New-CsRgsQuestion -Prompt $TopLevelPrompt [-AnswerList ($SupportAnswer, $SalesAnswer)]

14. <span data-ttu-id="203a6-p152">ここで、ワークフローを作成します。次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="203a6-p152">Now create the workflow. Run:</span></span>
    
        $IVRAction = New-CsRgsCallAction -Action TransferToQuestion [-Question $Question]
        $IVRWorkflow = New-CsRgsWorkflow -Parent $ServiceId -Name "Contoso Helpdesk" [-Description "The Contoso Helpdesk line."] -PrimaryUri "sip:helpdesk@contoso.com" [-LineUri tel:+14255554321] [-DisplayNumber "+1 (425) 555-4321"] [-Active $true] [-Anonymous $true] [-DefaultAction $IVRAction] [-Managed $true] [-ManagersByURI ("sip:mindy@contoso.com", "sip:bob@contoso.com")]
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="203a6-p153">応答グループのマネージャーに指定されているすべてのユーザーに CsResponseGroupManager ロールを割り当てる必要があります。このロールが割り当てられていない場合、ユーザーは応答グループを管理できません。</span><span class="sxs-lookup"><span data-stu-id="203a6-p153">All users who have been designated as manager of a response group must be assigned th CsResponseGroupManager role. If users are not assigned this role, they cannot manage response groups.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

