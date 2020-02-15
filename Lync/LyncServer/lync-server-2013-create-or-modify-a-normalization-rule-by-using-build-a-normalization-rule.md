---
title: 正規化ルールの構築を使用して正規化ルールを作成または変更する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a normalization rule by using Build a Normalization Rule
ms:assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399036(v=OCS.15)
ms:contentKeyID: 48185889
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc758fa99bd14dff345d7efa9d4c96b151abca57
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045940"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule-in-lync-server-2013"></a><span data-ttu-id="4b9e2-102">「Lync Server 2013 で正規化ルールを構築する」を使用して正規化ルールを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="4b9e2-102">Create or modify a normalization rule by using Build a Normalization Rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b9e2-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="4b9e2-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="4b9e2-104">Lync Server コントロールパネルで正規化ルールを作成または変更するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="4b9e2-104">Complete the following steps if you want to create or modify a normalization rule in Lync Server Control Panel.</span></span> <span data-ttu-id="4b9e2-105">または、手動で正規化ルールを作成または変更する場合は、「 [Lync Server 2013 で手動で正規化ルールを作成または変更](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b9e2-105">Alternatively, if you want to create or modify a normalization rule manually, see [Create or modify a normalization rule manually in Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-manually.md).</span></span>

<div>

## <a name="to-define-a-rule-by-using-build-a-normalization-rule"></a><span data-ttu-id="4b9e2-106">[正規化ルールの構築] を使用してルールを定義するには</span><span class="sxs-lookup"><span data-stu-id="4b9e2-106">To define a rule by using Build a Normalization Rule</span></span>

1.  <span data-ttu-id="4b9e2-107">RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="4b9e2-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="4b9e2-108">詳細については、「 [Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b9e2-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="4b9e2-109">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="4b9e2-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4b9e2-110">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b9e2-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4b9e2-111">オプション「 [Create a dial plan In Lync server 2013](lync-server-2013-create-a-dial-plan.md) 」または「 [Modify a Dial Plan in lync server 2013」](lync-server-2013-modify-a-dial-plan.md) ~ 手順10の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="4b9e2-111">(Optional) Follow the steps in [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) through step 11 or [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md) through step 10.</span></span>

4.  <span data-ttu-id="4b9e2-112">[**新しい正規化ルール**] または [**正規化ルールの編集**] の [**名前**] に、正規化される番号のパターンについてわかりやすい名前 (たとえば、**5DigitExtension**) を入力します。</span><span class="sxs-lookup"><span data-stu-id="4b9e2-112">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example, **5DigitExtension**).</span></span>

5.  <span data-ttu-id="4b9e2-113">(オプション) [**説明**] ボックスに、正規化ルールの説明を入力します (たとえば、"5 桁の内線番号を変換")。</span><span class="sxs-lookup"><span data-stu-id="4b9e2-113">(Optional) In **Description**, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

6.  <span data-ttu-id="4b9e2-114">[**正規化ルールの構築**] で、次のフィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="4b9e2-114">In **Build a Normalization Rule**, enter values in the following fields:</span></span>
    
      - <span data-ttu-id="4b9e2-115">**先頭の数字**   (省略可能) パターンに一致させるダイヤル番号の先頭の桁数を指定します。</span><span class="sxs-lookup"><span data-stu-id="4b9e2-115">**Starting digits**   (Optional) Specify the leading digits of dialed numbers you want the pattern to match.</span></span> <span data-ttu-id="4b9e2-116">たとえば、425 で始まるダイヤル番号とパターンが一致するようにする場合は、「**425**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="4b9e2-116">For example, type **425** if you want the pattern to match dialed numbers beginning with 425.</span></span>
    
      - <span data-ttu-id="4b9e2-117">**[長さ**   ] 一致パターンの桁数を指定し、パターンがこの長さと正確に一致するようにするか、または少なくともこの長さのダイヤル番号に一致するか、または任意の長さのダイヤル番号と一致するかを選択します。</span><span class="sxs-lookup"><span data-stu-id="4b9e2-117">**Length**   Specify the number of digits in the matching pattern and select whether you want the pattern to match this length exactly, match dialed numbers that are at least this length, or match dialed numbers of any length.</span></span>
    
      - <span data-ttu-id="4b9e2-118">**削除する桁数**   (オプション) パターンと照合するダイヤル番号の先頭から削除する数字の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="4b9e2-118">**Digits to remove**   (Optional) Specify the number of starting digits to be removed from dialed numbers you want the pattern to match.</span></span>
    
      - <span data-ttu-id="4b9e2-119">**追加する数字**   (オプション) パターンと照合するダイヤル番号に追加する数字を指定します。</span><span class="sxs-lookup"><span data-stu-id="4b9e2-119">**Digits to add**   (Optional) Specify digits to be added to dialed numbers you want the pattern to match.</span></span>
    
    <span data-ttu-id="4b9e2-p105">これらのフィールドに入力する値は、[**一致パターン**] および [**変換ルール**] に反映されます。 たとえば、[**開始桁の数字**] を空にして [**長さ**] フィールドに「**7**」と入力し、[**完全一致**] を選択し、[**削除する桁数**] で「**0**」と指定すると、[**一致パターン**] に表示される正規表現は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="4b9e2-p105">The values you enter in these fields are reflected in **Pattern to match** and **Translation rule**. For example, if you leave **Starting digits** empty, type **7** into the **Length** field and select **Exactly**, and specify **0** in **Digits to remove**, the resulting regular expression in the **Pattern to match** is:</span></span>
    
    <span data-ttu-id="4b9e2-122">**^ (\\d{7}) $**</span><span class="sxs-lookup"><span data-stu-id="4b9e2-122">**^(\\d{7})$**</span></span>

7.  <span data-ttu-id="4b9e2-123">[**変換ルール**] で、変換される E.164 電話番号の形式のパターンを次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="4b9e2-123">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers as follows:</span></span>
    
      - <span data-ttu-id="4b9e2-124">一致パターンで指定した桁数を表す値。</span><span class="sxs-lookup"><span data-stu-id="4b9e2-124">A value that represents the number of digits specified in the matching pattern.</span></span> <span data-ttu-id="4b9e2-125">たとえば、一致パターンが **^ (\\d{7}) $** の場合、変換ルールの **$1**は7桁のダイヤル番号を表します。</span><span class="sxs-lookup"><span data-stu-id="4b9e2-125">For example, if the matching pattern is **^(\\d{7})$** then **$1** in the translation rule represents 7-digit dialed numbers.</span></span>
    
      - <span data-ttu-id="4b9e2-126">(オプション) [**追加する数字**] フィールドに値を入力して、変換された番号に付加する数字を指定します (たとえば、「**+1425**」)。</span><span class="sxs-lookup"><span data-stu-id="4b9e2-126">(Optional) Type a value into the **Digits to add** field to specify digits to be prepended to the translated number (for example, **+1425**).</span></span>
    
    <span data-ttu-id="4b9e2-127">たとえば、**宛先に一致するパターンに** **^ (\\d{7}) $** が含まれている場合、ダイヤル番号と**変換ルール**には、e.164 電話番号のパターンとして **+ 1425 $ 1**が含まれます。このルールは5550100から + 14255550100 を正規化します。</span><span class="sxs-lookup"><span data-stu-id="4b9e2-127">For example, if **Pattern to match** contains **^(\\d{7})$** as the pattern for dialed numbers and **Translation rule** contains **+1425$1** as the pattern for E.164 phone numbers, the rule normalizes 5550100 to +14255550100.</span></span>

8.  <span data-ttu-id="4b9e2-128">(オプション) 正規化ルールによって電話番号が組織の内線番号になる場合は、[**内線番号**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b9e2-128">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

9.  <span data-ttu-id="4b9e2-p107">(オプション) 正規化ルールをテストする番号を入力し、[**次へ**] をクリックします。テスト結果は、[**テストする番号の入力**] の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b9e2-p107">(Optional) Enter a number to test the normalization rule, and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="4b9e2-131">テストにまだ合格していない正規化ルールは、保存しておいて後で再構成できます。</span><span class="sxs-lookup"><span data-stu-id="4b9e2-131">You can save a normalization rule that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="4b9e2-132">詳細については、「 <A href="lync-server-2013-test-voice-routing.md">Lync Server 2013 での音声ルーティングのテスト</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b9e2-132">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

10. <span data-ttu-id="4b9e2-133">[**OK**] をクリックして正規化ルールを保存します。</span><span class="sxs-lookup"><span data-stu-id="4b9e2-133">Click **OK** to save the normalization rule.</span></span>

11. <span data-ttu-id="4b9e2-134">[**OK**] をクリックしてダイヤル プランを保存します。</span><span class="sxs-lookup"><span data-stu-id="4b9e2-134">Click **OK** to save the dial plan.</span></span>

12. <span data-ttu-id="4b9e2-135">[**ダイヤル プラン**] ページで [**確定**] をクリックして、[**すべて確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4b9e2-135">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="4b9e2-136">正規化ルールを作成または変更するときにはいつでも、[<STRONG>すべて確定</STRONG>] コマンドを実行して構成の変更を公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b9e2-136">Whenever you create or change a normalization rule, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="4b9e2-137">詳細については、「操作」のドキュメントの「 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 での音声ルーティング構成に対する保留中の変更の公開</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b9e2-137">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4b9e2-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="4b9e2-138">See Also</span></span>


[<span data-ttu-id="4b9e2-139">Lync Server 2013 で正規化ルールを手動で作成または変更する</span><span class="sxs-lookup"><span data-stu-id="4b9e2-139">Create or modify a normalization rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)  
[<span data-ttu-id="4b9e2-140">Lync Server 2013 でダイヤルプランを作成する</span><span class="sxs-lookup"><span data-stu-id="4b9e2-140">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="4b9e2-141">Lync Server 2013 でダイヤルプランを変更する</span><span class="sxs-lookup"><span data-stu-id="4b9e2-141">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
[<span data-ttu-id="4b9e2-142">Lync Server 2013 で保留中の変更を音声ルーティング構成に公開する</span><span class="sxs-lookup"><span data-stu-id="4b9e2-142">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="4b9e2-143">Lync Server 2013 での音声ルーティングのテスト</span><span class="sxs-lookup"><span data-stu-id="4b9e2-143">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

