---
title: 既知の問題の計画を呼び出す
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: baa3645a-0518-472e-942e-971c63ba4ca0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: '(PSTN の呼び出し)、Office 365 と何ができるかについては、それらの呼び出し元の計画に関する既知の問題について説明します。 '
ms.openlocfilehash: d201db80c2da09223d8e3b1935c383089f997382
ms.sourcegitcommit: f942232d43fc4ad56b34dd400fdb4bca39013f5f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="calling-plans-known-issues"></a><span data-ttu-id="bf711-103">既知の問題の計画を呼び出す</span><span class="sxs-lookup"><span data-stu-id="bf711-103">Calling Plans known issues</span></span>

<span data-ttu-id="bf711-104">Office 365 の通話プランは、Skype については、オンライン ビジネスの新しい機能です。</span><span class="sxs-lookup"><span data-stu-id="bf711-104">Calling Plans in Office 365 are a new feature found in Skype for Business Online.</span></span> <span data-ttu-id="bf711-105">されている現在の問題が追跡され、積極的に調査します。</span><span class="sxs-lookup"><span data-stu-id="bf711-105">The following are current issues that are being tracked and actively investigated.</span></span> <span data-ttu-id="bf711-106">いる可能性があります解決されますオンライン ビジネスの将来のビルドでは、Office 365 と Skype の機能が更新されたとき。</span><span class="sxs-lookup"><span data-stu-id="bf711-106">They will be potentially resolved when the feature is updated in future builds in Office 365 and Skype for Business Online.</span></span>
  
## <a name="calling-plans-known-issues"></a><span data-ttu-id="bf711-107">既知の問題の計画を呼び出す</span><span class="sxs-lookup"><span data-stu-id="bf711-107">Calling Plans known issues</span></span>

|<span data-ttu-id="bf711-108">**既知の問題**</span><span class="sxs-lookup"><span data-stu-id="bf711-108">**Known issue**</span></span>|<span data-ttu-id="bf711-109">**コメント**</span><span class="sxs-lookup"><span data-stu-id="bf711-109">**Comments**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bf711-110">テクニカル プレビューからの移行計画を呼び出すための生産ライセンスをライセンスは自動的に更新ライセンス。</span><span class="sxs-lookup"><span data-stu-id="bf711-110">Transitioning from Tech Preview licenses to production licenses for Calling Plans don't automatically update the license.</span></span>  <br/> |<span data-ttu-id="bf711-111">ユーザーに割り当てる準備ができるように最初に、新しいライセンスを購入します。</span><span class="sxs-lookup"><span data-stu-id="bf711-111">Purchase your new licenses first so they are ready to be assigned to your users.</span></span> <span data-ttu-id="bf711-112">プロモーション (Tech Preview) ライセンスをユーザーから削除し、**すぐに****国内を呼び出すことを計画****国内および国際を呼び出す計画**の新しいライセンスをユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="bf711-112">Remove the promo (Tech Preview) license from a user, and then **IMMEDIATELY** assign the new **Domestic Calling Plan** and/or **Domestic and International Calling Plan** licenses to the user.</span></span> <br/> <span data-ttu-id="bf711-113">削除して、複数のユーザーのライセンスを追加している場合、すべての Windows PowerShell を使用してユーザーからライセンスを削除して、すべての Windows PowerShell を使用してユーザーのライセンスを**すぐに**割り当てることは非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="bf711-113">If you are removing and adding licenses for multiple users, it is extremely important that you remove the licenses from all of the users using Windows PowerShell and then **IMMEDIATELY** assign the licenses for all of the users also using Windows PowerShell.</span></span> <span data-ttu-id="bf711-114">これがあることを確認しないサービスの中断は大量のユーザー ライセンスの割り当てを処理する場合。</span><span class="sxs-lookup"><span data-stu-id="bf711-114">Doing this will ensure that there is no disruption in service when handling large volumes of user license assignments.</span></span> <span data-ttu-id="bf711-115">PowerShell のサンプル スクリプトは、[ビジネスおよびマイクロソフトのチームのライセンスの割り当ての Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf711-115">For sample PowerShell scripts, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>  <br/> <span data-ttu-id="bf711-116">**注:** ハイブリッド ユーザーに設置した PSTN 接続を使用する場合は、する*だけ***電話システム**のライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf711-116">**Note:** If you are using on-premises PSTN connectivity for hybrid users, you  *only*  need to assign a **Phone System** license.</span></span> <span data-ttu-id="bf711-117">**しないで**計画を呼び出すボイスを割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="bf711-117">You should **NOT** also assign a voice Calling Plan.</span></span> <span data-ttu-id="bf711-118">ただし、Office 365 ではユーザーに対して Office 365 のプランを呼び出すことを有効する場合は、まだ**国内を呼び出すことを計画**またはユーザーのための**国内および国際を呼び出す計画**ライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf711-118">However, if you are enabling Calling Plans in Office 365 for users that are in Office 365, you need to still assign a **Domestic Calling Plan** or a **Domestic and International Calling Plan** license for those users.</span></span> <span data-ttu-id="bf711-119">「[Skype for Business と Microsoft Teams のライセンスを割り当てる](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bf711-119">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

> [!NOTE]
> <span data-ttu-id="bf711-120">これよりも、他の電話番号を取得する場合は、[ビジネス製品の管理のヘルプのサポートに連絡](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)してください。         |</span><span class="sxs-lookup"><span data-stu-id="bf711-120">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="bf711-121">[米国 (無料の電話番号) 用の承認状 (LOA) (v.2.0)](http://download.microsoft.com/download/F/0/1/F01AE714-0F3C-4D9D-B41A-DFD180EC1622/Letter of Authorization %28LOA%29 for the U.S. (Toll Free numbers) (v.3.1) (en-US).pdf)</span><span class="sxs-lookup"><span data-stu-id="bf711-121">Related topics</span></span>
<span data-ttu-id="bf711-122">電話番号の管理フォームのダウンロード</span><span class="sxs-lookup"><span data-stu-id="bf711-122">[Transferring phone numbers common questions](transferring-phone-numbers-common-questions.md)</span></span>

[<span data-ttu-id="bf711-123">通話プランで使用されるさまざまな種類の電話番号</span><span class="sxs-lookup"><span data-stu-id="bf711-123">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

<span data-ttu-id="bf711-124">[[Skype for Business 新しい電話番号の申請](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)] に移動することによって、電話番号を取得するために利用できるすべてのフォームを一覧表示してダウンロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="bf711-124">[Manage phone numbers for your organization](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)</span></span>

[<span data-ttu-id="bf711-125">緊急通話の利用条件</span><span class="sxs-lookup"><span data-stu-id="bf711-125">Emergency calling terms and conditions</span></span>](../legal-and-regulatory/emergency-calling-terms-and-conditions.md)

<span data-ttu-id="bf711-126">[Skype for Business Online: 緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="bf711-126">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 