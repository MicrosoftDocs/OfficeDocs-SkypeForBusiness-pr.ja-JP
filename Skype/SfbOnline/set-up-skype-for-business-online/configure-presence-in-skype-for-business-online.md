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
ms.openlocfilehash: b06139d3614335505c7f8682700aa3d7d6fb5df8
ms.sourcegitcommit: 1db39fde090809d9abc6d7346dda55814d88993a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2020
ms.locfileid: "48739195"
---
# <a name="configure-presence-in-skype-for-business-online"></a><span data-ttu-id="14cb5-103">Skype for Business Online でプレゼンスを設定する</span><span class="sxs-lookup"><span data-stu-id="14cb5-103">Configure presence in Skype for Business Online</span></span>

> [!IMPORTANT]
> <span data-ttu-id="14cb5-104">Microsoft Teams 管理センターは、Skype for Business 管理センター (従来のポータル) に代わるものです。</span><span class="sxs-lookup"><span data-stu-id="14cb5-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="14cb5-105">Skype for Business を管理するためのすべての設定が Teams 管理センターになりました。</span><span class="sxs-lookup"><span data-stu-id="14cb5-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="14cb5-106">詳細については、「 [Microsoft Teams 管理センターで Skype For business の設定を管理](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14cb5-106">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

<span data-ttu-id="14cb5-107">既定では、Skype for Business を使用して組織内のいずれかのユーザーと通信できるユーザーは誰でも、そのユーザーがオンラインかどうかを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="14cb5-107">By default, anyone who can communicate with one of the people in your organization using Skype for Business can also see whether that person is online.</span></span> <span data-ttu-id="14cb5-108">Skype for Business では、ユーザーがオンライン、会議、オフライン、または別のインジケーターであるかどうかが表示されます。</span><span class="sxs-lookup"><span data-stu-id="14cb5-108">Skype for Business shows whether a person is available online, in a meeting, offline, or another indicator.</span></span>

![Skype for Business でのユーザーのオンライン状態の例。](../images/f0849132-1ddb-480f-bca6-cfe9eaa0486d.png)

<span data-ttu-id="14cb5-110">組織内のすべてのユーザーの **[管理者](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** として、Skype for business でオンラインプレゼンスを表示できるユーザーを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="14cb5-110">As the **[admin](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** for everyone in your business, you can choose who sees their online presence in Skype for Business.</span></span>

<span data-ttu-id="14cb5-111">![Skype for Business のロゴを表示したアイコン](../images/sfb-logo-30x30.png) **Skype for Business 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="14cb5-111">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="14cb5-112">管理センター >**管理センター**  >  **Skype for business**に移動します。</span><span class="sxs-lookup"><span data-stu-id="14cb5-112">Go to the admin center > **Admin centers** > **Skype for Business**.</span></span>

2. <span data-ttu-id="14cb5-113">**Skype For business 管理センター**で、[**組織**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="14cb5-113">In the **Skype for Business admin center**, choose **organization**.</span></span>

3. <span data-ttu-id="14cb5-114">[ **プレゼンスプライバシーモード**] で、次の設定のいずれかを選択し、[ **保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="14cb5-114">Under **presence privacy mode**, select one of the following settings, and then choose **Save**.</span></span>

|<span data-ttu-id="14cb5-115">**設定**</span><span class="sxs-lookup"><span data-stu-id="14cb5-115">**Setting**</span></span>|<span data-ttu-id="14cb5-116">**ユーザーのプレゼンスを表示できるユーザー**</span><span class="sxs-lookup"><span data-stu-id="14cb5-116">**Who can view a user's presence**</span></span>|
|:-----|:-----|
|<span data-ttu-id="14cb5-117">**プレゼンス情報を自動的に表示する**</span><span class="sxs-lookup"><span data-stu-id="14cb5-117">**Automatically display presence information**</span></span> <br/> |<span data-ttu-id="14cb5-118">ユーザーの **外部** または **ブロック** リストに追加されていない会社の Skype for business ユーザーは、そのユーザーのオンラインプレゼンス情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="14cb5-118">Any Skype for Business user in your business who has not been added to a person's **External** or **Blocked** list will be able to see that person's online presence.</span></span> <br/> |
|<span data-ttu-id="14cb5-119">**プレゼンス情報をユーザーの連絡先にのみ表示する**</span><span class="sxs-lookup"><span data-stu-id="14cb5-119">**Display presence information only to a user's contacts**</span></span> <br/> |<span data-ttu-id="14cb5-120">他のユーザーの連絡先リストに含まれているすべてのユーザーが、 **外部** または **ブロック** されたリストに追加されていない。</span><span class="sxs-lookup"><span data-stu-id="14cb5-120">Anyone in a person's Contacts list who they have not added to their **External** or **Blocked** list.</span></span> <br/> <span data-ttu-id="14cb5-121">ユーザーは、Skype for business アプリの既定の設定を上書きすることができます。 [**設定**  >  **ツール**  >  **] オプション**。</span><span class="sxs-lookup"><span data-stu-id="14cb5-121">Individuals can override your default settings in their Skype for Business app: **Settings** > **Tools** > **Options**.</span></span> <br/> |

<span data-ttu-id="14cb5-122">Skype for Business でユーザーが変更できる操作については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14cb5-122">For information about what your users can change in Skype for Business, see these articles:</span></span>

- [<span data-ttu-id="14cb5-123">Skype for Business のプレゼンス情報へのアクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="14cb5-123">Control access to your presence information in Skype for Business</span></span>](https://support.office.com/article/fea86e34-60cf-4dd0-bfb2-169a42afd92c)

- [<span data-ttu-id="14cb5-124">Skype for Business のステータスオプションを設定する</span><span class="sxs-lookup"><span data-stu-id="14cb5-124">Set Status options in Skype for Business</span></span>](https://support.office.com/article/efd25395-c8ef-4510-b9cb-6f70e2fff8a0)

## <a name="related-topics"></a><span data-ttu-id="14cb5-125">関連トピック</span><span class="sxs-lookup"><span data-stu-id="14cb5-125">Related topics</span></span>

[<span data-ttu-id="14cb5-126">Skype for Business Online をセットアップする</span><span class="sxs-lookup"><span data-stu-id="14cb5-126">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="14cb5-127">Skype for Business ユーザーが Skype の連絡先を追加できるようにする</span><span class="sxs-lookup"><span data-stu-id="14cb5-127">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)


