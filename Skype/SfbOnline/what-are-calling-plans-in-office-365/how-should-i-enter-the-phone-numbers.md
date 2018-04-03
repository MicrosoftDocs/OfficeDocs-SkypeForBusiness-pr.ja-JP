---
title: 電話番号を入力する方法必要がありますか。
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 28aa24b4-8c81-4327-9752-989ea7540db2
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords: ms.lync.lac.PortOrderNumbers
ms.custom:
- Calling Plans
description: 'Skype ビジネスのためにそれらを移植するときに、電話番号を設定する方法について説明します。 '
ms.openlocfilehash: 68fe698612c095e657dab56723df7de6eb13b858
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/03/2018
---
# <a name="how-should-i-enter-the-phone-numbers"></a><span data-ttu-id="58bc2-103">電話番号を入力する方法必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="58bc2-103">How should I enter the phone numbers?</span></span>

<span data-ttu-id="58bc2-104">電話番号を移植するときに正しい形式で入力してください。</span><span class="sxs-lookup"><span data-stu-id="58bc2-104">When you are porting phone numbers, you must enter them in the correct format.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="58bc2-105">各電話番号や電話番号の範囲は、行ごとに別々 に入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58bc2-105">Each phone number or range of phone number must be entered separately on each line.</span></span> 
  
- <span data-ttu-id="58bc2-106">1 つの電話番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="58bc2-106">When you are entering single phone numbers:</span></span>
    
  - <span data-ttu-id="58bc2-107">すべての特殊文字は無視されます (ダッシュを含む「-」)。</span><span class="sxs-lookup"><span data-stu-id="58bc2-107">All special characters will be ignored (including dash "-").</span></span> <span data-ttu-id="58bc2-108">例:</span><span class="sxs-lookup"><span data-stu-id="58bc2-108">For example:</span></span>
    
  - <span data-ttu-id="58bc2-109">10 桁の番号の: \*\* &amp; \*(425\*() (\*&amp;4&amp;\*()) (\*250649\*\* **+14255550649**に修正されます。</span><span class="sxs-lookup"><span data-stu-id="58bc2-109">For a 10-digit number: **&amp;\*(425\*()(\*&amp;4&amp;\*())(\*250649** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="58bc2-110">11 桁の数: **1\*() (\*&amp;42&amp;\*() (\*&amp;55550649** **+14255550649**に修正されます。</span><span class="sxs-lookup"><span data-stu-id="58bc2-110">For an 11-digit number: **1\*()(\*&amp;42&amp;\*()(\*&amp;55550649** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="58bc2-111">10 または 11 桁の数字がある場合、すべてのタグは無視されます。</span><span class="sxs-lookup"><span data-stu-id="58bc2-111">All tags will be ignored if there are 10 or 11 digits.</span></span> <span data-ttu-id="58bc2-112">たとえば、 ** \<div > 4255551234\</div >** **+14255551234**になります。</span><span class="sxs-lookup"><span data-stu-id="58bc2-112">For example, **\<div> 4255551234\</div>** will be **+14255551234**.</span></span>
    
  - <span data-ttu-id="58bc2-113">"-"、スペースとかっこは無視されます。</span><span class="sxs-lookup"><span data-stu-id="58bc2-113">"-", space, and parenthesis will be ignored.</span></span> <span data-ttu-id="58bc2-114">例:</span><span class="sxs-lookup"><span data-stu-id="58bc2-114">For example:</span></span>
    
  - <span data-ttu-id="58bc2-115">10 桁の番号: **(425) 555-6776**を**+14255556776**に修正されます。</span><span class="sxs-lookup"><span data-stu-id="58bc2-115">For a 10-digit number: **(425) 555-6776** will be corrected to **+14255556776**.</span></span>
    
  - <span data-ttu-id="58bc2-116">11 桁の数: **555-6776 の 1(425)**を**+14255556776**に修正されます。</span><span class="sxs-lookup"><span data-stu-id="58bc2-116">For an 11-digit number: **1(425) 555-6776** will be corrected to **+14255556776**.</span></span>
    
  - <span data-ttu-id="58bc2-117">すべての文字は特殊文字として扱われ、10 桁または 11 桁の電話番号がある場合は無視します。</span><span class="sxs-lookup"><span data-stu-id="58bc2-117">All letters will be treated as special characters and ignored if there is a 10-digit or 11-digit phone number.</span></span> <span data-ttu-id="58bc2-118">例:</span><span class="sxs-lookup"><span data-stu-id="58bc2-118">For example:</span></span>
    
  - <span data-ttu-id="58bc2-119">10 桁の番号: **14jaosia2reoij05jof55506ajfoj49isdjf**を**+14255550649**に修正されます。</span><span class="sxs-lookup"><span data-stu-id="58bc2-119">For a 10-digit number: **14jaosia2reoij05jof55506ajfoj49isdjf** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="58bc2-120">11 桁の数: **1ade4jaoda2rfoij05ojof55506dsfoj49if**を**+14255550649**に修正されます。</span><span class="sxs-lookup"><span data-stu-id="58bc2-120">For an 11-digit number: **1ade4jaoda2rfoij05ojof55506dsfoj49if** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="58bc2-121">他の言語であっても、特殊文字の任意の組み合わせが修正されます。</span><span class="sxs-lookup"><span data-stu-id="58bc2-121">Any combination of special characters, even in other languages, will be corrected.</span></span> <span data-ttu-id="58bc2-122">例:</span><span class="sxs-lookup"><span data-stu-id="58bc2-122">For example:</span></span> 
    
  - <span data-ttu-id="58bc2-123">10 桁の番号:**中文4中文2ajj5\*() (\*(5().551345** **+14555551345**に修正されます。</span><span class="sxs-lookup"><span data-stu-id="58bc2-123">For a 10-digit number: **中文4中文2ajj5\*（）（\*（5()...551345** will be corrected to **+14555551345**.</span></span>
    
  - <span data-ttu-id="58bc2-124">11 桁の数:**中文4中文2$ a5\*() (\*(5().55 (.1345** **+14555551345**に修正されます。</span><span class="sxs-lookup"><span data-stu-id="58bc2-124">For an 11-digit number: **中文4中文2$a5\*（）（\*（5()...55(.1345** will be corrected to **+14555551345**.</span></span>
    
  - <span data-ttu-id="58bc2-125">任意の数値には、10 桁または 11 以上の数字が含まれている、ユーザーを修正するためにハイライトされます。</span><span class="sxs-lookup"><span data-stu-id="58bc2-125">If any numbers contain fewer than 10 digits or more than 11 digits, they will be highlighted for the user to correct:</span></span>
    
  - <span data-ttu-id="58bc2-126">\*\*5551245\* \*がハイライトされ、修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58bc2-126">\*\*5551245\*\* will be highlighted and need to be corrected.</span></span>
    
  - <span data-ttu-id="58bc2-127">**1234567891011**がハイライトされ、修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58bc2-127">**1234567891011** will be highlighted and need to be corrected.</span></span>
    
  - <span data-ttu-id="58bc2-128">10 桁または 11 以上の数字、特殊文字、任意の数値が自動的に修正されることがなくハイライトされます。</span><span class="sxs-lookup"><span data-stu-id="58bc2-128">Any numbers that are fewer than 10 digits or more than 11 digits, with any special characters, will be highlighted without being automatically corrected.</span></span>
    
  - <span data-ttu-id="58bc2-129">入力される特殊文字なしの 7 桁の番号: 文字を無視しないが**123456abcdefg7**が強調表示され、修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58bc2-129">For a 7-digit number without special characters that is entered: **123456abcdefg7** will be highlighted and need to be corrected, but the letters won't be ignored.</span></span>
    
  - <span data-ttu-id="58bc2-130">入力される特殊文字と 7 桁の番号: **12345!@#$%^&amp;\*()--@# $% ^&amp;\*() 7**を修正するが強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="58bc2-130">For a 7-digit number with special characters that is entered: **12345!@#$%^&amp;\*()--@#$%^&amp;\*()7** will be highlighted to be corrected.</span></span> <span data-ttu-id="58bc2-131">特殊文字は無視されません。</span><span class="sxs-lookup"><span data-stu-id="58bc2-131">The special characters won't be ignored.</span></span>
    
- <span data-ttu-id="58bc2-132">電話番号の範囲を入力します。</span><span class="sxs-lookup"><span data-stu-id="58bc2-132">When you are entering a range of phone numbers.</span></span>
    
  - <span data-ttu-id="58bc2-133">2 つの電話番号を使用できます。</span><span class="sxs-lookup"><span data-stu-id="58bc2-133">Only two phone numbers are allowed.</span></span> <span data-ttu-id="58bc2-134">少ない数の範囲の最初の数値でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="58bc2-134">The smaller number must be the first number in the range.</span></span>
    
  - <span data-ttu-id="58bc2-135">すべての特殊文字 (ハイフンを除く"-") は 1 つの数値として扱われ、同じ。</span><span class="sxs-lookup"><span data-stu-id="58bc2-135">All special characters (except for the dash "-") are treated the same as single numbers.</span></span> <span data-ttu-id="58bc2-136">たとえば、 **(425) 555 0&amp;\*(123-(1425) 5557899nm**に修正されます。 **+14255550123 - +13202040659**。</span><span class="sxs-lookup"><span data-stu-id="58bc2-136">For example, **(425)555 0&amp;\*(123-(1425)5557899nm** will be corrected to **+14255550123 -+13202040659**.</span></span>
    
  - <span data-ttu-id="58bc2-137">"-"のみ 2 つの数値を区切るために使用します。</span><span class="sxs-lookup"><span data-stu-id="58bc2-137">The "-" is used for only separating the two numbers.</span></span> <span data-ttu-id="58bc2-138">複数を含めることはサポートされていません"、"番号の範囲の。</span><span class="sxs-lookup"><span data-stu-id="58bc2-138">It isn't supported to include multiple "-" in the number range.</span></span> <span data-ttu-id="58bc2-139">として**(425) 555-0649 ・ (425) 555-1115**を入力するたとえば、 **(425) 5550649-(425) 5551115**。</span><span class="sxs-lookup"><span data-stu-id="58bc2-139">For example, **(425) 555-0649 - (425) 555-1115** should be entered as **(425) 5550649 - (425) 5551115**.</span></span>
    
 <span data-ttu-id="58bc2-140">**完全な手順については、 [Office 365 に電話番号を転送する](transfer-phone-numbers-to-office-365.md)を参照してください。**</span><span class="sxs-lookup"><span data-stu-id="58bc2-140">**For complete step-by-step instructions, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).**</span></span>

 > [!NOTE]
> <span data-ttu-id="58bc2-141">無料電話番号</span><span class="sxs-lookup"><span data-stu-id="58bc2-141">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span></span>

  
## <a name="related-topics"></a><span data-ttu-id="58bc2-142">[米国 (無料の電話番号) 用の承認状 (LOA) (v.2.0)](http://download.microsoft.com/download/F/0/1/F01AE714-0F3C-4D9D-B41A-DFD180EC1622/Letter of Authorization %28LOA%29 for the U.S. (Toll Free numbers) (v.3.1) (en-US).pdf)</span><span class="sxs-lookup"><span data-stu-id="58bc2-142">Related topics</span></span>
<span data-ttu-id="58bc2-143">電話番号の管理フォームのダウンロード</span><span class="sxs-lookup"><span data-stu-id="58bc2-143">[Transferring phone numbers common questions](transferring-phone-numbers-common-questions.md)</span></span>

[<span data-ttu-id="58bc2-144">通話プランで使用されるさまざまな種類の電話番号</span><span class="sxs-lookup"><span data-stu-id="58bc2-144">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

<span data-ttu-id="58bc2-145">[[Skype for Business 新しい電話番号の申請](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)] に移動することによって、電話番号を取得するために利用できるすべてのフォームを一覧表示してダウンロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="58bc2-145">[Manage phone numbers for your organization](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)</span></span>

[<span data-ttu-id="58bc2-146">緊急通話の利用条件</span><span class="sxs-lookup"><span data-stu-id="58bc2-146">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

[<span data-ttu-id="58bc2-147">Skype for Business Online: 緊急通話の免責事項ラベル</span><span class="sxs-lookup"><span data-stu-id="58bc2-147">Skype for Business Online: Emergency Calling disclaimer label</span></span>](https://go.microsoft.com/fwlink/?LinkID=692099)

  
 