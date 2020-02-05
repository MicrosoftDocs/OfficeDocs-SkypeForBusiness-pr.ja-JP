---
title: Skype for Business での応答グループワークフローの設計と作成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: dcb9effb-5d12-4dee-80fc-ab9654222d5a
description: 回答グループワークフローの設計と作成は、Skype for Business Server Enterprise Voice で行います。 ハント グループ ワークフローと対話ワークフローの両方について説明します。
ms.openlocfilehash: a8e53ea6e36a175a33648e4e1783bf2040556c8f
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767360"
---
# <a name="designing-and-creating-response-group-workflows-in-skype-for-business"></a><span data-ttu-id="1a6c8-104">Skype for Business での応答グループワークフローの設計と作成</span><span class="sxs-lookup"><span data-stu-id="1a6c8-104">Designing and creating response group workflows in Skype for Business</span></span>

<span data-ttu-id="1a6c8-105">回答グループワークフローの設計と作成は、Skype for Business Server Enterprise Voice で行います。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-105">Design and create Response Group workflows, in Skype for Business Server Enterprise Voice.</span></span> <span data-ttu-id="1a6c8-106">ハント グループ ワークフローと対話ワークフローの両方について説明します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-106">Both hunt group workflows and interactive workflows are covered.</span></span>

<span data-ttu-id="1a6c8-107">ワークフローは、電話への着信から、だれかが呼び出しに応答するまでの通話の動作を定義します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-107">A workflow defines the behavior of a call from the time that the phone rings to the time that someone answers the call.</span></span> <span data-ttu-id="1a6c8-108">ワークフローは、通話の保留に使用されるキューを指定し、ハント グループ ワークフローで使用するルーティング方法や対話型応答グループ ワークフローで使用する質問と回答を指定します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-108">The workflow specifies the queue to use for holding the call, and specifies the routing method to use for hunt group workflows or the questions and answers to use for interactive response group workflows.</span></span>

<span data-ttu-id="1a6c8-109">また、ワークフローは、開始メッセージ、保留音、営業時間、休日などの設定も定義します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-109">A workflow also defines settings such as a welcome message, music on hold, business hours, and holidays.</span></span>

> [!NOTE]
> <span data-ttu-id="1a6c8-110">エージェント グループとキューは、これらを使用するワークフローの作成前に作成しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-110">You must create agent groups and queues before you create a workflow that uses them.</span></span>

## <a name="creating-or-modifying-a-hunt-group-workflow"></a><span data-ttu-id="1a6c8-111">ハントグループのワークフローを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="1a6c8-111">Creating or modifying a hunt group workflow</span></span>

### <a name="to-use-response-group-configuration-tool-to-create-or-modify-a-hunt-group-workflow"></a><span data-ttu-id="1a6c8-112">応答グループの構成ツールを使用して、ハントグループのワークフローを作成または変更するには</span><span class="sxs-lookup"><span data-stu-id="1a6c8-112">To use Response Group Configuration Tool to create or modify a hunt group workflow</span></span>

1. <span data-ttu-id="1a6c8-113">RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-113">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2. <span data-ttu-id="1a6c8-114">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="1a6c8-115">左側のナビゲーション バーで、[**応答グループ**] をクリックし、[**ワークフロー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-115">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>

4. <span data-ttu-id="1a6c8-116">[**ワークフロー**] ページで、[**ワークフローの作成または編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-116">On the **Workflow** page, click **Create or edit a workflow**.</span></span>

5. <span data-ttu-id="1a6c8-117">[**サービスの選択**] 検索フィールドに、作成または変更するワークフローをホストする **ApplicationServer** サービスの名前の全体または一部を入力します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-117">In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service that hosts the workflow that you want to create or change.</span></span> <span data-ttu-id="1a6c8-118">サービスの結果一覧で、対象のサービスをクリックして [**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-118">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1a6c8-119">応答グループ構成ツールが開きます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-119">The Response Group Configuration Tool opens.</span></span> <span data-ttu-id="1a6c8-120">次の URL を入力して、web ブラウザーから直接応答グループ構成ツールを開くこともでき\<ます。 Https://\>webpoolfqdn/RgsConfig.</span><span class="sxs-lookup"><span data-stu-id="1a6c8-120">You can also open the Response Group Configuration Tool directly from a web browser by typing the following URL: https://\<webPoolFqdn\>/RgsConfig.</span></span>

6. <span data-ttu-id="1a6c8-121">次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-121">Do one of the following:</span></span>

   - <span data-ttu-id="1a6c8-122">[**新しいワークフローの作成**] で、[**ハント] グループ**の横にある [**作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-122">Under **Create a New Workflow**, next to **Hunt Group**, click **Create**.</span></span>

   - <span data-ttu-id="1a6c8-123">[**既存ワークフローの管理**] で変更するワークフローを見つけて、[**アクション**] の [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-123">Under **Manage an Existing Workflow**, locate the workflow you want to change, and then under **Action**, click **Edit**.</span></span>

7. <span data-ttu-id="1a6c8-124">ユーザーがワークフローへの通話を開始する準備ができている場合は、[**ワークフローのアクティブ化**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-124">If you are ready for users to start calling the workflow, select **Activate the workflow**.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="1a6c8-125">管理ワークフローを作成する場合は、[**ワークフローのアクティブ化**] を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-125">If you are creating a managed workflow, you need to select **Activate the workflow**.</span></span> <span data-ttu-id="1a6c8-126">アクティブな管理ワークフローを保存した後、そのワークフローを変更したり、非アクティブ化したりできます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-126">After you save the active, managed workflow, you can then modify and deactivate it.</span></span>

8. <span data-ttu-id="1a6c8-127">フェデレーション ユーザーにグループへの通話を許可するには、[**フェデレーションを有効にする**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-127">To allow federated users to call the group, select the **Enable for federation** check box.</span></span> <span data-ttu-id="1a6c8-128">フェデレーション用に構成された応答グループアプリケーションに適用される外部アクセスポリシーも必要です。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-128">You must also have an external access policy that applies to the Response Group application configured for federation.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1a6c8-129">グローバル外部アクセスポリシーは、応答グループアプリケーションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-129">The global external access policy applies to the Response Group application.</span></span> <span data-ttu-id="1a6c8-130">[Skype for Business Server] コントロールパネルを使用するか、 **CsExternalAccessPolicy**コマンドレットを使用して EnableOutsideAccess パラメーターを True に設定することによって、応答グループのフェデレーションのグローバルポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-130">You can configure the global policy for response group federation by using Skype for Business Server Control Panel or by using the **Set-CsExternalAccessPolicy** cmdlet to set the EnableOutsideAccess parameter to True.</span></span> <span data-ttu-id="1a6c8-131">グローバル ポリシー設定は、サイトやユーザー ポリシーに割り当てられていない限り、すべてのユーザーに適用されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-131">Keep in mind that global policy settings apply to all users unless they are assigned a site or user policy.</span></span> <span data-ttu-id="1a6c8-132">そのため、応答グループ向けにこの設定を変更する前に、フェデレーション設定が組織の要件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-132">Therefore, before changing this setting for response groups, make sure that the federation setting meets the requirements of your organization.</span></span> <span data-ttu-id="1a6c8-133">ポリシーをユーザーに適用する方法の詳細については、「[Manage External Access Policy for Your Organization](https://technet.microsoft.com/library/5571811e-34c8-443a-b94c-1ab5d4275581.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-133">For details about how policies apply to users, see [Manage External Access Policy for Your Organization](https://technet.microsoft.com/library/5571811e-34c8-443a-b94c-1ab5d4275581.aspx).</span></span> <span data-ttu-id="1a6c8-134">フェデレーション設定の詳細については、「 [Set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/set-csexternalaccesspolicy?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-134">For details about the federation setting, see [Set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/set-csexternalaccesspolicy?view=skype-ps).</span></span>

    > [!NOTE]
    > <span data-ttu-id="1a6c8-135">Skype for Business Online でホストされているユーザーは、オンプレミス展開でホストされている応答グループに通話を発信することはできません。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-135">Users who are hosted in Skype for Business Online can't place calls to response groups that are hosted in an on-premises deployment.</span></span> <span data-ttu-id="1a6c8-136">これは、ハイブリッド展開と、オンプレミスの展開が Skype for Business Online 展開とフェデレーションされている場合に当てはまります。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-136">This is true in both hybrid deployments and in cases where an on-premises deployment is federated with a Skype for Business Online deployment.</span></span>

9. <span data-ttu-id="1a6c8-137">通話中、エージェントの ID を非表示にするには、[**エージェントの匿名性を有効にする**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-137">To hide the identity of agents during calls, select the **Enable agent anonymity** check box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1a6c8-p110">匿名の通話は、インスタント メッセージング (IM) やビデオから開始することはできません。ただし、通話の確立後、エージェントまたは発信者が IM やビデオを追加することはできます。匿名のエージェントは、通話の保留、通話の転送 (無条件転送と取次転送)、および通話の保留と保留解除を行うこともできます。匿名の通話では、会議、アプリケーション共有とデスクトップ共有、ファイル転送、ホワイトボードとデータのグループ作業、および通話の記録はサポートされません。Lync VDI プラグインを使用するエージェントは、着信通話を匿名で受信できますが、発信通話を匿名で行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p110">Anonymous calls cannot start with instant messaging (IM) or video, although the agent or the caller can add IM and video after the call is established. An anonymous agent can also put calls on hold, transfer calls (both blind and consultative transfers), and park and retrieve calls. Anonymous calls do not support conferencing, application sharing and desktop sharing, file transfer, whiteboarding and data collaboration, and call recording. Agents using the Lync VDI Plugin can receive incoming calls anonymously, but they cannot make outgoing calls anonymously.</span></span>

10. <span data-ttu-id="1a6c8-142">[**通話を受けるグループのアドレスを入力します**] に、ワークフローへの通話に応答するグループのプライマリ SIP Uniform Resource Identifier (URI) アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-142">Under **Enter the address of the group that will receive the calls**, type the primary SIP uniform resource identifier (URI) address of the group that will answer calls to the workflow.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1a6c8-143">ワークフローのプライマリ URI は、ワークフローをどのように識別および参照するかを表します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-143">The primary URI for a workflow is how the workflow is identified and referenced.</span></span> <span data-ttu-id="1a6c8-144">入力した SIP URI は、Active Directory ドメインサービスで連絡先オブジェクトとして作成されます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-144">The SIP URI that you enter is created as a contact object in Active Directory Domain Services.</span></span> <span data-ttu-id="1a6c8-145">URI を作成するには、オブジェクトが Active Directory 内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-145">To create the URI, the object must be unique in Active Directory.</span></span>

11. <span data-ttu-id="1a6c8-146">[**表示名**] に、ワークフローに対して表示する名前を入力します (たとえば、[売上高応答] グループ)。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-146">In **Display name**, type the name that you want to display for the workflow (for example, Sales Response Group).</span></span>

    > [!NOTE]
    > <span data-ttu-id="1a6c8-p112">表示名に「<」または「>」という文字を含めないでください。次の表示名は予約されているため、使用しないでください。**RGS Presence Watcher** または **Announcement Service**。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p112">Do not include the "<" or ">" characters in the display name. Do not use the following display names because they are reserved: **RGS Presence Watcher** or **Announcement Service**.</span></span>

12. <span data-ttu-id="1a6c8-149">[**電話番号**] に、応答グループの回線 URI を入力します (入力例 +14255550165)。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-149">Under **Telephone number**, type the line URI for the response group (for example, +14255550165).</span></span>

13. <span data-ttu-id="1a6c8-150">[**表示番号**] に、応答グループに対して表示する番号を入力します (入力例 +1 (425) 555-0165)。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-150">In **Display number**, type the number as you want it to appear for the response group (for example, +1 (425) 555-0165).</span></span>

14. <span data-ttu-id="1a6c8-151">省略[**説明**] に、Skype for business の連絡先カードに表示するワークフローの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-151">(Optional) In **Description**, type a description for the workflow as you want it to appear on the contact card in Skype for Business.</span></span>

15. <span data-ttu-id="1a6c8-152">このワークフローを応答グループのマネージャーが管理する場合は、[**ワークフローの種類**] で [**管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-152">In **Workflow Type**, select **Managed** if this workflow will be managed by a Response Group Manager.</span></span> <span data-ttu-id="1a6c8-153">応答グループマネージャーをワークフローに割り当てるには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-153">Do the following to assign Response Group Managers to the workflow:</span></span>

    <span data-ttu-id="1a6c8-154">a.</span><span class="sxs-lookup"><span data-stu-id="1a6c8-154">a.</span></span> <span data-ttu-id="1a6c8-155">このワークフローのマネージャーの SIP URI を入力して、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-155">Type the SIP URI of a manager for this workflow, and click **Add**.</span></span>

    <span data-ttu-id="1a6c8-156">b.</span><span class="sxs-lookup"><span data-stu-id="1a6c8-156">b.</span></span> <span data-ttu-id="1a6c8-157">ワークフローに追加するマネージャーの SIP URI を入力して、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-157">Type the SIP URI of additional managers to add to the workflow, and click **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="1a6c8-p116">応答グループのマネージャーに指定されているすべてのユーザーに CsResponseGroupManager ロールを割り当てる必要があります。このロールが割り当てられていない場合、ユーザーは応答グループを管理できません。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p116">Every user who is designated as a manager of a response group must be assigned the CsResponseGroupManager role. If users are not assigned this role, they cannot manage response groups.</span></span>

16. <span data-ttu-id="1a6c8-160">[**ステップ 2 言語の選択**] で、音声認識と音声合成で使用する言語をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-160">Under **Step 2 Select a Language**, click the language that you want to use for speech recognition and text-to-speech.</span></span>

17. <span data-ttu-id="1a6c8-161">開始メッセージを構成する場合は、[**ステップ 3 開始メッセージの構成**] で [**開始メッセージを再生する**] チェック ボックスをオンにして、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-161">If you want to configure a welcome message, under **Step 3 Configure a Welcome Message**, select the **Play a welcome message** check box, and then do one of the following:</span></span>

    - <span data-ttu-id="1a6c8-162">発信者用の音声に変換される開始メッセージをテキストとして入力するには、[**音声合成を使用する**] をクリックして、テキスト ボックスに開始メッセージを入力します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-162">To enter the welcome message as text that is converted to speech for callers, click **Use text-to-speech**, and then type the welcome message in the text box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1a6c8-163">入力するテキストに HTML タグを含めないでください。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-163">Do not include HTML tags in the text you enter.</span></span> <span data-ttu-id="1a6c8-164">HTML タグを含めると、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-164">If you include HTML tags, you will receive an error message.</span></span>

    - <span data-ttu-id="1a6c8-p118">開始メッセージに Wave (.wav) または Windows Media オーディオ (.wma) ファイルの録音を使用するには、[**録音を選択する**] をクリックします。新しいオーディオ ファイルをアップロードする場合は、[**録音**] リンクをクリックしてください。新しいブラウザー ウィンドウで [**参照**] をクリックし、使用するオーディオ ファイルを選択して、[**開く**] をクリックします。[**アップロード**] をクリックしてオーディオ ファイルを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p118">To use a wave (.wav) or Windows Media audio (.wma) file recording for the welcome message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the audio file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1a6c8-169">ユーザーが指定したすべてのオーディオ ファイルは、特定の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-169">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="1a6c8-170">サポートされているファイル形式の詳細については、「[Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-170">For details about supported file formats, see [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span>

18. <span data-ttu-id="1a6c8-171">[**ステップ 4 営業時間の指定**] の [**タイム ゾーン**] で、ワークフローのタイム ゾーンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-171">Under **Step 4 Specify Your Business Hours**, in **Your time zone**, click the time zone for the workflow.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1a6c8-p120">このタイム ゾーンは、ワークフローの発信者とエージェントの所在地のタイム ゾーンです。これを使用して、始業時間と終業時間が計算されます。たとえば、北アメリカ東部標準時を使用するようにワークフローが構成されており、ワークフローで始業が午前 7:00、終業が午後 11:00 にスケジュールされている場合は、東部標準時の 7:00 と 23:00 がそれぞれ始業時刻と終業時刻になります (時間は 24 時間表記で入力する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p120">The time zone is the time zone where the callers and agents of the workflow reside. It is used to calculate the open and close hours. For example, if the workflow is configured to use the North American Eastern Time zone and the workflow is scheduled to open at 7:00 A.M. and close at 11:00 P.M., the open and close times are assumed to be 7:00 Eastern Time and 23:00 Eastern Time respectively. (You must enter the times in 24-hour time notation.)</span></span>

19. <span data-ttu-id="1a6c8-177">次のいずれかの操作を実行して、使用する営業時間スケジュールの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-177">Select the type of business hours schedule you want to use by doing one of the following:</span></span>

    - <span data-ttu-id="1a6c8-178">事前に定義した営業時間スケジュールを使用するには、[**プリセット スケジュールを使用する**] をクリックして、ドロップダウン リストから使用するスケジュールを選択します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-178">To use a predefined schedule of business hours, click **Use a preset schedule**, and then select the schedule you want to use from the drop-down list.</span></span>

      > [!NOTE]
      > <span data-ttu-id="1a6c8-179">このオプションを選択できるようにするには、あらかじめ少なくとも 1 つのプリセット スケジュールを定義しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-179">You must have defined at least one preset schedule previously to be able to select this option.</span></span> <span data-ttu-id="1a6c8-180">**New-CSRgsHoursOfBusiness** コマンドレットを使用してプリセット スケジュールを定義します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-180">You define preset schedules by using the **New-CSRgsHoursOfBusiness** cmdlet.</span></span> <span data-ttu-id="1a6c8-181">詳細については、「(オプション)」を参照してください。 [Skype For business で応答グループの勤務時間を定義](optional-define-response-group-business-hours.md)します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-181">For details, see [(Optional) Define Response Group business hours in Skype for Business](optional-define-response-group-business-hours.md).</span></span>

      > [!NOTE]
      > <span data-ttu-id="1a6c8-182">プリセット スケジュールを選択すると、応答グループの対応日時で、[**曜日**]、[**開始**]、[**終了**] が自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-182">When you select a preset schedule, **Day**, **Open**, and **Close** are automatically filled with the days and hours that the response group is available.</span></span>

    - <span data-ttu-id="1a6c8-183">このワークフローのみに適用するカスタム スケジュールを使用するには、[**カスタム スケジュールを使用する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-183">To use a custom schedule that applies only to this workflow, click **Use a custom schedule**.</span></span>

20. <span data-ttu-id="1a6c8-184">このワークフロー用のカスタム スケジュールを作成する場合は、応答グループが対応可能な曜日のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-184">If you are creating a custom schedule for this workflow, click the check boxes for the days of the week that the response group is available.</span></span>

21. <span data-ttu-id="1a6c8-185">ユーザー設定のスケジュールを作成する場合は、[返信] グループが利用できるようになる曜日ごとに、**始値**と**終値**の時間を入力します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-185">If you are creating a custom schedule, type the **Open** and **Close** hours for each day of the week that the response group is available.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1a6c8-p122">[**開始**] 時間と [**終了**] 時間は 24 時間表記で入力する必要があります。たとえば、職場の営業時間が営業日の 9 時から 5 時までで、昼休みのために正午にオフィスを一度閉める場合、営業時間は [**開始**] 9:00、[**終了**] 12:00、[**開始**] 13:00、[**終了**] 17:00 として指定します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p122">The **Open** and **Close** hours must be in 24-hour time notation. For example, if your office works a 9-to-5 work day and closes at noon for lunch, the business hours are specified as **Open** 9:00, **Close** 12:00, **Open** 13:00, and **Close** 17:00.</span></span>

22. <span data-ttu-id="1a6c8-188">営業時間外にメッセージを再生するには、[**応答グループの営業時間外にメッセージを再生する**] チェック ボックスをオンにしてから、次のいずれかの操作を実行して再生するメッセージを指定します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-188">If you want to play a message when the office is not open, select the **Play a message when the response group is outside of business hours** check box, and then specify the message to play by doing one of the following:</span></span>

    - <span data-ttu-id="1a6c8-189">発信者用に音声に変換されるメッセージをテキストとして入力するには、[**音声合成を使用する**] をクリックして、テキスト ボックスにメッセージを入力します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-189">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>

      > [!NOTE]
      > <span data-ttu-id="1a6c8-190">入力するテキストに HTML タグを含めないでください。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-190">Do not include HTML tags in the text you enter.</span></span> <span data-ttu-id="1a6c8-191">HTML タグを含めると、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-191">If you include HTML tags, you will receive an error message.</span></span>

    - <span data-ttu-id="1a6c8-p124">メッセージにオーディオ ファイルの録音を使用するには、[**録音を選択する**] をクリックします。新しいオーディオ ファイルをアップロードする場合は、[**録音**] リンクをクリックしてください。新しいブラウザー ウィンドウで [**参照**] をクリックし、使用するファイルを選択して、[**開く**] をクリックします。[**アップロード**] をクリックしてオーディオ ファイルを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p124">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>

      > [!NOTE]
      > <span data-ttu-id="1a6c8-p125">ユーザーが指定したすべてのオーディオ ファイルは、特定の要件を満たしている必要があります。サポートされているオーディオ ファイル形式の詳細については、「[Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p125">All user-provided audio files must meet certain requirements. For details about supported audio file formats, see [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span>

23. <span data-ttu-id="1a6c8-198">メッセージが構成されている場合は、メッセージ再生後の通話の処理方法を次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-198">Specify how to handle calls after the message is played (if a message is configured):</span></span>

    - <span data-ttu-id="1a6c8-199">通話を終了するには、[**終話**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-199">To disconnect the call, click **Disconnect Call**.</span></span>

    - <span data-ttu-id="1a6c8-200">通話をボイス メールに転送するには、[**ボイス メールに転送**] をクリックして、ボイス メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-200">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="1a6c8-201">ボイスメールのアドレスの形式は@ \* \<、ユーザー\>名\*\*\<domainName\> \* (例 bob@contoso.com) です。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-201">The format for the voice mail address is  *\<username\>*@*\<domainName\>* (for example, bob@contoso.com).</span></span>

    - <span data-ttu-id="1a6c8-202">通話を別のユーザーに転送するには、[**SIP URI に転送**] をクリックして、ユーザー アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-202">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="1a6c8-203">ユーザーアドレスの形式は@ _ \<、username\>__\<domainName\>_ です。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-203">The format for the user address is  _\<username\>_@_\<domainName\>_.</span></span>

    - <span data-ttu-id="1a6c8-204">通話を別の電話番号に転送するには、[**電話番号に転送**] をクリックして、電話番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-204">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="1a6c8-205">電話番号の形式は\* \<番号\>*@*\<domainName\> \* (+ 14255550121@contoso.com など) です。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-205">The format for the telephone number is  *\<number\>*@*\<domainName\>* (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="1a6c8-206">発信者は、ドメイン名を使用して適切な宛先にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-206">The domain name is used to route the caller to the correct destination.</span></span>

24. <span data-ttu-id="1a6c8-207">[**ステップ 5 休日の指定**] で、応答グループが営業しない日を定義する、1 つまたは複数の休日セットのチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-207">Under **Step 5 Specify Your Holidays**, click the check boxes for one or more sets of holidays that define the days when the response group is closed for business.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1a6c8-208">ワークフローを構成する前に、休日および休日セットを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-208">You need to define holidays and holiday sets before you configure the workflow.</span></span> <span data-ttu-id="1a6c8-209">休日および休日セットを定義するには、**New-CsRgsHoliday** コマンドレットおよび **New-CsRgsHolidaySet** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-209">Use the **New-CsRgsHoliday** and **New-CsRgsHolidaySet** cmdlets to define holidays and holiday sets.</span></span> <span data-ttu-id="1a6c8-210">詳細については、「 [(オプション) Skype For business で応答グループの休日セットを定義](optional-define-response-group-holiday-sets.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-210">For details, see [(Optional) Define Response Group holiday sets in Skype for Business](optional-define-response-group-holiday-sets.md).</span></span>

25. <span data-ttu-id="1a6c8-211">休日にメッセージを再生するには、[**休日にメッセージを再生する**] チェック ボックスをオンにしてから、次のいずれかの操作を実行して再生するメッセージを指定します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-211">If you want to play a message on holidays, select the **Play a message during holidays** check box, and then specify the message to play by doing one of the following:</span></span>

    - <span data-ttu-id="1a6c8-212">発信者用に音声に変換されるメッセージをテキストとして入力するには、[**音声合成を使用する**] をクリックして、テキスト ボックスにメッセージを入力します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-212">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1a6c8-213">入力するテキストに HTML タグを含めないでください。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-213">Do not include HTML tags in the text you enter.</span></span> <span data-ttu-id="1a6c8-214">HTML タグを含めると、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-214">If you include HTML tags, you will receive an error message.</span></span>

    - <span data-ttu-id="1a6c8-p131">メッセージにオーディオ ファイルの録音を使用するには、[**録音を選択する**] をクリックします。新しいオーディオ ファイルをアップロードする場合は、[**録音**] リンクをクリックしてください。新しいブラウザー ウィンドウで [**参照**] をクリックし、使用するファイルを選択して、[**開く**] をクリックします。[**アップロード**] をクリックしてオーディオ ファイルを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p131">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>

      > [!NOTE]
      > <span data-ttu-id="1a6c8-p132">ユーザーが指定したすべてのオーディオ ファイルは、特定の要件を満たしている必要があります。サポートされているオーディオ ファイル形式の詳細については、「[Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p132">All user-provided audio files must meet certain requirements. For details about supported audio file formats, see [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span>

26. <span data-ttu-id="1a6c8-221">メッセージが構成されている場合は、メッセージ再生後の通話の処理方法を次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-221">Specify how to handle calls after the message is played (if a message is configured):</span></span>

    - <span data-ttu-id="1a6c8-222">通話を終了するには、[**終話**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-222">To disconnect the call, click **Disconnect Call**.</span></span>

    - <span data-ttu-id="1a6c8-223">通話をボイス メールに転送するには、[**ボイス メールに転送**] をクリックして、ボイス メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-223">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="1a6c8-224">ボイスメールのアドレスの形式は@ \* \<、ユーザー\>名\*\*\<domainName\> \* (例 bob@contoso.com) です。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-224">The format for the voice mail address is  *\<username\>*@*\<domainName\>* (for example, bob@contoso.com).</span></span>

    - <span data-ttu-id="1a6c8-225">通話を別のユーザーに転送するには、[**SIP URI に転送**] をクリックして、ユーザー アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-225">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="1a6c8-226">ユーザーアドレスの形式は@ _ \<、username\>__\<domainName\>_ です。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-226">The format for the user address is  _\<username\>_@_\<domainName\>_.</span></span>

    - <span data-ttu-id="1a6c8-227">通話を別の電話番号に転送するには、[**電話番号に転送**] をクリックして、電話番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-227">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="1a6c8-228">電話番号の形式は\* \<番号\>*@*\<domainName\> \* (+ 14255550121@contoso.com など) です。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-228">The format for the telephone number is  *\<number\>*@*\<domainName\>* (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="1a6c8-229">発信者は、ドメイン名を使用して適切な宛先にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-229">The domain name is used to route the caller to the correct destination.</span></span>

27. <span data-ttu-id="1a6c8-230">[**ステップ 6 キューの構成**] の [**通話を受け取るキューを選択します**] で、エージェントが応答可能になるまで発信者を保留するキューを選択します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-230">Under **Step 6 Configure a Queue**, in **Select the queue that will receive the calls**, select the queue that you want to hold callers until an agent becomes available.</span></span>

28. <span data-ttu-id="1a6c8-231">[**ステップ 7 保留音の構成**] で次のいずれかの操作を実行して、発信者がエージェントの応答を待機しているときの保留音を選択します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-231">Under **Step 7 Configure Music on Hold**, choose the music you want callers to listen to while waiting for an agent by doing one of the following:</span></span>

    - <span data-ttu-id="1a6c8-232">既定の保留音の録音を使用するには、[**既定値を使用する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-232">To use the default music-on-hold recording, click **Use default**.</span></span>

    - <span data-ttu-id="1a6c8-p136">保留音にオーディオ ファイルの録音を使用するには、[**音楽ファイルを選択する**] をクリックします。新しいオーディオ ファイルをアップロードする場合は、[**音楽ファイル**] リンクをクリックします。新しいブラウザー ウィンドウで [**参照**] をクリックし、使用するファイルを選択して、[**開く**] をクリックします。[**アップロード**] をクリックしてオーディオ ファイルを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p136">To use an audio file recording for the music on hold, click **Select a music file**. If you want to upload a new audio file, click the **a music file** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>

      > [!NOTE]
      > <span data-ttu-id="1a6c8-p137">ユーザーが指定したすべてのオーディオ ファイルは、特定の要件を満たしている必要があります。サポートされているオーディオ ファイル形式の詳細については、「[Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p137">All user provided audio files must meet certain requirements. For details about supported audio file formats, see [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span>

29. <span data-ttu-id="1a6c8-239">[**展開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-239">Click **Deploy**.</span></span>

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-hunt-group-workflow"></a><span data-ttu-id="1a6c8-240">Skype for Business Server 管理シェルを使ってハントグループワークフローを作成または変更するには</span><span class="sxs-lookup"><span data-stu-id="1a6c8-240">To use Skype for Business Server Management Shell to create or modify a hunt group workflow</span></span>

1. <span data-ttu-id="1a6c8-241">RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-241">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2. <span data-ttu-id="1a6c8-242">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-242">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="1a6c8-p138">開始メッセージで再生されるプロンプトを作成し、変数に格納します。コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p138">Create the prompt to be played for the welcome message, and save it in a variable. At the command line, run:</span></span>

   ```powershell
   $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

    <span data-ttu-id="1a6c8-245">例:</span><span class="sxs-lookup"><span data-stu-id="1a6c8-245">For example:</span></span>

   ```powershell
   $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "Welcome to Contoso. Please wait for an available agent."
   ```

     > [!NOTE]
     > <span data-ttu-id="1a6c8-246">プロンプトにオーディオ ファイルを使用するには、 **Import-CsRgsAudioFile** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-246">To use an audio file for the prompt, use the **Import-CsRgsAudioFile** cmdlet.</span></span> <span data-ttu-id="1a6c8-247">詳細については、「[インポート-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-247">For details, see [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span></span>

4. <span data-ttu-id="1a6c8-248">通話が転送されることになるキューまたは質問の ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-248">Get the identity of the queue or question where the calls will be directed.</span></span> <span data-ttu-id="1a6c8-249">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-249">At the command line, run:</span></span>

   ```powershell
   $qid = (Get-CsRgsQueue -Name "Help Desk").Identity
   ```

    <span data-ttu-id="1a6c8-250">キューの作成の詳細については、「[新しい-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/new-csrgsqueue?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-250">For details about creating the queue, see [New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/new-csrgsqueue?view=skype-ps).</span></span>

5. <span data-ttu-id="1a6c8-p141">営業時間中にワークフローを開いたときに実行される既定のアクションを定義し、変数に格納します。コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p141">Define the default action to be taken when a workflow is opened during business hours, and save it in a variable. At the command line, run:</span></span>

   ```powershell
   $actionWM = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken> -QueueID $qid
   ```

    > [!NOTE]
    > <span data-ttu-id="1a6c8-253">ハント グループ ワークフローでは、既定のアクションにより通話がキューに転送される必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-253">For hunt group workflows, the default action must direct the call to a queue.</span></span> <span data-ttu-id="1a6c8-254">このパラメーターは、アクティブなワークフローに必要です。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-254">This parameter is required for active workflows.</span></span> <span data-ttu-id="1a6c8-255">非アクティブなワークフローでは不要です。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-255">It is not required for inactive workflows.</span></span>

    <span data-ttu-id="1a6c8-256">例:</span><span class="sxs-lookup"><span data-stu-id="1a6c8-256">For example:</span></span>

   ```powershell
   $actionWM = New-CsRgsCallAction -Prompt $promptWM -Action TransferToQueue -QueueID $qid.Identity
   ```

6. <span data-ttu-id="1a6c8-257">営業時間と休日を定義する場合は、ワークフローを作成または変更する前に、営業時間と休日を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-257">If you want to define business hours and holidays, you need to create them before you create or modify the workflow.</span></span> <span data-ttu-id="1a6c8-258">詳細については、「 [(オプション) skype For business で応答グループの勤務時間を定義](optional-define-response-group-business-hours.md)する」および「オプション」を参照してください。 [skype For Business で応答グループの休日セットを定義](optional-define-response-group-holiday-sets.md)します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-258">For details, see [(Optional) Define Response Group business hours in Skype for Business](optional-define-response-group-business-hours.md) and [(Optional) Define Response Group holiday sets in Skype for Business](optional-define-response-group-holiday-sets.md).</span></span>

7. <span data-ttu-id="1a6c8-259">営業時間外または休日に受信する通話用のプロンプトを保持する場合は、**New-CsRgsPrompt** コマンドレットを使用してプロンプトを定義し、**New-CsRgsCallAction** を使用して、プロンプトの後に実行するアクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-259">If you want to have prompts for calls that are received out of business hours or on holidays, use the **New-CsRgsPrompt** cmdlet to define the prompt, and use the **New-CsRgsCallAction** to define the action to be taken after the prompt.</span></span> <span data-ttu-id="1a6c8-260">詳しくは、「[新しい-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps) 」と「[新規-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-260">For details, see [New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps) and [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span></span>

8. <span data-ttu-id="1a6c8-261">Lync サーバー応答グループサービスのサービス名を取得して、それを変数に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-261">Retrieve the service name for the Lync Server Response Group service and assign it to a variable.</span></span> <span data-ttu-id="1a6c8-262">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-262">At the command, run:</span></span>

   ```powershell
   $serviceId = "service:" + (Get-CsService | ?{$_.Applications -like "*RGS*"}).ServiceId;
   ```

9. <span data-ttu-id="1a6c8-263">ワークフローを作成または変更します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-263">Create or modify the workflow.</span></span> <span data-ttu-id="1a6c8-264">ワークフローを作成するには、**New-CsRgsWorkflow** を使用します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-264">To create a workflow, use **New-CsRgsWorkflow**.</span></span> <span data-ttu-id="1a6c8-265">ワークフローを変更するには、**Set-CsRgsWorkflow** を使用します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-265">To modify a workflow, use **Set-CsRgsWorkflow**.</span></span> <span data-ttu-id="1a6c8-266">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-266">At the command line, type:</span></span>

   ```powershell
   $workflowHG = New-CsRgsWorkflow -Parent <service ID for the Response Group service> -Name "<hunt group name>" [-Description "<hunt group description>"] -PrimaryUri "<SIP address for the workflow>" [-LineUri "<Phone number for the workflow>"] [-DisplayNumber "<Phone number displayed in Lync>"] [-Active <$true | $false>] [-Anonymous <$true | $false>] [-DefaultAction <variable from preceding step>] [-EnabledForFederation <$true | $false>] [-Managed <$true | $false>] [-ManagersByUri <SIP addresses for Response Group Managers who can manage the workflow>]
   ```

    <span data-ttu-id="1a6c8-267">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-267">For example:</span></span>

   ```powershell
   $workflowHG = New-CsRgsWorkflow -Parent $serviceID -Name "Human Resources" -Description "Human Resources workflow" -PrimaryUri "sip:humanresources@contoso.com" -LineUri "TEL:+14255551219" -DisplayNumber "555-1219" -Active $true -Anonymous $true -DefaultAction $actionWM -EnabledForFederation $false -Managed $true -ManagersByUri "sip:bob@contoso.com", "mindy@contoso.com"
   ```

     > [!IMPORTANT]
     > <span data-ttu-id="1a6c8-268">ワークフローのマネージャーに指定されているすべてのユーザーに CsResponseGroupManager ロールを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-268">All users who are designated managers for workflows must be assigned the CsResponseGroupManager role.</span></span>

     > [!NOTE]
     > <span data-ttu-id="1a6c8-269">追加のオプションパラメーターの詳細については、「[新しい-csrgsworkflow](https://docs.microsoft.com/powershell/module/skype/new-csrgsworkflow?view=skype-ps) 」または「 [Set-csrgsworkflow](https://docs.microsoft.com/powershell/module/skype/set-csrgsworkflow?view=skype-ps) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-269">For details about additional optional parameters, see [New-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/new-csrgsworkflow?view=skype-ps) or [Set-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/set-csrgsworkflow?view=skype-ps)</span></span>

## <a name="designing-an-interactive-workflow"></a><span data-ttu-id="1a6c8-270">対話ワークフローの設計</span><span class="sxs-lookup"><span data-stu-id="1a6c8-270">Designing an interactive workflow</span></span>

<span data-ttu-id="1a6c8-271">対話型音声応答 (IVR) を使用すると、発信者から情報を取得し、通話を適切なキューに転送できます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-271">You can use interactive voice response (IVR) to obtain information from callers and direct the call to the appropriate queue.</span></span> <span data-ttu-id="1a6c8-272">使用するキューは質問と回答のペアによって決定されます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-272">Question-and-answer pairs determine which queue to use.</span></span> <span data-ttu-id="1a6c8-273">発信者の応答に応じて、発信者はフォローアップの質問を聞くか、適切なキューにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-273">Depending on the caller's response, the caller either hears a follow-up question, or is routed to the appropriate queue.</span></span> <span data-ttu-id="1a6c8-274">IVR の質問と発信者の応答は、通話を受け入れ、エージェントに貴重な情報を提供する応答エージェントに提供されます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-274">The IVR questions and the caller's responses are provided to the responding agent who accepts the call, providing valuable information to the agent.</span></span>

### <a name="overview-of-ivr-features"></a><span data-ttu-id="1a6c8-275">IVR 機能の概要</span><span class="sxs-lookup"><span data-stu-id="1a6c8-275">Overview of IVR Features</span></span>

<span data-ttu-id="1a6c8-276">応答グループアプリケーションは、26言語の音声認識と音声合成機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-276">The Response Group application offers speech recognition and text-to-speech capabilities in 26 languages.</span></span> <span data-ttu-id="1a6c8-277">IVR の質問は、音声合成や wave (.wav) または Windows Media オーディオ (.wma) ファイルを使用して入力できます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-277">You can enter IVR questions using text-to-speech or a wave (.wav) or Windows Media audio (.wma) file.</span></span> <span data-ttu-id="1a6c8-278">発信者は、音声またはデュアルトーン多重周波数 (DTMF) 応答を使用して応答できます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-278">Callers can respond by using voice or dual-tone multifrequency (DTMF) responses.</span></span>

<span data-ttu-id="1a6c8-279">対話ワークフローでは最高 2 問の質問がサポートされ、各質問には回答の選択肢を 4 つまで設定できます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-279">Interactive workflows support up to two levels of questions, with each question having up to four possible answers.</span></span> <span data-ttu-id="1a6c8-280">IVR は、発信者に質問し、発信者の応答に応じて発信者をキューにルーティングするか、または2番目の質問を求めます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-280">The IVR asks the caller a question, and depending on the caller's response, routes the caller to a queue or asks a second question.</span></span> <span data-ttu-id="1a6c8-281">2 番目の質問にも、4 つの回答を設定できます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-281">The second question can also have four possible answers.</span></span> <span data-ttu-id="1a6c8-282">2 番目のレベルの質問に対する回答に応じて、発信者は適切なキューにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-282">Depending on the answer to the second-level question, the caller is routed to the appropriate queue.</span></span>

> [!NOTE]
> <span data-ttu-id="1a6c8-283">Skype for Business Server 管理シェルを使用してコールフローを設計する場合は、さまざまなレベルの IVR の質問と回答を定義できます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-283">When you design call flows by using Skype for Business Server Management Shell, you can define any number of levels of IVR questions and any number of answers.</span></span> <span data-ttu-id="1a6c8-284">ただし、発信者の利便性を考え、3 問より多くの質問は使用せず、それぞれの回答の選択肢を 5 つ以下にするようお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-284">However, for caller usability, we recommend that you not use more than three levels of questions, with not more than five answers each.</span></span> <span data-ttu-id="1a6c8-285">また、3つ以上の種類の質問が含まれている通話フローを設計する場合は、Skype for Business Server コントロールパネルを使って通話フローを編集することはできません。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-285">In addition, if you design a call flow that has more than two levels of questions with more than four answers each, you cannot edit the call flow by using Skype for Business Server Control Panel.</span></span>

<span data-ttu-id="1a6c8-286">IVR の質問と発信者の応答は、通話を受けることができる応答エージェントに提供されます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-286">The IVR questions and the caller's responses are provided to the responding agent who accepts the call.</span></span>

### <a name="working-with-speech-technologies"></a><span data-ttu-id="1a6c8-287">音声テクノロジの操作</span><span class="sxs-lookup"><span data-stu-id="1a6c8-287">Working with Speech Technologies</span></span>

<span data-ttu-id="1a6c8-p151">音声認識や音声合成などの音声テクノロジにより、顧客のエクスペリエンスが強化され、情報へのより自然で効率的なアクセスが可能となります。ただし、指定したテキストやユーザーの音声応答が、音声エンジンによって正しく認識されない場合もあります。たとえば、"#" 記号は、音声合成エンジンによって "番号" という語に変換されます。この問題は、次の方法によって軽減されます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p151">Speech technologies, such as speech recognition and text-to-speech, can enhance customer experience and let people access information more naturally and effectively. However, there can be cases where the specified text or the user voice response is not recognized correctly by the speech engine. For example, the "#" symbol is translated by the text-to-speech engine as the word "number." This issue can be mitigated by the following:</span></span>

- <span data-ttu-id="1a6c8-p152">音声エンジンにより、発信者は 5 回まで質問に回答することができます。発信者の質問に対する回答が不適切な場合 (回答が指定された応答のいずれでもない)、またはまったく回答がない場合には、発信者にもう一度その質問に回答する機会が与えられます。発信者は、通話が切断されるまでに 5 回質問に回答することができます。IVR は、発信者の回答に誤りがあるたびにカスタマイズしたメッセージを再生するように構成できます。質問は毎回繰り返されます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p152">The speech engine gives the caller five attempts to answer the question. If the caller answers the question incorrectly (that is, the answer is not one of the specified responses) or does not provide an answer at all, the caller gets another chance to answer the question. The caller has five attempts to answer the question before being disconnected. You can configure the IVR to play a customized message after each caller error. The question is repeated each time.</span></span>

- <span data-ttu-id="1a6c8-p153">音声エンジンによって周囲の雑音が応答として解釈される可能性を最小限に抑えるため、長めの応答を使用してください。たとえば、応答には複数の音節を含め、発音が相互に明確に異なるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p153">To minimize the potential for ambient noise to be interpreted by the speech engine as a response, use longer responses. For example, responses should have more than one syllable and should sound significantly different from each other.</span></span>

- <span data-ttu-id="1a6c8-p154">質問に音声応答と DTMF 応答の両方が含まれる場合は、DTMF 応答ではなく概念を表す語句で音声応答を構成してください。たとえば、「1 を押すか 1 とお答えください」を使用する代わりに、「1 を押すか請求とお答えください」を使用します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p154">If your questions have both speech and DTMF responses, configure the speech responses with words that represent the concept rather than the DTMF response. For example, instead of using "Press or say one" use "Press 1 or say billing."</span></span>

- <span data-ttu-id="1a6c8-p155">IVR を設計したら、ワークフローを呼び出して質問を聞き、音声で各質問に応答して、IVR が正常に再生および動作することを確認します。その後、IVR を変更して、解釈の問題を修正できます。# キーを示す必要がある場合は、前の例に従って、# 記号ではなく、キー名を使用して IVR の質問を書き直すことができます。たとえば、「営業部門をご希望の場合は、シャープを押してください」とします。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p155">After you design your IVR, call the workflow, listen to the prompts, respond to each of the prompts using voice, and verify that the IVR sounds and behaves as expected. You can then modify the IVR to fix any interpretation issues. Following the previous example, if you need to refer to the # key, you can rewrite your IVR prompt to use the key name, rather than the # symbol. For example, "To talk to sales, press the pound key."</span></span>

### <a name="ivr-design-examples"></a><span data-ttu-id="1a6c8-305">IVR 設計の例</span><span class="sxs-lookup"><span data-stu-id="1a6c8-305">IVR Design Examples</span></span>

<span data-ttu-id="1a6c8-306">以下のセクションでは、さまざまな IVR シナリオおよび質問と回答のペアの例を示します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-306">The following sections contain examples of different IVR scenarios and question-and-answer pairs.</span></span>

#### <a name="ivr-with-one-level-of-questions"></a><span data-ttu-id="1a6c8-307">1 問の質問が設定された IVR</span><span class="sxs-lookup"><span data-stu-id="1a6c8-307">IVR with One Level of Questions</span></span>

<span data-ttu-id="1a6c8-308">次の例は、1 問の質問を使用する IVR を示しています。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-308">The following example shows an IVR that uses one level of questions.</span></span> <span data-ttu-id="1a6c8-309">音声認識を使って、発信者の応答を検出します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-309">It uses speech recognition to detect the caller's response.</span></span>

 <span data-ttu-id="1a6c8-p157">**質問:** 「人事部にお問い合わせいただき、ありがとうございます。給与課をご希望の場合は、給与課とお答えください。それ以外の場合は、人事部とお答えください。」</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p157">**Question:** "Thank you for calling Human Resources. If you would like to speak to payroll, say payroll. Otherwise, say HR."</span></span>

- <span data-ttu-id="1a6c8-313">**1 つ目のオプションが選択された場合:** 発信者は給与課にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-313">**Option 1 is selected:** The caller is routed to the payroll team.</span></span>

- <span data-ttu-id="1a6c8-314">**2 つ目のオプションが選択された場合:** 発信者は人事部にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-314">**Option 2 is selected:** The caller is routed to the human resources team.</span></span>

<span data-ttu-id="1a6c8-315">次の図は、通話の流れを示します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-315">The following figure shows the call flow.</span></span>

 <span data-ttu-id="1a6c8-316">**1 問対話の通話の流れ**</span><span class="sxs-lookup"><span data-stu-id="1a6c8-316">**One-level interactive call flow**</span></span>

![対話型音声応答の使用による通話フローの設計](../../media/Ops_OCS_RGS_IVRLevel1.jpg)

#### <a name="ivr-with-two-levels-of-questions"></a><span data-ttu-id="1a6c8-318">2 問の質問が設定された IVR</span><span class="sxs-lookup"><span data-stu-id="1a6c8-318">IVR with Two Levels of Questions</span></span>

<span data-ttu-id="1a6c8-p158">次の例は、2 問の質問を使用する IVR を示しています。この例で発信者は、音声または DTMF キーパッド入力を使用して応答できます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p158">The following example shows an IVR that uses two levels of questions. It allows callers to respond using either speech or DTMF keypad input.</span></span>

 <span data-ttu-id="1a6c8-p159">**質問:** 「IT ヘルプ デスクにお問い合わせいただき、ありがとうございます。ネットワーク アクセスに問題がある場合は、1 を押すか、ネットワークとお答えください。ソフトウェアに問題がある場合は、2 を押すか、ソフトウェアとお答えください。ハードウェアに問題がある場合は、3 を押すか、ハードウェアとお答えください。」</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p159">**Question:** "Thank you for calling the IT Help Desk. If you have a network access problem, press 1 or say network. If you have a software problem, press 2 or say software. If you have a hardware problem, press 3 or say hardware."</span></span>

- <span data-ttu-id="1a6c8-325">**1 つ目のオプションが選択された場合:** 発信者はネットワーク サポート チームにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-325">**Option 1 is selected:** The caller is routed to the network support team.</span></span>

- <span data-ttu-id="1a6c8-326">**2 つ目のオプションが選択された場合:** 発信者には、追加の質問が行われます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-326">**Option 2 is selected:** The caller is asked a follow-up question:</span></span>

    <span data-ttu-id="1a6c8-p160">**質問:** 「オペレーティング システムに問題がある場合は、1 を押すか、オペレーティング システムとお答えください。内部アプリケーションに問題がある場合は、2 を押すか、内部アプリケーションとお答えください。それ以外の場合は、3 を押すか、それ以外とお答えください。」</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p160">**Question:** "If this is an operating system problem, press 1 or say operating system. If this is a problem with an internal application, press 2 or say internal application. Otherwise, press 3 or say other."</span></span>

  - <span data-ttu-id="1a6c8-330">**1 つ目のオプションが選択された場合:** 発信者はオペレーティング システムのサポート チームにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-330">**Option 1 is selected:** The caller is routed to the operating systems support team.</span></span>

  - <span data-ttu-id="1a6c8-331">**2 つ目のオプションが選択された場合:** 発信者は内部アプリケーションのサポート チームにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-331">**Option 2 is selected:** The caller is routed to the internal applications support team.</span></span>

  - <span data-ttu-id="1a6c8-332">**3 つ目のオプションが選択された場合:** 発信者はソフトウェアのサポート チームにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-332">**Option 3 is selected:** The caller is routed to the software support team.</span></span>

- <span data-ttu-id="1a6c8-333">**3 つ目のオプションが選択された場合:** 発信者には、追加の質問が行われます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-333">**Option 3 is selected:** The caller is asked a follow-up question:</span></span>

    <span data-ttu-id="1a6c8-p161">**質問:** 「プリンターに問題がある場合は 1 を、それ以外の場合は 2 を押してください。」</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p161">**Question:** "If this is a printer problem press 1. Otherwise, press 2."</span></span>

  - <span data-ttu-id="1a6c8-336">**1 つ目のオプションが選択された場合:** 発信者はプリンターのサポート チームにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-336">**Option 1 is selected:** The caller is routed to the printer support team.</span></span>

  - <span data-ttu-id="1a6c8-337">**2 つ目のオプションが選択された場合:** 発信者はハードウェアのサポート チームにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-337">**Option 2 is selected:** The caller is routed to the hardware support team.</span></span>

<span data-ttu-id="1a6c8-338">次の図は、通話の流れを示します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-338">The following figure shows the call flow.</span></span>

 <span data-ttu-id="1a6c8-339">**2 問対話の通話の流れ**</span><span class="sxs-lookup"><span data-stu-id="1a6c8-339">**Two-level interactive call flow**</span></span>

![対話型音声応答の使用による通話フローの設計](../../media/Ops_OCS_RGS_IVRLevel2.jpg)

### <a name="best-practices"></a><span data-ttu-id="1a6c8-341">ベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="1a6c8-341">Best Practices</span></span>

<span data-ttu-id="1a6c8-342">以下に、IVR を設計する場合のベスト プラクティスをいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-342">The following list describes some best practices for designing your IVR:</span></span>

- <span data-ttu-id="1a6c8-p162">発信者がすばやくタスクに取りかかることができるようにする。過剰な情報や長いマーケティング メッセージを IVR に含めないようにする。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p162">Let the caller get to the task quickly. Avoid providing too much information or lengthy marketing messages in your IVR.</span></span>

- <span data-ttu-id="1a6c8-p163">長いメッセージを含める場合は、開始メッセージの代わりに、最初の質問に追加することを考慮する。発信者は、そのメッセージが最初の質問の一部であれば、質問に回答することによって省略できるが、開始メッセージを省略することはできない。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p163">If you want to include a lengthy message, consider appending it to the first question instead of to the welcome message. Callers can bypass the message if it is part of the first question by answering the question, but they cannot bypass the welcome message.</span></span>

- <span data-ttu-id="1a6c8-347">発信者の言語で話します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-347">Speak in the caller's language.</span></span> <span data-ttu-id="1a6c8-348">堅苦しい言い回しを避ける。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-348">Avoid stilted language.</span></span> <span data-ttu-id="1a6c8-349">自然に話す。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-349">Speak naturally.</span></span>

- <span data-ttu-id="1a6c8-350">効率的かつ効果的な案内を記述する。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-350">Write efficient and effective prompts.</span></span> <span data-ttu-id="1a6c8-351">不要なオプションを削除する。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-351">Remove any unnecessary options.</span></span> <span data-ttu-id="1a6c8-352">情報を構造化して、呼び出し元の期待される応答が文の最後にあるようにします。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-352">Structure the information so that the caller's expected response is at the end of the sentence.</span></span> <span data-ttu-id="1a6c8-353">たとえば、"営業チームに話すには、1を押します。"</span><span class="sxs-lookup"><span data-stu-id="1a6c8-353">For example, "To speak to the sales team, press 1."</span></span>

- <span data-ttu-id="1a6c8-p166">音声応答をわかりやすいものにする。たとえば、DTMF 応答と音声応答の両方を指定する場合は、次のようにする。「営業部をご希望の場合は、1 を押すか、営業と答えてください。」</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p166">Make voice responses user friendly. For example, if you specify both DTMF and voice responses, use something like: "To speak to the sales team, press 1 or say sales."</span></span>

- <span data-ttu-id="1a6c8-356">組織全体で展開する前に、ユーザーのグループで IVR をテストする。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-356">Test the IVR on a group of users before you deploy it across your organization.</span></span>

## <a name="creating-or-modifying-an-interactive-workflow"></a><span data-ttu-id="1a6c8-357">対話ワークフローの作成または変更</span><span class="sxs-lookup"><span data-stu-id="1a6c8-357">Creating or modifying an interactive workflow</span></span>

### <a name="to-use-response-group-configuration-tool-to-create-or-modify-an-interactive-workflow"></a><span data-ttu-id="1a6c8-358">応答グループ構成ツールを使用して対話型ワークフローを作成または変更するには</span><span class="sxs-lookup"><span data-stu-id="1a6c8-358">To use Response Group Configuration Tool to create or modify an Interactive workflow</span></span>

1. <span data-ttu-id="1a6c8-359">RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-359">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2. <span data-ttu-id="1a6c8-360">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-360">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="1a6c8-361">左側のナビゲーション バーで、[**応答グループ**] をクリックし、[**ワークフロー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-361">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>

4. <span data-ttu-id="1a6c8-362">[**ワークフロー**] ページで、[**ワークフローの作成または編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-362">On the **Workflow** page, click **Create or edit a workflow**.</span></span>

5. <span data-ttu-id="1a6c8-363">[**サービスの選択**] 検索フィールドに、作成または変更するワークフローをホストする **ApplicationServer** サービスの名前の全体または一部を入力します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-363">In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service that hosts the workflow that you want to create or modify.</span></span> <span data-ttu-id="1a6c8-364">サービスの結果一覧で、対象のサービスをクリックして [**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-364">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1a6c8-365">応答グループ構成ツールが開きます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-365">The Response Group Configuration Tool opens.</span></span> <span data-ttu-id="1a6c8-366">次の URL を入力して、web ブラウザーから直接応答グループ構成ツールを開くこともでき\<ます。 Https://\>webpoolfqdn/RgsConfig.</span><span class="sxs-lookup"><span data-stu-id="1a6c8-366">You can also open the Response Group Configuration Tool directly from a web browser by typing the following URL: https://\<webPoolFqdn\>/RgsConfig.</span></span>

6. <span data-ttu-id="1a6c8-367">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-367">Do one of the following:</span></span>

   - <span data-ttu-id="1a6c8-368">[**新規ワークフローの作成**] の [**対話型**] の横にある [**作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-368">Under **Create a New Workflow**, next to **Interactive**, click **Create**.</span></span>

   - <span data-ttu-id="1a6c8-369">[**既存ワークフローの管理**] で変更するワークフローを見つけて、[**アクション**] の [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-369">Under **Manage an Existing Workflow**, locate the workflow you want to change, and then under **Action**, click **Edit**.</span></span>

7. <span data-ttu-id="1a6c8-370">ユーザーがワークフローへの通話を開始できる状態ではない場合は、[**ワークフローのアクティブ化**] チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-370">If you are not ready for users to start calling the workflow, clear the **Activate the workflow** check box.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="1a6c8-371">管理ワークフローを作成する場合は、[**ワークフローのアクティブ化**] を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-371">If you are creating a managed workflow, you need to select **Activate the workflow**.</span></span> <span data-ttu-id="1a6c8-372">アクティブな管理ワークフローを保存した後、そのワークフローを変更したり、非アクティブ化したりできます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-372">After you save the active, managed workflow, you can then modify and deactivate it.</span></span>

8. <span data-ttu-id="1a6c8-373">フェデレーション ユーザーにグループへの通話を許可するには、[**フェデレーションを有効にする**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-373">To allow federated users to call the group, select the **Enable for federation** check box.</span></span> <span data-ttu-id="1a6c8-374">フェデレーション用に構成された応答グループアプリケーションに適用される外部アクセスポリシーも必要です。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-374">You must also have an external access policy that applies to the Response Group application configured for federation.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1a6c8-375">グローバル外部アクセスポリシーは、応答グループアプリケーションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-375">The global external access policy applies to the Response Group application.</span></span> <span data-ttu-id="1a6c8-376">[Skype for Business Server] コントロールパネルを使用するか、 **CsExternalAccessPolicy**コマンドレットを使用して EnableOutsideAccess パラメーターを True に設定することによって、応答グループのフェデレーションのグローバルポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-376">You can configure the global policy for response group federation by using Skype for Business Server Control Panel or by using the **Set-CsExternalAccessPolicy** cmdlet to set the EnableOutsideAccess parameter to True.</span></span> <span data-ttu-id="1a6c8-377">グローバル ポリシー設定は、サイトやユーザー ポリシーに割り当てられていない限り、すべてのユーザーに適用されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-377">Keep in mind that global policy settings apply to all users unless they are assigned a site or user policy.</span></span> <span data-ttu-id="1a6c8-378">そのため、応答グループ向けにこの設定を変更する前に、フェデレーション設定が組織の要件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-378">Therefore, before changing this setting for response groups, make sure that the federation setting meets the requirements of your organization.</span></span> <span data-ttu-id="1a6c8-379">ポリシーをユーザーに適用する方法の詳細については、「[Manage External Access Policy for Your Organization](https://technet.microsoft.com/library/5571811e-34c8-443a-b94c-1ab5d4275581.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-379">For details about how policies apply to users, see [Manage External Access Policy for Your Organization](https://technet.microsoft.com/library/5571811e-34c8-443a-b94c-1ab5d4275581.aspx).</span></span> <span data-ttu-id="1a6c8-380">フェデレーション設定の詳細については、「ドキュメントに**CsExternalAccessPolicy を設定**する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-380">For details about the federation setting, see **Set-CsExternalAccessPolicy** in documentation..</span></span>

    > [!NOTE]
    > <span data-ttu-id="1a6c8-381">Skype for Business Online でホストされているユーザーは、オンプレミス展開でホストされている応答グループに通話を発信することはできません。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-381">Users who are hosted in Skype for Business Online can't place calls to response groups that are hosted in an on-premises deployment.</span></span> <span data-ttu-id="1a6c8-382">これは、ハイブリッド展開と、オンプレミスの展開が Skype for Business Online 展開とフェデレーションされている場合に当てはまります。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-382">This is true in both hybrid deployments and in cases where an on-premises deployment is federated with a Skype for Business Online deployment.</span></span>

9. <span data-ttu-id="1a6c8-383">通話中、エージェントの ID を非表示にするには、[**エージェントの匿名性を有効にする**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-383">To hide the identity of agents during calls, select the **Enable agent anonymity** check box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1a6c8-p173">匿名の通話は、インスタント メッセージング (IM) やビデオから開始することはできません。ただし、通話の確立後、エージェントまたは発信者が IM やビデオを追加することはできます。匿名のエージェントは、通話の保留、通話の転送 (無条件転送と取次転送)、および通話の保留と保留解除を行うこともできます。匿名の通話では、会議、アプリケーション共有とデスクトップ共有、ファイル転送、ホワイトボードとデータのグループ作業、および通話の記録はサポートされません。Lync VDI プラグインを使用するエージェントは、着信通話を匿名で受信できますが、発信通話を匿名で行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p173">Anonymous calls cannot start with instant messaging (IM) or video, although the agent or the caller can add IM and video after the call is established. An anonymous agent can also put calls on hold, transfer calls (both blind and consultative transfers), and park and retrieve calls. Anonymous calls do not support conferencing, application sharing and desktop sharing, file transfer, whiteboarding and data collaboration, and call recording. Agents using the Lync VDI Plugin can receive incoming calls anonymously, but they cannot make outgoing calls anonymously.</span></span>

10. <span data-ttu-id="1a6c8-388">[**通話を受けるグループのアドレスを入力します**] に、ワークフローへの通話に応答するグループのプライマリ SIP Uniform Resource Identifier (URI) アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-388">Under **Enter the address of the group that will receive the calls**, type the primary SIP uniform resource identifier (URI) address of the group that will answer calls to the workflow.</span></span>

11. <span data-ttu-id="1a6c8-389">[**表示名**] に、ワークフローに表示する名前を入力します (入力例: Sales IVR Response Group)。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-389">In **Display name**, type the name that you want to display for the workflow (for example, Sales IVR Response Group).</span></span>

    > [!NOTE]
    > <span data-ttu-id="1a6c8-390">表示名に "\<" または "\>" という文字を含めないでください。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-390">Do not include the "\<" or "\>" characters in the display name.</span></span> <span data-ttu-id="1a6c8-391">以下の表示名は、予約されているため使用しないでください。 **Rg プレゼンスウォッチャー**または**お知らせサービス**。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-391">Do not use the following display names because they are reserved: **RGS Presence Watcher** or **Announcement Service**.</span></span>

12. <span data-ttu-id="1a6c8-392">[**電話番号**] に、応答グループの回線 URI を入力します (入力例 +14255550165)。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-392">In **Telephone number**, type the line URI for the response group (for example, +14255550165).</span></span>

13. <span data-ttu-id="1a6c8-393">[**表示番号**] に、応答グループに対して表示する番号を入力します (入力例 +1 (425) 555-0165)。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-393">In **Display number**, type the number as you want it to appear for the response group (for example, +1 (425) 555-0165).</span></span>

14. <span data-ttu-id="1a6c8-394">省略[**説明**] に、Skype for business の連絡先カードに表示するワークフローの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-394">(Optional) In **Description**, type a description for the workflow that you want to appear on the contact card in Skype for Business.</span></span>

15. <span data-ttu-id="1a6c8-395">このワークフローを応答グループのマネージャーが管理する場合は、[**ワークフローの種類**] で [**管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-395">In **Workflow Type**, select **Managed** if this workflow will be managed by a Response Group Manager.</span></span> <span data-ttu-id="1a6c8-396">応答グループマネージャーをワークフローに割り当てるには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-396">Do the following to assign Response Group Managers to the workflow:</span></span>

    <span data-ttu-id="1a6c8-397">a.</span><span class="sxs-lookup"><span data-stu-id="1a6c8-397">a.</span></span> <span data-ttu-id="1a6c8-398">このワークフローのマネージャーの SIP URI を入力して、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-398">Type the SIP URI of a manager for this workflow, and click **Add**.</span></span>

    <span data-ttu-id="1a6c8-399">b.</span><span class="sxs-lookup"><span data-stu-id="1a6c8-399">b.</span></span> <span data-ttu-id="1a6c8-400">ワークフローに追加するマネージャーの SIP URI を入力して、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-400">Type the SIP URI of additional managers to add to the workflow, and click **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="1a6c8-p178">応答グループのマネージャーに指定されているすべてのユーザーに CsResponseGroupManager ロールを割り当てる必要があります。このロールが割り当てられていない場合、ユーザーは応答グループを管理できません。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p178">Every user who is designated as a manager of a response group must be assigned the CsResponseGroupManager role. If users are not assigned this role, they cannot manage response groups.</span></span>

16. <span data-ttu-id="1a6c8-403">[**ステップ 2 言語の選択**] で、音声認識と音声合成で使用する言語をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-403">Under **Step 2 Select a Language**, click the language to use for speech recognition and text-to-speech.</span></span>

17. <span data-ttu-id="1a6c8-404">開始メッセージを構成する場合は、[**ステップ 3 開始メッセージの構成**] で [**開始メッセージを再生する**] チェック ボックスをオンにして、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-404">If you want to configure a welcome message, under **Step 3 Configure a Welcome Message**, select the **Play a welcome message** check box, and then do one of the following:</span></span>

    - <span data-ttu-id="1a6c8-405">発信者用の音声に変換される開始メッセージをテキストとして入力するには、[**音声合成を使用する**] をクリックして、テキスト ボックスに開始メッセージを入力します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-405">To enter the welcome message as text that is converted to speech for callers, click **Use text-to-speech**, and then type the welcome message in the text box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1a6c8-p179">入力するテキストに HTML タグを含めないでください。HTML タグを含めると、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p179">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

    - <span data-ttu-id="1a6c8-p180">開始メッセージに Wave または Windows Media オーディオ ファイルの録音を使用するには、[**録音を選択する**] をクリックします。新しいオーディオ ファイルをアップロードする場合は、[**録音**] リンクをクリックしてください。新しいブラウザー ウィンドウで [**参照**] をクリックし、使用するオーディオ ファイルを選択して、[**開く**] をクリックします。[**アップロード**] をクリックしてオーディオ ファイルを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p180">To use a Wave or Windows Media Audio file recording for the welcome message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the audio file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1a6c8-412">ユーザーが指定したすべてのオーディオ ファイルは、特定の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-412">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="1a6c8-413">サポートされているファイル形式の詳細については、「[Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-413">For details about supported file formats, see [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span>

18. <span data-ttu-id="1a6c8-414">[**ステップ 4 営業時間の指定**] の [**タイム ゾーン**] ボックスで、ワークフローのタイム ゾーンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-414">Under **Step 4 Specify Your Business Hours**, in the **Your time zone** box, click the time zone of the workflow.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1a6c8-p182">このタイム ゾーンは、ワークフローの発信者とエージェントの所在地のタイム ゾーンです。これを使用して、始業時間と終業時間が計算されます。たとえば、北アメリカ東部標準時を使用するようにワークフローが構成されており、ワークフローで始業が午前 7:00、終業が午後 11:00 にスケジュールされている場合は、東部標準時の 7:00 と 23:00 がそれぞれ始業時刻と終業時刻になります (時間は 24 時間表記で入力する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p182">The time zone is the time zone where the callers and agents of the workflow reside. It is used to calculate the open and close hours. For example, if the workflow is configured to use the North American Eastern Time zone and the workflow is scheduled to open at 7:00 A.M. and close at 11:00 P.M., the open and close times are assumed to be 7:00 Eastern Time and 11:00 Eastern Time respectively. (You must enter the times in 24-hour time notation.)</span></span>

19. <span data-ttu-id="1a6c8-420">次のいずれかの操作を実行して、使用する営業時間スケジュールの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-420">Select the type of business hours schedule you want to use by doing one of the following:</span></span>

    - <span data-ttu-id="1a6c8-421">事前に定義した営業時間スケジュールを使用するには、[**プリセット スケジュールを使用する**] をクリックして、ドロップダウン リストから使用するスケジュールを選択します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-421">To use a predefined schedule of business hours, click **Use a preset schedule**, and then select the schedule you want to use from the drop-down list.</span></span>

      > [!NOTE]
      > <span data-ttu-id="1a6c8-422">このオプションを選択できるようにするには、あらかじめ少なくとも 1 つのプリセット スケジュールを定義しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-422">You must have defined at least one preset schedule previously to be able to select this option.</span></span> <span data-ttu-id="1a6c8-423">事前設定されたスケジュールを定義するには、 **CsRgsHoursOfBusiness**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-423">You define preset schedules by using the **New-CsRgsHoursOfBusiness** cmdlet.</span></span> <span data-ttu-id="1a6c8-424">詳細については、「(オプション)」を参照してください。 [Skype For business で応答グループの勤務時間を定義](optional-define-response-group-business-hours.md)します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-424">For details, see [(Optional) Define Response Group business hours in Skype for Business](optional-define-response-group-business-hours.md).</span></span> <span data-ttu-id="1a6c8-425">プリセット スケジュールを選択すると、応答グループの対応日時で、[**曜日**]、[**開始**]、[**終了**] が自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-425">When you select a preset schedule, **Day**, **Open**, and **Close** are automatically filled with the days and hours that the response group is available.</span></span>

    - <span data-ttu-id="1a6c8-426">このワークフローのみに適用するカスタム スケジュールを使用するには、[**カスタム スケジュールを使用する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-426">To use a custom schedule that applies only to this workflow, click **Use a custom schedule**.</span></span>

20. <span data-ttu-id="1a6c8-427">このワークフロー用のカスタム スケジュールを作成する場合は、応答グループが対応可能な曜日のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-427">If you are creating a custom schedule for this workflow, click the check boxes for the days of the week that the response group is available.</span></span>

21. <span data-ttu-id="1a6c8-428">ユーザー設定のスケジュールを作成する場合は、返信グループ\*\*\*\* が利用できるようになる**までの時間を入力します**。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-428">If you are creating a custom schedule, type the **Open** and **Close** hours when the response group will be available.</span></span>

     > [!NOTE]
     > <span data-ttu-id="1a6c8-p184">[**開始**] 時間と [**終了**] 時間は 24 時間表記で入力する必要があります。たとえば、職場の営業時間が営業日の 9 時から 5 時までで、昼休みのために正午にオフィスを一度閉める場合、営業時間は [**開始**] 9:00、[**終了**] 12:00、[**開始**] 13:00、[**終了**] 17:00 として指定します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p184">The **Open** and **Close** hours must be in 24-hour time notation. For example, if your office works a 9-to-5 work day and closes at noon for lunch, the business hours are specified as **Open** 9:00, **Close** 12:00, **Open** 13:00, and **Close** 17:00.</span></span>

22. <span data-ttu-id="1a6c8-431">営業時間外にメッセージを再生するには、[**応答グループの営業時間外にメッセージを再生する**] チェック ボックスをオンにしてから、次のいずれかの操作を実行して再生するメッセージを指定します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-431">If you want to play a message when the office is not open, select the **Play a message when the response group is outside of business hours** check box, and then specify the message to play by doing one of the following:</span></span>

    - <span data-ttu-id="1a6c8-432">発信者用に音声に変換されるメッセージをテキストとして入力するには、[**音声合成を使用する**] をクリックして、テキスト ボックスにメッセージを入力します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-432">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>

      > [!NOTE]
      > <span data-ttu-id="1a6c8-433">入力するテキストに HTML タグを含めないでください。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-433">Do not include HTML tags in the text you enter.</span></span> <span data-ttu-id="1a6c8-434">HTML タグを含めると、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-434">If you include HTML tags, you will receive an error message.</span></span>

    - <span data-ttu-id="1a6c8-p186">メッセージにオーディオ ファイルの録音を使用するには、[**録音を選択する**] をクリックします。新しいオーディオ ファイルをアップロードする場合は、[**録音**] リンクをクリックしてください。新しいブラウザー ウィンドウで [**参照**] をクリックし、使用するファイルを選択して、[**開く**] をクリックします。[**アップロード**] をクリックしてオーディオ ファイルを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p186">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1a6c8-439">ユーザーが指定したすべてのオーディオ ファイルは、特定の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-439">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="1a6c8-440">サポートされているファイル形式の詳細については、「[Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-440">For details about supported file formats, see [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span>

23. <span data-ttu-id="1a6c8-441">メッセージが構成されている場合は、メッセージ再生後の通話の処理方法を次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-441">Specify how to handle calls after the message is played (if a message is configured):</span></span>

    - <span data-ttu-id="1a6c8-442">通話を終了するには、[**終話**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-442">To disconnect the call, click **Disconnect Call**.</span></span>

    - <span data-ttu-id="1a6c8-443">通話をボイス メールに転送するには、[**ボイス メールに転送**] をクリックして、ボイス メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-443">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="1a6c8-444">ボイスメールのアドレスの形式は@ \* \<、ユーザー\>名\*\*\<domainname\> \* (例 bob@contoso.com) です。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-444">The format for the voice mail address is  *\<username\>*@*\<domainname\>* (for example, bob@contoso.com).</span></span>

    - <span data-ttu-id="1a6c8-445">通話を別のユーザーに転送するには、[**SIP URI に転送**] をクリックして、ユーザー アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-445">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="1a6c8-446">ユーザーアドレスの形式は@ _ \<、username\>__\<domainname\>_ です。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-446">The format for the user address is  _\<username\>_@_\<domainname\>_.</span></span>

    - <span data-ttu-id="1a6c8-447">通話を別の電話番号に転送するには、[**電話番号に転送**] をクリックして、電話番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-447">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="1a6c8-448">電話番号の形式は\* \<番号\>*@*\<domainname\> \* (+ 14255550121@contoso.com など) です。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-448">The format for the telephone number is  *\<number\>*@*\<domainname\>* (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="1a6c8-449">発信者は、ドメイン名を使用して適切な宛先にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-449">The domain name is used to route the caller to the correct destination.</span></span>

24. <span data-ttu-id="1a6c8-450">[**ステップ 5 休日の指定**] で、応答グループが営業しない日を定義する、1 つまたは複数の休日セットのチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-450">Under **Step 5 Specify Your Holidays**, click the check boxes for one or more sets of holidays that define the days when the response group is closed for business.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1a6c8-451">ワークフローを構成する前に、休日および休日セットを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-451">You need to define holidays and holiday sets before you configure the workflow.</span></span> <span data-ttu-id="1a6c8-452">休日および休日セットを定義するには、**New-CsRgsHoliday** コマンドレットおよび **New-CsRgsHolidaySet** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-452">Use the **New-CsRgsHoliday** and **New-CsRgsHolidaySet** cmdlets to define holidays and holiday sets.</span></span> <span data-ttu-id="1a6c8-453">詳細については、「 [(オプション) Skype For business で応答グループの休日セットを定義](optional-define-response-group-holiday-sets.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-453">For details, see [(Optional) Define Response Group holiday sets in Skype for Business](optional-define-response-group-holiday-sets.md).</span></span>

25. <span data-ttu-id="1a6c8-454">休日にメッセージを再生するには、[**休日にメッセージを再生する**] チェック ボックスをオンにしてから、次のいずれかの操作を実行して再生するメッセージを指定します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-454">If you want to play a message on holidays, select the **Play a message during holidays** check box, and then specify the message to play by doing one of the following:</span></span>

    - <span data-ttu-id="1a6c8-455">発信者用に音声に変換されるメッセージをテキストとして入力するには、[**音声合成を使用する**] をクリックして、テキスト ボックスにメッセージを入力します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-455">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>

      > [!NOTE]
      > <span data-ttu-id="1a6c8-456">入力するテキストに HTML タグを含めないでください。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-456">Do not include HTML tags in the text you enter.</span></span> <span data-ttu-id="1a6c8-457">HTML タグを含めると、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-457">If you include HTML tags, you will receive an error message.</span></span>

    - <span data-ttu-id="1a6c8-p193">メッセージにオーディオ ファイルの録音を使用するには、[**録音を選択する**] をクリックします。新しいオーディオ ファイルをアップロードする場合は、[**録音**] リンクをクリックしてください。新しいブラウザー ウィンドウで [**参照**] をクリックし、使用するファイルを選択して、[**開く**] をクリックします。[**アップロード**] をクリックしてオーディオ ファイルを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p193">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>

      > [!NOTE]
      > <span data-ttu-id="1a6c8-p194">ユーザーが指定したすべてのオーディオ ファイルは、特定の要件を満たしている必要があります。サポートされているオーディオ ファイル形式の詳細については、「[Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p194">All user-provided audio files must meet certain requirements. For details about supported audio file formats, see [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span>

26. <span data-ttu-id="1a6c8-464">メッセージが構成されている場合は、メッセージ再生後の通話の処理方法を次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-464">Specify how to handle calls after the message is played (if a message is configured):</span></span>

    - <span data-ttu-id="1a6c8-465">通話を終了するには、[**終話**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-465">To disconnect the call, click **Disconnect Call**.</span></span>

    - <span data-ttu-id="1a6c8-466">通話をボイス メールに転送するには、[**ボイス メールに転送**] をクリックして、ボイス メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-466">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="1a6c8-467">ボイスメールのアドレスの形式は@ \* \<、ユーザー\>名\*\*\<domainname\> \* (例 bob@contoso.com) です。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-467">The format for the voice mail address is  *\<username\>*@*\<domainname\>* (for example, bob@contoso.com).</span></span>

    - <span data-ttu-id="1a6c8-468">通話を別のユーザーに転送するには、[**SIP URI に転送**] をクリックして、ユーザー アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-468">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="1a6c8-469">ユーザーアドレスの形式は@ _ \<、username\>__\<domainname\>_ です。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-469">The format for the user address is  _\<username\>_@_\<domainname\>_.</span></span>

    - <span data-ttu-id="1a6c8-470">通話を別の電話番号に転送するには、[**電話番号に転送**] をクリックして、電話番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-470">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="1a6c8-471">電話番号の形式は\* \<番号\>*@*\<domainname\> \* (+ 14255550121@contoso.com など) です。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-471">The format for the telephone number is  *\<number\>*@*\<domainname\>* (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="1a6c8-472">発信者は、ドメイン名を使用して適切な宛先にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-472">The domain name is used to route the caller to the correct destination.</span></span>

27. <span data-ttu-id="1a6c8-473">[**ステップ 6 保留音の構成**] で、次のいずれかの操作を実行して、発信者がエージェントの応答を待機しているときの保留音を選択します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-473">Under **Step 6 Configure Music on Hold**, choose what you want callers to listen to while waiting for an agent by doing one of the following:</span></span>

    - <span data-ttu-id="1a6c8-474">既定の保留音の録音を使用するには、[**既定値を使用する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-474">To use the default music on-hold recording, click **Use default**.</span></span>

    - <span data-ttu-id="1a6c8-p198">保留音にオーディオ ファイルの録音を使用するには、[**音楽ファイルを選択する**] をクリックします。新しいオーディオ ファイルをアップロードする場合は、[**音楽ファイル**] リンクをクリックします。新しいブラウザー ウィンドウで [**参照**] をクリックし、使用するファイルを選択して、[**開く**] をクリックします。[**アップロード**] をクリックしてオーディオ ファイルを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p198">To use an audio file recording for the on-hold music, click **Select a music file**. If you want to upload a new audio file, click the **a music file** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1a6c8-p199">ユーザーが指定したすべてのオーディオ ファイルは、特定の要件を満たしている必要があります。サポートされているファイル形式の詳細については、「[Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p199">All user-provided audio files must meet certain requirements. For details about supported file formats, see [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span>

28. <span data-ttu-id="1a6c8-481">[**ステップ 7 対話型音声応答の構成**] の [**ユーザーには、次のテキストまたは録音メッセージを再生します**] という見出しの下で、次のように発信者に対する質問を指定します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-481">Under **Step 7 Configure Interactive Voice Response**, under the **The user will hear the following text or recorded message** heading, specify the question to ask callers as follows:</span></span>

    - <span data-ttu-id="1a6c8-482">質問をテキスト形式で入力するには、[**音声合成を使用する**] をクリックして、テキスト ボックスに質問を入力します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-482">To enter the question in text format, click **Use text-to-speech**, and type the question in the text box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1a6c8-p200">入力するテキストに HTML タグを含めないでください。HTML タグを含めると、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p200">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1a6c8-485">"#" 記号は、音声合成エンジンによって "番号" という語に変換されます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-485">The "#" symbol is translated by the text-to-speech engine as the word "number".</span></span> <span data-ttu-id="1a6c8-486"># キーを示す必要がある場合は、記号ではなく、キーの名前を質問に使用してください。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-486">If you need to refer to the # key, you should use the key name, rather than the symbol, in your prompt.</span></span> <span data-ttu-id="1a6c8-487">たとえば、「営業部門をご希望の場合は、シャープを押してください」とします。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-487">For example, "To talk to sales, press the pound key."</span></span>

    - <span data-ttu-id="1a6c8-488">質問を含む録音済みのオーディオ ファイルを使用する場合は、[**録音を選択する**] をクリックし、[**録音**] リンクをクリックしてファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-488">To use a prerecorded audio file that contains the question, click **Select a recording**, and then click the **a recording** link to upload the file.</span></span> <span data-ttu-id="1a6c8-489">新しいブラウザー ウィンドウで [**参照**] をクリックし、オーディオ ファイルを選択して、[**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-489">In the new browser window, click **Browse**, select the audio file, and then click **Open**.</span></span> <span data-ttu-id="1a6c8-490">[**アップロード**] をクリックしてファイルを読み込み、必要に応じてテキストボックスに質問を入力します (これにより、質問と発信者の返信が対応するエージェントに転送されます)。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-490">Click **Upload** to load the file, and then optionally you can type the question in the text box (this enables the question, and the caller's response, to be forwarded to the responding agent).</span></span>

      > [!NOTE]
      > <span data-ttu-id="1a6c8-p203">ユーザーが指定したすべてのオーディオ ファイルは、特定の要件を満たしている必要があります。サポートされているファイル形式の詳細については、「[Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p203">All user-provided audio files must meet certain requirements. For details about supported file formats, see [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span>

29. <span data-ttu-id="1a6c8-493">[**応答 1**] で次の操作を実行して、質問に対する 1 つ目の回答を指定します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-493">Under **Response 1**, specify the first possible answer to the question by doing the following:</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="1a6c8-p204">いずれの音声応答にも引用符 (") を使用しないでください。引用符は IVR が失敗する原因になります。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p204">Do not use quotation marks (") in any voice responses. Quotation marks cause the IVR to fail.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1a6c8-496">発信者が音声、英数字のキーパッド入力、または両方を使用して回答できるようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-496">You can choose to allow callers to answer using speech, alphanumeric keypad input, or both.</span></span>

    - <span data-ttu-id="1a6c8-497">発信者が音声で応答できるようにする場合は、[**音声応答の入力**] に応答を入力します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-497">If you want to allow the caller to respond using speech, enter the answer in **Enter a voice response**.</span></span>

    - <span data-ttu-id="1a6c8-498">発信者がキーパッドのキー入力で応答できるようにする場合は、[**数字**] で、目的のキーパッドの数字をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-498">If you want to allow the caller to respond by pressing a key on the keypad, in **Digit**, click the keypad digit.</span></span>

30. <span data-ttu-id="1a6c8-499">次のように、発信者をキューにルーティングするか、もう 1 つ質問するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-499">Specify whether to route the caller to a queue, or to ask another question as follows:</span></span>

    - <span data-ttu-id="1a6c8-500">発信者をキューにルーティングするには [**キューに送る**] をクリックし、[**キューの選択**] で、使用するキューをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-500">To route the caller to a queue, click **Send to a queue**, and in **Select a queue**, click the queue that you want to use.</span></span>

    - <span data-ttu-id="1a6c8-p205">もう 1 つ質問をするには、[**もう 1 つ質問する**] をクリックしてから、[**音声合成を使用する**] をクリックして質問を入力するか、[**録音を選択する**] をクリックします。このセクションにある応答グループを使用して、追加の質問に対する最大 4 つの応答と、各応答で使用するキューを指定します。3 番目または 4 番目の応答を指定するには、[**応答 3**] チェック ボックスまたは [**応答 4**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p205">To ask another question, click **Ask another question**, and then click **Use text-to-speech** and type the question, or click **Select a recording**. Use the response groupings in this section to specify up to four possible responses to the additional question and the queue to use for each response. To specify a third or fourth possible response, click the **Response 3** check box or the **Response 4** check box.</span></span>

31. <span data-ttu-id="1a6c8-p206">手順 28 と 29 を繰り返して応答と各応答に対するアクションを指定し、元の質問に対する回答を最大 3 つ追加します。3 番目または 4 番目の回答を指定するには、[**応答 3**] チェック ボックスまたは [**応答 4**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p206">Specify up to three more possible answers to the original question by repeating steps 28 and 29 to specify the possible responses and the action to take for each response. To specify a third or fourth possible answer, click the **Response 3** check box or the **Response 4** check box.</span></span>

32. <span data-ttu-id="1a6c8-506">[**展開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-506">Click **Deploy**.</span></span>

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-an-interactive-workflow"></a><span data-ttu-id="1a6c8-507">Skype for Business Server 管理シェルを使用して対話型ワークフローを作成または変更するには</span><span class="sxs-lookup"><span data-stu-id="1a6c8-507">To use Skype for Business Server Management Shell to create or modify an Interactive workflow</span></span>

1.  <span data-ttu-id="1a6c8-508">RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-508">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2. <span data-ttu-id="1a6c8-509">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-509">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="1a6c8-p207">応答グループ サービスのサービス名を取得し、変数に割り当てます。コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p207">Retrieve the service name for the Response Group service and assign it to a variable. At the command line, run:</span></span>

   ```powershell
   $serviceId = "service:" + (Get-CsService | ?{$_.Applications -like "*RGS*"}).ServiceId;
   ```

4. <span data-ttu-id="1a6c8-p208">対話ワークフローには、2 つ以上のキューと 2 つ以上のエージェント グループが必要です。まず、エージェント グループを作成します。次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p208">An interactive workflow requires two or more queues and two or more agent groups. First, create the agent groups. Run:</span></span>

   ```powershell
   $AGSupport = New-CsRgsAgentGroup -Parent $serviceId -Name "Technical Support" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:agent1@contoso.com", "sip:agent2@contoso.com")]
   $AGSales = New-CsRgsAgentGroup -Parent $serviceId -Name "Sales Team" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:bob@contoso.com", "sip:alice@contoso.com")]
   ```

5. <span data-ttu-id="1a6c8-p209">キューを作成します。次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p209">Create the queues. Run:</span></span>

   ```powershell
   $QSupport = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Support" -AgentGroupIDList($AG-Support.Identity)
   $QSales = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Sales" -AgentGroupIDList($AG-Sales.Identity)
   ```

6. <span data-ttu-id="1a6c8-p210">応答グループ プロンプトを作成します。次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p210">Create the first response group prompt. Run:</span></span>

   ```powershell
   $SupportPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please be patient while we connect you with Contoso Technical Support."
   ```

7. <span data-ttu-id="1a6c8-p211">次に、プロンプトの後に実行するアクションを作成します。次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p211">Then create the action to be performed after the prompt. Run:</span></span>

   ```powershell
   $SupportAction = New-CsRgsCallAction -Prompt $SupportPrompt -Action TransferToQueue -QueueID $QSupport.Identity
   ```

8. <span data-ttu-id="1a6c8-p212">最初の応答グループ回答を作成します。次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p212">Create the first response group answer. Run:</span></span>

   ```powershell
   $SupportAnswer = New-CsRgsAnswer -Action $SupportAction [-DtmfResponse 1]
   ```

9. <span data-ttu-id="1a6c8-p213">2 番目のプロンプト、通話アクション、および回答を作成します。まず、プロンプトを作成します。次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p213">Now create the second prompt, call action, and answer. First create the prompt. Run:</span></span>

   ```powershell
   $SalesPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please hold while we connect you with Contoso Sales."
   ```

10. <span data-ttu-id="1a6c8-p214">2 番目の通話アクションを作成します。次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p214">Create the second call action. Run:</span></span>

    ```powershell
    $SalesAction = New-CsRgsCallAction -Prompt $SalesPrompt -Action TransferToQueue -QueueID $QSales.Identity
    ```

11. <span data-ttu-id="1a6c8-p215">2 番目の応答グループ回答を作成します。次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p215">Create the second response group answer. Run:</span></span>

    ```powershell
    $SalesAnswer = New-CsRgsAnswer -Action $SalesAction [-DtmfResponse 2]
    ```

12. <span data-ttu-id="1a6c8-p216">最上位のプロンプトを作成します。次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p216">Create the top-level prompt. Run:</span></span>

    ```powershell
    $TopLevelPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Thank you for calling Contoso. For Technical Support, press 1. For a Sales Representative, press 2."
    ```

13. <span data-ttu-id="1a6c8-p217">最上位の質問を作成します。次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p217">Create the top-level question. Run:</span></span>

    ```powershell
    $TopLevelQuestion = New-CsRgsQuestion -Prompt $TopLevelPrompt [-AnswerList ($SupportAnswer, $SalesAnswer)]
    ```

14. <span data-ttu-id="1a6c8-p218">ここで、ワークフローを作成します。次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-p218">Now create the workflow. Run:</span></span>

    ```powershell
    $IVRAction = New-CsRgsCallAction -Action TransferToQuestion [-Question $Question]
    $IVRWorkflow = New-CsRgsWorkflow -Parent $ServiceId -Name "Contoso Helpdesk" [-Description "The Contoso Helpdesk line."] -PrimaryUri "sip:helpdesk@contoso.com" [-LineUri tel:+14255554321] [-DisplayNumber "+1 (425) 555-4321"] [-Active $true] [-Anonymous $true] [-DefaultAction $IVRAction] [-Managed $true] [-ManagersByURI ("sip:mindy@contoso.com", "sip:bob@contoso.com")]
    ```

     > [!NOTE]
     > <span data-ttu-id="1a6c8-536">応答グループの管理者として指定されているすべてのユーザーに、CsResponseGroupManager の役割を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-536">All users who have been designated as manager of a response group must be assigned the CsResponseGroupManager role.</span></span> <span data-ttu-id="1a6c8-537">このロールが割り当てられていない場合、ユーザーは応答グループを管理できません。</span><span class="sxs-lookup"><span data-stu-id="1a6c8-537">If users are not assigned this role, they cannot manage response groups.</span></span>

## <a name="see-also"></a><span data-ttu-id="1a6c8-538">関連項目</span><span class="sxs-lookup"><span data-stu-id="1a6c8-538">See also</span></span>

[<span data-ttu-id="1a6c8-539">省略Skype for Business で応答グループの休日セットを定義する</span><span class="sxs-lookup"><span data-stu-id="1a6c8-539">(Optional) Define Response Group holiday sets in Skype for Business</span></span>](optional-define-response-group-holiday-sets.md)

[<span data-ttu-id="1a6c8-540">省略Skype for Business で応答グループの勤務時間を定義する</span><span class="sxs-lookup"><span data-stu-id="1a6c8-540">(Optional) Define Response Group business hours in Skype for Business</span></span>](optional-define-response-group-business-hours.md)

[<span data-ttu-id="1a6c8-541">New-CsRgsWorkflow</span><span class="sxs-lookup"><span data-stu-id="1a6c8-541">New-CsRgsWorkflow</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsworkflow?view=skype-ps)

[<span data-ttu-id="1a6c8-542">Set-CsRgsWorkflow</span><span class="sxs-lookup"><span data-stu-id="1a6c8-542">Set-CsRgsWorkflow</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csrgsworkflow?view=skype-ps)

[<span data-ttu-id="1a6c8-543">New-CsRgsPrompt</span><span class="sxs-lookup"><span data-stu-id="1a6c8-543">New-CsRgsPrompt</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps)

[<span data-ttu-id="1a6c8-544">New-CsRgsCallAction</span><span class="sxs-lookup"><span data-stu-id="1a6c8-544">New-CsRgsCallAction</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)

