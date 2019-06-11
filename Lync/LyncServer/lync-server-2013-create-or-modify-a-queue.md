---
title: 'Lync Server 2013: キューを作成または変更する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a queue
ms:assetid: b9d6366a-839f-4651-a01d-9254546cadeb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205207(v=OCS.15)
ms:contentKeyID: 48185247
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96b6bc1e5f956b5b975e14f07a3c37f2802d1b39
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833792"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-queue-in-lync-server-2013"></a><span data-ttu-id="939cc-102">Lync Server 2013 でキューを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="939cc-102">Create or modify a queue in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="939cc-103">_**最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="939cc-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="939cc-104">キューを作成または変更するには、以下のいずれかの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="939cc-104">Use one of the following procedures to create or modify a queue.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-a-queue"></a><span data-ttu-id="939cc-105">Lync Server コントロールパネルを使用してキューを作成または変更するには</span><span class="sxs-lookup"><span data-stu-id="939cc-105">To use Lync Server Control Panel to create or modify a queue</span></span>

1.  <span data-ttu-id="939cc-106">RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="939cc-106">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="939cc-107">管理ワークフローを委任された応答グループ マネージャーのいずれかである場合は、応答グループ キューを作成または変更して、管理するワークグループに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="939cc-107">If you are one of the delegated Response Group Managers for a managed workflow, you can create or modify response group queues and assign them to the workflows that you manage.</span></span>

    
    </div>

2.  <span data-ttu-id="939cc-108">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="939cc-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="939cc-109">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="939cc-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="939cc-110">左側のナビゲーション バーで [**応答グループ**] をクリックし、[**キュー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="939cc-110">In the left navigation bar, click **Response Groups**, and then click **Queue**.</span></span>

4.  <span data-ttu-id="939cc-111">[**キュー**] ページで、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="939cc-111">On the **Queue** page, do one of the following:</span></span>
    
      - <span data-ttu-id="939cc-112">新しいキューを作成するには、[**新規作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="939cc-112">To create a new queue, click **New**.</span></span> <span data-ttu-id="939cc-113">[**サービスの選択**] の検索フィールドに、キューを追加する **ApplicationServer** サービスの名前の一部またはすべてを入力します。</span><span class="sxs-lookup"><span data-stu-id="939cc-113">In **Select a Service**, type part or all of the name of the **ApplicationServer** service where you want to add the queue in the search field.</span></span> <span data-ttu-id="939cc-114">表示されたサービスの一覧で、目的のサービスをクリックし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="939cc-114">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="939cc-p103">既存のキューを変更するには、キューの名前または名前の一部を検索フィールドに入力します。結果のキューの一覧で、対象のキューをクリックし、[**編集**]、[**詳細の表示**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="939cc-p103">To modify an existing queue, type all or part of the queue name in the search field. In the resulting list of queues, click the queue that you want, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="939cc-117">[**名前**] にキューの識別名を入力します。</span><span class="sxs-lookup"><span data-stu-id="939cc-117">In **Name**, type an identifying name for the queue.</span></span>

6.  <span data-ttu-id="939cc-118">[**説明**] に、キューの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="939cc-118">In **Description**, type a description for the queue.</span></span>

7.  <span data-ttu-id="939cc-p104">[**グループ**] で、キューに割り当てるグループを指定します。次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="939cc-p104">In **Groups**, specify the groups you want to assign to the queue. Do one of the following:</span></span>
    
      - <span data-ttu-id="939cc-p105">キューにグループを追加するには、[**選択**] をクリックします。[**グループの選択**] の検索フィールドに、キューに割り当てるエージェント グループの名前または名前の一部を入力し、一覧で目的のエージェント グループをクリックして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="939cc-p105">To add a group to the queue, click **Select**. In the **Select Groups** search field, type all or part of the name of the agent group that you want to assign to the queue, click the agent group that you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="939cc-123">キューからグループを削除するには、エージェント グループの一覧で、削除するグループをクリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="939cc-123">To remove a group from the queue, in the list of agent groups, click the group that you want to remove, and then click **Remove**.</span></span>
    
      - <span data-ttu-id="939cc-124">エージェントを検索する順序を変更するには、エージェント グループの一覧でグループをクリックし、上矢印または下矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="939cc-124">To change the order in which agents are searched, in the list of agent groups, click a group, and then click the up arrow or down arrow.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="939cc-p106">サーバーでは、キューで利用可能なエージェントを検索するときには、グループの順序が使用されます。つまり、一覧の最初のグループが最初に検索され、一覧の 2 番目のグループが次に検索され、以降も同様に検索されます。</span><span class="sxs-lookup"><span data-stu-id="939cc-p106">When the server searches for an available agent for the queue, it uses group order. That is, the first group in the list is searched first, followed by the second group in the list, and so on.</span></span>

        
        </div>

8.  <span data-ttu-id="939cc-127">エージェントが通話に応答するまで発信者を保留状態にする最長時間を指定するには、[**キューのタイムアウトを有効にする**] チェック ボックスをオンにして次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="939cc-127">To specify a maximum period of time for a caller to wait on hold before an agent answers the call, select the **Enable queue time-out** check box, and then do the following:</span></span>
    
    1.  <span data-ttu-id="939cc-128">[**タイムアウト時間 (秒)**] で、エージェントが通話に応答するのを発信者が待つ最大秒数を指定します。</span><span class="sxs-lookup"><span data-stu-id="939cc-128">In **Time-out period (seconds)**, specify the maximum number of seconds a caller waits for an agent to answer the call.</span></span>
    
    2.  <span data-ttu-id="939cc-129">[**通話アクション**] で、呼び出しがタイムアウトになったときに行う動作を次のように選択します。</span><span class="sxs-lookup"><span data-stu-id="939cc-129">In **Call Action**, select the action that occurs when a call times out as follows:</span></span>
    
    <!-- end list -->
    
      - <span data-ttu-id="939cc-130">タイムアウト後通話を終了するには、[**切断**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="939cc-130">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
      - <span data-ttu-id="939cc-131">通話をボイスメールに転送するには、[**ボイスメールに転送**] をクリックし、[ **sip アドレス**\<] フィールドに、「sip: username\>@\<domainname\> (sip:)」という形式でボイスメールアドレスを入力します (たとえば、sip:bob@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="939cc-131">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip:\<username\>@\<domainname\> (for example, sip:bob@contoso.com).</span></span>
    
      - <span data-ttu-id="939cc-132">別の電話番号に通話を転送するには、[**電話番号に転送**] をクリックして、[ **sip アドレス**] フィールドに電話番号を\<「\>@\<sip\> : 番号のドメイン名」という形式で入力します (例 sip:+14255550121@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="939cc-132">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip:\<number\>@\<domainname\> (for example, sip:+14255550121@contoso.com).</span></span>
    
      - <span data-ttu-id="939cc-133">通話を別のユーザーに転送するには、[ **sip アドレスに転送**] をクリックし、[ **sip アドレス**] フィールドにユーザーの URI を「sip\<:\>@\<username\>domainname」という形式で入力します。</span><span class="sxs-lookup"><span data-stu-id="939cc-133">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip:\<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="939cc-134">別のキューに通話を転送する場合は [**別のキューに転送**] をクリックし、使用するキューを参照します。</span><span class="sxs-lookup"><span data-stu-id="939cc-134">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>

9.  <span data-ttu-id="939cc-135">キューに保持できる最大通話数を指定するには、[**キューのオーバーフローを有効にする**] チェック ボックスをオンにして次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="939cc-135">To specify a maximum number of calls that the queue can hold, select the **Enable queue overflow** check box, and then do the following:</span></span>
    
    1.  <span data-ttu-id="939cc-136">[**最大通話数**] で、キューで保持する最大通話数を選択します。</span><span class="sxs-lookup"><span data-stu-id="939cc-136">In **Maximum number of calls**, select the maximum number of calls that you want the queue to hold.</span></span>
    
    2.  <span data-ttu-id="939cc-137">[**通話の転送**] で、キューが一杯になったときに転送する通話を、[**最新の通話**] または [**最も古い通話**] から選択します。</span><span class="sxs-lookup"><span data-stu-id="939cc-137">In **Forward the call**, select which call is to be forwarded when the queue is full: **Newest Call** or **Oldest Call**.</span></span>
    
    3.  <span data-ttu-id="939cc-138">[**通話アクション**] で、オーバーフローしきい値に達したときに実行する処理を、次のように選択します。</span><span class="sxs-lookup"><span data-stu-id="939cc-138">In **Call action**, select the action that occurs when the overflow threshold is met as follows:</span></span>
    
    <!-- end list -->
    
      - <span data-ttu-id="939cc-139">タイムアウト後通話を終了するには、[**切断**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="939cc-139">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
      - <span data-ttu-id="939cc-140">通話をボイスメールに転送するには、[**ボイスメールに転送**] をクリックし、[ **sip アドレス**\<] フィールドに、「sip: username\>@\<domainname\> (sip:)」という形式でボイスメールアドレスを入力します (たとえば、sip:bob@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="939cc-140">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip:\<username\>@\<domainname\> (for example, sip:bob@contoso.com).</span></span>
    
      - <span data-ttu-id="939cc-141">別の電話番号に通話を転送するには、[**電話番号に転送**] をクリックして、[ **sip アドレス**] フィールドに電話番号を\<「\>@\<sip\> : 番号のドメイン名」という形式で入力します (例 sip:+14255550121@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="939cc-141">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip:\<number\>@\<domainname\> (for example, sip:+14255550121@contoso.com).</span></span>
    
      - <span data-ttu-id="939cc-142">通話を別のユーザーに転送するには、[ **sip アドレスに転送**] をクリックし、[ **sip アドレス**] フィールドにユーザーの URI を「sip\<:\>@\<username\>domainname」という形式で入力します。</span><span class="sxs-lookup"><span data-stu-id="939cc-142">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip:\<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="939cc-143">別のキューに通話を転送する場合は [**別のキューに転送**] をクリックし、使用するキューを参照します。</span><span class="sxs-lookup"><span data-stu-id="939cc-143">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>

10. <span data-ttu-id="939cc-144">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="939cc-144">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-queue"></a><span data-ttu-id="939cc-145">Windows PowerShell を使用してキューを作成または変更するには</span><span class="sxs-lookup"><span data-stu-id="939cc-145">To use Windows PowerShell to create or modify a queue</span></span>

1.  <span data-ttu-id="939cc-146">RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="939cc-146">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="939cc-147">管理ワークフローを委任された応答グループ マネージャーのいずれかである場合は、エージェント グループおよびキューを作成して、エージェント グループをキューに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="939cc-147">If you are one of the delegated Response Group Managers for a managed workflow, you will be able to create agent groups and queues, and assign agent groups to queues.</span></span>

    
    </div>

2.  <span data-ttu-id="939cc-148">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="939cc-148">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="939cc-p107">キューのタイムアウトしきい値に達したときに再生されるプロンプトを作成し、変数に格納します。コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="939cc-p107">Create the prompt to be played when the queue timeout threshold is met, and save it in a variable. At the command line, run:</span></span>
    
        $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    <span data-ttu-id="939cc-151">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="939cc-151">For example:</span></span>
    
        "All agents are currently busy. Please call back later."
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="939cc-152">プロンプトにオーディオ ファイルを使用するには、 <STRONG>Import-CsRgsAudioFile</STRONG> コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="939cc-152">To use an audio file for the prompt, use the <STRONG>Import-CsRgsAudioFile</STRONG> cmdlet.</span></span> <span data-ttu-id="939cc-153">詳細については、「<A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">インポート-CsRgsAudioFile</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="939cc-153">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="939cc-p109">キューのタイムアウトしきい値に達したときに実行されるアクションを定義し、変数に格納します。コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="939cc-p109">Define the action to be taken when the queue timeout threshold is met, and save it in a variable. At the command line, run:</span></span>
    
        $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="939cc-156">可能なアクションとその構文の詳細については、「<A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">新しい-CsRgsCallAction</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="939cc-156">For details about possible actions and their syntax, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="939cc-157">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="939cc-157">For example:</span></span>
    
        $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate

5.  <span data-ttu-id="939cc-p110">キューのオーバーフローしきい値に達したときに再生されるプロンプトを作成し、変数に格納します。コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="939cc-p110">Create the prompt to be played when the queue overflow threshold is met, and save it in a variable. At the command line, run:</span></span>
    
        $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    <span data-ttu-id="939cc-160">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="939cc-160">For example:</span></span>
    
        $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="939cc-161">プロンプトにオーディオ ファイルを使用するには、 <STRONG>Import-CsRgsAudioFile</STRONG> コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="939cc-161">To use an audio file for the prompt, use the <STRONG>Import-CsRgsAudioFile</STRONG> cmdlet.</span></span> <span data-ttu-id="939cc-162">詳細については、「<A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">インポート-CsRgsAudioFile</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="939cc-162">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span></span>

    
    </div>

6.  <span data-ttu-id="939cc-p112">キューのオーバーフローしきい値に達したときに実行されるアクションを定義し、変数に格納します。コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="939cc-p112">Define the action to be taken when the queue overflow threshold is met, and save it in a variable. At the command line, run:</span></span>
    
        $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="939cc-165">可能なアクションとその構文の詳細については、「<A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">新しい-CsRgsCallAction</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="939cc-165">For details about possible actions and their syntax, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="939cc-166">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="939cc-166">For example:</span></span>
    
        $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate

7.  <span data-ttu-id="939cc-p113">応答グループ サービスのサービス名を取得し、変数に割り当てます。コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="939cc-p113">Retrieve the service name for the Response Group service and assign it to a variable. At the command line, run:</span></span>
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;

8.  <span data-ttu-id="939cc-p114">キューに割り当てるエージェント グループの Identity を取得します。コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="939cc-p114">Get the identity of the agent group to be assigned to the queue. At the command line, run:</span></span>
    
        $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="939cc-171">エージェントグループの作成の詳細については、「<A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup">新しい-CsRgsAgentGroup</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="939cc-171">For details about creating the agent group, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup">New-CsRgsAgentGroup</A></span></span>

    
    </div>

9.  <span data-ttu-id="939cc-p115">キューを作成します。コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="939cc-p115">Create the queue. At the command line, run:</span></span>
    
        $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
    
    <span data-ttu-id="939cc-174">例:</span><span class="sxs-lookup"><span data-stu-id="939cc-174">For example:</span></span>
    
        $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;

10. <span data-ttu-id="939cc-p116">キューが作成されたことを確認します。次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="939cc-p116">Confirm that the queue is created. Run:</span></span>
    
        Get-CsRgsQueue -Name "Help Desk"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="939cc-177">関連項目</span><span class="sxs-lookup"><span data-stu-id="939cc-177">See Also</span></span>


[<span data-ttu-id="939cc-178">新規-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="939cc-178">New-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue)  
[<span data-ttu-id="939cc-179">Set-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="939cc-179">Set-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsQueue)  
[<span data-ttu-id="939cc-180">新規-CsRgsPrompt</span><span class="sxs-lookup"><span data-stu-id="939cc-180">New-CsRgsPrompt</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt)  
[<span data-ttu-id="939cc-181">新規-CsRgsCallAction</span><span class="sxs-lookup"><span data-stu-id="939cc-181">New-CsRgsCallAction</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction)  
[<span data-ttu-id="939cc-182">Get-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="939cc-182">Get-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsQueue)  
[<span data-ttu-id="939cc-183">インポート-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="939cc-183">Import-CsRgsAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile)  
[<span data-ttu-id="939cc-184">削除-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="939cc-184">Remove-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsRgsQueue)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

