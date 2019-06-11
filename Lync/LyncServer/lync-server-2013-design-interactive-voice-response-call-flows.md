---
title: 'Lync Server 2013: 対話型音声応答通話フローの設計'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Design interactive voice response call flows
ms:assetid: f3477f0a-3ad5-4b13-a73c-046aa451db19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413020(v=OCS.15)
ms:contentKeyID: 48185826
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 487fa3d4842ad67f3433966a08a889e454450351
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833466"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="design-interactive-voice-response-call-flows-in-lync-server-2013"></a><span data-ttu-id="da6c5-102">Lync Server 2013 での対話型音声応答通話フローの設計</span><span class="sxs-lookup"><span data-stu-id="da6c5-102">Design interactive voice response call flows in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da6c5-103">_**最終更新日:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="da6c5-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="da6c5-p101">対話型音声応答 (IVR) を使用すると、発信者から情報を取得し、通話を適切なキューに転送できます。使用するキューは質問と回答のペアによって決定されます。発信者の応答に応じて、発信者は、追加の質問を受けるか、適切なキューにルーティングされます。IVR の質問と発信者の応答は、通話を承諾した応答エージェントに提供され、これによりそのエージェントは有益な情報を得られます。</span><span class="sxs-lookup"><span data-stu-id="da6c5-p101">You can use interactive voice response (IVR) to obtain information from callers and direct the call to the appropriate queue. Question-and-answer pairs determine which queue to use. Depending on the caller’s response, the caller either hears a follow-up question, or is routed to the appropriate queue. The IVR questions and the caller’s responses are provided to the responding agent who accepts the call, providing valuable information to the agent.</span></span>

<div>

## <a name="overview-of-ivr-features"></a><span data-ttu-id="da6c5-108">IVR 機能の概要</span><span class="sxs-lookup"><span data-stu-id="da6c5-108">Overview of IVR Features</span></span>

<span data-ttu-id="da6c5-109">応答グループアプリケーションは、26言語の音声認識と音声合成機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="da6c5-109">The Response Group application offers speech recognition and text-to-speech capabilities in 26 languages.</span></span> <span data-ttu-id="da6c5-110">IVR の質問は、音声合成や wave (.wav) または Windows Media オーディオ (.wma) ファイルを使用して入力できます。</span><span class="sxs-lookup"><span data-stu-id="da6c5-110">You can enter IVR questions using text-to-speech or a wave (.wav) or Windows Media audio (.wma) file.</span></span> <span data-ttu-id="da6c5-111">発信者は、音声またはデュアルトーン多重周波数 (DTMF) 応答を使用して応答できます。</span><span class="sxs-lookup"><span data-stu-id="da6c5-111">Callers can respond by using voice or dual-tone multifrequency (DTMF) responses.</span></span>

<span data-ttu-id="da6c5-p103">対話ワークフローでは最高 2 問の質問がサポートされ、各質問には回答の選択肢を 4 つまで設定できます。IVR は、発信者に質問をして、発信者の応答に応じて、発信者をキューにルーティングするか、2 番目の質問をします。2 番目の質問にも、4 つの回答を設定できます。2 番目のレベルの質問に対する回答に応じて、発信者は適切なキューにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="da6c5-p103">Interactive workflows support up to two levels of questions, with each question having up to four possible answers. The IVR asks the caller a question, and depending on the caller’s response, routes the caller to a queue or asks a second question. The second question can also have four possible answers. Depending on the answer to the second-level question, the caller is routed to the appropriate queue.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="da6c5-116">Lync Server Management Shell を使用してコールフローを設計するときには、IVR の質問と回答の数のレベルを定義できます。</span><span class="sxs-lookup"><span data-stu-id="da6c5-116">When you design call flows by using Lync Server Management Shell, you can define any number levels of IVR questions and any number of answers.</span></span> <span data-ttu-id="da6c5-117">ただし、発信者の利便性を考え、3 問より多くの質問は使用せず、それぞれの回答の選択肢を 5 つ以下にするようお勧めします。</span><span class="sxs-lookup"><span data-stu-id="da6c5-117">However, for caller usability, we recommend that you not use more than three levels of questions, with not more than five answers each.</span></span> <span data-ttu-id="da6c5-118">また、3つ以上の種類の質問が含まれているコールフローを設計する場合は、Lync Server 2013 コントロールパネルを使って通話フローを編集することはできません。</span><span class="sxs-lookup"><span data-stu-id="da6c5-118">In addition, if you design a call flow that has more than two levels of questions with more than four answers each, you cannot edit the call flow by using Lync Server 2013 Control Panel.</span></span>



</div>

<span data-ttu-id="da6c5-119">IVR の質問と発信者の応答は、通話を承諾した応答エージェントに提供されます。</span><span class="sxs-lookup"><span data-stu-id="da6c5-119">The IVR questions and the caller’s responses are provided to the responding agent who accepts the call.</span></span>

</div>

<div>

## <a name="working-with-speech-technologies"></a><span data-ttu-id="da6c5-120">音声テクノロジの操作</span><span class="sxs-lookup"><span data-stu-id="da6c5-120">Working with Speech Technologies</span></span>

<span data-ttu-id="da6c5-121">音声認識や音声合成などの音声テクノロジにより、顧客のエクスペリエンスが強化され、情報へのより自然で効率的なアクセスが可能となります。</span><span class="sxs-lookup"><span data-stu-id="da6c5-121">Speech technologies, such as speech recognition and text-to-speech, can enhance customer experience and let people access information more naturally and effectively.</span></span> <span data-ttu-id="da6c5-122">ただし、指定したテキストやユーザーの音声応答が、音声エンジンによって正しく認識されない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="da6c5-122">However, there can be cases where the specified text or the user voice response is not recognized correctly by the speech engine.</span></span> <span data-ttu-id="da6c5-123">たとえば、"\#" という記号は、"数値" という単語として、音声合成エンジンによって変換されます。</span><span class="sxs-lookup"><span data-stu-id="da6c5-123">For example, the "\#" symbol is translated by the text-to-speech engine as the word "number."</span></span> <span data-ttu-id="da6c5-124">この問題は、次の方法によって軽減されます。</span><span class="sxs-lookup"><span data-stu-id="da6c5-124">This issue can be mitigated by the following:</span></span>

  - <span data-ttu-id="da6c5-p106">音声エンジンにより、発信者は 5 回まで質問に回答することができます。発信者の質問に対する回答が不適切な場合 (回答が指定された応答のいずれでもない)、またはまったく回答がない場合には、発信者にもう一度その質問に回答する機会が与えられます。発信者は、通話が切断されるまでに 5 回質問に回答することができます。IVR は、発信者の回答に誤りがあるたびにカスタマイズしたメッセージを再生するように構成できます。質問は毎回繰り返されます。</span><span class="sxs-lookup"><span data-stu-id="da6c5-p106">The speech engine gives the caller five attempts to answer the question. If the caller answers the question incorrectly (that is, the answer is not one of the specified responses) or does not provide an answer at all, the caller gets another chance to answer the question. The caller has five attempts to answer the question before being disconnected. You can configure the IVR to play a customized message after each caller error. The question is repeated each time.</span></span>

  - <span data-ttu-id="da6c5-p107">音声エンジンによって周囲の雑音が応答として解釈される可能性を最小限に抑えるため、長めの応答を使用してください。たとえば、応答には複数の音節を含め、発音が相互に明確に異なるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="da6c5-p107">To minimize the potential for ambient noise to be interpreted by the speech engine as a response, use longer responses. For example, responses should have more than one syllable and should sound significantly different from each other.</span></span>

  - <span data-ttu-id="da6c5-p108">質問に音声応答と DTMF 応答の両方が含まれる場合は、DTMF 応答ではなく概念を表す語句で音声応答を構成してください。たとえば、「1 を押すか 1 とお答えください」を使用する代わりに、「1 を押すか請求とお答えください」を使用します。</span><span class="sxs-lookup"><span data-stu-id="da6c5-p108">If your questions have both speech and DTMF responses, configure the speech responses with words that represent the concept rather than the DTMF response. For example, instead of using "Press or say one" use "Press 1 or say billing."</span></span>

  - <span data-ttu-id="da6c5-134">IVR を設計したら、ワークフローを呼び出して質問を聞き、音声で各質問に応答して、IVR が正常に再生および動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="da6c5-134">After you design your IVR, call the workflow, listen to the prompts, respond to each of the prompts using voice, and verify that the IVR sounds and behaves as expected.</span></span> <span data-ttu-id="da6c5-135">その後、IVR を変更して、解釈の問題を修正できます。</span><span class="sxs-lookup"><span data-stu-id="da6c5-135">You can then modify the IVR to fix any interpretation issues.</span></span> <span data-ttu-id="da6c5-136">前の例の後で、 \#キーを参照する必要がある場合は、 \#記号ではなく、IVR のプロンプトでキー名を使用するように書き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="da6c5-136">Following the previous example, if you need to refer to the \# key, you can rewrite your IVR prompt to use the key name, rather than the \# symbol.</span></span> <span data-ttu-id="da6c5-137">たとえば、「営業部門をご希望の場合は、シャープを押してください」とします。</span><span class="sxs-lookup"><span data-stu-id="da6c5-137">For example, "To talk to sales, press the pound key."</span></span>

</div>

<div>

## <a name="ivr-design-examples"></a><span data-ttu-id="da6c5-138">IVR 設計の例</span><span class="sxs-lookup"><span data-stu-id="da6c5-138">IVR Design Examples</span></span>

<span data-ttu-id="da6c5-139">以下のセクションでは、さまざまな IVR シナリオおよび質問と回答のペアの例を示します。</span><span class="sxs-lookup"><span data-stu-id="da6c5-139">The following sections contain examples of different IVR scenarios and question-and-answer pairs.</span></span>

<div>

## <a name="ivr-with-one-level-of-questions"></a><span data-ttu-id="da6c5-140">1 問の質問が設定された IVR</span><span class="sxs-lookup"><span data-stu-id="da6c5-140">IVR with One Level of Questions</span></span>

<span data-ttu-id="da6c5-p110">次の例は、1 問の質問を使用する IVR を示しています。この例では、音声認識を使用して発信者の応答を検出します。</span><span class="sxs-lookup"><span data-stu-id="da6c5-p110">The following example shows an IVR that uses one level of questions. It uses speech recognition to detect the caller’s response.</span></span>

<span data-ttu-id="da6c5-p111">**質問:** 「人事部にお問い合わせいただき、ありがとうございます。給与課をご希望の場合は、給与課とお答えください。それ以外の場合は、人事部とお答えください。」</span><span class="sxs-lookup"><span data-stu-id="da6c5-p111">**Question:** "Thank you for calling Human Resources. If you would like to speak to payroll, say payroll. Otherwise, say HR."</span></span>

  - <span data-ttu-id="da6c5-146">**1 つ目のオプションが選択された場合:** 発信者は給与課にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="da6c5-146">**Option 1 is selected:** The caller is routed to the payroll team.</span></span>

  - <span data-ttu-id="da6c5-147">**2 つ目のオプションが選択された場合:** 発信者は人事部にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="da6c5-147">**Option 2 is selected:** The caller is routed to the human resources team.</span></span>

<span data-ttu-id="da6c5-148">次の図は、通話の流れを示します。</span><span class="sxs-lookup"><span data-stu-id="da6c5-148">The following figure shows the call flow.</span></span>

<span data-ttu-id="da6c5-149">**1 問対話の通話の流れ**</span><span class="sxs-lookup"><span data-stu-id="da6c5-149">**One-level interactive call flow**</span></span>

<span data-ttu-id="da6c5-150">![対話型音声通信を使って通話フローを設計する](images/Gg413020.4820a9f7-b5b0-4831-b972-baae0c015ec1(OCS.15).jpg "対話型音声通信を使って通話フローを設計する")</span><span class="sxs-lookup"><span data-stu-id="da6c5-150">![Design Call Flows by Using Interactive Voice Respo](images/Gg413020.4820a9f7-b5b0-4831-b972-baae0c015ec1(OCS.15).jpg "Design Call Flows by Using Interactive Voice Respo")</span></span>

</div>

<div>

## <a name="ivr-with-two-levels-of-questions"></a><span data-ttu-id="da6c5-151">2 問の質問が設定された IVR</span><span class="sxs-lookup"><span data-stu-id="da6c5-151">IVR with Two Levels of Questions</span></span>

<span data-ttu-id="da6c5-p112">次の例は、2 問の質問を使用する IVR を示しています。この例で発信者は、音声または DTMF キーパッド入力を使用して応答できます。</span><span class="sxs-lookup"><span data-stu-id="da6c5-p112">The following example shows an IVR that uses two levels of questions. It allows callers to respond using either speech or DTMF keypad input.</span></span>

<span data-ttu-id="da6c5-p113">**質問:** 「IT ヘルプ デスクにお問い合わせいただき、ありがとうございます。ネットワーク アクセスに問題がある場合は、1 を押すか、ネットワークとお答えください。ソフトウェアに問題がある場合は、2 を押すか、ソフトウェアとお答えください。ハードウェアに問題がある場合は、3 を押すか、ハードウェアとお答えください。」</span><span class="sxs-lookup"><span data-stu-id="da6c5-p113">**Question:** "Thank you for calling the IT Help Desk. If you have a network access problem, press 1 or say network. If you have a software problem, press 2 or say software. If you have a hardware problem, press 3 or say hardware."</span></span>

  - <span data-ttu-id="da6c5-158">**1 つ目のオプションが選択された場合:** 発信者はネットワーク サポート チームにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="da6c5-158">**Option 1 is selected:** The caller is routed to the network support team.</span></span>

  - <span data-ttu-id="da6c5-159">**2 つ目のオプションが選択された場合:** 発信者には、追加の質問が行われます。</span><span class="sxs-lookup"><span data-stu-id="da6c5-159">**Option 2 is selected:** The caller is asked a follow-up question:</span></span>
    
    <span data-ttu-id="da6c5-p114">**質問:** 「オペレーティング システムに問題がある場合は、1 を押すか、オペレーティング システムとお答えください。内部アプリケーションに問題がある場合は、2 を押すか、内部アプリケーションとお答えください。それ以外の場合は、3 を押すか、それ以外とお答えください。」</span><span class="sxs-lookup"><span data-stu-id="da6c5-p114">**Question:** "If this is an operating system problem, press 1 or say operating system. If this is a problem with an internal application, press 2 or say internal application. Otherwise, press 3 or say other."</span></span>
    
      - <span data-ttu-id="da6c5-163">**1 つ目のオプションが選択された場合:** 発信者はオペレーティング システムのサポート チームにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="da6c5-163">**Option 1 is selected:** The caller is routed to the operating systems support team.</span></span>
    
      - <span data-ttu-id="da6c5-164">**2 つ目のオプションが選択された場合:** 発信者は内部アプリケーションのサポート チームにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="da6c5-164">**Option 2 is selected:** The caller is routed to the internal applications support team.</span></span>
    
      - <span data-ttu-id="da6c5-165">**3 つ目のオプションが選択された場合:** 発信者はソフトウェアのサポート チームにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="da6c5-165">**Option 3 is selected:** The caller is routed to the software support team.</span></span>

  - <span data-ttu-id="da6c5-166">**3 つ目のオプションが選択された場合:** 発信者には、追加の質問が行われます。</span><span class="sxs-lookup"><span data-stu-id="da6c5-166">**Option 3 is selected:** The caller is asked a follow-up question:</span></span>
    
    <span data-ttu-id="da6c5-p115">**質問:** 「プリンターに問題がある場合は 1 を、それ以外の場合は 2 を押してください。」</span><span class="sxs-lookup"><span data-stu-id="da6c5-p115">**Question:** "If this is a printer problem press 1. Otherwise, press 2."</span></span>
    
      - <span data-ttu-id="da6c5-169">**1 つ目のオプションが選択された場合:** 発信者はプリンターのサポート チームにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="da6c5-169">**Option 1 is selected:** The caller is routed to the printer support team.</span></span>
    
      - <span data-ttu-id="da6c5-170">**2 つ目のオプションが選択された場合:** 発信者はハードウェアのサポート チームにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="da6c5-170">**Option 2 is selected:** The caller is routed to the hardware support team.</span></span>

<span data-ttu-id="da6c5-171">次の図は、通話の流れを示します。</span><span class="sxs-lookup"><span data-stu-id="da6c5-171">The following figure shows the call flow.</span></span>

<span data-ttu-id="da6c5-172">**2 問対話の通話の流れ**</span><span class="sxs-lookup"><span data-stu-id="da6c5-172">**Two-level interactive call flow**</span></span>

<span data-ttu-id="da6c5-173">![対話型音声通信を使って通話フローを設計する](images/Gg413020.a5b62083-312d-4419-898b-d1a225a5379f(OCS.15).jpg "対話型音声通信を使って通話フローを設計する")</span><span class="sxs-lookup"><span data-stu-id="da6c5-173">![Design Call Flows by Using Interactive Voice Respo](images/Gg413020.a5b62083-312d-4419-898b-d1a225a5379f(OCS.15).jpg "Design Call Flows by Using Interactive Voice Respo")</span></span>

</div>

</div>

<div>

## <a name="best-practices"></a><span data-ttu-id="da6c5-174">ベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="da6c5-174">Best Practices</span></span>

<span data-ttu-id="da6c5-175">以下に、IVR を設計する場合のベスト プラクティスをいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="da6c5-175">The following list describes some best practices for designing your IVR:</span></span>

  - <span data-ttu-id="da6c5-p116">発信者がすばやくタスクに取りかかることができるようにする。過剰な情報や長いマーケティング メッセージを IVR に含めないようにする。</span><span class="sxs-lookup"><span data-stu-id="da6c5-p116">Let the caller get to the task quickly. Avoid providing too much information or lengthy marketing messages in your IVR.</span></span>

  - <span data-ttu-id="da6c5-p117">長いメッセージを含める場合は、開始メッセージの代わりに、最初の質問に追加することを考慮する。発信者は、そのメッセージが最初の質問の一部であれば、質問に回答することによって省略できるが、開始メッセージを省略することはできない。</span><span class="sxs-lookup"><span data-stu-id="da6c5-p117">If you want to include a lengthy message, consider appending it to the first question instead of to the welcome message. Callers can bypass the message if it is part of the first question by answering the question, but they cannot bypass the welcome message.</span></span>

  - <span data-ttu-id="da6c5-p118">発信者の言語で話す。堅苦しい言い回しを避ける。自然に話す。</span><span class="sxs-lookup"><span data-stu-id="da6c5-p118">Speak in the caller’s language. Avoid stilted language. Speak naturally.</span></span>

  - <span data-ttu-id="da6c5-p119">効率的かつ効果的な案内を記述する。不要なオプションを削除する。情報を構造化し、発信者が予期している応答が文の最後になるようにする。たとえば、「営業部をご希望の場合は、1 を押してください」とする。</span><span class="sxs-lookup"><span data-stu-id="da6c5-p119">Write efficient and effective prompts. Remove any unnecessary options. Structure the information so that the caller’s expected response is at the end of the sentence. For example, “To speak to the sales team, press 1."</span></span>

  - <span data-ttu-id="da6c5-p120">音声応答をわかりやすいものにする。たとえば、DTMF 応答と音声応答の両方を指定する場合は、次のようにする。「営業部をご希望の場合は、1 を押すか、営業と答えてください。」</span><span class="sxs-lookup"><span data-stu-id="da6c5-p120">Make voice responses user friendly. For example, if you specify both DTMF and voice responses, use something like: "To speak to the sales team, press 1 or say sales."</span></span>

  - <span data-ttu-id="da6c5-189">組織全体で展開する前に、ユーザーのグループで IVR をテストする。</span><span class="sxs-lookup"><span data-stu-id="da6c5-189">Test the IVR on a group of users before you deploy it across your organization.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

