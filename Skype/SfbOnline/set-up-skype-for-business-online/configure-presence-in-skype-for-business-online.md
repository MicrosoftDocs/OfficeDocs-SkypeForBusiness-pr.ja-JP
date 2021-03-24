---
title: Skype for Business Online でプレゼンスを設定する
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: ce59ac0b-8115-4c6b-8174-e3aef982d3cb
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Setup
- O365P_OnlinePresenceDesc
description: 'Learn how to set up Skype for Business so you can see the availability of your co-workers. '
ms.openlocfilehash: 807b2dd15b3bdbe1fac42192ed9052b26bf1f256
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093491"
---
# <a name="configure-presence-in-skype-for-business-online"></a><span data-ttu-id="77d2e-103">Skype for Business Online でプレゼンスを設定する</span><span class="sxs-lookup"><span data-stu-id="77d2e-103">Configure presence in Skype for Business Online</span></span>

> [!IMPORTANT]
> <span data-ttu-id="77d2e-104">Microsoft Teams 管理センターは、Skype for Business 管理センター (従来のポータル) に置き換えました。</span><span class="sxs-lookup"><span data-stu-id="77d2e-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="77d2e-105">Skype for Business を管理するためのすべての設定が Teams 管理センターに表示されます。</span><span class="sxs-lookup"><span data-stu-id="77d2e-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="77d2e-106">Teams 管理センターで Skype for Business [AD](/azure/active-directory/roles/permissions-reference) を管理するには、グローバル管理者または Skype for Business 管理者の Azure 管理者の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="77d2e-106">You must be assigned the [Azure AD admin role](/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="77d2e-107">詳細については、「[Microsoft Teams 管理センターで Skype for Business の設定を管理する](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77d2e-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span></span>

<span data-ttu-id="77d2e-108">既定では、Skype for Business を使用して組織内のユーザーの 1 人と通信できるユーザーは、そのユーザーがオンラインかどうかも確認できます。</span><span class="sxs-lookup"><span data-stu-id="77d2e-108">By default, anyone who can communicate with one of the people in your organization using Skype for Business can also see whether that person is online.</span></span> <span data-ttu-id="77d2e-109">Skype for Business では、ユーザーがオンライン、会議、オフライン、または別のインジケーターを使用できるかどうかが表示されます。</span><span class="sxs-lookup"><span data-stu-id="77d2e-109">Skype for Business shows whether a person is available online, in a meeting, offline, or another indicator.</span></span>

![Skype for Business でのユーザーのオンライン状態の例。](../images/f0849132-1ddb-480f-bca6-cfe9eaa0486d.png)

<span data-ttu-id="77d2e-111">ビジネスのすべての **[ユーザー](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** の管理者は、Skype for Business でオンライン プレゼンスを表示するユーザーを選択できます。</span><span class="sxs-lookup"><span data-stu-id="77d2e-111">As the **[admin](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** for everyone in your business, you can choose who sees their online presence in Skype for Business.</span></span>

<span data-ttu-id="77d2e-112">![Skype for Business のロゴを表示したアイコン](../images/sfb-logo-30x30.png) **Skype for Business 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="77d2e-112">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="77d2e-113">管理センターに移動し、>   >  **Skype for Business にアクセスします**。</span><span class="sxs-lookup"><span data-stu-id="77d2e-113">Go to the admin center > **Admin centers** > **Skype for Business**.</span></span>

2. <span data-ttu-id="77d2e-114">Skype **for Business 管理センターで、[組織**] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="77d2e-114">In the **Skype for Business admin center**, choose **organization**.</span></span>

3. <span data-ttu-id="77d2e-115">プレゼンス **プライバシー モードで、次** のいずれかの設定を選択し、[保存] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="77d2e-115">Under **presence privacy mode**, select one of the following settings, and then choose **Save**.</span></span>

|<span data-ttu-id="77d2e-116">**設定**</span><span class="sxs-lookup"><span data-stu-id="77d2e-116">**Setting**</span></span>|<span data-ttu-id="77d2e-117">**ユーザーのプレゼンスを表示できるユーザー**</span><span class="sxs-lookup"><span data-stu-id="77d2e-117">**Who can view a user's presence**</span></span>|
|:-----|:-----|
|<span data-ttu-id="77d2e-118">**プレゼンス情報を自動的に表示する**</span><span class="sxs-lookup"><span data-stu-id="77d2e-118">**Automatically display presence information**</span></span> <br/> |<span data-ttu-id="77d2e-119">ユーザーの外部リストまたはブロックリストに追加されていない、あなたのビジネスの Skype for  Businessユーザーは、そのユーザーのオンライン プレゼンスを表示できます。</span><span class="sxs-lookup"><span data-stu-id="77d2e-119">Any Skype for Business user in your business who has not been added to a person's **External** or **Blocked** list will be able to see that person's online presence.</span></span> <br/> |
|<span data-ttu-id="77d2e-120">**ユーザーの連絡先にのみプレゼンス情報を表示する**</span><span class="sxs-lookup"><span data-stu-id="77d2e-120">**Display presence information only to a user's contacts**</span></span> <br/> |<span data-ttu-id="77d2e-121">外部リストまたはブロックリストに追加していないユーザーの連絡先リスト **内のすべての** ユーザー。 </span><span class="sxs-lookup"><span data-stu-id="77d2e-121">Anyone in a person's Contacts list who they have not added to their **External** or **Blocked** list.</span></span> <br/> <span data-ttu-id="77d2e-122">個人は、Skype for Business アプリの既定の設定を上書きできます **。[** 設定ツール  >  **]**  >  **オプション**。</span><span class="sxs-lookup"><span data-stu-id="77d2e-122">Individuals can override your default settings in their Skype for Business app: **Settings** > **Tools** > **Options**.</span></span> <br/> |

<span data-ttu-id="77d2e-123">Skype for Business でユーザーが変更できる内容の詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77d2e-123">For information about what your users can change in Skype for Business, see these articles:</span></span>

- [<span data-ttu-id="77d2e-124">Skype for Business で自分のプレゼンス情報へのアクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="77d2e-124">Control access to your presence information in Skype for Business</span></span>](https://support.office.com/article/fea86e34-60cf-4dd0-bfb2-169a42afd92c)

- <span data-ttu-id="77d2e-125">[Skype for Business の [状態] オプションを設定する](https://support.office.com/article/efd25395-c8ef-4510-b9cb-6f70e2fff8a0)</span><span class="sxs-lookup"><span data-stu-id="77d2e-125">[Set Status options in Skype for Business](https://support.office.com/article/efd25395-c8ef-4510-b9cb-6f70e2fff8a0)</span></span>

## <a name="related-topics"></a><span data-ttu-id="77d2e-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="77d2e-126">Related topics</span></span>

[<span data-ttu-id="77d2e-127">Skype for Business Online をセットアップする</span><span class="sxs-lookup"><span data-stu-id="77d2e-127">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="77d2e-128">Skype for Business ユーザーが Skype の連絡先を追加できるようにする</span><span class="sxs-lookup"><span data-stu-id="77d2e-128">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)