---
title: Skype for Business Server で呼び出された ID プレゼンテーションの翻訳ルールを作成または変更する
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
ms.assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
description: '概要: Skype for Business Server の翻訳ルールの作成ツールを使用して、翻訳ルールを定義する方法について説明します。'
ms.openlocfilehash: 3c72e53044abe44660423bbd9bc1adbbeed2a3ed
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233785"
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server"></a><span data-ttu-id="c0acd-103">Skype for Business Server で呼び出された ID プレゼンテーションの翻訳ルールを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="c0acd-103">Create or modify a translation rule for called ID presentation in Skype for Business Server</span></span>

<span data-ttu-id="c0acd-104">**概要:** Skype for Business Server の翻訳ルールの作成ツールを使用して、翻訳ルールを定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c0acd-104">**Summary:** Learn how to define a translation rule by using the Build a Translation Rule tool in Skype for Business Server.</span></span>

<span data-ttu-id="c0acd-105">翻訳ルールを定義する場合は、次の手順に従います。**翻訳**ルールツールで値のセットを入力し、Skype For Business Server コントロールパネルを有効にすると、対応する一致パターンと翻訳ルールが生成されます。</span><span class="sxs-lookup"><span data-stu-id="c0acd-105">Follow these steps if you want to define a translation rule by entering a set of values in the **Build a Translation Rule** tool and enabling Skype for Business Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="c0acd-106">または、手動で正規表現を記述して一致パターンと変換ルールを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="c0acd-106">Alternatively, you can a write regular expression manually to define the matching pattern and translation rule.</span></span> <span data-ttu-id="c0acd-107">詳細については、「[Create or Modify a Translation Rule Manually](https://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0acd-107">For details, see [Create or Modify a Translation Rule Manually](https://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx).</span></span>

### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a><span data-ttu-id="c0acd-108">変換ルールの構築ツールを使用してルールを定義するには</span><span class="sxs-lookup"><span data-stu-id="c0acd-108">To define a rule by using the Build a Translation Rule tool</span></span>

1. <span data-ttu-id="c0acd-109">Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c0acd-109">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="c0acd-110">翻訳ルールの定義を開始するには、「 [skype For Business server でメディアバイパスを使用してトランクを構成](configure-trunk-with-media-bypass.md)する」を参照するか、手順9から[Skype for business server でメディアバイパスを構成](configure-trunk-without-media-bypass.md)します。</span><span class="sxs-lookup"><span data-stu-id="c0acd-110">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md) through step 9.</span></span>

3. <span data-ttu-id="c0acd-111">[**新しい変換ルール**] ページまたは [**変換ルールの編集**] ページの [**名前**] に、変換対象の番号パターンを説明する名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="c0acd-111">Under **Name** on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

4. <span data-ttu-id="c0acd-112">省略[**説明**] に、翻訳ルールの説明を入力します (例: 米国国際長距離電話)。</span><span class="sxs-lookup"><span data-stu-id="c0acd-112">(Optional) Under **Description**, type a description of the translation rule, for example US International long-distance dialing.</span></span>

5. <span data-ttu-id="c0acd-113">ダイアログ ボックスの [**変換ルールの構築**] セクションの次のフィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="c0acd-113">In the **Build a Translation Rule** section of the dialog box, enter values in the following fields:</span></span>

   - <span data-ttu-id="c0acd-114">[**開始番号**]: (オプション) パターンに一致させる番号の先頭の番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="c0acd-114">**Starting digits**: (Optional) Specify the leading digits of numbers you want the pattern to match.</span></span> <span data-ttu-id="c0acd-115">たとえば、+ で開始される E.164 形式の番号に一致させるには、このフィールドに「+」を入力します。</span><span class="sxs-lookup"><span data-stu-id="c0acd-115">For example, enter + in this field to match numbers in E.164 format (which begin with +).</span></span>

   - <span data-ttu-id="c0acd-116">[**長さ**]: 一致パターンの桁数を指定し、パターンをこの長さと同じ桁数の番号に一致させるか、この長さ以上の番号に一致させるか、どの長さの番号にも一致させるかを選択します。</span><span class="sxs-lookup"><span data-stu-id="c0acd-116">**Length**: Specify the number of digits in the matching pattern and select whether you want the pattern to match numbers that are this length exactly, at least this length, or any length.</span></span> <span data-ttu-id="c0acd-117">たとえば、11桁以上の数字を一致させるには、「11」と入力し、ドロップダウンリストで少なくとも1つを選択します。</span><span class="sxs-lookup"><span data-stu-id="c0acd-117">For example, enter 11 and selectAt least in the drop-down list to match numbers that are at least 11 digits in length.</span></span>

   - <span data-ttu-id="c0acd-118">[**削除する番号**]: (オプション) 開始番号から削除する桁数を指定します。</span><span class="sxs-lookup"><span data-stu-id="c0acd-118">**Digits to remove**: (Optional) Specify the number of starting digits to be removed.</span></span> <span data-ttu-id="c0acd-119">たとえば、「1」と入力すると、番号の先頭から + が取り除かれます。</span><span class="sxs-lookup"><span data-stu-id="c0acd-119">For example, enter 1 to strip out the+ from the beginning of the number.</span></span>

   - <span data-ttu-id="c0acd-120">[**追加する番号**]: (オプション) 変換済みの番号の先頭に追加する番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="c0acd-120">**Digits to add**: (Optional) Specify digits to be prepended to the translated numbers.</span></span> <span data-ttu-id="c0acd-121">たとえば、ルール適用時、変換済みの番号の先頭に 011 を追加したい場合は、「011」と入力します。</span><span class="sxs-lookup"><span data-stu-id="c0acd-121">For example, enter 011 if you want 011 to be prepended to the translated numbers when the rule is applied.</span></span>

     <span data-ttu-id="c0acd-p106">これらのフィールドに入力した値は、[**一致するパターン**] フィールドおよび [**変換ルール**] フィールドに反映されます。たとえば、上述の例の値を指定した場合、[**一致するパターン**] フィールドに設定される正規表現は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="c0acd-p106">The values you enter in these fields are reflected in the **Pattern to match** and **Translation rule** fields. For example, if you specify the preceding example values, the resulting regular expression in the **Pattern to match** field is:</span></span>

     <span data-ttu-id="c0acd-124">^\+(\d{9}\d +) $</span><span class="sxs-lookup"><span data-stu-id="c0acd-124">^\+(\d{9}\d+)$</span></span>

     <span data-ttu-id="c0acd-125">[**変換ルール**] フィールドには、変換済みの番号の形式のパターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="c0acd-125">The **Translation rule** field specifies a pattern for the format of translated numbers.</span></span> <span data-ttu-id="c0acd-126">このパターンには、次の 2 つのパーツがあります。</span><span class="sxs-lookup"><span data-stu-id="c0acd-126">This pattern has two parts:</span></span>

   - <span data-ttu-id="c0acd-127">一致パターンの桁数を表す値 ($1 など)</span><span class="sxs-lookup"><span data-stu-id="c0acd-127">A value (for example, $1) that represents the number of digits in the matching pattern</span></span>

   - <span data-ttu-id="c0acd-128">(オプション) [**追加する番号**] フィールドに入力することで先頭に追加できる値</span><span class="sxs-lookup"><span data-stu-id="c0acd-128">(Optional) A value that you can prepend by entering it in the **Digits to add** field</span></span>

     <span data-ttu-id="c0acd-129">上述の例の値を使用した場合、[変換ルール] フィールドに **011$1** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c0acd-129">Using the preceding example values, 011$1 appears in the **Translation rule** field.</span></span>

     <span data-ttu-id="c0acd-130">この変換ルールを適用すると、+441235551010 が 011441235551010 になります。</span><span class="sxs-lookup"><span data-stu-id="c0acd-130">When this translation rule is applied, +441235551010 becomes 011441235551010.</span></span>

6. <span data-ttu-id="c0acd-131">[**OK**] をクリックして変換ルールを保存します。</span><span class="sxs-lookup"><span data-stu-id="c0acd-131">Click **OK** to save the translation rule.</span></span>

7. <span data-ttu-id="c0acd-132">[**OK**] をクリックしてトランク構成を保存します。</span><span class="sxs-lookup"><span data-stu-id="c0acd-132">Click **OK** to save the trunk configuration.</span></span>

8. <span data-ttu-id="c0acd-133">[**トランク構成**] ページで [**確定**] をクリックして、[**すべて確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0acd-133">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c0acd-134">変換ルールを作成または変更したときは必ず、[**すべて確定**] コマンドを実行して構成の変更を公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0acd-134">Whenever you create or modify a translation rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="c0acd-135">詳細については、「 [Skype For business の音声ルーティング構成に保留中の変更を発行する](voice-route-config-changes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0acd-135">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

### <a name="to-define-a-translation-rule-manually"></a><span data-ttu-id="c0acd-136">変換ルールを手動で定義するには</span><span class="sxs-lookup"><span data-stu-id="c0acd-136">To define a translation rule manually</span></span>

1. <span data-ttu-id="c0acd-137">Skype for Business Server コントロールパネルを開く</span><span class="sxs-lookup"><span data-stu-id="c0acd-137">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="c0acd-138">翻訳ルールの定義を開始するには、「 [skype For Business server でメディアバイパスを使用してトランクを構成](configure-trunk-with-media-bypass.md)する」を参照するか、手順9から[Skype for business server でメディアバイパスを構成](configure-trunk-without-media-bypass.md)します。</span><span class="sxs-lookup"><span data-stu-id="c0acd-138">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md) through step 9.</span></span>

3. <span data-ttu-id="c0acd-139">[**新しい変換ルール**] ページまたは [**変換ルールの編集**] ページの [**名前**] フィールドに、変換対象の番号パターンを説明する名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="c0acd-139">In the **Name** field on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

4. <span data-ttu-id="c0acd-140">省略[**説明**] に、翻訳ルールの説明を入力します (例: 米国国際長距離電話)。</span><span class="sxs-lookup"><span data-stu-id="c0acd-140">(Optional) In **Description**, type a description of the translation rule, for example US International long-distance dialing.</span></span>

5. <span data-ttu-id="c0acd-141">[**変換ルールの構築**] セクションの一番下にある [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0acd-141">Click **Edit** at the bottom of the **Build a Translation Rule** section.</span></span>

6. <span data-ttu-id="c0acd-142">[**正規表現の入力**] で次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="c0acd-142">Enter the following in **Type a Regular Expression**:</span></span>

   - <span data-ttu-id="c0acd-143">[**このパターンと一致**] に、変換する番号を照合するために使用するパターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="c0acd-143">In **Match this pattern**, specify the pattern that will be used to match the numbers to be translated.</span></span>

   - <span data-ttu-id="c0acd-144">[**変換ルール**] に、変換される番号の形式のパターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="c0acd-144">In **Translation rule**, specify a pattern for the format of translated numbers.</span></span>

     <span data-ttu-id="c0acd-145">\+たとえば、"^ (\d{9}\d +) $" と入力すると、**翻訳ルール**の and011 $ 1 というパターンになります。**この**ルールは、+ 441235551010 から011441235551010に翻訳されます。</span><span class="sxs-lookup"><span data-stu-id="c0acd-145">For example, if you enter ^\+(\d{9}\d+)$ in **Match this pattern** and011$1 in **Translation rule**, the rule will translate +441235551010 to 011441235551010.</span></span>

7. <span data-ttu-id="c0acd-146">[**OK**] をクリックして変換ルールを保存します。</span><span class="sxs-lookup"><span data-stu-id="c0acd-146">Click **OK** to save the translation rule.</span></span>

8. <span data-ttu-id="c0acd-147">[**OK**] をクリックしてトランク構成を保存します。</span><span class="sxs-lookup"><span data-stu-id="c0acd-147">Click **OK** to save the trunk configuration.</span></span>

9. <span data-ttu-id="c0acd-148">[**トランク構成**] ページで [**確定**] をクリックして、[**すべて確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0acd-148">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c0acd-149">変換ルールを作成または変更したときは必ず、[**すべて確定**] コマンドを実行して構成の変更を公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0acd-149">Whenever you create or modify a translation rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="c0acd-150">詳細については、「 [Skype For business の音声ルーティング構成に保留中の変更を発行する](voice-route-config-changes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0acd-150">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="c0acd-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="c0acd-151">See also</span></span>

[<span data-ttu-id="c0acd-152">Skype for Business Server でメディアバイパスを使用してトランクを構成する</span><span class="sxs-lookup"><span data-stu-id="c0acd-152">Configure a trunk with media bypass in Skype for Business Server</span></span>](configure-trunk-with-media-bypass.md)

[<span data-ttu-id="c0acd-153">Skype for Business Server でメディアをバイパスせずにトランクを構成する</span><span class="sxs-lookup"><span data-stu-id="c0acd-153">Configure a trunk without media bypass in Skype for Business Server</span></span>](configure-trunk-without-media-bypass.md)

[<span data-ttu-id="c0acd-154">Skype for Business の音声ルーティング構成に保留中の変更を公開する</span><span class="sxs-lookup"><span data-stu-id="c0acd-154">Publish pending changes to the voice routing configuration in Skype for Business</span></span>](voice-route-config-changes.md)

[<span data-ttu-id="c0acd-155">Skype for Business Server でメディアバイパスを展開する</span><span class="sxs-lookup"><span data-stu-id="c0acd-155">Deploy media bypass in Skype for Business Server</span></span>](deploy-media-bypass.md)

