---
title: 通話プランの既知の問題
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: baa3645a-0518-472e-942e-971c63ba4ca0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Calling Plans
description: PSTN 通話の通話プランの既知の問題とその対処方法について説明します。
ms.openlocfilehash: 3a97057f61c154ded83b85becbfcf53dc2b4bc78
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220737"
---
# <a name="calling-plans-known-issues"></a><span data-ttu-id="8cf1e-103">通話プランの既知の問題</span><span class="sxs-lookup"><span data-stu-id="8cf1e-103">Calling Plans known issues</span></span>

<span data-ttu-id="8cf1e-104">通話プランは、Skype for Business Online の新機能です。</span><span class="sxs-lookup"><span data-stu-id="8cf1e-104">Calling Plans are a new feature found in Skype for Business Online.</span></span> <span data-ttu-id="8cf1e-105">次のような現在の問題が追跡され、積極的に調査されています。</span><span class="sxs-lookup"><span data-stu-id="8cf1e-105">The following are current issues that are being tracked and actively investigated.</span></span> <span data-ttu-id="8cf1e-106">今後のビルドで機能が更新されると、それらのメンバーは解決される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8cf1e-106">They will be potentially resolved when the feature is updated in future builds.</span></span>
  
## <a name="calling-plans-known-issues"></a><span data-ttu-id="8cf1e-107">通話プランの既知の問題</span><span class="sxs-lookup"><span data-stu-id="8cf1e-107">Calling Plans known issues</span></span>

|<span data-ttu-id="8cf1e-108">**既知の問題**</span><span class="sxs-lookup"><span data-stu-id="8cf1e-108">**Known issue**</span></span>|<span data-ttu-id="8cf1e-109">**注釈**</span><span class="sxs-lookup"><span data-stu-id="8cf1e-109">**Comments**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8cf1e-110">技術プレビューのライセンスを、通話プランの運用ライセンスに移行しても、ライセンスが自動的に更新されることはありません。</span><span class="sxs-lookup"><span data-stu-id="8cf1e-110">Transitioning from Tech Preview licenses to production licenses for Calling Plans don't automatically update the license.</span></span>  <br/> |<span data-ttu-id="8cf1e-111">最初に新しいライセンスを購入して、ユーザーに割り当てる準備ができたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="8cf1e-111">Purchase your new licenses first so they are ready to be assigned to your users.</span></span> <span data-ttu-id="8cf1e-112">ユーザーからプロモーション (Tech Preview) ライセンスを削除し、新しい**国内通話プラン**または**国内および国際通話プラン**のライセンスをユーザーに**直ち**に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="8cf1e-112">Remove the promo (Tech Preview) license from a user, and then **IMMEDIATELY** assign the new **Domestic Calling Plan** and/or **Domestic and International Calling Plan** licenses to the user.</span></span> <br/> <span data-ttu-id="8cf1e-113">複数のユーザーのライセンスを削除して追加する場合は、Windows PowerShell を使用しているすべてのユーザーからライセンスを削除し、Windows PowerShell を使用してすべてのユーザーのライセンスを**直ち**に割り当てることが非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="8cf1e-113">If you are removing and adding licenses for multiple users, it is extremely important that you remove the licenses from all of the users using Windows PowerShell and then **IMMEDIATELY** assign the licenses for all of the users also using Windows PowerShell.</span></span> <span data-ttu-id="8cf1e-114">こうすることで、大量のユーザーライセンスの割り当てを処理する際にサービスが中断されることがなくなります。</span><span class="sxs-lookup"><span data-stu-id="8cf1e-114">Doing this will ensure that there is no disruption in service when handling large volumes of user license assignments.</span></span> <span data-ttu-id="8cf1e-115">PowerShell スクリプトの例については、「 [Skype For business および Microsoft Teams のライセンスを割り当てる](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8cf1e-115">For sample PowerShell scripts, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>  <br/> <span data-ttu-id="8cf1e-116">**注:** ハイブリッドユーザー用にオンプレミスの PSTN 接続を使用している場合は、**電話システム**のライセンスを*割り当てる必要が*あります。</span><span class="sxs-lookup"><span data-stu-id="8cf1e-116">**Note:** If you are using on-premises PSTN connectivity for hybrid users, you *only* need to assign a **Phone System** license.</span></span> <span data-ttu-id="8cf1e-117">音声通話プランを割り当てることはでき**ません**。</span><span class="sxs-lookup"><span data-stu-id="8cf1e-117">You should **NOT** also assign a voice Calling Plan.</span></span> <span data-ttu-id="8cf1e-118">ただし、microsoft 365 365 または office 365 の通話プランを有効にし365ている場合は、そのユーザーの**国内通話プラン**または**国内および国際通話プラン**のライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="8cf1e-118">However, if you are enabling Calling Plans in Microsoft 365 or Office 365 for users that are in Microsoft 365 or Office 365, you need to still assign a **Domestic Calling Plan** or a **Domestic and International Calling Plan** license for those users.</span></span> <span data-ttu-id="8cf1e-119">[Skype for Business と Microsoft Teams のライセンスを割り当てる](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8cf1e-119">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

> [!NOTE]
> <span data-ttu-id="8cf1e-120">その他の電話番号を取得する必要がある場合は、[ビジネス製品のサポートにお問い合わせください。管理者向けヘルプ](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span><span class="sxs-lookup"><span data-stu-id="8cf1e-120">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="8cf1e-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="8cf1e-121">Related topics</span></span>
[<span data-ttu-id="8cf1e-122">電話番号の移行に関するよくある質問</span><span class="sxs-lookup"><span data-stu-id="8cf1e-122">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="8cf1e-123">通話プランで使用されるさまざまな種類の電話番号</span><span class="sxs-lookup"><span data-stu-id="8cf1e-123">Different kinds of phone numbers used for Calling Plans</span></span>](/MicrosoftTeams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="8cf1e-124">組織の電話番号を管理する</span><span class="sxs-lookup"><span data-stu-id="8cf1e-124">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="8cf1e-125">緊急通話の利用条件</span><span class="sxs-lookup"><span data-stu-id="8cf1e-125">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="8cf1e-126">[Skype for Business Online: 緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="8cf1e-126">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
