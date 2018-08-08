---
title: 作成するか、ビジネスの Skype の正規化ルールを変更
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
description: '概要: 定義、作成、および業務サーバーの Skype の正規化ルールを変更する方法を説明します。'
ms.openlocfilehash: d9c56d96c0eb9069e4ec02b196a326ad8b599e75
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20972549"
---
# <a name="create-or-modify-a-normalization-rule-in-skype-for-business"></a><span data-ttu-id="e7486-103">作成するか、ビジネスの Skype の正規化ルールを変更</span><span class="sxs-lookup"><span data-stu-id="e7486-103">Create or modify a normalization rule in Skype for Business</span></span>
 
<span data-ttu-id="e7486-104">**の概要:** 定義、作成、および業務サーバーの Skype の正規化ルールを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e7486-104">**Summary:** Learn how to define, create, and modify a normalization rule in Skype for Business Server.</span></span>
  
<span data-ttu-id="e7486-105">定義、作成、および業務サーバーの Skype での正規化ルールを変更します。</span><span class="sxs-lookup"><span data-stu-id="e7486-105">Define, create, and modify normalization rules in Skype for Business Server.</span></span>
  
### <a name="to-define-a-normalization-rule-by-using-build-a-normalization-rule"></a><span data-ttu-id="e7486-106">[正規化ルールの構築] を使用して正規化ルールを定義するには</span><span class="sxs-lookup"><span data-stu-id="e7486-106">To define a normalization rule by using Build a Normalization Rule</span></span>

1. <span data-ttu-id="e7486-107">ビジネス サーバーのコントロール パネルの Skype を開く</span><span class="sxs-lookup"><span data-stu-id="e7486-107">Open Skype for Business Server Control Panel</span></span>
    
2. <span data-ttu-id="e7486-108">(省略可能)手順に従って、[を作成するまたはビジネス サーバーの Skype のダイヤル プランを変更する](dial-plans.md)手順 11] または [ステップ 10 の[ダイヤル プランの変更](http://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx)をします。</span><span class="sxs-lookup"><span data-stu-id="e7486-108">(Optional) Follow the steps in [Create or modify a dial plan in Skype for Business Server](dial-plans.md) through step 11 or [Modify a Dial Plan](http://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx) through step 10.</span></span>
    
3. <span data-ttu-id="e7486-109">**新しい正規化ルール**または**正規化ルールの編集**、**名前**(たとえば、5DigitExtension) で標準化されている番号のパターンを説明する名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="e7486-109">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example,5DigitExtension).</span></span>
    
4. <span data-ttu-id="e7486-110">(オプション) [**説明**] ボックスに、正規化ルールの説明を入力します (たとえば、「5 桁の内線番号を変換」)。</span><span class="sxs-lookup"><span data-stu-id="e7486-110">(Optional) In **Description**, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>
    
5. <span data-ttu-id="e7486-111">[**正規化ルールの構築**] で、次のフィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="e7486-111">In **Build a Normalization Rule**, enter values in the following fields:</span></span>
    
   - <span data-ttu-id="e7486-112">**開始桁の数字**(省略可能)パターンの一致するようにダイヤルする番号の先頭の桁を指定します。</span><span class="sxs-lookup"><span data-stu-id="e7486-112">**Starting digits** (Optional) Specify the leading digits of dialed numbers you want the pattern to match.</span></span> <span data-ttu-id="e7486-113">たとえば、type425 と一致するパターンをする場合はダイヤル 425 から始まる番号。</span><span class="sxs-lookup"><span data-stu-id="e7486-113">For example, type425 if you want the pattern to match dialed numbers beginning with 425.</span></span>
    
   - <span data-ttu-id="e7486-114">**長さ**一致するパターンの桁数を指定し、この長さを正確に一致するパターンをする、ダイヤルする長さでは、少なくとも番号を一致または一致する任意の長さの番号をダイヤルするかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="e7486-114">**Length** Specify the number of digits in the matching pattern and select whether you want the pattern to match this length exactly, match dialed numbers that are at least this length, or match dialed numbers of any length.</span></span>
    
   - <span data-ttu-id="e7486-115">**桁を削除するには**(省略可能)数の指定と一致するパターンをダイヤルした番号から削除する桁数を開始します。</span><span class="sxs-lookup"><span data-stu-id="e7486-115">**Digits to remove** (Optional) Specify the number of starting digits to be removed from dialed numbers you want the pattern to match.</span></span>
    
   - <span data-ttu-id="e7486-116">**数字を追加するには**(省略可能)パターンの一致するようにダイヤルした番号に追加する数字を指定します。</span><span class="sxs-lookup"><span data-stu-id="e7486-116">**Digits to add** (Optional) Specify digits to be added to dialed numbers you want the pattern to match.</span></span>
    
    <span data-ttu-id="e7486-117">これらのフィールドに入力する値は、[**一致パターン**] および [**変換ルール**] に反映されます。</span><span class="sxs-lookup"><span data-stu-id="e7486-117">The values you enter in these fields are reflected in **Pattern to match** and **Translation rule**.</span></span> <span data-ttu-id="e7486-118">[**長さ**] フィールドに空、type7 を**開始桁の数字**のままにして、**正確に**、選択および**削除するのには数字**で 0 を指定すると結果として得られる正規表現**と一致するパターン**では。</span><span class="sxs-lookup"><span data-stu-id="e7486-118">For example, if you leave **Starting digits** empty, type7 into the **Length** field and select **Exactly**, and specify 0 in **Digits to remove**, the resulting regular expression in the **Pattern to match** is:</span></span>
    
    <span data-ttu-id="e7486-119">^(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="e7486-119">^(\d{7})$</span></span>
    
6. <span data-ttu-id="e7486-120">[**変換ルール**] で、変換される E.164 電話番号の形式のパターンを次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="e7486-120">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers as follows:</span></span>
    
   - <span data-ttu-id="e7486-121">一致パターンで指定した桁数を表す値。</span><span class="sxs-lookup"><span data-stu-id="e7486-121">A value that represents the number of digits specified in the matching pattern.</span></span> <span data-ttu-id="e7486-122">たとえば、一致するパターンは、^(\d{7})$、$1 の書き換えルールは 7 桁のダイヤルした番号です。</span><span class="sxs-lookup"><span data-stu-id="e7486-122">For example, if the matching pattern is ^(\d{7})$ then$1 in the translation rule represents 7-digit dialed numbers.</span></span>
    
   - <span data-ttu-id="e7486-123">(省略可能)変換された数値 (たとえば、+1425) に前置する桁数を指定する**数字を追加する**フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="e7486-123">(Optional) Type a value into the **Digits to add** field to specify digits to be prepended to the translated number (for example,+1425).</span></span>
    
    <span data-ttu-id="e7486-124">**一致させるパターン**が含まれている場合など、^(\d{7})$ のパターンとしては、番号をダイヤルし、**翻訳ルール**が含まれています + 1425 E.164 のパターンとして、$1 では電話番号、ルールが +14255550100 に 5550100 を正規化します。</span><span class="sxs-lookup"><span data-stu-id="e7486-124">For example, if **Pattern to match** contains^(\d{7})$ as the pattern for dialed numbers and **Translation rule** contains+1425$1 as the pattern for E.164 phone numbers, the rule normalizes 5550100 to +14255550100.</span></span>
    
7. <span data-ttu-id="e7486-125">(オプション) 正規化ルールによって電話番号が組織の内線番号になる場合は、[**内線番号**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7486-125">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>
    
8. <span data-ttu-id="e7486-p104">(オプション) 正規化ルールをテストする番号を入力し、[**実行**] をクリックします。テスト結果は、[**テストする番号の入力**] の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7486-p104">(Optional) Enter a number to test the normalization rule, and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e7486-128">テストにまだ合格していない正規化ルールは、保存しておいて後で再構成できます。</span><span class="sxs-lookup"><span data-stu-id="e7486-128">You can save a normalization rule that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="e7486-129">詳細については、[音声ルーティングのテスト](http://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7486-129">For details, see [Test Voice Routing](http://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx).</span></span> 
  
9. <span data-ttu-id="e7486-130">[**OK**] をクリックして正規化ルールを保存します。</span><span class="sxs-lookup"><span data-stu-id="e7486-130">Click **OK** to save the normalization rule.</span></span>
    
10. <span data-ttu-id="e7486-131">[**OK**] をクリックしてダイヤル プランを保存します。</span><span class="sxs-lookup"><span data-stu-id="e7486-131">Click **OK** to save the dial plan.</span></span>
    
11. <span data-ttu-id="e7486-132">[**ダイヤル プラン**] ページで [**確定**] をクリックして、[**すべて確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e7486-132">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="e7486-133">正規化ルールを作成または変更するときにはいつでも、[**すべて確定**] コマンドを実行して構成の変更を公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7486-133">Whenever you create or change a normalization rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="e7486-134">詳細については、操作マニュアルの[発行保留中のビジネス用の Skype で音声ルーティング構成の変更](voice-route-config-changes.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7486-134">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>
  
### <a name="to-define-a-normalization-rule-manually"></a><span data-ttu-id="e7486-135">正規化ルールを手動で定義するには</span><span class="sxs-lookup"><span data-stu-id="e7486-135">To define a normalization rule manually</span></span>

1. <span data-ttu-id="e7486-136">ビジネス サーバーのコントロール パネルの Skype を開く</span><span class="sxs-lookup"><span data-stu-id="e7486-136">Open Skype for Business Server Control Panel</span></span>
    
2. <span data-ttu-id="e7486-137">(省略可能)手順に従って、[を作成するまたはビジネス サーバーの Skype のダイヤル プランを変更する](dial-plans.md)です。</span><span class="sxs-lookup"><span data-stu-id="e7486-137">(Optional) Follow the steps in [Create or modify a dial plan in Skype for Business Server](dial-plans.md).</span></span> 
    
3. <span data-ttu-id="e7486-138">**新しい正規化ルール**または**正規化ルールの編集**では、(たとえば、正規化の rule5DigitExtension の名前) の**名前**で標準化されている番号のパターンを説明する名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="e7486-138">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example, name the normalization rule5DigitExtension).</span></span>
    
4. <span data-ttu-id="e7486-139">(オプション) [**説明**] ボックスに、正規化ルールの説明を入力します (たとえば、「5 桁の内線番号を変換」)。</span><span class="sxs-lookup"><span data-stu-id="e7486-139">(Optional) In **Description** field, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>
    
5. <span data-ttu-id="e7486-140">[**正規化ルールの構築**] で [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e7486-140">In **Build a Normalization Rule**, click **Edit**.</span></span>
    
6. <span data-ttu-id="e7486-141">[**正規表現の入力**] で次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="e7486-141">Enter the following in **Type a Regular Expression**:</span></span>
    
   - <span data-ttu-id="e7486-142">[**このパターンを照合**] で、ダイヤル電話番号を照合するために使用するパターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="e7486-142">In **Match this pattern**, specify the pattern that you want to use to match the dialed phone number.</span></span>
    
   - <span data-ttu-id="e7486-143">[**変換ルール**] で、変換される E.164 電話番号の形式のパターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="e7486-143">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers.</span></span>
    
    <span data-ttu-id="e7486-144">入力する場合など、^(\d{7})**このパターンの一致**で $ と 1425 +**翻訳ルール**ルールでは 1 ドルが +14255550100 に 5550100 を正規化します。</span><span class="sxs-lookup"><span data-stu-id="e7486-144">For example, if you enter ^(\d{7})$ in **Match this pattern** and+1425$1 in **Translation rule**, the rule normalizes 5550100 to +14255550100.</span></span>
    
7. <span data-ttu-id="e7486-145">(オプション) 正規化ルールによって電話番号が組織の内線番号になる場合は、[**内線番号**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7486-145">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>
    
8. <span data-ttu-id="e7486-p107">(オプション) 正規化ルールをテストする番号を入力し、[**実行**] をクリックします。テスト結果は、[**テストする番号の入力**] の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7486-p107">(Optional) Enter a number to test the normalization rule and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>
    
9. <span data-ttu-id="e7486-148">[**OK**] をクリックして正規化ルールを保存します。</span><span class="sxs-lookup"><span data-stu-id="e7486-148">Click **OK** to save the normalization rule.</span></span>
    
10. <span data-ttu-id="e7486-149">[**OK**] をクリックしてダイヤル プランを保存します。</span><span class="sxs-lookup"><span data-stu-id="e7486-149">Click **OK** to save the dial plan.</span></span>
    
11. <span data-ttu-id="e7486-150">[**ダイヤル プラン**] ページで [**確定**] をクリックして、[**すべて確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e7486-150">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e7486-151">正規化ルールを作成または変更するときにはいつでも、[**すべて確定**] コマンドを実行して構成の変更を公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7486-151">Whenever you create or change a normalization rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="e7486-152">詳細については、操作マニュアルの[発行保留中のビジネス用の Skype で音声ルーティング構成の変更](voice-route-config-changes.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7486-152">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>
  

