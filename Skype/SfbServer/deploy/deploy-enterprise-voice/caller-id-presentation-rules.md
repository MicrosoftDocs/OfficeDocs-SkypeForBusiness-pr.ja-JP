---
title: Skype for Business Server で発信者 ID プレゼンテーションの翻訳ルールを作成または変更する
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
ms.assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
description: '概要: Skype for Business Server コントロール パネルを使用して発信者 ID を構成する方法について学習します。'
ms.openlocfilehash: 2ffe547927c9f4d6df16a06cc8c95dff9814fc7f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113033"
---
# <a name="create-or-modify-a-translation-rule-for-caller-id-presentation-in-skype-for-business-server"></a><span data-ttu-id="87cff-103">Skype for Business Server で発信者 ID プレゼンテーションの翻訳ルールを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="87cff-103">Create or modify a translation rule for caller ID presentation in Skype for Business Server</span></span>

<span data-ttu-id="87cff-104">**概要:** Skype for Business Server コントロール パネルを使用して発信者 ID を構成する方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="87cff-104">**Summary:** Learn how to configure Caller ID by using the Skype for Business Server Control Panel.</span></span>

<span data-ttu-id="87cff-105">Skype for Business Server では、呼び出し側の電話番号 (つまり、呼び出された電話番号) を E.164 形式から、トランク ピア  _(関連_ 付けられたゲートウェイ、プライベート ブランチ 交換 (PBX)、または SIP トランク) で必要なローカル ダイヤル形式に変換できます。</span><span class="sxs-lookup"><span data-stu-id="87cff-105">With Skype for Business Server, the called party's phone number (that is, the phone number called) can be translated from E.164 format to the local dialing format that is required by the  _trunk peer_ (that is, the associated gateway, private branch exchange (PBX), or SIP trunk).</span></span> <span data-ttu-id="87cff-106">これを行うためには、トランク ピアへのルーティングの前に要求 URI を変換する変換ルールを 1 つ以上定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="87cff-106">To do this, you must define one or more translation rules to translate the Request URI before routing it to the trunk peer.</span></span>

<span data-ttu-id="87cff-107">また、Skype for Business Server では、発信者の電話番号 (発信者が呼び出している電話番号) を E.164 形式からトランク ピアで必要なローカル ダイヤル形式に変換することもできます。</span><span class="sxs-lookup"><span data-stu-id="87cff-107">Skype for Business Server also gives you the option to also translate the calling party's phone number (that is, the phone number that the caller is calling from) from E.164 format to the local dialing format that is required by the trunk peer.</span></span> <span data-ttu-id="87cff-108">たとえば、ダイヤル文字列の冒頭から +44 を取り除いて 0114 に置き換える変換ルールを記述できます。</span><span class="sxs-lookup"><span data-stu-id="87cff-108">For example, you can write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>

### <a name="to-configure-caller-id-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="87cff-109">Skype for Business Server コントロール パネルを使用して発信者 ID を構成するには</span><span class="sxs-lookup"><span data-stu-id="87cff-109">To configure Caller ID by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="87cff-110">Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="87cff-110">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="87cff-111">左側のナビゲーション バーで [**音声のルーティング**] をクリックし、[**トランク構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="87cff-111">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

3. <span data-ttu-id="87cff-112">[**トランク構成**] ページで、既存のトランク (たとえば [**グローバル**] トランク) をダブルクリックして [**編集トランク構成**] ダイアログ ボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="87cff-112">On the **Trunk Configuration** page, double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>

4. <span data-ttu-id="87cff-113">発信者番号のプレゼンテーションを構成するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="87cff-113">To configure caller ID presentation:</span></span>

   - <span data-ttu-id="87cff-114">エンタープライズ VoIP 展開で利用できるすべての変換ルールの一覧から 1 つ以上のルールを選択するには、**[選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="87cff-114">To choose one or more rules from a list of all translation rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="87cff-115">[**発信者番号の変換ルール**] で、トランクに関連付けるルールをクリックし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="87cff-115">In **Calling number translation rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>

   - <span data-ttu-id="87cff-116">新しい変換ルールを定義してトランクに関連付ける場合は、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="87cff-116">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="87cff-117">新しいルールの定義の詳細については、「展開」のドキュメント  [の「翻訳](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules) ルールの定義」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87cff-117">For details about defining a new rule, see  [Defining Translation Rules](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules) in the Deployment documentation.</span></span>

   - <span data-ttu-id="87cff-118">既にトランクに関連付けられている変換ルールを編集するには、ルールの名前をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="87cff-118">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="87cff-119">詳細については、「展開」のドキュメントの「[Defining Translation Rules](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87cff-119">For details, see [Defining Translation Rules](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules) in the Deployment documentation.</span></span>

   - <span data-ttu-id="87cff-120">既存の変換ルールをコピーしてそれを基に新しいルールを定義するには、ルールの名前をクリックして [**コピー**] をクリックし、[**貼り付け**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="87cff-120">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="87cff-121">詳細については、「[Defining Translation Rules](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87cff-121">For details, see [Defining Translation Rules](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules).</span></span>

   - <span data-ttu-id="87cff-122">トランクから変換ルールを削除するには、ルールの名前を選択状態にし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="87cff-122">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>

     > [!CAUTION]
     > <span data-ttu-id="87cff-123">関連付けられたトランク ピアに対して変換ルールを構成している場合は、2 つのルールが競合する危険があるため、変換ルールをトランクに関連付けないでください。</span><span class="sxs-lookup"><span data-stu-id="87cff-123">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>