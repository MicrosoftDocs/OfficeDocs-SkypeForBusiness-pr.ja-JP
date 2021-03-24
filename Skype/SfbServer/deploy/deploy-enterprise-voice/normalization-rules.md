---
title: Skype for Business で正規化ルールを作成または変更する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
description: '概要: Skype for Business Server で正規化ルールを定義、作成、および変更する方法について説明します。'
ms.openlocfilehash: 3550e27884d125f065c4688fec2ace797f9e8ce2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103393"
---
# <a name="create-or-modify-a-normalization-rule-in-skype-for-business"></a><span data-ttu-id="b4956-103">Skype for Business で正規化ルールを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="b4956-103">Create or modify a normalization rule in Skype for Business</span></span>

<span data-ttu-id="b4956-104">**概要:** Skype for Business Server で正規化ルールを定義、作成、および変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b4956-104">**Summary:** Learn how to define, create, and modify a normalization rule in Skype for Business Server.</span></span>

<span data-ttu-id="b4956-105">Skype for Business Server で正規化ルールを定義、作成、および変更します。</span><span class="sxs-lookup"><span data-stu-id="b4956-105">Define, create, and modify normalization rules in Skype for Business Server.</span></span>

### <a name="to-define-a-normalization-rule-by-using-build-a-normalization-rule"></a><span data-ttu-id="b4956-106">正規化ルールの作成を使用して正規化ルールを定義するには</span><span class="sxs-lookup"><span data-stu-id="b4956-106">To define a normalization rule by using Build a Normalization Rule</span></span>

1. <span data-ttu-id="b4956-107">Skype for Business Server コントロール パネルを開く</span><span class="sxs-lookup"><span data-stu-id="b4956-107">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="b4956-108">(省略可能)「手順 11[で Skype for Business Server](dial-plans.md)でダイヤル プラン[](/previous-versions/office/lync-server-2013/lync-server-2013-modify-a-dial-plan)を作成または変更する」または「手順 10 でダイヤル プランを変更する」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="b4956-108">(Optional) Follow the steps in [Create or modify a dial plan in Skype for Business Server](dial-plans.md) through step 11 or [Modify a Dial Plan](/previous-versions/office/lync-server-2013/lync-server-2013-modify-a-dial-plan) through step 10.</span></span>

3. <span data-ttu-id="b4956-109">[**新しい正規化ルール**] または [正規化ルールの編集] で、正規化される番号パターンを表す名前を **Name** (5DigitExtension など) に入力します。 </span><span class="sxs-lookup"><span data-stu-id="b4956-109">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example,5DigitExtension).</span></span>

4. <span data-ttu-id="b4956-110">(オプション) [**説明**] ボックスに、正規化ルールの説明を入力します (たとえば、"5 桁の内線番号を変換")。</span><span class="sxs-lookup"><span data-stu-id="b4956-110">(Optional) In **Description**, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

5. <span data-ttu-id="b4956-111">[**正規化ルールの構築**] で、次のフィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="b4956-111">In **Build a Normalization Rule**, enter values in the following fields:</span></span>

   - <span data-ttu-id="b4956-112">**開始桁** (省略可能) パターンに一致するダイヤル番号の先頭の数字を指定します。</span><span class="sxs-lookup"><span data-stu-id="b4956-112">**Starting digits** (Optional) Specify the leading digits of dialed numbers you want the pattern to match.</span></span> <span data-ttu-id="b4956-113">たとえば、パターンが 425 で始まるダイヤル番号と一致する場合は、「425」と入力します。</span><span class="sxs-lookup"><span data-stu-id="b4956-113">For example, type425 if you want the pattern to match dialed numbers beginning with 425.</span></span>

   - <span data-ttu-id="b4956-114">**長さ** 一致するパターンの桁数を指定し、パターンをこの長さと正確に一致するか、少なくともこの長さのダイヤル番号と一致するか、任意の長さのダイヤル番号と一致するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="b4956-114">**Length** Specify the number of digits in the matching pattern and select whether you want the pattern to match this length exactly, match dialed numbers that are at least this length, or match dialed numbers of any length.</span></span>

   - <span data-ttu-id="b4956-115">**削除する数字** (オプション) パターンを一致するダイヤル番号から削除する開始桁数を指定します。</span><span class="sxs-lookup"><span data-stu-id="b4956-115">**Digits to remove** (Optional) Specify the number of starting digits to be removed from dialed numbers you want the pattern to match.</span></span>

   - <span data-ttu-id="b4956-116">**追加する数字** (オプション) パターンに一致するダイヤル番号に追加する数字を指定します。</span><span class="sxs-lookup"><span data-stu-id="b4956-116">**Digits to add** (Optional) Specify digits to be added to dialed numbers you want the pattern to match.</span></span>

     <span data-ttu-id="b4956-117">これらのフィールドに入力する値は、[**一致パターン**] および [**変換ルール**] に反映されます。</span><span class="sxs-lookup"><span data-stu-id="b4956-117">The values you enter in these fields are reflected in **Pattern to match** and **Translation rule**.</span></span> <span data-ttu-id="b4956-118">たとえば、開始桁を空のままにし、[長さ] フィールドに「7」と入力し、[正確] を選択し、[削除する桁数] に0 を指定すると、一致するパターンの結果の正規表現は次のようになります。  </span><span class="sxs-lookup"><span data-stu-id="b4956-118">For example, if you leave **Starting digits** empty, type7 into the **Length** field and select **Exactly**, and specify 0 in **Digits to remove**, the resulting regular expression in the **Pattern to match** is:</span></span>

     <span data-ttu-id="b4956-119">^(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="b4956-119">^(\d{7})$</span></span>

6. <span data-ttu-id="b4956-120">[**変換ルール**] で、変換される E.164 電話番号の形式のパターンを次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="b4956-120">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers as follows:</span></span>

   - <span data-ttu-id="b4956-121">一致パターンで指定した桁数を表す値。</span><span class="sxs-lookup"><span data-stu-id="b4956-121">A value that represents the number of digits specified in the matching pattern.</span></span> <span data-ttu-id="b4956-122">たとえば、変換ルールの一致パターンが ^(\d )$ の場合、$1 は {7} 7 桁のダイヤル番号を表します。</span><span class="sxs-lookup"><span data-stu-id="b4956-122">For example, if the matching pattern is ^(\d{7})$ then$1 in the translation rule represents 7-digit dialed numbers.</span></span>

   - <span data-ttu-id="b4956-123">(省略可能)[追加する **桁数]** フィールドに値を入力して、翻訳された番号の先頭に付加する数字を指定します (たとえば、+1425)。</span><span class="sxs-lookup"><span data-stu-id="b4956-123">(Optional) Type a value into the **Digits to add** field to specify digits to be prepended to the translated number (for example,+1425).</span></span>

     <span data-ttu-id="b4956-124">たとえば、一致するパターンにダイヤル番号のパターンとして^(\d )$ が含まれている場合、変換ルールには {7} E.164 電話番号のパターンとして +1425$1 が含まれている場合、ルールは 5550100 から +1425550100に正規化されます。</span><span class="sxs-lookup"><span data-stu-id="b4956-124">For example, if **Pattern to match** contains^(\d{7})$ as the pattern for dialed numbers and **Translation rule** contains+1425$1 as the pattern for E.164 phone numbers, the rule normalizes 5550100 to +14255550100.</span></span>

7. <span data-ttu-id="b4956-125">(オプション) 正規化ルールによって電話番号が組織の内線番号になる場合は、[**内線番号**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b4956-125">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

8. <span data-ttu-id="b4956-p104">(オプション) 正規化ルールをテストする番号を入力し、[**次へ**] をクリックします。テスト結果は、[**テストする番号の入力**] の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="b4956-p104">(Optional) Enter a number to test the normalization rule, and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b4956-128">テストにまだ合格していない正規化ルールは、保存しておいて後で再構成できます。</span><span class="sxs-lookup"><span data-stu-id="b4956-128">You can save a normalization rule that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="b4956-129">詳細については、「[Test Voice Routing](/previous-versions/office/lync-server-2013/lync-server-2013-test-voice-routing)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4956-129">For details, see [Test Voice Routing](/previous-versions/office/lync-server-2013/lync-server-2013-test-voice-routing).</span></span>

9. <span data-ttu-id="b4956-130">[**OK**] をクリックして正規化ルールを保存します。</span><span class="sxs-lookup"><span data-stu-id="b4956-130">Click **OK** to save the normalization rule.</span></span>

10. <span data-ttu-id="b4956-131">[**OK**] をクリックしてダイヤル プランを保存します。</span><span class="sxs-lookup"><span data-stu-id="b4956-131">Click **OK** to save the dial plan.</span></span>

11. <span data-ttu-id="b4956-132">[**ダイヤル プラン**] ページで [**確定**] をクリックして、[**すべて確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4956-132">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b4956-133">正規化ルールを作成または変更するときにはいつでも、[**すべて確定**] コマンドを実行して構成の変更を公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4956-133">Whenever you create or change a normalization rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="b4956-134">詳細については、「操作」の [ドキュメントの「Skype for Business](voice-route-config-changes.md) の音声ルーティング構成に保留中の変更を公開する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4956-134">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

### <a name="to-define-a-normalization-rule-manually"></a><span data-ttu-id="b4956-135">正規化ルールを手動で定義するには</span><span class="sxs-lookup"><span data-stu-id="b4956-135">To define a normalization rule manually</span></span>

1. <span data-ttu-id="b4956-136">Skype for Business Server コントロール パネルを開く</span><span class="sxs-lookup"><span data-stu-id="b4956-136">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="b4956-137">(省略可能)「Skype for Business Server でダイヤル [プランを作成または変更する」の手順に従います](dial-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="b4956-137">(Optional) Follow the steps in [Create or modify a dial plan in Skype for Business Server](dial-plans.md).</span></span>

3. <span data-ttu-id="b4956-138">[**新しい正規化ルール**] または [正規化ルールの編集] で、正規化する番号パターンを示す名前を **[名前**] に入力します (たとえば、正規化ルール 5DigitExtension に名前を付けます)。 </span><span class="sxs-lookup"><span data-stu-id="b4956-138">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example, name the normalization rule5DigitExtension).</span></span>

4. <span data-ttu-id="b4956-139">(オプション) [**説明**] フィールドに、正規化ルールの説明を入力します (たとえば、"5 桁の内線番号を変換")。</span><span class="sxs-lookup"><span data-stu-id="b4956-139">(Optional) In **Description** field, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

5. <span data-ttu-id="b4956-140">[**正規化ルールの構築**] で [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4956-140">In **Build a Normalization Rule**, click **Edit**.</span></span>

6. <span data-ttu-id="b4956-141">[**正規表現の入力**] で次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="b4956-141">Enter the following in **Type a Regular Expression**:</span></span>

   - <span data-ttu-id="b4956-142">[**このパターンを照合**] で、ダイヤル電話番号を照合するために使用するパターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="b4956-142">In **Match this pattern**, specify the pattern that you want to use to match the dialed phone number.</span></span>

   - <span data-ttu-id="b4956-143">[**変換ルール**] で、変換される E.164 電話番号の形式のパターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="b4956-143">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers.</span></span>

     <span data-ttu-id="b4956-144">たとえば、[このパターンの一致] に ^(\d )$ と入力し、変換ルールに {7} +1425$1 を入力すると、ルールは 5550100 から +14255550100に正規化されます。</span><span class="sxs-lookup"><span data-stu-id="b4956-144">For example, if you enter ^(\d{7})$ in **Match this pattern** and+1425$1 in **Translation rule**, the rule normalizes 5550100 to +14255550100.</span></span>

7. <span data-ttu-id="b4956-145">(オプション) 正規化ルールによって電話番号が組織の内線番号になる場合は、[**内線番号**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b4956-145">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

8. <span data-ttu-id="b4956-p107">(オプション) 正規化ルールをテストする番号を入力し、[**次へ**] をクリックします。 テスト結果は、[**テストする番号の入力**] の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="b4956-p107">(Optional) Enter a number to test the normalization rule and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>

9. <span data-ttu-id="b4956-148">[**OK**] をクリックして正規化ルールを保存します。</span><span class="sxs-lookup"><span data-stu-id="b4956-148">Click **OK** to save the normalization rule.</span></span>

10. <span data-ttu-id="b4956-149">[**OK**] をクリックしてダイヤル プランを保存します。</span><span class="sxs-lookup"><span data-stu-id="b4956-149">Click **OK** to save the dial plan.</span></span>

11. <span data-ttu-id="b4956-150">[**ダイヤル プラン**] ページで [**確定**] をクリックして、[**すべて確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4956-150">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b4956-151">正規化ルールを作成または変更するときにはいつでも、[**すべて確定**] コマンドを実行して構成の変更を公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4956-151">Whenever you create or change a normalization rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="b4956-152">詳細については、「操作」の [ドキュメントの「Skype for Business](voice-route-config-changes.md) の音声ルーティング構成に保留中の変更を公開する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4956-152">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>