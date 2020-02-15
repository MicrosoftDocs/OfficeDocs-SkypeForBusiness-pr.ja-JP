---
title: 'Lync Server 2013: 手動で正規化ルールを作成または変更する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a normalization rule manually
ms:assetid: fc0335e6-8830-4cfb-8c64-6aeb98c0a992
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413074(v=OCS.15)
ms:contentKeyID: 48185943
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 305369719631361e0e8f8d9e9d12101fbdbfb1e5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045930"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-normalization-rule-manually-in-lync-server-2013"></a><span data-ttu-id="297a1-102">Lync Server 2013 で正規化ルールを手動で作成または変更する</span><span class="sxs-lookup"><span data-stu-id="297a1-102">Create or modify a normalization rule manually in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="297a1-103">_**トピックの最終更新日:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="297a1-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="297a1-104">正規化ルールを手動で作成または変更する場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="297a1-104">Complete the following steps if you want to create or modify a normalization rule manually.</span></span> <span data-ttu-id="297a1-105">Lync Server コントロールパネルの [正規化ルールの構築] を使用して正規化ルールを作成または変更する場合は、「 [create a 正規化 rule in Using Lync server 2013](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="297a1-105">If you want to create or modify a normalization rule by using Build a Normalization Rule in Lync Server Control Panel, see [Create or modify a normalization rule by using Build a Normalization Rule in Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md).</span></span>

<div>

## <a name="to-define-a-normalization-rule-manually"></a><span data-ttu-id="297a1-106">正規化ルールを手動で定義するには</span><span class="sxs-lookup"><span data-stu-id="297a1-106">To define a normalization rule manually</span></span>

1.  <span data-ttu-id="297a1-107">RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="297a1-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="297a1-108">詳細については、「 [Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="297a1-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="297a1-109">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="297a1-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="297a1-110">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="297a1-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="297a1-111">オプション「 [Create a dial plan In Lync server 2013](lync-server-2013-create-a-dial-plan.md) 」または「 [Modify a Dial Plan in lync server 2013](lync-server-2013-modify-a-dial-plan.md)」の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="297a1-111">(Optional) Follow the steps in [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) or [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

4.  <span data-ttu-id="297a1-112">[**新しい正規化ルール**] または [**正規化ルールの編集**] の [**名前**] に、正規化される番号のパターンについてわかりやすい名前を入力します (たとえば、正規化ルールに「**5DigitExtension**」という名前を付けます)。</span><span class="sxs-lookup"><span data-stu-id="297a1-112">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example, name the normalization rule **5DigitExtension**).</span></span>

5.  <span data-ttu-id="297a1-113">(オプション) [**説明**] フィールドに、正規化ルールの説明を入力します (たとえば、"5 桁の内線番号を変換")。</span><span class="sxs-lookup"><span data-stu-id="297a1-113">(Optional) In **Description** field, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

6.  <span data-ttu-id="297a1-114">[**正規化ルールの構築**] で [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="297a1-114">In **Build a Normalization Rule**, click **Edit**.</span></span>

7.  <span data-ttu-id="297a1-115">[**正規表現の入力**] で次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="297a1-115">Enter the following in **Type a Regular Expression**:</span></span>
    
      - <span data-ttu-id="297a1-116">[**このパターンを照合**] で、ダイヤル電話番号を照合するために使用するパターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="297a1-116">In **Match this pattern**, specify the pattern that you want to use to match the dialed phone number.</span></span>
    
      - <span data-ttu-id="297a1-117">[**変換ルール**] で、変換される E.164 電話番号の形式のパターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="297a1-117">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers.</span></span>
    
    <span data-ttu-id="297a1-118">たとえば、[**このパターンを照合**] に「 **^\\(d{7}) $** 」と入力し、[**変換ルール**] に「 **+ 1425 $ 1** 」と入力すると、ルールは5550100から + 14255550100 に正規化されます。</span><span class="sxs-lookup"><span data-stu-id="297a1-118">For example, if you enter **^(\\d{7})$** in **Match this pattern** and **+1425$1** in **Translation rule**, the rule normalizes 5550100 to +14255550100.</span></span>

8.  <span data-ttu-id="297a1-119">(オプション) 正規化ルールによって電話番号が組織の内線番号になる場合は、[**内線番号**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="297a1-119">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

9.  <span data-ttu-id="297a1-p104">(オプション) 正規化ルールをテストする番号を入力し、[**次へ**] をクリックします。 テスト結果は、[**テストする番号の入力**] の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="297a1-p104">(Optional) Enter a number to test the normalization rule and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="297a1-122">テストにまだ合格していない正規化ルールは、保存しておいて後で再構成できます。</span><span class="sxs-lookup"><span data-stu-id="297a1-122">You can save a normalization rule that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="297a1-123">詳細については、「 <A href="lync-server-2013-test-voice-routing.md">Lync Server 2013 での音声ルーティングのテスト</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="297a1-123">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

10. <span data-ttu-id="297a1-124">[**OK**] をクリックして正規化ルールを保存します。</span><span class="sxs-lookup"><span data-stu-id="297a1-124">Click **OK** to save the normalization rule.</span></span>

11. <span data-ttu-id="297a1-125">[**OK**] をクリックしてダイヤル プランを保存します。</span><span class="sxs-lookup"><span data-stu-id="297a1-125">Click **OK** to save the dial plan.</span></span>

12. <span data-ttu-id="297a1-126">[**ダイヤル プラン**] ページで [**確定**] をクリックして、[**すべて確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="297a1-126">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="297a1-127">正規化ルールを作成または変更するときにはいつでも、[<STRONG>すべて確定</STRONG>] コマンドを実行して構成の変更を公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="297a1-127">Whenever you create or change a normalization rule, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="297a1-128">詳細については、「操作」のドキュメントの「 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 での音声ルーティング構成に対する保留中の変更の公開</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="297a1-128">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="297a1-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="297a1-129">See Also</span></span>


[<span data-ttu-id="297a1-130">「Lync Server 2013 で正規化ルールを構築する」を使用して正規化ルールを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="297a1-130">Create or modify a normalization rule by using Build a Normalization Rule in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)  
[<span data-ttu-id="297a1-131">Lync Server 2013 でダイヤルプランを作成する</span><span class="sxs-lookup"><span data-stu-id="297a1-131">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="297a1-132">Lync Server 2013 でダイヤルプランを変更する</span><span class="sxs-lookup"><span data-stu-id="297a1-132">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
[<span data-ttu-id="297a1-133">Lync Server 2013 で保留中の変更を音声ルーティング構成に公開する</span><span class="sxs-lookup"><span data-stu-id="297a1-133">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="297a1-134">Lync Server 2013 での音声ルーティングのテスト</span><span class="sxs-lookup"><span data-stu-id="297a1-134">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

