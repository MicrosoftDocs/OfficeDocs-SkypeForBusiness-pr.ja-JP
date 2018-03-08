---
title: "プランの既知の問題を呼び出す"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.date: 01/22/2018
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
description: "(PSTN 通話) Office 365 とは何ができる通話プランの既知の問題について説明します。 "
ms.openlocfilehash: cb572c9de92cd53384c07c4e48779598ca73bb8c
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="calling-plans-known-issues"></a><span data-ttu-id="75ffb-103">プランの既知の問題を呼び出す</span><span class="sxs-lookup"><span data-stu-id="75ffb-103">Calling Plans known issues</span></span>

<span data-ttu-id="75ffb-p101">通話プランの Office 365 では、skype for Business Online に表示される新しい機能です。されている現在の問題が管理されていると、実際に調査します。可能性があるときに解決 for Business Online の Office 365 と Skype の将来のビルドの機能が更新します。</span><span class="sxs-lookup"><span data-stu-id="75ffb-p101">Calling Plans in Office 365 are a new feature found in Skype for Business Online. The following are current issues that are being tracked and actively investigated. They will be potentially resolved when the feature is updated in future builds in Office 365 and Skype for Business Online.</span></span>
  
## <a name="calling-plans-known-issues"></a><span data-ttu-id="75ffb-107">プランの既知の問題を呼び出す</span><span class="sxs-lookup"><span data-stu-id="75ffb-107">Calling Plans known issues</span></span>

|<span data-ttu-id="75ffb-108">**既知の問題**</span><span class="sxs-lookup"><span data-stu-id="75ffb-108">**Known issue**</span></span>|<span data-ttu-id="75ffb-109">**コメント**</span><span class="sxs-lookup"><span data-stu-id="75ffb-109">**Comments**</span></span>|
|:-----|:-----|
|<span data-ttu-id="75ffb-110">Tech Preview から移行する際に通話プランのライセンスを運用するライセンスしない自動的に更新ライセンス。</span><span class="sxs-lookup"><span data-stu-id="75ffb-110">Transitioning from Tech Preview licenses to production licenses for Calling Plans don't automatically update the license.</span></span>  <br/> |<span data-ttu-id="75ffb-p102">新しいライセンスを購入まず、ユーザーに割り当てる準備ができるようにします。ユーザーのプロモーション (Tech Preview) のライセンスを削除して、**すぐに**新しい**国内通話プラン**または**国内と国際通話プラン**のライセンスをユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="75ffb-p102">Purchase your new licenses first so they are ready to be assigned to your users. Remove the promo (Tech Preview) license from a user, and then **IMMEDIATELY** assign the new **Domestic Calling Plan** and/or **Domestic and International Calling Plan** licenses to the user. </span></span><br/> <span data-ttu-id="75ffb-p103">削除するが、複数のユーザーのライセンスを追加し、すべての Windows PowerShell を使用してユーザーからライセンスを削除して、し、**すぐに**すべての Windows PowerShell を使用しても、ユーザーのライセンスを割り当てることに非常に重要です。これがあることを確認しないサービスの中断大量のユーザーのライセンスの割り当てを処理する場合。サンプルの PowerShell スクリプト、[ビジネスや Microsoft チームのライセンスを割り当てる Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75ffb-p103">If you are removing and adding licenses for multiple users, it is extremely important that you remove the licenses from all of the users using Windows PowerShell and then **IMMEDIATELY** assign the licenses for all of the users also using Windows PowerShell. Doing this will ensure that there is no disruption in service when handling large volumes of user license assignments. For sample PowerShell scripts, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).  </span></span><br/> <span data-ttu-id="75ffb-p104">**メモ:**ハイブリッドのユーザーを内部設置型 PSTN への接続を使用している場合は、する*のみ***電話システムで**ライセンスを割り当てる必要があります。**しないで**計画発信の音声を割り当てることもできます。ただしを有効にするには、Office 365 プランの呼び出しは Office 365 のユーザーに対して場合、は、まだ**国内通話プラン**またはそれらのユーザーの**国内と国際通話プラン**のライセンスを割り当てる必要があります。[ビジネスや Microsoft チームのライセンスを割り当てる Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75ffb-p104">**Note:** If you are using on-premises PSTN connectivity for hybrid users, you  *only*  need to assign a **Phone System** license. You should **NOT** also assign a voice Calling Plan. However, if you are enabling Calling Plans in Office 365 for users that are in Office 365, you need to still assign a **Domestic Calling Plan** or a **Domestic and International Calling Plan** license for those users. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

> [!NOTE]
> <span data-ttu-id="75ffb-120">これよりも、その他の電話番号を取得する必要がある場合は、[ビジネス製品 - 管理者向けヘルプのサポートに連絡](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)してください。         |</span><span class="sxs-lookup"><span data-stu-id="75ffb-120">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="75ffb-121">関連トピック</span><span class="sxs-lookup"><span data-stu-id="75ffb-121">Related topics</span></span>
[<span data-ttu-id="75ffb-122">電話番号のよく寄せられる質問を転送します。</span><span class="sxs-lookup"><span data-stu-id="75ffb-122">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)

[<span data-ttu-id="75ffb-123">さまざまなプランの呼び出し用の電話番号</span><span class="sxs-lookup"><span data-stu-id="75ffb-123">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="75ffb-124">組織の電話番号を管理します。</span><span class="sxs-lookup"><span data-stu-id="75ffb-124">Manage phone numbers for your organization</span></span>](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="75ffb-125">緊急の呼び出し元の条項および条件</span><span class="sxs-lookup"><span data-stu-id="75ffb-125">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

[<span data-ttu-id="75ffb-126">Skype for Business Online: 緊急発信免責事項のラベル</span><span class="sxs-lookup"><span data-stu-id="75ffb-126">Skype for Business Online: Emergency Calling disclaimer label</span></span>](https://go.microsoft.com/fwlink/?LinkID=692099)
