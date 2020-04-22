---
title: Microsoft Teams のゲスト アクセスに関する問題のトラブルシューティング
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: corbinm
search.appverid: MET150
description: Microsoft Teams のゲスト アクセスに関する問題のトラブルシューティングと解決に役立つヘルプをご利用ください。
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 52d3922bc68e942ad1cd58e40861fa8820ee6614
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "43778403"
---
<a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a><span data-ttu-id="58abb-103">Microsoft Teams のゲスト アクセスに関する問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="58abb-103">Troubleshoot problems with guest access in Microsoft Teams</span></span>
======================================================

> [!IMPORTANT]
> <span data-ttu-id="58abb-104">変更が有効になるまで最大で 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="58abb-104">You may have to wait up to 24 hours for your changes to take effect.</span></span> 


- <span data-ttu-id="58abb-105">Teams でのゲスト アクセスに関する最新のサポートの問題を確認するには、[Teams のトラブルシューティング](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)に関するページに移動します。</span><span class="sxs-lookup"><span data-stu-id="58abb-105">To check for current support issues with guest access in Teams, go to [Teams Troubleshooting](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).</span></span>
- <span data-ttu-id="58abb-106">Microsoft がお客様の問題を把握しているかどうかを確認するには、「[Microsoft Teams の既知の問題](Known-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58abb-106">To see whether we know about your problem, check out [Known issues for Microsoft Teams](Known-issues.md).</span></span>
- <span data-ttu-id="58abb-107">ゲストとは、自分の組織の外部のユーザーのことです。</span><span class="sxs-lookup"><span data-stu-id="58abb-107">Guests are users outside your organization.</span></span> <span data-ttu-id="58abb-108">ユーザーが組織内にいる場合 (社内の従業員、オンサイトの請負業者、オンサイトの代理業者など) は、ゲストとして追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="58abb-108">If someone is inside your organization (including your employees, onsite contractors, or onsite agents), they can't be added as guests.</span></span> <span data-ttu-id="58abb-109">これは、関連会社についても同じです。</span><span class="sxs-lookup"><span data-stu-id="58abb-109">The same applies to your affiliates.</span></span>
- <span data-ttu-id="58abb-110">今後実装される新機能や更新されたゲスト アクセス機能については、「[Teams のロードマップ](https://aka.ms/teamsroadmap)」で見つけてください。</span><span class="sxs-lookup"><span data-stu-id="58abb-110">Find out about upcoming new or updated guest access features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="58abb-111">ご要望については、「[Teams UserVoice](https://aka.ms/TeamsUserVoice)」でお知らせください。</span><span class="sxs-lookup"><span data-stu-id="58abb-111">Tell us what you want in [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="58abb-112">ゲストに対してライセンスのエラーが表示されている場合</span><span class="sxs-lookup"><span data-stu-id="58abb-112">If your guests are seeing license errors</span></span>

<span data-ttu-id="58abb-113">Teams のゲスト アクセスでは Azure Active Directory (Azure AD) ビジネス ツー ビジネス (B2B) およびそのライセンス モデルを使用しています。</span><span class="sxs-lookup"><span data-stu-id="58abb-113">Guest access in Teams uses Azure Active Directory (Azure AD) Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="58abb-114">ゲストアクセスは、すべての Microsoft 365 ビジネス標準、Office 365 Enterprise、Office 365 エデュケーションサブスクリプションに含まれています。</span><span class="sxs-lookup"><span data-stu-id="58abb-114">Guest access is included with all Microsoft 365 Business Standard, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="58abb-115">追加の Office 365 ライセンスは不要です。</span><span class="sxs-lookup"><span data-stu-id="58abb-115">No additional Office 365 license is necessary.</span></span>

> [!NOTE]
> <span data-ttu-id="58abb-116">ゲストのゲストのホームテナントで teams を有効にしておく必要があるのは、ゲストが別の (リソース) テナントでゲストとしてチームにサインインして使用できるようにするためです。</span><span class="sxs-lookup"><span data-stu-id="58abb-116">Teams must be enabled on a guest's home tenant for guests to be able to sign in and use Teams as a guest on another (resource) tenant.</span></span>

<span data-ttu-id="58abb-117">ライセンスエラーが表示される場合は、組織でのゲストアクセスのニーズに合わせて、ライセンス要件を特定するために、 [Azure Active DIRECTORY B2B ライセンスガイダンス](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)をお読みください。</span><span class="sxs-lookup"><span data-stu-id="58abb-117">If you're seeing licensing errors, make sure to read the [Azure Active Directory B2B licensing guidance](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) to determine licensing requirements to meet your needs for guest access in your organization.</span></span>


- <span data-ttu-id="58abb-118">ゲスト ライセンスは、招待する組織に対してカウントされます。</span><span class="sxs-lookup"><span data-stu-id="58abb-118">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="58abb-119">必要なライセンスの数を算出するときは、このことを考慮に入れます。</span><span class="sxs-lookup"><span data-stu-id="58abb-119">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="58abb-120">招待されたゲストが別の Office 365 組織から提供されているか、または個人用メールアドレスを使用しているかにかかわらず、ライセンスは組織によってカウントされます。</span><span class="sxs-lookup"><span data-stu-id="58abb-120">Licenses are counted against your organization whether the invited guests come from another Office 365 organization or are using their personal email addresses.</span></span>

## <a name="support-for-b2b-user-types"></a><span data-ttu-id="58abb-121">B2B ユーザーの種類のサポート</span><span class="sxs-lookup"><span data-stu-id="58abb-121">Support for B2B User types</span></span>
<span data-ttu-id="58abb-122">現在、Teams Only は、[Azure B2B で定義](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)されている状態 1 および状態 2 のゲスト ユーザーをサポートします。</span><span class="sxs-lookup"><span data-stu-id="58abb-122">Currently Teams only has support for State 1 and State 2 types of Guest users [as defined by Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).</span></span>

## <a name="related-topics"></a><span data-ttu-id="58abb-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="58abb-123">Related topics</span></span>

[<span data-ttu-id="58abb-124">Teams でのゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="58abb-124">Guest access in Teams</span></span>](guest-access.md)


