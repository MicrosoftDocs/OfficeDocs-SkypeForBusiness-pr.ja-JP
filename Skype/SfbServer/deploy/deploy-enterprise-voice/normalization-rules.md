---
title: Skype for Business で正規化ルールを作成または変更する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
description: '概要: Skype for Business Server で正規化ルールを定義、作成、変更する方法について説明します。'
ms.openlocfilehash: af0f09710d427dc97a919468b5decfa9ef3d93fa
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240261"
---
# <a name="create-or-modify-a-normalization-rule-in-skype-for-business"></a><span data-ttu-id="e2fea-103">Skype for Business で正規化ルールを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="e2fea-103">Create or modify a normalization rule in Skype for Business</span></span>

<span data-ttu-id="e2fea-104">**概要:** Skype for Business Server で正規化ルールを定義、作成、変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e2fea-104">**Summary:** Learn how to define, create, and modify a normalization rule in Skype for Business Server.</span></span>

<span data-ttu-id="e2fea-105">Skype for Business Server で正規化ルールを定義、作成、変更します。</span><span class="sxs-lookup"><span data-stu-id="e2fea-105">Define, create, and modify normalization rules in Skype for Business Server.</span></span>

### <a name="to-define-a-normalization-rule-by-using-build-a-normalization-rule"></a><span data-ttu-id="e2fea-106">[正規化ルールの構築] を使用して正規化ルールを定義するには</span><span class="sxs-lookup"><span data-stu-id="e2fea-106">To define a normalization rule by using Build a Normalization Rule</span></span>

1. <span data-ttu-id="e2fea-107">Skype for Business Server コントロールパネルを開く</span><span class="sxs-lookup"><span data-stu-id="e2fea-107">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="e2fea-108">省略手順11で「 [Skype For Business Server でダイヤルプランを作成または変更](dial-plans.md)する」または「[ダイヤルプランを変更](https://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx)する」の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e2fea-108">(Optional) Follow the steps in [Create or modify a dial plan in Skype for Business Server](dial-plans.md) through step 11 or [Modify a Dial Plan](https://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx) through step 10.</span></span>

3. <span data-ttu-id="e2fea-109">[**新しい正規化ルール**] または [**正規化ルールの編集**] で、**名前**に正規化されている番号パターンを説明する名前を入力します (たとえば、5DigitExtension)。</span><span class="sxs-lookup"><span data-stu-id="e2fea-109">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example,5DigitExtension).</span></span>

4. <span data-ttu-id="e2fea-110">(オプション) [**説明**] ボックスに、正規化ルールの説明を入力します (たとえば、「5 桁の内線番号を変換」)。</span><span class="sxs-lookup"><span data-stu-id="e2fea-110">(Optional) In **Description**, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

5. <span data-ttu-id="e2fea-111">[**正規化ルールの構築**] で、次のフィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="e2fea-111">In **Build a Normalization Rule**, enter values in the following fields:</span></span>

   - <span data-ttu-id="e2fea-112">**開始番号**省略パターンと一致させるダイヤル番号の先頭の数字を指定します。</span><span class="sxs-lookup"><span data-stu-id="e2fea-112">**Starting digits** (Optional) Specify the leading digits of dialed numbers you want the pattern to match.</span></span> <span data-ttu-id="e2fea-113">たとえば、type425 のように、ダイヤルした番号を425から始まる番号に一致させることができます。</span><span class="sxs-lookup"><span data-stu-id="e2fea-113">For example, type425 if you want the pattern to match dialed numbers beginning with 425.</span></span>

   - <span data-ttu-id="e2fea-114">**長さ**一致するパターンの桁数を指定し、パターンをこの長さと正確に一致させるか、またはダイヤルされた電話番号に一致する番号と一致するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="e2fea-114">**Length** Specify the number of digits in the matching pattern and select whether you want the pattern to match this length exactly, match dialed numbers that are at least this length, or match dialed numbers of any length.</span></span>

   - <span data-ttu-id="e2fea-115">**削除する数字**省略番号をダイヤルする番号から削除する番号の開始番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="e2fea-115">**Digits to remove** (Optional) Specify the number of starting digits to be removed from dialed numbers you want the pattern to match.</span></span>

   - <span data-ttu-id="e2fea-116">**追加する数字**省略ダイヤルした番号に追加する数字を指定します。</span><span class="sxs-lookup"><span data-stu-id="e2fea-116">**Digits to add** (Optional) Specify digits to be added to dialed numbers you want the pattern to match.</span></span>

     <span data-ttu-id="e2fea-117">これらのフィールドに入力する値は、[**一致パターン**] および [**変換ルール**] に反映されます。</span><span class="sxs-lookup"><span data-stu-id="e2fea-117">The values you enter in these fields are reflected in **Pattern to match** and **Translation rule**.</span></span> <span data-ttu-id="e2fea-118">たとえば、**数字**を空のままにした場合は、type7 **Length**フィールドに移動して、[**完全**] を選択し、**削除する数字**に0を指定すると、**一致するパターン**の正規表現は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="e2fea-118">For example, if you leave **Starting digits** empty, type7 into the **Length** field and select **Exactly**, and specify 0 in **Digits to remove**, the resulting regular expression in the **Pattern to match** is:</span></span>

     <span data-ttu-id="e2fea-119">^ (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="e2fea-119">^(\d{7})$</span></span>

6. <span data-ttu-id="e2fea-120">[**変換ルール**] で、変換される E.164 電話番号の形式のパターンを次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="e2fea-120">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers as follows:</span></span>

   - <span data-ttu-id="e2fea-121">一致パターンで指定した桁数を表す値。</span><span class="sxs-lookup"><span data-stu-id="e2fea-121">A value that represents the number of digits specified in the matching pattern.</span></span> <span data-ttu-id="e2fea-122">たとえば、対応するパターンが ^ (\d{7}) $ の場合、翻訳ルールの $ 1 は7桁のダイヤル番号を表します。</span><span class="sxs-lookup"><span data-stu-id="e2fea-122">For example, if the matching pattern is ^(\d{7})$ then$1 in the translation rule represents 7-digit dialed numbers.</span></span>

   - <span data-ttu-id="e2fea-123">省略[**追加する桁数**] フィールドに値を入力して、翻訳された番号に付加する数字 (+ 1425 など) を指定します。</span><span class="sxs-lookup"><span data-stu-id="e2fea-123">(Optional) Type a value into the **Digits to add** field to specify digits to be prepended to the translated number (for example,+1425).</span></span>

     <span data-ttu-id="e2fea-124">たとえば、[**一致するパターン] に**^ (\d{7}) という文字列が含まれている場合、ダイヤルする番号と**翻訳ルール**のパターンに + 1425 $ 1 が含まれていると、ルールは5550100から + 14255550100 を正規化します。</span><span class="sxs-lookup"><span data-stu-id="e2fea-124">For example, if **Pattern to match** contains^(\d{7})$ as the pattern for dialed numbers and **Translation rule** contains+1425$1 as the pattern for E.164 phone numbers, the rule normalizes 5550100 to +14255550100.</span></span>

7. <span data-ttu-id="e2fea-125">(オプション) 正規化ルールによって電話番号が組織の内線番号になる場合は、[**内線番号**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2fea-125">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

8. <span data-ttu-id="e2fea-p104">(オプション) 正規化ルールをテストする番号を入力し、[**実行**] をクリックします。テスト結果は、[**テストする番号の入力**] の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="e2fea-p104">(Optional) Enter a number to test the normalization rule, and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e2fea-p105">テストにまだ合格していない正規化ルールは、保存しておいて後で再構成できます。詳細については、「[Test Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2fea-p105">You can save a normalization rule that does not yet pass the test and then reconfigure it later. For details, see [Test Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx).</span></span>

9. <span data-ttu-id="e2fea-130">[**OK**] をクリックして正規化ルールを保存します。</span><span class="sxs-lookup"><span data-stu-id="e2fea-130">Click **OK** to save the normalization rule.</span></span>

10. <span data-ttu-id="e2fea-131">[**OK**] をクリックしてダイヤル プランを保存します。</span><span class="sxs-lookup"><span data-stu-id="e2fea-131">Click **OK** to save the dial plan.</span></span>

11. <span data-ttu-id="e2fea-132">[**ダイヤル プラン**] ページで [**確定**] をクリックして、[**すべて確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2fea-132">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e2fea-133">正規化ルールを作成または変更するときにはいつでも、[**すべて確定**] コマンドを実行して構成の変更を公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2fea-133">Whenever you create or change a normalization rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="e2fea-134">詳細については、「 [Skype For business の音声ルーティング構成に保留中の変更を発行する](voice-route-config-changes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2fea-134">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

### <a name="to-define-a-normalization-rule-manually"></a><span data-ttu-id="e2fea-135">正規化ルールを手動で定義するには</span><span class="sxs-lookup"><span data-stu-id="e2fea-135">To define a normalization rule manually</span></span>

1. <span data-ttu-id="e2fea-136">Skype for Business Server コントロールパネルを開く</span><span class="sxs-lookup"><span data-stu-id="e2fea-136">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="e2fea-137">省略「 [Skype For Business Server でダイヤルプランを作成または変更](dial-plans.md)する」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="e2fea-137">(Optional) Follow the steps in [Create or modify a dial plan in Skype for Business Server](dial-plans.md).</span></span>

3. <span data-ttu-id="e2fea-138">[**新しい正規化ルール**] または [**正規化ルールの編集**] で、**名前**に正規化されている番号パターンを説明する名前を入力します (たとえば、"正規化 rule5DigitExtension" という名前を入力します)。</span><span class="sxs-lookup"><span data-stu-id="e2fea-138">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example, name the normalization rule5DigitExtension).</span></span>

4. <span data-ttu-id="e2fea-139">(オプション) [**説明**] ボックスに、正規化ルールの説明を入力します (たとえば、「5 桁の内線番号を変換」)。</span><span class="sxs-lookup"><span data-stu-id="e2fea-139">(Optional) In **Description** field, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

5. <span data-ttu-id="e2fea-140">[**正規化ルールの構築**] で [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2fea-140">In **Build a Normalization Rule**, click **Edit**.</span></span>

6. <span data-ttu-id="e2fea-141">[**正規表現の入力**] で次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="e2fea-141">Enter the following in **Type a Regular Expression**:</span></span>

   - <span data-ttu-id="e2fea-142">[**このパターンを照合**] で、ダイヤル電話番号を照合するために使用するパターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="e2fea-142">In **Match this pattern**, specify the pattern that you want to use to match the dialed phone number.</span></span>

   - <span data-ttu-id="e2fea-143">[**変換ルール**] で、変換される E.164 電話番号の形式のパターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="e2fea-143">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers.</span></span>

     <span data-ttu-id="e2fea-144">たとえば、"^ (\d) $"{7}と入力する\*\*\*\* と、**翻訳ルール**の "^ (\d) $" と + 1425 $ 1 と入力した場合、ルールは5550100から + 14255550100 に正規化されます。</span><span class="sxs-lookup"><span data-stu-id="e2fea-144">For example, if you enter ^(\d{7})$ in **Match this pattern** and+1425$1 in **Translation rule**, the rule normalizes 5550100 to +14255550100.</span></span>

7. <span data-ttu-id="e2fea-145">(オプション) 正規化ルールによって電話番号が組織の内線番号になる場合は、[**内線番号**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2fea-145">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

8. <span data-ttu-id="e2fea-p107">(オプション) 正規化ルールをテストする番号を入力し、[**実行**] をクリックします。テスト結果は、[**テストする番号の入力**] の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="e2fea-p107">(Optional) Enter a number to test the normalization rule and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>

9. <span data-ttu-id="e2fea-148">[**OK**] をクリックして正規化ルールを保存します。</span><span class="sxs-lookup"><span data-stu-id="e2fea-148">Click **OK** to save the normalization rule.</span></span>

10. <span data-ttu-id="e2fea-149">[**OK**] をクリックしてダイヤル プランを保存します。</span><span class="sxs-lookup"><span data-stu-id="e2fea-149">Click **OK** to save the dial plan.</span></span>

11. <span data-ttu-id="e2fea-150">[**ダイヤル プラン**] ページで [**確定**] をクリックして、[**すべて確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2fea-150">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e2fea-151">正規化ルールを作成または変更するときにはいつでも、[**すべて確定**] コマンドを実行して構成の変更を公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2fea-151">Whenever you create or change a normalization rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="e2fea-152">詳細については、「 [Skype For business の音声ルーティング構成に保留中の変更を発行する](voice-route-config-changes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2fea-152">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>


