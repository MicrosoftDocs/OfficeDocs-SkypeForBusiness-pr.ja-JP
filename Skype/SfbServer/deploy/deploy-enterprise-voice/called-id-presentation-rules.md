---
title: Skype for Business Server 2015 での着信者番号のプレゼンテーションの変換ルールの作成または変更
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
description: '概要: ビジネス サーバー 2015 の Skype でビルド規則の翻訳ツールを使用して変換ルールを定義する方法を説明します。'
ms.openlocfilehash: aa433375ad4dfa2dcc0c141d36b6d51ae28647f1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server-2015"></a><span data-ttu-id="5d556-103">Skype for Business Server 2015 での着信者番号のプレゼンテーションの変換ルールの作成または変更</span><span class="sxs-lookup"><span data-stu-id="5d556-103">Create or modify a translation rule for called ID presentation in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="5d556-104">**の概要:**ビジネス サーバー 2015 の Skype でビルド規則の翻訳ツールを使用して変換ルールを定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5d556-104">**Summary:** Learn how to define a translation rule by using the Build a Translation Rule tool in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="5d556-105">**変換ルールの構築**ツールの一連の値を入力して、Skype ビジネス サーバーのコントロール パネルの対応する一致パターンと変換ルールを生成するを有効にすることにより翻訳ルールを定義する場合は、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5d556-105">Follow these steps if you want to define a translation rule by entering a set of values in the **Build a Translation Rule** tool and enabling Skype for Business Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="5d556-106">または、手動で正規表現を記述して一致パターンと変換ルールを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="5d556-106">Alternatively, you can a write regular expression manually to define the matching pattern and translation rule.</span></span> <span data-ttu-id="5d556-107">詳細については、[作成または変更を手動での翻訳ルール](http://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d556-107">For details, see [Create or Modify a Translation Rule Manually](http://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx).</span></span>
  
### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a><span data-ttu-id="5d556-108">変換ルールの構築ツールを使用してルールを定義するには</span><span class="sxs-lookup"><span data-stu-id="5d556-108">To define a rule by using the Build a Translation Rule tool</span></span>

1. <span data-ttu-id="5d556-109">Skype をビジネス サーバーのコントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="5d556-109">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="5d556-110">変換ルールを定義するには、まずの手順に従って操作[ビジネス サーバー 2015 の Skype でメディアを使用してトランクの構成をバイパス](configure-trunk-with-media-bypass.md)することで 10 のステップまたは[ビジネス サーバー 2015 の Skype でメディアのないトランクの構成をバイパス](configure-trunk-without-media-bypass.md)手順 9 を使用します。</span><span class="sxs-lookup"><span data-stu-id="5d556-110">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server 2015](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server 2015](configure-trunk-without-media-bypass.md) through step 9.</span></span>
    
3. <span data-ttu-id="5d556-111">[**新しい変換ルール**] ページまたは [**変換ルールの編集**] ページの [**名前**] に、変換対象の番号パターンを説明する名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="5d556-111">Under **Name** on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>
    
4. <span data-ttu-id="5d556-112">(省略可能)[**説明**] には、例の u. s. 国際市外通話のため、変換ルールの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="5d556-112">(Optional) Under **Description**, type a description of the translation rule, for example US International long-distance dialing.</span></span>
    
5. <span data-ttu-id="5d556-113">ダイアログ ボックスの [**変換ルールの構築**] セクションの次のフィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="5d556-113">In the **Build a Translation Rule** section of the dialog box, enter values in the following fields:</span></span>
    
   - <span data-ttu-id="5d556-114">[**開始番号**]: (オプション) パターンに一致させる番号の先頭の番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="5d556-114">**Starting digits**: (Optional) Specify the leading digits of numbers you want the pattern to match.</span></span> <span data-ttu-id="5d556-115">たとえば、入力 + E.164 の番号と一致するには、このフィールドに書式を設定 (から始まる +)。</span><span class="sxs-lookup"><span data-stu-id="5d556-115">For example, enter + in this field to match numbers in E.164 format (which begin with +).</span></span>
    
   - <span data-ttu-id="5d556-116">[**長さ**]: 一致パターンの桁数を指定し、パターンをこの長さと同じ桁数の番号に一致させるか、この長さ以上の番号に一致させるか、どの長さの番号にも一致させるかを選択します。</span><span class="sxs-lookup"><span data-stu-id="5d556-116">**Length**: Specify the number of digits in the matching pattern and select whether you want the pattern to match numbers that are this length exactly, at least this length, or any length.</span></span> <span data-ttu-id="5d556-117">11 と selectAt をたとえば、入力は、少なくとも 11 桁の番号と一致するドロップ ダウン リストで最低です。</span><span class="sxs-lookup"><span data-stu-id="5d556-117">For example, enter 11 and selectAt least in the drop-down list to match numbers that are at least 11 digits in length.</span></span>
    
   - <span data-ttu-id="5d556-118">[**削除する番号**]: (オプション) 開始番号から削除する桁数を指定します。</span><span class="sxs-lookup"><span data-stu-id="5d556-118">**Digits to remove**: (Optional) Specify the number of starting digits to be removed.</span></span> <span data-ttu-id="5d556-119">などを除外する場合は 1 を入力、+、番号の先頭から。</span><span class="sxs-lookup"><span data-stu-id="5d556-119">For example, enter 1 to strip out the+ from the beginning of the number.</span></span>
    
   - <span data-ttu-id="5d556-120">[**追加する番号**]: (オプション) 変換済みの番号の先頭に追加する番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="5d556-120">**Digits to add**: (Optional) Specify digits to be prepended to the translated numbers.</span></span> <span data-ttu-id="5d556-121">たとえば、011 にルールを適用すると変換後の番号に追加される場合は、011 を入力します。</span><span class="sxs-lookup"><span data-stu-id="5d556-121">For example, enter 011 if you want 011 to be prepended to the translated numbers when the rule is applied.</span></span>
    
    <span data-ttu-id="5d556-p106">これらのフィールドに入力した値は、[**一致するパターン**] フィールドおよび [**変換ルール**] フィールドに反映されます。たとえば、上述の例の値を指定した場合、[**一致するパターン**] フィールドに設定される正規表現は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="5d556-p106">The values you enter in these fields are reflected in the **Pattern to match** and **Translation rule** fields. For example, if you specify the preceding example values, the resulting regular expression in the **Pattern to match** field is:</span></span>
    
    <span data-ttu-id="5d556-124">^\+(\d{9}\d+)$</span><span class="sxs-lookup"><span data-stu-id="5d556-124">^\+(\d{9}\d+)$</span></span>
    
    <span data-ttu-id="5d556-p107">[**変換ルール**] フィールドには、変換済みの番号の形式のパターンを指定します。このパターンには、次の 2 つのパーツがあります。</span><span class="sxs-lookup"><span data-stu-id="5d556-p107">The **Translation rule** field specifies a pattern for the format of translated numbers. This pattern has two parts:</span></span>
    
   - <span data-ttu-id="5d556-127">一致パターンの桁数を表す値 (たとえば、$1)</span><span class="sxs-lookup"><span data-stu-id="5d556-127">A value (for example, $1) that represents the number of digits in the matching pattern</span></span>
    
   - <span data-ttu-id="5d556-128">(オプション) [**追加する番号**] フィールドに入力することで先頭に追加できる値</span><span class="sxs-lookup"><span data-stu-id="5d556-128">(Optional) A value that you can prepend by entering it in the **Digits to add** field</span></span>
    
    <span data-ttu-id="5d556-129">前の値の例、011 を使用して**変換ルール**] フィールドで $1 が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5d556-129">Using the preceding example values, 011$1 appears in the **Translation rule** field.</span></span>
    
    <span data-ttu-id="5d556-130">この変換ルールを適用すると、+441235551010 が 011441235551010 になります。</span><span class="sxs-lookup"><span data-stu-id="5d556-130">When this translation rule is applied, +441235551010 becomes 011441235551010.</span></span>
    
6. <span data-ttu-id="5d556-131">[**OK**] をクリックして変換ルールを保存します。</span><span class="sxs-lookup"><span data-stu-id="5d556-131">Click **OK** to save the translation rule.</span></span>
    
7. <span data-ttu-id="5d556-132">[**OK**] をクリックしてトランク構成を保存します。</span><span class="sxs-lookup"><span data-stu-id="5d556-132">Click **OK** to save the trunk configuration.</span></span>
    
8. <span data-ttu-id="5d556-133">[**トランク構成**] ページで [**確定**] をクリックして、[**すべて確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d556-133">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span> 
    
   > [!NOTE]
   > <span data-ttu-id="5d556-134">変換ルールを作成または変更したときは必ず、[**すべて確定**] コマンドを実行して構成の変更を公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d556-134">Whenever you create or modify a translation rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="5d556-135">詳細については、操作マニュアルの[発行保留中のビジネス 2015年の Skype で音声ルーティング構成の変更](voice-route-config-changes.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d556-135">For details, see [Publish pending changes to the voice routing configuration in Skype for Business 2015](voice-route-config-changes.md) in the Operations documentation.</span></span>
  
### <a name="to-define-a-translation-rule-manually"></a><span data-ttu-id="5d556-136">変換ルールを手動で定義するには</span><span class="sxs-lookup"><span data-stu-id="5d556-136">To define a translation rule manually</span></span>

1. <span data-ttu-id="5d556-137">ビジネス サーバーのコントロール パネルの Skype を開く</span><span class="sxs-lookup"><span data-stu-id="5d556-137">Open Skype for Business Server Control Panel</span></span>
    
2. <span data-ttu-id="5d556-138">変換ルールを定義するには、まずの手順に従って操作[ビジネス サーバー 2015 の Skype でメディアを使用してトランクの構成をバイパス](configure-trunk-with-media-bypass.md)することで 10 のステップまたは[ビジネス サーバー 2015 の Skype でメディアのないトランクの構成をバイパス](configure-trunk-without-media-bypass.md)手順 9 を使用します。</span><span class="sxs-lookup"><span data-stu-id="5d556-138">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server 2015](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server 2015](configure-trunk-without-media-bypass.md) through step 9.</span></span>
    
3. <span data-ttu-id="5d556-139">[**新しい変換ルール**] ページまたは [**変換ルールの編集**] ページの [**名前**] フィールドに、変換対象の番号パターンを説明する名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="5d556-139">In the **Name** field on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>
    
4. <span data-ttu-id="5d556-140">(省略可能)[**説明**] には、変換ルール、たとえば米国国際長距離通話の説明を入力がダイヤル中です。</span><span class="sxs-lookup"><span data-stu-id="5d556-140">(Optional) In **Description**, type a description of the translation rule, for example US International long-distance dialing.</span></span>
    
5. <span data-ttu-id="5d556-141">[**変換ルールの構築**] セクションの一番下にある [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d556-141">Click **Edit** at the bottom of the **Build a Translation Rule** section.</span></span>
    
6. <span data-ttu-id="5d556-142">[**正規表現の入力**] で次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="5d556-142">Enter the following in **Type a Regular Expression**:</span></span>
    
   - <span data-ttu-id="5d556-143">[**このパターンと一致**] に、変換する番号を照合するために使用するパターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="5d556-143">In **Match this pattern**, specify the pattern that will be used to match the numbers to be translated.</span></span>
    
   - <span data-ttu-id="5d556-144">[**変換ルール**] に、変換される番号の形式のパターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="5d556-144">In **Translation rule**, specify a pattern for the format of translated numbers.</span></span>
    
    <span data-ttu-id="5d556-145">入力する場合など、^\+(**このパターンに一致する**and011 の \d{9}\d+)$**変換ルール**ルールの中の $1 は、+441235551010 が 011441235551010 に変換します。</span><span class="sxs-lookup"><span data-stu-id="5d556-145">For example, if you enter ^\+(\d{9}\d+)$ in **Match this pattern** and011$1 in **Translation rule**, the rule will translate +441235551010 to 011441235551010.</span></span>
    
7. <span data-ttu-id="5d556-146">[**OK**] をクリックして変換ルールを保存します。</span><span class="sxs-lookup"><span data-stu-id="5d556-146">Click **OK** to save the translation rule.</span></span>
    
8. <span data-ttu-id="5d556-147">[**OK**] をクリックしてトランク構成を保存します。</span><span class="sxs-lookup"><span data-stu-id="5d556-147">Click **OK** to save the trunk configuration.</span></span>
    
9. <span data-ttu-id="5d556-148">[**トランク構成**] ページで [**確定**] をクリックして、[**すべて確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d556-148">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="5d556-149">変換ルールを作成または変更したときは必ず、[**すべて確定**] コマンドを実行して構成の変更を公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d556-149">Whenever you create or modify a translation rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="5d556-150">詳細については、操作マニュアルの[発行保留中のビジネス 2015年の Skype で音声ルーティング構成の変更](voice-route-config-changes.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d556-150">For details, see [Publish pending changes to the voice routing configuration in Skype for Business 2015](voice-route-config-changes.md) in the Operations documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5d556-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="5d556-151">See also</span></span>

#### 

[<span data-ttu-id="5d556-152">ビジネス サーバー 2015 の Skype でのメディア バイ パスを使用してトランクを構成します。</span><span class="sxs-lookup"><span data-stu-id="5d556-152">Configure a trunk with media bypass in Skype for Business Server 2015</span></span>](configure-trunk-with-media-bypass.md)
  
[<span data-ttu-id="5d556-153">ビジネス サーバー 2015 のメディアが Skype で省略せずに、トランクを構成します。</span><span class="sxs-lookup"><span data-stu-id="5d556-153">Configure a trunk without media bypass in Skype for Business Server 2015</span></span>](configure-trunk-without-media-bypass.md)
  
[<span data-ttu-id="5d556-154">発行保留中のビジネス 2015年の Skype で音声ルーティング構成の変更</span><span class="sxs-lookup"><span data-stu-id="5d556-154">Publish pending changes to the voice routing configuration in Skype for Business 2015</span></span>](voice-route-config-changes.md)
#### 

[<span data-ttu-id="5d556-155">ビジネス サーバー 2015 に Skype でのメディア バイ パスを展開します。</span><span class="sxs-lookup"><span data-stu-id="5d556-155">Deploy media bypass in Skype for Business Server 2015</span></span>](deploy-media-bypass.md)

