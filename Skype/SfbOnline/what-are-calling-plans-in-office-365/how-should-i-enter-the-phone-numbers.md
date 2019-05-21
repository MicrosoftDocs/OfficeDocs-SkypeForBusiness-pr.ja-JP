---
title: 電話番号を入力する方法を教えてください。
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 28aa24b4-8c81-4327-9752-989ea7540db2
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords: ms.lync.lac.PortOrderNumbers
ms.custom:
- Calling Plans
description: 'Skype for Business に発信するときに電話番号を設定する方法について説明します。 '
ms.openlocfilehash: df9d82a6e785954a95a455f0e43aa0e077f40bcf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280532"
---
# <a name="how-should-i-enter-the-phone-numbers"></a><span data-ttu-id="51a88-103">電話番号を入力する方法を教えてください。</span><span class="sxs-lookup"><span data-stu-id="51a88-103">How should I enter the phone numbers?</span></span>

<span data-ttu-id="51a88-104">電話番号を移行するときは、正しい形式で入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51a88-104">When you are porting phone numbers, you must enter them in the correct format.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="51a88-105">各電話番号または電話番号の範囲は、各行に個別に入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51a88-105">Each phone number or range of phone number must be entered separately on each line.</span></span> 
  
- <span data-ttu-id="51a88-106">1つの電話番号を入力する場合:</span><span class="sxs-lookup"><span data-stu-id="51a88-106">When you are entering single phone numbers:</span></span>
    
  - <span data-ttu-id="51a88-107">すべての特殊文字は無視されます (ダッシュ "-" を含む)。</span><span class="sxs-lookup"><span data-stu-id="51a88-107">All special characters will be ignored (including dash "-").</span></span> <span data-ttu-id="51a88-108">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="51a88-108">For example:</span></span>
    
  - <span data-ttu-id="51a88-109">10桁の番号の場合: \*\* &amp; \*(425\*() (\*&amp;4&amp;\*()) (\*250649\*\*は、 **+ 14255550649**に修正されます)。</span><span class="sxs-lookup"><span data-stu-id="51a88-109">For a 10-digit number: **&amp;\*(425\*()(\*&amp;4&amp;\*())(\*250649** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="51a88-110">11桁の番号の場合: **1\*() (\*&amp;42&amp;\*()\*&amp;(55550649**は、 **+ 14255550649**に修正されます。</span><span class="sxs-lookup"><span data-stu-id="51a88-110">For an 11-digit number: **1\*()(\*&amp;42&amp;\*()(\*&amp;55550649** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="51a88-111">10桁または11桁の場合、すべてのタグが無視されます。</span><span class="sxs-lookup"><span data-stu-id="51a88-111">All tags will be ignored if there are 10 or 11 digits.</span></span> <span data-ttu-id="51a88-112">たとえば、 \*\* \<div> 4255551234\</div>\*\* は **+ 14255551234**になります。</span><span class="sxs-lookup"><span data-stu-id="51a88-112">For example, **\<div> 4255551234\</div>** will be **+14255551234**.</span></span>
    
  - <span data-ttu-id="51a88-113">"-"、スペース、およびかっこは無視されます。</span><span class="sxs-lookup"><span data-stu-id="51a88-113">"-", space, and parenthesis will be ignored.</span></span> <span data-ttu-id="51a88-114">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="51a88-114">For example:</span></span>
    
  - <span data-ttu-id="51a88-115">10桁の番号の場合: **(425) 555-6776**は、 **+ 14255556776**に修正されます。</span><span class="sxs-lookup"><span data-stu-id="51a88-115">For a 10-digit number: **(425) 555-6776** will be corrected to **+14255556776**.</span></span>
    
  - <span data-ttu-id="51a88-116">11桁の番号の場合: **1 (425) 555-6776**は **+ 14255556776**に修正されます。</span><span class="sxs-lookup"><span data-stu-id="51a88-116">For an 11-digit number: **1(425) 555-6776** will be corrected to **+14255556776**.</span></span>
    
  - <span data-ttu-id="51a88-117">すべての文字は特殊文字として扱われ、10桁または11桁の電話番号がある場合は無視されます。</span><span class="sxs-lookup"><span data-stu-id="51a88-117">All letters will be treated as special characters and ignored if there is a 10-digit or 11-digit phone number.</span></span> <span data-ttu-id="51a88-118">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="51a88-118">For example:</span></span>
    
  - <span data-ttu-id="51a88-119">10桁の番号の場合: **14jaosia2reoij05jof55506ajfoj49isdjf**は **+ 14255550649**に修正されます。</span><span class="sxs-lookup"><span data-stu-id="51a88-119">For a 10-digit number: **14jaosia2reoij05jof55506ajfoj49isdjf** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="51a88-120">11桁の番号の場合: **1ade4jaoda2rfoij05ojof55506dsfoj49if**は **+ 14255550649**に修正されます。</span><span class="sxs-lookup"><span data-stu-id="51a88-120">For an 11-digit number: **1ade4jaoda2rfoij05ojof55506dsfoj49if** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="51a88-121">他の言語でも、特殊文字の任意の組み合わせが修正されます。</span><span class="sxs-lookup"><span data-stu-id="51a88-121">Any combination of special characters, even in other languages, will be corrected.</span></span> <span data-ttu-id="51a88-122">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="51a88-122">For example:</span></span> 
    
  - <span data-ttu-id="51a88-123">10桁の番号の場合:**中文4中文 2ajj5\*() (\*(5 ()...551345**は **+ 14555551345**に修正されます。</span><span class="sxs-lookup"><span data-stu-id="51a88-123">For a 10-digit number: **中文4中文2ajj5\*（）（\*（5()...551345** will be corrected to **+14555551345**.</span></span>
    
  - <span data-ttu-id="51a88-124">11桁の番号の場合:**中文4中文 2 $ a5\*() (\*(5 ()...55 (.1345**は **+ 14555551345**に修正されます。</span><span class="sxs-lookup"><span data-stu-id="51a88-124">For an 11-digit number: **中文4中文2$a5\*（）（\*（5()...55(.1345** will be corrected to **+14555551345**.</span></span>
    
  - <span data-ttu-id="51a88-125">10桁未満か11桁を超える数値が含まれている場合は、ユーザーが修正できるように強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="51a88-125">If any numbers contain fewer than 10 digits or more than 11 digits, they will be highlighted for the user to correct:</span></span>
    
  - <span data-ttu-id="51a88-126">\*\*5551245\* \*は強調表示され、修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51a88-126">\*\*5551245\*\* will be highlighted and need to be corrected.</span></span>
    
  - <span data-ttu-id="51a88-127">**1234567891011**は強調表示され、修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51a88-127">**1234567891011** will be highlighted and need to be corrected.</span></span>
    
  - <span data-ttu-id="51a88-128">10桁未満の数値、または特殊文字を含む11桁を超える数値は、自動的に修正されることなく強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="51a88-128">Any numbers that are fewer than 10 digits or more than 11 digits, with any special characters, will be highlighted without being automatically corrected.</span></span>
    
  - <span data-ttu-id="51a88-129">特殊文字が入力されていない7桁の数字の場合: **123456abcdefg7**は強調表示され、修正する必要がありますが、文字は無視されません。</span><span class="sxs-lookup"><span data-stu-id="51a88-129">For a 7-digit number without special characters that is entered: **123456abcdefg7** will be highlighted and need to be corrected, but the letters won't be ignored.</span></span>
    
  - <span data-ttu-id="51a88-130">入力された特殊文字を含む7桁の数字の場合: **12345! @ # $&amp;\*% ^ ()--@ # $&amp;\*% ^ () 7**が強調表示され、修正されます。</span><span class="sxs-lookup"><span data-stu-id="51a88-130">For a 7-digit number with special characters that is entered: **12345!@#$%^&amp;\*()--@#$%^&amp;\*()7** will be highlighted to be corrected.</span></span> <span data-ttu-id="51a88-131">特殊文字は無視されません。</span><span class="sxs-lookup"><span data-stu-id="51a88-131">The special characters won't be ignored.</span></span>
    
- <span data-ttu-id="51a88-132">電話番号の範囲を入力する場合。</span><span class="sxs-lookup"><span data-stu-id="51a88-132">When you are entering a range of phone numbers.</span></span>
    
  - <span data-ttu-id="51a88-133">2つの電話番号のみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="51a88-133">Only two phone numbers are allowed.</span></span> <span data-ttu-id="51a88-134">小さい数値は、範囲内の最初の数値である必要があります。</span><span class="sxs-lookup"><span data-stu-id="51a88-134">The smaller number must be the first number in the range.</span></span>
    
  - <span data-ttu-id="51a88-135">すべての特殊文字 (ダッシュ "-" 以外) は、1つの数値と同じように扱われます。</span><span class="sxs-lookup"><span data-stu-id="51a88-135">All special characters (except for the dash "-") are treated the same as single numbers.</span></span> <span data-ttu-id="51a88-136">たとえば、 **(425) 555 0&amp;\*(123-(1425) 5557899nm**は、 **+ 14255550123-+ 13202040659**に修正されます。</span><span class="sxs-lookup"><span data-stu-id="51a88-136">For example, **(425)555 0&amp;\*(123-(1425)5557899nm** will be corrected to **+14255550123 -+13202040659**.</span></span>
    
  - <span data-ttu-id="51a88-137">"-" は、2つの数値のみを区切るために使われます。</span><span class="sxs-lookup"><span data-stu-id="51a88-137">The "-" is used for only separating the two numbers.</span></span> <span data-ttu-id="51a88-138">数値の範囲に複数の "-" を含めることはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="51a88-138">It isn't supported to include multiple "-" in the number range.</span></span> <span data-ttu-id="51a88-139">たとえば、 **(425) 555-0649-(425) 555-1115**は、 **(425) 5550649-(425) 5551115**として入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51a88-139">For example, **(425) 555-0649 - (425) 555-1115** should be entered as **(425) 5550649 - (425) 5551115**.</span></span>
    
  <span data-ttu-id="51a88-140">**詳細な手順については、「 [Office 365 に電話番号を転送する](/microsoftteams/transfer-phone-numbers-to-office-365)」を参照してください。**</span><span class="sxs-lookup"><span data-stu-id="51a88-140">**For complete step-by-step instructions, see [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).**</span></span>

  > [!NOTE]
  > <span data-ttu-id="51a88-141">さらに追加で電話番号が必要な場合は、「[一般法人向け Office 365 のサポートへのお問い合わせ - 管理者向けヘルプ](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="51a88-141">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span></span>

  
## <a name="related-topics"></a><span data-ttu-id="51a88-142">関連トピック</span><span class="sxs-lookup"><span data-stu-id="51a88-142">Related topics</span></span>
[<span data-ttu-id="51a88-143">電話番号の移行に関するよくある質問</span><span class="sxs-lookup"><span data-stu-id="51a88-143">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="51a88-144">通話プランで使用されるさまざまな種類の電話番号</span><span class="sxs-lookup"><span data-stu-id="51a88-144">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

<span data-ttu-id="51a88-145">[[[Skype for Business 新しい電話番号の申請](/microsoftteams/manage-phone-numbers-for-your-organization)] に移動することによって、電話番号を取得するために利用できるすべてのフォームを一覧表示してダウンロードすることができます。](/microsoftteams/manage-phone-numbers-for-your-organization)</span><span class="sxs-lookup"><span data-stu-id="51a88-145">[Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization)</span></span>

[<span data-ttu-id="51a88-146">緊急通話の利用条件</span><span class="sxs-lookup"><span data-stu-id="51a88-146">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="51a88-147">[Skype for Business Online: 緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="51a88-147">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 