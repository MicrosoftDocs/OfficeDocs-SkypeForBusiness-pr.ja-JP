---
title: 'Lync Server 2013: キューを作成または変更する'
description: 'Lync Server 2013: キューを作成または変更します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a queue
ms:assetid: b9d6366a-839f-4651-a01d-9254546cadeb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205207(v=OCS.15)
ms:contentKeyID: 48185247
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cbd8d6d00df8d6a09ef5861d876bd1363db09e3d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574533"
---
# <a name="create-or-modify-a-queue-in-lync-server-2013"></a><span data-ttu-id="7e955-103">Lync Server 2013 でキューを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="7e955-103">Create or modify a queue in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e955-104">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="7e955-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="7e955-105">キューを作成または変更するには、以下のいずれかの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="7e955-105">Use one of the following procedures to create or modify a queue.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-a-queue"></a><span data-ttu-id="7e955-106">Lync Server コントロールパネルを使用してキューを作成または変更するには</span><span class="sxs-lookup"><span data-stu-id="7e955-106">To use Lync Server Control Panel to create or modify a queue</span></span>

1.  <span data-ttu-id="7e955-107">RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="7e955-107">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7e955-108">管理ワークフローを委任された応答グループ マネージャーのいずれかである場合は、応答グループ キューを作成または変更して、管理するワークグループに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="7e955-108">If you are one of the delegated Response Group Managers for a managed workflow, you can create or modify response group queues and assign them to the workflows that you manage.</span></span>

    
    </div>

2.  <span data-ttu-id="7e955-109">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="7e955-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7e955-110">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e955-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7e955-111">左側のナビゲーション バーで [**応答グループ**] をクリックし、[**キュー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e955-111">In the left navigation bar, click **Response Groups**, and then click **Queue**.</span></span>

4.  <span data-ttu-id="7e955-112">[**キュー**] ページで、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="7e955-112">On the **Queue** page, do one of the following:</span></span>
    
      - <span data-ttu-id="7e955-113">新しいキューを作成するには、[**新規作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e955-113">To create a new queue, click **New**.</span></span> <span data-ttu-id="7e955-114">[**サービスの選択**] の検索フィールドに、キューを追加する **ApplicationServer** サービスの名前の一部またはすべてを入力します。</span><span class="sxs-lookup"><span data-stu-id="7e955-114">In **Select a Service**, type part or all of the name of the **ApplicationServer** service where you want to add the queue in the search field.</span></span> <span data-ttu-id="7e955-115">表示されたサービスの一覧で、目的のサービスをクリックし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e955-115">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="7e955-p103">既存のキューを変更するには、キューの名前または名前の一部を検索フィールドに入力します。結果のキューの一覧で、対象のキューをクリックし、[**編集**]、[**詳細の表示**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e955-p103">To modify an existing queue, type all or part of the queue name in the search field. In the resulting list of queues, click the queue that you want, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="7e955-118">[**名前**] にキューの識別名を入力します。</span><span class="sxs-lookup"><span data-stu-id="7e955-118">In **Name**, type an identifying name for the queue.</span></span>

6.  <span data-ttu-id="7e955-119">[**説明**] に、キューの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="7e955-119">In **Description**, type a description for the queue.</span></span>

7.  <span data-ttu-id="7e955-p104">[**グループ**] で、キューに割り当てるグループを指定します。次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="7e955-p104">In **Groups**, specify the groups you want to assign to the queue. Do one of the following:</span></span>
    
      - <span data-ttu-id="7e955-122">キューにグループを追加するには、[ **選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e955-122">To add a group to the queue, click **Select**.</span></span> <span data-ttu-id="7e955-123">**[グループの選択**] 検索フィールドに、キューに割り当てるエージェントグループの名前または名前の一部を入力し、目的のエージェントグループをクリックして、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e955-123">In the **Select Groups** search field, type all or part of the name of the agent group that you want to assign to the queue, click the agent group that you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="7e955-124">キューからグループを削除するには、エージェント グループの一覧で、削除するグループをクリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e955-124">To remove a group from the queue, in the list of agent groups, click the group that you want to remove, and then click **Remove**.</span></span>
    
      - <span data-ttu-id="7e955-125">エージェントを検索する順序を変更するには、エージェント グループの一覧でグループをクリックし、上矢印または下矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e955-125">To change the order in which agents are searched, in the list of agent groups, click a group, and then click the up arrow or down arrow.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="7e955-p106">サーバーでは、キューで利用可能なエージェントを検索するときには、グループの順序が使用されます。つまり、一覧の最初のグループが最初に検索され、一覧の 2 番目のグループが次に検索され、以降も同様に検索されます。</span><span class="sxs-lookup"><span data-stu-id="7e955-p106">When the server searches for an available agent for the queue, it uses group order. That is, the first group in the list is searched first, followed by the second group in the list, and so on.</span></span>

        
        </div>

8.  <span data-ttu-id="7e955-128">エージェントが通話に応答するまで発信者を保留状態にする最長時間を指定するには、[**キューのタイムアウトを有効にする**] チェック ボックスをオンにして次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="7e955-128">To specify a maximum period of time for a caller to wait on hold before an agent answers the call, select the **Enable queue time-out** check box, and then do the following:</span></span>
    
    1.  <span data-ttu-id="7e955-129">[**タイムアウト時間 (秒)**] で、エージェントが通話に応答するのを発信者が待つ最大秒数を指定します。</span><span class="sxs-lookup"><span data-stu-id="7e955-129">In **Time-out period (seconds)**, specify the maximum number of seconds a caller waits for an agent to answer the call.</span></span>
    
    2.  <span data-ttu-id="7e955-130">[**通話アクション**] で、呼び出しがタイムアウトになったときに行う動作を次のように選択します。</span><span class="sxs-lookup"><span data-stu-id="7e955-130">In **Call Action**, select the action that occurs when a call times out as follows:</span></span>
    
    <!-- end list -->
    
      - <span data-ttu-id="7e955-131">タイムアウト後通話を終了するには、[**切断**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e955-131">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
      - <span data-ttu-id="7e955-132">通話をボイスメールに転送するには、[**ボイスメールに転送**] をクリックし、[ **sip アドレス**] フィールドに、sip: \<username\> @ (たとえば、sip:bob@contoso.com) の形式でボイスメールアドレスを入力し \<domainname\> ます。</span><span class="sxs-lookup"><span data-stu-id="7e955-132">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip:\<username\>@\<domainname\> (for example, sip:bob@contoso.com).</span></span>
    
      - <span data-ttu-id="7e955-133">別の電話番号に通話を転送するには、[**電話番号に転送**] をクリックし、[ **sip アドレス**] フィールドに電話番号を sip: \<number\> @ (たとえば、sip:+14255550121@contoso.com) の形式で入力し \<domainname\> ます。</span><span class="sxs-lookup"><span data-stu-id="7e955-133">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip:\<number\>@\<domainname\> (for example, sip:+14255550121@contoso.com).</span></span>
    
      - <span data-ttu-id="7e955-134">別のユーザーに通話を転送するには、[ **sip アドレスに転送**] をクリックし、[ **sip アドレス**] フィールドに、ユーザーの URI を sip: の形式で入力し \<username\> @ \<domainname\> ます。</span><span class="sxs-lookup"><span data-stu-id="7e955-134">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip:\<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="7e955-135">別のキューに通話を転送する場合は [**別のキューに転送**] をクリックし、使用するキューを参照します。</span><span class="sxs-lookup"><span data-stu-id="7e955-135">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>

9.  <span data-ttu-id="7e955-136">キューに保持できる最大通話数を指定するには、[**キューのオーバーフローを有効にする**] チェック ボックスをオンにして次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="7e955-136">To specify a maximum number of calls that the queue can hold, select the **Enable queue overflow** check box, and then do the following:</span></span>
    
    1.  <span data-ttu-id="7e955-137">[**最大通話数**] で、キューで保持する最大通話数を選択します。</span><span class="sxs-lookup"><span data-stu-id="7e955-137">In **Maximum number of calls**, select the maximum number of calls that you want the queue to hold.</span></span>
    
    2.  <span data-ttu-id="7e955-138">[**通話の転送**] で、キューが一杯になったときに転送する通話を、[**最新の通話**] または [**最も古い通話**] から選択します。</span><span class="sxs-lookup"><span data-stu-id="7e955-138">In **Forward the call**, select which call is to be forwarded when the queue is full: **Newest Call** or **Oldest Call**.</span></span>
    
    3.  <span data-ttu-id="7e955-139">[**通話アクション**] で、オーバーフローしきい値に達したときに実行する処理を、次のように選択します。</span><span class="sxs-lookup"><span data-stu-id="7e955-139">In **Call action**, select the action that occurs when the overflow threshold is met as follows:</span></span>
    
    <!-- end list -->
    
      - <span data-ttu-id="7e955-140">タイムアウト後通話を終了するには、[**切断**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e955-140">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
      - <span data-ttu-id="7e955-141">通話をボイスメールに転送するには、[**ボイスメールに転送**] をクリックし、[ **sip アドレス**] フィールドに、sip: \<username\> @ (たとえば、sip:bob@contoso.com) の形式でボイスメールアドレスを入力し \<domainname\> ます。</span><span class="sxs-lookup"><span data-stu-id="7e955-141">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip:\<username\>@\<domainname\> (for example, sip:bob@contoso.com).</span></span>
    
      - <span data-ttu-id="7e955-142">別の電話番号に通話を転送するには、[**電話番号に転送**] をクリックし、[ **sip アドレス**] フィールドに電話番号を sip: \<number\> @ (たとえば、sip:+14255550121@contoso.com) の形式で入力し \<domainname\> ます。</span><span class="sxs-lookup"><span data-stu-id="7e955-142">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip:\<number\>@\<domainname\> (for example, sip:+14255550121@contoso.com).</span></span>
    
      - <span data-ttu-id="7e955-143">別のユーザーに通話を転送するには、[ **sip アドレスに転送**] をクリックし、[ **sip アドレス**] フィールドに、ユーザーの URI を sip: の形式で入力し \<username\> @ \<domainname\> ます。</span><span class="sxs-lookup"><span data-stu-id="7e955-143">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip:\<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="7e955-144">別のキューに通話を転送する場合は [**別のキューに転送**] をクリックし、使用するキューを参照します。</span><span class="sxs-lookup"><span data-stu-id="7e955-144">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>

10. <span data-ttu-id="7e955-145">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e955-145">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-queue"></a><span data-ttu-id="7e955-146">Windows PowerShell を使用してキューを作成または変更するには</span><span class="sxs-lookup"><span data-stu-id="7e955-146">To use Windows PowerShell to create or modify a queue</span></span>

1.  <span data-ttu-id="7e955-147">RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="7e955-147">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7e955-148">管理ワークフローを委任された応答グループ マネージャーのいずれかである場合は、エージェント グループおよびキューを作成して、エージェント グループをキューに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="7e955-148">If you are one of the delegated Response Group Managers for a managed workflow, you will be able to create agent groups and queues, and assign agent groups to queues.</span></span>

    
    </div>

2.  <span data-ttu-id="7e955-149">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e955-149">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="7e955-p107">キューのタイムアウトしきい値に達したときに再生されるプロンプトを作成し、変数に格納します。コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7e955-p107">Create the prompt to be played when the queue timeout threshold is met, and save it in a variable. At the command line, run:</span></span>
    
        $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    <span data-ttu-id="7e955-152">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="7e955-152">For example:</span></span>
    
        "All agents are currently busy. Please call back later."
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7e955-153">プロンプトにオーディオ ファイルを使用するには、<STRONG>Import-CsRgsAudioFile</STRONG> コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="7e955-153">To use an audio file for the prompt, use the <STRONG>Import-CsRgsAudioFile</STRONG> cmdlet.</span></span> <span data-ttu-id="7e955-154">詳細については、「 <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">import-csrgsaudiofile</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e955-154">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="7e955-p109">キューのタイムアウトしきい値に達したときに実行されるアクションを定義し、変数に格納します。コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7e955-p109">Define the action to be taken when the queue timeout threshold is met, and save it in a variable. At the command line, run:</span></span>
    
        $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7e955-157">使用可能なアクションとその構文の詳細については、「 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e955-157">For details about possible actions and their syntax, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="7e955-158">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="7e955-158">For example:</span></span>
    
        $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate

5.  <span data-ttu-id="7e955-p110">キューのオーバーフローしきい値に達したときに再生されるプロンプトを作成し、変数に格納します。コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7e955-p110">Create the prompt to be played when the queue overflow threshold is met, and save it in a variable. At the command line, run:</span></span>
    
        $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    <span data-ttu-id="7e955-161">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="7e955-161">For example:</span></span>
    
        $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7e955-162">プロンプトにオーディオ ファイルを使用するには、<STRONG>Import-CsRgsAudioFile</STRONG> コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="7e955-162">To use an audio file for the prompt, use the <STRONG>Import-CsRgsAudioFile</STRONG> cmdlet.</span></span> <span data-ttu-id="7e955-163">詳細については、「 <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">import-csrgsaudiofile</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e955-163">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span></span>

    
    </div>

6.  <span data-ttu-id="7e955-p112">キューのオーバーフローしきい値に達したときに実行されるアクションを定義し、変数に格納します。コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7e955-p112">Define the action to be taken when the queue overflow threshold is met, and save it in a variable. At the command line, run:</span></span>
    
        $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7e955-166">使用可能なアクションとその構文の詳細については、「 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e955-166">For details about possible actions and their syntax, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="7e955-167">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="7e955-167">For example:</span></span>
    
        $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate

7.  <span data-ttu-id="7e955-168">応答グループ サービスのサービス名を取得して変数に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="7e955-168">Retrieve the service name for the Response Group service and assign it to a variable.</span></span> <span data-ttu-id="7e955-169">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7e955-169">At the command line, run:</span></span>
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;

8.  <span data-ttu-id="7e955-170">キューに割り当てるエージェント グループの Identity を取得します。</span><span class="sxs-lookup"><span data-stu-id="7e955-170">Get the identity of the agent group to be assigned to the queue.</span></span> <span data-ttu-id="7e955-171">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7e955-171">At the command line, run:</span></span>
    
        $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7e955-172">エージェントグループの作成の詳細については、「 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup">New-CsRgsAgentGroup</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e955-172">For details about creating the agent group, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup">New-CsRgsAgentGroup</A></span></span>

    
    </div>

9.  <span data-ttu-id="7e955-p115">キューを作成します。コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7e955-p115">Create the queue. At the command line, run:</span></span>
    
        $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
    
    <span data-ttu-id="7e955-175">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="7e955-175">For example:</span></span>
    
        $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;

10. <span data-ttu-id="7e955-p116">キューが作成されたことを確認します。次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="7e955-p116">Confirm that the queue is created. Run:</span></span>
    
        Get-CsRgsQueue -Name "Help Desk"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7e955-178">関連項目</span><span class="sxs-lookup"><span data-stu-id="7e955-178">See Also</span></span>


[<span data-ttu-id="7e955-179">New-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="7e955-179">New-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue)  
[<span data-ttu-id="7e955-180">Set-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="7e955-180">Set-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsQueue)  
[<span data-ttu-id="7e955-181">New-CsRgsPrompt</span><span class="sxs-lookup"><span data-stu-id="7e955-181">New-CsRgsPrompt</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt)  
[<span data-ttu-id="7e955-182">New-CsRgsCallAction</span><span class="sxs-lookup"><span data-stu-id="7e955-182">New-CsRgsCallAction</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction)  
[<span data-ttu-id="7e955-183">Get-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="7e955-183">Get-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsQueue)  
[<span data-ttu-id="7e955-184">Import-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="7e955-184">Import-CsRgsAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile)  
[<span data-ttu-id="7e955-185">Remove-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="7e955-185">Remove-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsRgsQueue)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

