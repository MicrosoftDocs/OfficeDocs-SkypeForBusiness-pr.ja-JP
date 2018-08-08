---
title: 作成または Skype のビジネス サーバーの呼び出し元の ID をプレゼンテーションの変換ルールを変更します。
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
ms.assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
description: '概要: ビジネス サーバーのコントロール パネルの Skype を使用して、呼び出し元の ID を構成する方法を説明します。'
ms.openlocfilehash: 2748677c00e74de4b26cd62494d90dc44c4b5a6a
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "21000156"
---
# <a name="create-or-modify-a-translation-rule-for-caller-id-presentation-in-skype-for-business-server"></a><span data-ttu-id="02410-103">作成または Skype のビジネス サーバーの呼び出し元の ID をプレゼンテーションの変換ルールを変更します。</span><span class="sxs-lookup"><span data-stu-id="02410-103">Create or modify a translation rule for caller ID presentation in Skype for Business Server</span></span>
 
<span data-ttu-id="02410-104">**の概要:** ビジネス サーバーのコントロール パネルの Skype を使用して、呼び出し元の ID を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="02410-104">**Summary:** Learn how to configure Caller ID by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="02410-105">ビジネス サーバー、呼び出し先の電話番号を Skype で (つまり、電話番号と呼ばれる) (つまり、関連付けられているゲートウェイ、構内交換 (_トランク ピア_で必要とされるローカルのダイヤル形式に E.164 形式から変換することができますPBX)、または SIP トランク)。</span><span class="sxs-lookup"><span data-stu-id="02410-105">With Skype for Business Server, the called party's phone number (that is, the phone number called) can be translated from E.164 format to the local dialing format that is required by the  _trunk peer_ (that is, the associated gateway, private branch exchange (PBX), or SIP trunk).</span></span> <span data-ttu-id="02410-106">これを行うためには、トランク ピアへのルーティングの前に要求 URI を変換する変換ルールを 1 つ以上定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="02410-106">To do this, you must define one or more translation rules to translate the Request URI before routing it to the trunk peer.</span></span>
  
<span data-ttu-id="02410-107">Skype ビジネス サーバーのもこともできますも呼び出し元の関係者の電話番号 (つまりからの呼び出し元の呼び出しは、電話番号) を翻訳する E.164 形式からトランク ピアで必要とされるローカルのダイヤル形式にします。</span><span class="sxs-lookup"><span data-stu-id="02410-107">Skype for Business Server also gives you the option to also translate the calling party's phone number (that is, the phone number that the caller is calling from) from E.164 format to the local dialing format that is required by the trunk peer.</span></span> <span data-ttu-id="02410-108">たとえば、ダイヤル文字列の冒頭から +44 を取り除いて 0114 に置き換える変換ルールを記述できます。</span><span class="sxs-lookup"><span data-stu-id="02410-108">For example, you can write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>
  
### <a name="to-configure-caller-id-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="02410-109">ビジネス サーバーのコントロール パネルの Skype を使用して、呼び出し元の ID を構成するのには</span><span class="sxs-lookup"><span data-stu-id="02410-109">To configure Caller ID by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="02410-110">Skype をビジネス サーバーのコントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="02410-110">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="02410-111">左側のナビゲーション バーで [**音声ルーティング**] をクリックし、[**トランク構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02410-111">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>
    
3. <span data-ttu-id="02410-112">[**トランク構成**] ページで、既存のトランク (たとえば [**グローバル**] トランク) をダブルクリックして [**編集トランク構成**] ダイアログ ボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="02410-112">On the **Trunk Configuration** page, double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>
    
4. <span data-ttu-id="02410-113">発信者番号のプレゼンテーションを構成するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="02410-113">To configure caller ID presentation:</span></span>
    
   - <span data-ttu-id="02410-114">エンタープライズ VoIP 展開で利用可能なすべての変換ルールの一覧から 1 つまたは複数のルールを選択するのには [**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02410-114">To choose one or more rules from a list of all translation rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="02410-115">[**発信者番号の変換ルール**] で、トランクに関連付けるルールをクリックし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02410-115">In **Calling number translation rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
   - <span data-ttu-id="02410-116">新しい変換ルールを定義してトランクに関連付ける場合は、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02410-116">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="02410-117">新しいルールを定義する方法については、展開に関するドキュメントの[変換ルールの定義](http://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02410-117">For details about defining a new rule, see  [Defining Translation Rules](http://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) in the Deployment documentation.</span></span>
    
   - <span data-ttu-id="02410-118">既にトランクに関連付けられている変換ルールを編集するには、ルールの名前をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02410-118">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="02410-119">詳細については、展開に関するドキュメントの[変換ルールの定義](http://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02410-119">For details, see [Defining Translation Rules](http://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) in the Deployment documentation.</span></span>
    
   - <span data-ttu-id="02410-120">既存の変換ルールをコピーしてそれを基に新しいルールを定義するには、ルールの名前をクリックして [**コピー**] をクリックし、[**貼り付け**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02410-120">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="02410-121">詳細については、[変換ルールの定義](http://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02410-121">For details, see [Defining Translation Rules](http://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx).</span></span> 
    
   - <span data-ttu-id="02410-122">トランクから変換ルールを削除するには、ルールの名前を選択状態にして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02410-122">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="02410-123">関連付けられたトランク ピアに対して変換ルールを構成している場合は、2 つのルールが競合する危険があるため、変換ルールをトランクに関連付けないでください。</span><span class="sxs-lookup"><span data-stu-id="02410-123">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span> 
  

