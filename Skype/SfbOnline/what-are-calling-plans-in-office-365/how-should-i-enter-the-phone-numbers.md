---
title: 電話番号の入力方法について
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
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
ms.openlocfilehash: b5b547a88dab1c812a47c310645254985cc0b606
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2018
ms.locfileid: "23780601"
---
# <a name="how-should-i-enter-the-phone-numbers"></a><span data-ttu-id="f69e4-103">電話番号の入力方法について</span><span class="sxs-lookup"><span data-stu-id="f69e4-103">How should I enter the phone numbers?</span></span>

<span data-ttu-id="f69e4-104">電話番号を移植するときに正しい形式で入力してください。</span><span class="sxs-lookup"><span data-stu-id="f69e4-104">When you are porting phone numbers, you must enter them in the correct format.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f69e4-105">各電話番号や電話番号の範囲は、行ごとに別々 に入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f69e4-105">Each phone number or range of phone number must be entered separately on each line.</span></span> 
  
- <span data-ttu-id="f69e4-106">1 つの電話番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="f69e4-106">When you are entering single phone numbers:</span></span>
    
  - <span data-ttu-id="f69e4-107">すべての特殊文字は無視されます (ダッシュを含む「-」)。</span><span class="sxs-lookup"><span data-stu-id="f69e4-107">All special characters will be ignored (including dash "-").</span></span> <span data-ttu-id="f69e4-108">例:</span><span class="sxs-lookup"><span data-stu-id="f69e4-108">For example:</span></span>
    
  - <span data-ttu-id="f69e4-109">10 桁の番号の: \*\* &amp; \*(425\*() (\*&amp;4&amp;\*()) (\*250649\*\* **+14255550649**に修正されます。</span><span class="sxs-lookup"><span data-stu-id="f69e4-109">For a 10-digit number: **&amp;\*(425\*()(\*&amp;4&amp;\*())(\*250649** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="f69e4-110">11 桁の数: **1\*() (\*&amp;42&amp;\*() (\*&amp;55550649** **+14255550649**に修正されます。</span><span class="sxs-lookup"><span data-stu-id="f69e4-110">For an 11-digit number: **1\*()(\*&amp;42&amp;\*()(\*&amp;55550649** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="f69e4-111">10 または 11 桁の数字がある場合、すべてのタグは無視されます。</span><span class="sxs-lookup"><span data-stu-id="f69e4-111">All tags will be ignored if there are 10 or 11 digits.</span></span> <span data-ttu-id="f69e4-112">たとえば、 ** \<div > 4255551234\</div >** **+14255551234**になります。</span><span class="sxs-lookup"><span data-stu-id="f69e4-112">For example, **\<div> 4255551234\</div>** will be **+14255551234**.</span></span>
    
  - <span data-ttu-id="f69e4-113">"-"、スペースとかっこは無視されます。</span><span class="sxs-lookup"><span data-stu-id="f69e4-113">"-", space, and parenthesis will be ignored.</span></span> <span data-ttu-id="f69e4-114">例:</span><span class="sxs-lookup"><span data-stu-id="f69e4-114">For example:</span></span>
    
  - <span data-ttu-id="f69e4-115">10 桁の番号: **(425) 555-6776**を **+14255556776**に修正されます。</span><span class="sxs-lookup"><span data-stu-id="f69e4-115">For a 10-digit number: **(425) 555-6776** will be corrected to **+14255556776**.</span></span>
    
  - <span data-ttu-id="f69e4-116">11 桁の数: **555-6776 の 1(425)** を **+14255556776**に修正されます。</span><span class="sxs-lookup"><span data-stu-id="f69e4-116">For an 11-digit number: **1(425) 555-6776** will be corrected to **+14255556776**.</span></span>
    
  - <span data-ttu-id="f69e4-117">すべての文字は特殊文字として扱われ、10 桁または 11 桁の電話番号がある場合は無視します。</span><span class="sxs-lookup"><span data-stu-id="f69e4-117">All letters will be treated as special characters and ignored if there is a 10-digit or 11-digit phone number.</span></span> <span data-ttu-id="f69e4-118">例:</span><span class="sxs-lookup"><span data-stu-id="f69e4-118">For example:</span></span>
    
  - <span data-ttu-id="f69e4-119">10 桁の番号: **14jaosia2reoij05jof55506ajfoj49isdjf**を **+14255550649**に修正されます。</span><span class="sxs-lookup"><span data-stu-id="f69e4-119">For a 10-digit number: **14jaosia2reoij05jof55506ajfoj49isdjf** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="f69e4-120">11 桁の数: **1ade4jaoda2rfoij05ojof55506dsfoj49if**を **+14255550649**に修正されます。</span><span class="sxs-lookup"><span data-stu-id="f69e4-120">For an 11-digit number: **1ade4jaoda2rfoij05ojof55506dsfoj49if** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="f69e4-121">他の言語であっても、特殊文字の任意の組み合わせが修正されます。</span><span class="sxs-lookup"><span data-stu-id="f69e4-121">Any combination of special characters, even in other languages, will be corrected.</span></span> <span data-ttu-id="f69e4-122">例:</span><span class="sxs-lookup"><span data-stu-id="f69e4-122">For example:</span></span> 
    
  - <span data-ttu-id="f69e4-123">10 桁の番号:**中文4中文2ajj5\*() (\*(5().551345** **+14555551345**に修正されます。</span><span class="sxs-lookup"><span data-stu-id="f69e4-123">For a 10-digit number: **中文4中文2ajj5\*（）（\*（5()...551345** will be corrected to **+14555551345**.</span></span>
    
  - <span data-ttu-id="f69e4-124">11 桁の数:**中文4中文2$ a5\*() (\*(5().55 (.1345** **+14555551345**に修正されます。</span><span class="sxs-lookup"><span data-stu-id="f69e4-124">For an 11-digit number: **中文4中文2$a5\*（）（\*（5()...55(.1345** will be corrected to **+14555551345**.</span></span>
    
  - <span data-ttu-id="f69e4-125">任意の数値には、10 桁または 11 以上の数字が含まれている、ユーザーを修正するためにハイライトされます。</span><span class="sxs-lookup"><span data-stu-id="f69e4-125">If any numbers contain fewer than 10 digits or more than 11 digits, they will be highlighted for the user to correct:</span></span>
    
  - <span data-ttu-id="f69e4-126">\*\*5551245\* \*がハイライトされ、修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f69e4-126">\*\*5551245\*\* will be highlighted and need to be corrected.</span></span>
    
  - <span data-ttu-id="f69e4-127">**1234567891011**がハイライトされ、修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f69e4-127">**1234567891011** will be highlighted and need to be corrected.</span></span>
    
  - <span data-ttu-id="f69e4-128">10 桁または 11 以上の数字、特殊文字、任意の数値が自動的に修正されることがなくハイライトされます。</span><span class="sxs-lookup"><span data-stu-id="f69e4-128">Any numbers that are fewer than 10 digits or more than 11 digits, with any special characters, will be highlighted without being automatically corrected.</span></span>
    
  - <span data-ttu-id="f69e4-129">入力される特殊文字なしの 7 桁の番号: 文字を無視しないが**123456abcdefg7**が強調表示され、修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f69e4-129">For a 7-digit number without special characters that is entered: **123456abcdefg7** will be highlighted and need to be corrected, but the letters won't be ignored.</span></span>
    
  - <span data-ttu-id="f69e4-130">入力される特殊文字と 7 桁の番号: **12345!@#$%^&amp;\*()--@# $% ^&amp;\*() 7**を修正するが強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="f69e4-130">For a 7-digit number with special characters that is entered: **12345!@#$%^&amp;\*()--@#$%^&amp;\*()7** will be highlighted to be corrected.</span></span> <span data-ttu-id="f69e4-131">特殊文字は無視されません。</span><span class="sxs-lookup"><span data-stu-id="f69e4-131">The special characters won't be ignored.</span></span>
    
- <span data-ttu-id="f69e4-132">電話番号の範囲を入力します。</span><span class="sxs-lookup"><span data-stu-id="f69e4-132">When you are entering a range of phone numbers.</span></span>
    
  - <span data-ttu-id="f69e4-133">2 つの電話番号を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f69e4-133">Only two phone numbers are allowed.</span></span> <span data-ttu-id="f69e4-134">少ない数の範囲の最初の数値でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="f69e4-134">The smaller number must be the first number in the range.</span></span>
    
  - <span data-ttu-id="f69e4-135">すべての特殊文字 (ハイフンを除く"-") は 1 つの数値として扱われ、同じ。</span><span class="sxs-lookup"><span data-stu-id="f69e4-135">All special characters (except for the dash "-") are treated the same as single numbers.</span></span> <span data-ttu-id="f69e4-136">たとえば、 **(425) 555 0&amp;\*(123-(1425) 5557899nm**に修正されます。 **+14255550123 - +13202040659**。</span><span class="sxs-lookup"><span data-stu-id="f69e4-136">For example, **(425)555 0&amp;\*(123-(1425)5557899nm** will be corrected to **+14255550123 -+13202040659**.</span></span>
    
  - <span data-ttu-id="f69e4-137">"-"のみ 2 つの数値を区切るために使用します。</span><span class="sxs-lookup"><span data-stu-id="f69e4-137">The "-" is used for only separating the two numbers.</span></span> <span data-ttu-id="f69e4-138">複数を含めることはサポートされていません"、"番号の範囲の。</span><span class="sxs-lookup"><span data-stu-id="f69e4-138">It isn't supported to include multiple "-" in the number range.</span></span> <span data-ttu-id="f69e4-139">として **(425) 555-0649 ・ (425) 555-1115**を入力するたとえば、 **(425) 5550649-(425) 5551115**。</span><span class="sxs-lookup"><span data-stu-id="f69e4-139">For example, **(425) 555-0649 - (425) 555-1115** should be entered as **(425) 5550649 - (425) 5551115**.</span></span>
    
 <span data-ttu-id="f69e4-140">**完全な手順については、 [Office 365 に電話番号を転送する](/microsoftteams/transfer-phone-numbers-to-office-365)を参照してください。**</span><span class="sxs-lookup"><span data-stu-id="f69e4-140">**For complete step-by-step instructions, see [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).**</span></span>

 > [!NOTE]
> <span data-ttu-id="f69e4-141">無料電話番号</span><span class="sxs-lookup"><span data-stu-id="f69e4-141">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span></span>

  
## <a name="related-topics"></a><span data-ttu-id="f69e4-142">関連トピック</span><span class="sxs-lookup"><span data-stu-id="f69e4-142">Related topics</span></span>
[<span data-ttu-id="f69e4-143">電話番号の移行に関するよくある質問</span><span class="sxs-lookup"><span data-stu-id="f69e4-143">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="f69e4-144">通話プランで使用されるさまざまな種類の電話番号</span><span class="sxs-lookup"><span data-stu-id="f69e4-144">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

<span data-ttu-id="f69e4-145">[[[Skype for Business 新しい電話番号の申請](/microsoftteams/manage-phone-numbers-for-your-organization)] に移動することによって、電話番号を取得するために利用できるすべてのフォームを一覧表示してダウンロードすることができます。](/microsoftteams/manage-phone-numbers-for-your-organization)</span><span class="sxs-lookup"><span data-stu-id="f69e4-145">[Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization)</span></span>

[<span data-ttu-id="f69e4-146">緊急通話の利用条件</span><span class="sxs-lookup"><span data-stu-id="f69e4-146">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="f69e4-147">[Skype for Business Online: 緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="f69e4-147">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 