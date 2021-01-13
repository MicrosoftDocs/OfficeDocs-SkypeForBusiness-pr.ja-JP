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
ms.openlocfilehash: 6f8619304e9d3d801dfa430e6addb5105a2b82a2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830767"
---
# <a name="create-or-modify-a-normalization-rule-in-skype-for-business"></a><span data-ttu-id="e4c10-103">Skype for Business で正規化ルールを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="e4c10-103">Create or modify a normalization rule in Skype for Business</span></span>

<span data-ttu-id="e4c10-104">**概要:** Skype for Business Server で正規化ルールを定義、作成、および変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e4c10-104">**Summary:** Learn how to define, create, and modify a normalization rule in Skype for Business Server.</span></span>

<span data-ttu-id="e4c10-105">Skype for Business Server の正規化ルールを定義、作成、および変更します。</span><span class="sxs-lookup"><span data-stu-id="e4c10-105">Define, create, and modify normalization rules in Skype for Business Server.</span></span>

### <a name="to-define-a-normalization-rule-by-using-build-a-normalization-rule"></a><span data-ttu-id="e4c10-106">正規化ルールの作成を使用して正規化ルールを定義するには</span><span class="sxs-lookup"><span data-stu-id="e4c10-106">To define a normalization rule by using Build a Normalization Rule</span></span>

1. <span data-ttu-id="e4c10-107">Skype for Business Server コントロール パネルを開く</span><span class="sxs-lookup"><span data-stu-id="e4c10-107">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="e4c10-108">(省略可能)手順 11. で[Skype for Business Server](dial-plans.md)のダイヤル プラン[](https://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx)を作成または変更する、または手順 10 でダイヤル プランを変更する手順に従います。</span><span class="sxs-lookup"><span data-stu-id="e4c10-108">(Optional) Follow the steps in [Create or modify a dial plan in Skype for Business Server](dial-plans.md) through step 11 or [Modify a Dial Plan](https://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx) through step 10.</span></span>

3. <span data-ttu-id="e4c10-109">[ **新しい正規化ルール** ] または [ **正規化** ルールの編集] で、正規化される番号パターンを示す名前を **[名前** ] に入力します (例: 5DigitExtension)。</span><span class="sxs-lookup"><span data-stu-id="e4c10-109">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example,5DigitExtension).</span></span>

4. <span data-ttu-id="e4c10-110">(オプション) [**説明**] ボックスに、正規化ルールの説明を入力します (たとえば、"5 桁の内線番号を変換")。</span><span class="sxs-lookup"><span data-stu-id="e4c10-110">(Optional) In **Description**, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

5. <span data-ttu-id="e4c10-111">[**正規化ルールの構築**] で、次のフィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="e4c10-111">In **Build a Normalization Rule**, enter values in the following fields:</span></span>

   - <span data-ttu-id="e4c10-112">**開始番号** (オプション) パターンに一致するダイヤル番号の先頭の数字を指定します。</span><span class="sxs-lookup"><span data-stu-id="e4c10-112">**Starting digits** (Optional) Specify the leading digits of dialed numbers you want the pattern to match.</span></span> <span data-ttu-id="e4c10-113">たとえば、425 で始まるダイヤル番号とパターンを一致する場合は、「425」と入力します。</span><span class="sxs-lookup"><span data-stu-id="e4c10-113">For example, type425 if you want the pattern to match dialed numbers beginning with 425.</span></span>

   - <span data-ttu-id="e4c10-114">**長さ** 一致パターンの桁数を指定し、パターンをこの長さと正確に一致するか、この長さ以上のダイヤル番号と一致するか、任意の長さのダイヤル番号と一致するか選択します。</span><span class="sxs-lookup"><span data-stu-id="e4c10-114">**Length** Specify the number of digits in the matching pattern and select whether you want the pattern to match this length exactly, match dialed numbers that are at least this length, or match dialed numbers of any length.</span></span>

   - <span data-ttu-id="e4c10-115">**削除する数字** (オプション) パターンに一致するダイヤル番号から削除する開始番号の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="e4c10-115">**Digits to remove** (Optional) Specify the number of starting digits to be removed from dialed numbers you want the pattern to match.</span></span>

   - <span data-ttu-id="e4c10-116">**追加する数字** (オプション) パターンに一致するダイヤル番号に追加する数字を指定します。</span><span class="sxs-lookup"><span data-stu-id="e4c10-116">**Digits to add** (Optional) Specify digits to be added to dialed numbers you want the pattern to match.</span></span>

     <span data-ttu-id="e4c10-117">これらのフィールドに入力する値は、[**一致パターン**] および [**変換ルール**] に反映されます。</span><span class="sxs-lookup"><span data-stu-id="e4c10-117">The values you enter in these fields are reflected in **Pattern to match** and **Translation rule**.</span></span> <span data-ttu-id="e4c10-118">たとえば、開始桁を空のままにした場合 **、[Length]** フィールドに「7」と入力して **[Exactly]** を選択し、削除する桁数に 0 を指定すると、一致する **パターン** の正規表現は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="e4c10-118">For example, if you leave **Starting digits** empty, type7 into the **Length** field and select **Exactly**, and specify 0 in **Digits to remove**, the resulting regular expression in the **Pattern to match** is:</span></span>

     <span data-ttu-id="e4c10-119">^(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="e4c10-119">^(\d{7})$</span></span>

6. <span data-ttu-id="e4c10-120">[**変換ルール**] で、変換される E.164 電話番号の形式のパターンを次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="e4c10-120">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers as follows:</span></span>

   - <span data-ttu-id="e4c10-121">一致パターンで指定した桁数を表す値。</span><span class="sxs-lookup"><span data-stu-id="e4c10-121">A value that represents the number of digits specified in the matching pattern.</span></span> <span data-ttu-id="e4c10-122">たとえば、変換ルールの一致パターンが ^(\d )$ の場合 {7} 、$1 は 7 桁のダイヤル番号を表します。</span><span class="sxs-lookup"><span data-stu-id="e4c10-122">For example, if the matching pattern is ^(\d{7})$ then$1 in the translation rule represents 7-digit dialed numbers.</span></span>

   - <span data-ttu-id="e4c10-123">(省略可能)[桁数] フィールドに値を入力して、変換された番号の先頭に付加する数字を指定します (例: +1425)。</span><span class="sxs-lookup"><span data-stu-id="e4c10-123">(Optional) Type a value into the **Digits to add** field to specify digits to be prepended to the translated number (for example,+1425).</span></span>

     <span data-ttu-id="e4c10-124">たとえば、一致するパターンにダイヤル番号のパターンとして^(\d )$ が含まれる場合、変換ルールに {7} E.164 電話番号のパターンとして +1425$1 が含まれている場合、ルールは 5550100 を +14255550100に正規化します。</span><span class="sxs-lookup"><span data-stu-id="e4c10-124">For example, if **Pattern to match** contains^(\d{7})$ as the pattern for dialed numbers and **Translation rule** contains+1425$1 as the pattern for E.164 phone numbers, the rule normalizes 5550100 to +14255550100.</span></span>

7. <span data-ttu-id="e4c10-125">(オプション) 正規化ルールによって電話番号が組織の内線番号になる場合は、[**内線番号**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e4c10-125">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

8. <span data-ttu-id="e4c10-p104">(オプション) 正規化ルールをテストする番号を入力し、[**次へ**] をクリックします。テスト結果は、[**テストする番号の入力**] の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="e4c10-p104">(Optional) Enter a number to test the normalization rule, and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e4c10-128">テストにまだ合格していない正規化ルールは、保存しておいて後で再構成できます。</span><span class="sxs-lookup"><span data-stu-id="e4c10-128">You can save a normalization rule that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="e4c10-129">詳細については、「[Test Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4c10-129">For details, see [Test Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx).</span></span>

9. <span data-ttu-id="e4c10-130">[**OK**] をクリックして正規化ルールを保存します。</span><span class="sxs-lookup"><span data-stu-id="e4c10-130">Click **OK** to save the normalization rule.</span></span>

10. <span data-ttu-id="e4c10-131">[**OK**] をクリックしてダイヤル プランを保存します。</span><span class="sxs-lookup"><span data-stu-id="e4c10-131">Click **OK** to save the dial plan.</span></span>

11. <span data-ttu-id="e4c10-132">[**ダイヤル プラン**] ページで [**確定**] をクリックして、[**すべて確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4c10-132">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e4c10-133">正規化ルールを作成または変更するときにはいつでも、[**すべて確定**] コマンドを実行して構成の変更を公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4c10-133">Whenever you create or change a normalization rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="e4c10-134">詳細については、「操作」のドキュメント [の「Skype for Business](voice-route-config-changes.md) での音声ルーティング構成に対する保留中の変更の公開」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4c10-134">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

### <a name="to-define-a-normalization-rule-manually"></a><span data-ttu-id="e4c10-135">正規化ルールを手動で定義するには</span><span class="sxs-lookup"><span data-stu-id="e4c10-135">To define a normalization rule manually</span></span>

1. <span data-ttu-id="e4c10-136">Skype for Business Server コントロール パネルを開く</span><span class="sxs-lookup"><span data-stu-id="e4c10-136">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="e4c10-137">(省略可能) [「Skype for Business Server でダイヤル プランを作成または変更する」の手順に従います](dial-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="e4c10-137">(Optional) Follow the steps in [Create or modify a dial plan in Skype for Business Server](dial-plans.md).</span></span>

3. <span data-ttu-id="e4c10-138">[**新しい正規化ルール**] または [正規化ルールの編集] で、正規化される番号パターンを説明する名前を **[** 名前] に入力します (たとえば、正規化ルールに5DigitExtension という名前を付けます)。 </span><span class="sxs-lookup"><span data-stu-id="e4c10-138">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example, name the normalization rule5DigitExtension).</span></span>

4. <span data-ttu-id="e4c10-139">(オプション) [**説明**] フィールドに、正規化ルールの説明を入力します (たとえば、"5 桁の内線番号を変換")。</span><span class="sxs-lookup"><span data-stu-id="e4c10-139">(Optional) In **Description** field, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

5. <span data-ttu-id="e4c10-140">[**正規化ルールの構築**] で [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4c10-140">In **Build a Normalization Rule**, click **Edit**.</span></span>

6. <span data-ttu-id="e4c10-141">[**正規表現の入力**] で次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="e4c10-141">Enter the following in **Type a Regular Expression**:</span></span>

   - <span data-ttu-id="e4c10-142">[**このパターンを照合**] で、ダイヤル電話番号を照合するために使用するパターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="e4c10-142">In **Match this pattern**, specify the pattern that you want to use to match the dialed phone number.</span></span>

   - <span data-ttu-id="e4c10-143">[**変換ルール**] で、変換される E.164 電話番号の形式のパターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="e4c10-143">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers.</span></span>

     <span data-ttu-id="e4c10-144">たとえば、このパターンと一致するパターンに ^(\d )$ を入力し、変換ルールに {7} +1425$1 を入力すると、ルールは 5550100 から +14255550100に正規化されます。</span><span class="sxs-lookup"><span data-stu-id="e4c10-144">For example, if you enter ^(\d{7})$ in **Match this pattern** and+1425$1 in **Translation rule**, the rule normalizes 5550100 to +14255550100.</span></span>

7. <span data-ttu-id="e4c10-145">(オプション) 正規化ルールによって電話番号が組織の内線番号になる場合は、[**内線番号**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e4c10-145">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

8. <span data-ttu-id="e4c10-p107">(オプション) 正規化ルールをテストする番号を入力し、[**次へ**] をクリックします。 テスト結果は、[**テストする番号の入力**] の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="e4c10-p107">(Optional) Enter a number to test the normalization rule and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>

9. <span data-ttu-id="e4c10-148">[**OK**] をクリックして正規化ルールを保存します。</span><span class="sxs-lookup"><span data-stu-id="e4c10-148">Click **OK** to save the normalization rule.</span></span>

10. <span data-ttu-id="e4c10-149">[**OK**] をクリックしてダイヤル プランを保存します。</span><span class="sxs-lookup"><span data-stu-id="e4c10-149">Click **OK** to save the dial plan.</span></span>

11. <span data-ttu-id="e4c10-150">[**ダイヤル プラン**] ページで [**確定**] をクリックして、[**すべて確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4c10-150">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e4c10-151">正規化ルールを作成または変更するときにはいつでも、[**すべて確定**] コマンドを実行して構成の変更を公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4c10-151">Whenever you create or change a normalization rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="e4c10-152">詳細については、「操作」のドキュメント [の「Skype for Business](voice-route-config-changes.md) での音声ルーティング構成に対する保留中の変更の公開」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4c10-152">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>


