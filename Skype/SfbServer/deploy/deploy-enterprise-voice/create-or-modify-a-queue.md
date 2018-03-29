---
title: Skype for Business 2015 でのキューの作成または変更
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: b9d6366a-839f-4651-a01d-9254546cadeb
description: 作成またはビジネス サーバーのエンタープライズ VoIP の Skype での応答グループ キューを変更します。
ms.openlocfilehash: a5b76fd8003fcdd4152f57404b14271c4eaa8ef8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="create-or-modify-a-queue-in-skype-for-business-2015"></a><span data-ttu-id="b4967-103">Skype for Business 2015 でのキューの作成または変更</span><span class="sxs-lookup"><span data-stu-id="b4967-103">Create or modify a queue in Skype for Business 2015</span></span>
 
<span data-ttu-id="b4967-104">作成またはビジネス サーバーのエンタープライズ VoIP の Skype での応答グループ キューを変更します。</span><span class="sxs-lookup"><span data-stu-id="b4967-104">Create or modify a Response Group queue, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="b4967-105">エージェントが通話に応答するまで、キューには発信者が保持されます。</span><span class="sxs-lookup"><span data-stu-id="b4967-105">Queues hold callers until an agent answers the call.</span></span> <span data-ttu-id="b4967-106">応答グループ アプリケーションは、使用可能なエージェントを検索する場合は、それらが一覧表示される順序でエージェント グループを検索します。</span><span class="sxs-lookup"><span data-stu-id="b4967-106">When the Response Group application searches for an available agent, it searches agent groups in the order that you list them.</span></span> <span data-ttu-id="b4967-107">キューに割り当てられるエージェント グループを選択し、キューに保持する通話の最大数や、エージェントが応答するまで通話を待機させる時間などのキューの動作を指定できます。</span><span class="sxs-lookup"><span data-stu-id="b4967-107">You can select the agent groups that are assigned to the queue and specify queue behavior, such as limiting the number of calls that the queue can hold and the period of time that a call waits until an agent answers the call.</span></span>
  
<span data-ttu-id="b4967-108">キューを作成または変更するには、以下のいずれかの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="b4967-108">Use one of the following procedures to create or modify a queue.</span></span>
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-queue"></a><span data-ttu-id="b4967-109">ビジネス サーバーのコントロール パネルの Skype を使用して作成または、キューを変更するには</span><span class="sxs-lookup"><span data-stu-id="b4967-109">To use Skype for Business Server Control Panel to create or modify a queue</span></span>

1. <span data-ttu-id="b4967-110">RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="b4967-110">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b4967-111">管理ワークフローを委任された応答グループ マネージャーのいずれかである場合は、応答グループ キューを作成または変更して、管理するワークグループに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="b4967-111">If you are one of the delegated Response Group Managers for a managed workflow, you can create or modify response group queues and assign them to the workflows that you manage.</span></span> 
  
2. <span data-ttu-id="b4967-112">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="b4967-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="b4967-113">左側のナビゲーション バーで [**応答グループ**] をクリックし、[**キュー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4967-113">In the left navigation bar, click **Response Groups**, and then click **Queue**.</span></span>
    
4. <span data-ttu-id="b4967-114">[**キュー**] ページで、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="b4967-114">On the **Queue** page, do one of the following:</span></span>
    
   - <span data-ttu-id="b4967-115">新しいキューを作成するには、[**新規作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4967-115">To create a new queue, click **New**.</span></span> <span data-ttu-id="b4967-116">] で**サービスを選択して**、先**のアプリケーション サーバー**のサービスの名前の種類の一部またはすべては、検索フィールドに、キューを追加します。</span><span class="sxs-lookup"><span data-stu-id="b4967-116">In **Select a Service**, type part or all of the name of the **ApplicationServer** service where you want to add the queue in the search field.</span></span> <span data-ttu-id="b4967-117">表示されたサービスの一覧で、目的のサービスをクリックし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4967-117">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
   - <span data-ttu-id="b4967-p103">既存のキューを変更するには、キューの名前または名前の一部を検索フィールドに入力します。結果のキューの一覧で、対象のキューをクリックし、[**編集**]、[**詳細の表示**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4967-p103">To modify an existing queue, type all or part of the queue name in the search field. In the resulting list of queues, click the queue that you want, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="b4967-120">[**名前**] にキューの識別名を入力します。</span><span class="sxs-lookup"><span data-stu-id="b4967-120">In **Name**, type an identifying name for the queue.</span></span>
    
6. <span data-ttu-id="b4967-121">[**説明**] に、キューの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="b4967-121">In **Description**, type a description for the queue.</span></span>
    
7. <span data-ttu-id="b4967-p104">[**グループ**] で、キューに割り当てるグループを指定します。次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b4967-p104">In **Groups**, specify the groups you want to assign to the queue. Do one of the following:</span></span> 
    
   - <span data-ttu-id="b4967-p105">キューにグループを追加するには、[**選択**] をクリックします。[**グループの選択**] の検索フィールドに、キューに割り当てるエージェント グループの名前または名前の一部を入力し、一覧で目的のエージェント グループをクリックして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4967-p105">To add a group to the queue, click **Select**. In the **Select Groups** search field, type all or part of the name of the agent group that you want to assign to the queue, click the agent group that you want, and then click **OK**.</span></span>
    
   - <span data-ttu-id="b4967-126">キューからグループを削除するには、エージェント グループの一覧で、削除するグループをクリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4967-126">To remove a group from the queue, in the list of agent groups, click the group that you want to remove, and then click **Remove**.</span></span>
    
   - <span data-ttu-id="b4967-127">エージェントを検索する順序を変更するには、エージェント グループの一覧でグループをクリックし、上矢印または下矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4967-127">To change the order in which agents are searched, in the list of agent groups, click a group, and then click the up arrow or down arrow.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b4967-p106">サーバーでは、キューで利用可能なエージェントを検索するときには、グループの順序が使用されます。つまり、一覧の最初のグループが最初に検索され、一覧の 2 番目のグループが次に検索され、以降も同様に検索されます。</span><span class="sxs-lookup"><span data-stu-id="b4967-p106">When the server searches for an available agent for the queue, it uses group order. That is, the first group in the list is searched first, followed by the second group in the list, and so on.</span></span> 
  
8. <span data-ttu-id="b4967-130">エージェントが通話に応答するまで発信者を保留状態にする最長時間を指定するには、[**キューのタイムアウトを有効にする**] チェック ボックスをオンにして次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="b4967-130">To specify a maximum period of time for a caller to wait on hold before an agent answers the call, select the **Enable queue time-out** check box, and then do the following:</span></span>
    
    <span data-ttu-id="b4967-131">a.</span><span class="sxs-lookup"><span data-stu-id="b4967-131">a.</span></span> <span data-ttu-id="b4967-132">[**タイムアウト時間 (秒)**] で、エージェントが通話に応答するのを発信者が待つ最大秒数を指定します。</span><span class="sxs-lookup"><span data-stu-id="b4967-132">In **Time-out period (seconds)**, specify the maximum number of seconds a caller waits for an agent to answer the call.</span></span>
    
    <span data-ttu-id="b4967-133">b.</span><span class="sxs-lookup"><span data-stu-id="b4967-133">b.</span></span> <span data-ttu-id="b4967-134">[**通話アクション**] で、呼び出しがタイムアウトになったときに行う動作を次のように選択します。</span><span class="sxs-lookup"><span data-stu-id="b4967-134">In **Call Action**, select the action that occurs when a call times out as follows:</span></span>
    
     - <span data-ttu-id="b4967-135">タイムアウト後通話を終了するには、[**切断**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4967-135">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
     - <span data-ttu-id="b4967-136">ボイス メール、**ボイス メールを転送**する] をクリックし、 **SIP アドレス**] フィールドに、アドレスを入力、音声メール形式の sip に呼び出しを転送する:_\<ユーザー名\>_@ _\<ドメイン名\>_(例、sip:bob@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="b4967-136">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip: _\<username\>_@ _\<domainname\>_ (for example, sip:bob@contoso.com).</span></span>
    
     - <span data-ttu-id="b4967-137">別の電話番号への呼び出しを転送するに**転送先の電話番号**をクリックし、 **SIP アドレス**] フィールドに、入力形式の sip の電話番号:_\<数\>_@ _\<\>_ (sip:+14255550121@contoso.com など)。</span><span class="sxs-lookup"><span data-stu-id="b4967-137">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip: _\<number\>_@ _\<domainname\>_ (for example, sip:+14255550121@contoso.com).</span></span>
    
     - <span data-ttu-id="b4967-138">他のユーザーへの呼び出しを転送するには、 **SIP アドレスに転送**をクリックして、 **SIP アドレス**] フィールドに、sip の形式でユーザーの URI を入力:_\<ユーザー名\>_@ _\<ドメイン名\>_。</span><span class="sxs-lookup"><span data-stu-id="b4967-138">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip: _\<username\>_@ _\<domainname\>_.</span></span>
    
     - <span data-ttu-id="b4967-139">別のキューに通話を転送する場合は [**別のキューに転送**] をクリックし、使用するキューを参照します。</span><span class="sxs-lookup"><span data-stu-id="b4967-139">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>
    
9. <span data-ttu-id="b4967-140">キューに保持できる最大通話数を指定するには、[**キューのオーバーフローを有効にする**] チェック ボックスをオンにして次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="b4967-140">To specify a maximum number of calls that the queue can hold, select the **Enable queue overflow** check box, and then do the following:</span></span>
    
    <span data-ttu-id="b4967-141">a.</span><span class="sxs-lookup"><span data-stu-id="b4967-141">a.</span></span> <span data-ttu-id="b4967-142">[**最大通話数**] で、キューで保持する最大通話数を選択します。</span><span class="sxs-lookup"><span data-stu-id="b4967-142">In **Maximum number of calls**, select the maximum number of calls that you want the queue to hold.</span></span> 
    
    <span data-ttu-id="b4967-143">b.</span><span class="sxs-lookup"><span data-stu-id="b4967-143">b.</span></span> <span data-ttu-id="b4967-144">[**通話の転送**] で、キューが一杯になったときに転送する通話を、[**最新の通話**] または [**最も古い通話**] から選択します。</span><span class="sxs-lookup"><span data-stu-id="b4967-144">In **Forward the call**, select which call is to be forwarded when the queue is full: **Newest Call** or **Oldest Call**.</span></span>
    
    <span data-ttu-id="b4967-145">c.</span><span class="sxs-lookup"><span data-stu-id="b4967-145">c.</span></span> <span data-ttu-id="b4967-146">[**通話アクション**] で、オーバーフローしきい値に達したときに実行する処理を、次のように選択します。</span><span class="sxs-lookup"><span data-stu-id="b4967-146">In **Call action**, select the action that occurs when the overflow threshold is met as follows:</span></span>
    
     - <span data-ttu-id="b4967-147">タイムアウト後通話を終了するには、[**切断**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4967-147">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
     - <span data-ttu-id="b4967-148">ボイス メール、**ボイス メールを転送**する] をクリックし、 **SIP アドレス**] フィールドに、アドレスを入力、音声メール形式の sip に呼び出しを転送する:_\<ユーザー名\>_@ _\<ドメイン名\>_(例、sip:bob@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="b4967-148">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip: _\<username\>_@ _\<domainname\>_ (for example, sip:bob@contoso.com).</span></span>
    
     - <span data-ttu-id="b4967-149">別の電話番号への呼び出しを転送するに**転送先の電話番号**をクリックし、 **SIP アドレス**] フィールドに、入力形式の sip の電話番号:_\<数\>_@ _\<\>_ (sip:+14255550121@contoso.com など)。</span><span class="sxs-lookup"><span data-stu-id="b4967-149">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip: _\<number\>_@ _\<domainname\>_ (for example, sip:+14255550121@contoso.com).</span></span>
    
     - <span data-ttu-id="b4967-150">他のユーザーへの呼び出しを転送するには、 **SIP アドレスに転送**をクリックして、 **SIP アドレス**] フィールドに、sip の形式でユーザーの URI を入力:_\<ユーザー名\>_@ _\<ドメイン名\>_。</span><span class="sxs-lookup"><span data-stu-id="b4967-150">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip: _\<username\>_@ _\<domainname\>_.</span></span>
    
     - <span data-ttu-id="b4967-151">別のキューに通話を転送する場合は [**別のキューに転送**] をクリックし、使用するキューを参照します。</span><span class="sxs-lookup"><span data-stu-id="b4967-151">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>
    
10. <span data-ttu-id="b4967-152">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4967-152">Click **Commit**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-queue"></a><span data-ttu-id="b4967-153">Skype ビジネス サーバー管理シェルを使用して作成または、待ち行列を変更するのには</span><span class="sxs-lookup"><span data-stu-id="b4967-153">To use Skype for Business Server Management Shell to create or modify a queue</span></span>

1. <span data-ttu-id="b4967-154">RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="b4967-154">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b4967-155">管理ワークフローを委任された応答グループ マネージャーのいずれかである場合は、エージェント グループおよびキューを作成して、エージェント グループをキューに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="b4967-155">If you are one of the delegated Response Group Managers for a managed workflow, you will be able to create agent groups and queues, and assign agent groups to queues.</span></span> 
  
2. <span data-ttu-id="b4967-156">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4967-156">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="b4967-p112">キューのタイムアウトしきい値に達したときに再生されるプロンプトを作成し、変数に格納します。コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b4967-p112">Create the prompt to be played when the queue timeout threshold is met, and save it in a variable. At the command line, run:</span></span>
    
   ```
   $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   <span data-ttu-id="b4967-159">例:</span><span class="sxs-lookup"><span data-stu-id="b4967-159">For example:</span></span>
    
   ```
   "All agents are currently busy. Please call back later."
   ```

   > [!NOTE]
   > <span data-ttu-id="b4967-160">プロンプトのオーディオ ファイルを使用するには、**インポート CsRgsAudioFile**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="b4967-160">To use an audio file for the prompt, use the **Import-CsRgsAudioFile** cmdlet.</span></span> <span data-ttu-id="b4967-161">詳細については、[インポートの CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4967-161">For details, see [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span></span> 
  
4. <span data-ttu-id="b4967-p114">キューのタイムアウトしきい値に達したときに実行されるアクションを定義し、変数に格納します。コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b4967-p114">Define the action to be taken when the queue timeout threshold is met, and save it in a variable. At the command line, run:</span></span>
    
   ```
   $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

   > [!NOTE]
   > <span data-ttu-id="b4967-164">実行可能なアクションとその構文の詳細については、[新規 CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4967-164">For details about possible actions and their syntax, see [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span></span> 
  
    <span data-ttu-id="b4967-165">例:</span><span class="sxs-lookup"><span data-stu-id="b4967-165">For example:</span></span>
    
   ```
   $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate
   ```

5. <span data-ttu-id="b4967-p115">キューのオーバーフローしきい値に達したときに再生されるプロンプトを作成し、変数に格納します。コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b4967-p115">Create the prompt to be played when the queue overflow threshold is met, and save it in a variable. At the command line, run:</span></span>
    
  ```
  $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
  ```

   <span data-ttu-id="b4967-168">例:</span><span class="sxs-lookup"><span data-stu-id="b4967-168">For example:</span></span>
    
  ```
  $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
  ```

      > [!NOTE]
      > <span data-ttu-id="b4967-169">プロンプトのオーディオ ファイルを使用するには、**インポート CsRgsAudioFile**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="b4967-169">To use an audio file for the prompt, use the **Import-CsRgsAudioFile** cmdlet.</span></span> <span data-ttu-id="b4967-170">詳細については、[インポートの CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4967-170">For details, see [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span></span> 
  
6. <span data-ttu-id="b4967-p117">キューのオーバーフローしきい値に達したときに実行されるアクションを定義し、変数に格納します。コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b4967-p117">Define the action to be taken when the queue overflow threshold is met, and save it in a variable. At the command line, run:</span></span>
    
  ```
  $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
  ```

    > [!NOTE]
    > <span data-ttu-id="b4967-173">実行可能なアクションとその構文の詳細については、[新規 CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4967-173">For details about possible actions and their syntax, see [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span></span> 
  
    <span data-ttu-id="b4967-174">例:</span><span class="sxs-lookup"><span data-stu-id="b4967-174">For example:</span></span>
    
   ```
   $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate
   ```

7. <span data-ttu-id="b4967-p118">応答グループ サービスのサービス名を取得し、変数に割り当てます。コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b4967-p118">Retrieve the service name for the Response Group service and assign it to a variable. At the command line, run:</span></span>
    
   ```
   $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;
   ```

8. <span data-ttu-id="b4967-p119">キューに割り当てるエージェント グループの Identity を取得します。コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b4967-p119">Get the identity of the agent group to be assigned to the queue. At the command line, run:</span></span>
    
   ```
   $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
   ```

    > [!NOTE]
    > <span data-ttu-id="b4967-179">エージェント グループを作成する方法については、[新規 CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4967-179">For details about creating the agent group, see [New-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)</span></span>
  
9. <span data-ttu-id="b4967-p120">キューを作成します。コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b4967-p120">Create the queue. At the command line, run:</span></span>
    
   ```
   $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
   ```

   <span data-ttu-id="b4967-182">例:</span><span class="sxs-lookup"><span data-stu-id="b4967-182">For example:</span></span>
    
   ```
   $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;
   ```

10. <span data-ttu-id="b4967-p121">キューが作成されたことを確認します。次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="b4967-p121">Confirm that the queue is created. Run:</span></span>
    
   ```
   Get-CsRgsQueue -Name "Help Desk"
   ```

## <a name="see-also"></a><span data-ttu-id="b4967-185">関連項目</span><span class="sxs-lookup"><span data-stu-id="b4967-185">See also</span></span>

#### 

[<span data-ttu-id="b4967-186">新しい-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="b4967-186">New-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsqueue?view=skype-ps)
  
[<span data-ttu-id="b4967-187">セット CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="b4967-187">Set-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csrgsqueue?view=skype-ps)
  
[<span data-ttu-id="b4967-188">新しい-CsRgsPrompt</span><span class="sxs-lookup"><span data-stu-id="b4967-188">New-CsRgsPrompt</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps)
  
[<span data-ttu-id="b4967-189">新しい-CsRgsCallAction</span><span class="sxs-lookup"><span data-stu-id="b4967-189">New-CsRgsCallAction</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)
  
[<span data-ttu-id="b4967-190">Get CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="b4967-190">Get-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csrgsqueue?view=skype-ps)
  
[<span data-ttu-id="b4967-191">インポート-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="b4967-191">Import-CsRgsAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)
  
[<span data-ttu-id="b4967-192">削除 CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="b4967-192">Remove-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csrgsqueue?view=skype-ps)

