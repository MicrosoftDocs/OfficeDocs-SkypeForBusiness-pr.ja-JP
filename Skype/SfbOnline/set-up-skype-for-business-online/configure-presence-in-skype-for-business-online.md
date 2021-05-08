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
ms.openlocfilehash: 5eec57f295dbb45649fea6590147798881297a1b
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239968"
---
# <a name="configure-presence-in-skype-for-business-online"></a><span data-ttu-id="55e57-103">Skype for Business Online でプレゼンスを設定する</span><span class="sxs-lookup"><span data-stu-id="55e57-103">Configure presence in Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!IMPORTANT]
> <span data-ttu-id="55e57-104">管理Microsoft Teamsセンターは、管理センター (レガシ ポータルSkype for Business置き換えました。</span><span class="sxs-lookup"><span data-stu-id="55e57-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="55e57-105">現在、管理センター Skype for Business管理センターにTeams設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="55e57-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="55e57-106">グローバル管理者の[Azure AD 管理者](/azure/active-directory/roles/permissions-reference)ロールが割り当てられている必要があります。または、Skype for Business 管理センターでSkype for Business機能を管理するには、Teams必要があります。</span><span class="sxs-lookup"><span data-stu-id="55e57-106">You must be assigned the [Azure AD admin role](/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="55e57-107">詳細については、「[Microsoft Teams 管理センターで Skype for Business の設定を管理する](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55e57-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span></span>

<span data-ttu-id="55e57-108">既定では、組織内のユーザーと Skype for Businessを使用して通信できるユーザーも、そのユーザーがオンラインかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="55e57-108">By default, anyone who can communicate with one of the people in your organization using Skype for Business can also see whether that person is online.</span></span> <span data-ttu-id="55e57-109">Skype for Business、会議、オフライン、または別のインジケーターで、ユーザーがオンラインで利用できるかどうかが表示されます。</span><span class="sxs-lookup"><span data-stu-id="55e57-109">Skype for Business shows whether a person is available online, in a meeting, offline, or another indicator.</span></span>

![ユーザーのオンライン状態の例Skype for Business。](../images/f0849132-1ddb-480f-bca6-cfe9eaa0486d.png)

<span data-ttu-id="55e57-111">ビジネスのすべての **[ユーザー](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** の管理者は、ユーザーのオンライン プレゼンスを表示するユーザーを選択Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="55e57-111">As the **[admin](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** for everyone in your business, you can choose who sees their online presence in Skype for Business.</span></span>

<span data-ttu-id="55e57-112">![Skype for Business のロゴを表示したアイコン](../images/sfb-logo-30x30.png) **Skype for Business 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="55e57-112">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="55e57-113">[管理センター] の [管理>**に移動**  >  **Skype for Business。**</span><span class="sxs-lookup"><span data-stu-id="55e57-113">Go to the admin center > **Admin centers** > **Skype for Business**.</span></span>

2. <span data-ttu-id="55e57-114">[管理 **Skype for Business で、[組織**] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="55e57-114">In the **Skype for Business admin center**, choose **organization**.</span></span>

3. <span data-ttu-id="55e57-115">プレゼンス **プライバシー モードで、** 次のいずれかの設定を選択し、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="55e57-115">Under **presence privacy mode**, select one of the following settings, and then choose **Save**.</span></span>

|<span data-ttu-id="55e57-116">**設定**</span><span class="sxs-lookup"><span data-stu-id="55e57-116">**Setting**</span></span>|<span data-ttu-id="55e57-117">**Whoユーザーのプレゼンスを表示できる**</span><span class="sxs-lookup"><span data-stu-id="55e57-117">**Who can view a user's presence**</span></span>|
|:-----|:-----|
|<span data-ttu-id="55e57-118">**プレゼンス情報を自動的に表示する**</span><span class="sxs-lookup"><span data-stu-id="55e57-118">**Automatically display presence information**</span></span> <br/> |<span data-ttu-id="55e57-119">ユーザー Skype for Businessの [外部] リストまたは [ブロック] リストに追加されていないユーザーは、そのユーザーのオンライン プレゼンスを表示できます。</span><span class="sxs-lookup"><span data-stu-id="55e57-119">Any Skype for Business user in your business who has not been added to a person's **External** or **Blocked** list will be able to see that person's online presence.</span></span> <br/> |
|<span data-ttu-id="55e57-120">**ユーザーの連絡先にのみプレゼンス情報を表示する**</span><span class="sxs-lookup"><span data-stu-id="55e57-120">**Display presence information only to a user's contacts**</span></span> <br/> |<span data-ttu-id="55e57-121">外部リストまたはブロックリストに追加していないユーザーの連絡先リスト **内のすべての** ユーザー。 </span><span class="sxs-lookup"><span data-stu-id="55e57-121">Anyone in a person's Contacts list who they have not added to their **External** or **Blocked** list.</span></span> <br/> <span data-ttu-id="55e57-122">ユーザーは、アプリで既定の設定をオーバーライド **Skype for Businessツール** オプション設定  >  **設定**  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="55e57-122">Individuals can override your default settings in their Skype for Business app: **Settings** > **Tools** > **Options**.</span></span> <br/> |

<span data-ttu-id="55e57-123">ユーザーが変更できる機能については、次のSkype for Business参照してください。</span><span class="sxs-lookup"><span data-stu-id="55e57-123">For information about what your users can change in Skype for Business, see these articles:</span></span>

- [<span data-ttu-id="55e57-124">自分のプレゼンス情報へのアクセスを制御Skype for Business</span><span class="sxs-lookup"><span data-stu-id="55e57-124">Control access to your presence information in Skype for Business</span></span>](https://support.office.com/article/fea86e34-60cf-4dd0-bfb2-169a42afd92c)

- <span data-ttu-id="55e57-125">[[状態] オプションを設定Skype for Business](https://support.office.com/article/efd25395-c8ef-4510-b9cb-6f70e2fff8a0)</span><span class="sxs-lookup"><span data-stu-id="55e57-125">[Set Status options in Skype for Business](https://support.office.com/article/efd25395-c8ef-4510-b9cb-6f70e2fff8a0)</span></span>

## <a name="related-topics"></a><span data-ttu-id="55e57-126">関連トピック</span><span class="sxs-lookup"><span data-stu-id="55e57-126">Related topics</span></span>

[<span data-ttu-id="55e57-127">Skype for Business Online をセットアップする</span><span class="sxs-lookup"><span data-stu-id="55e57-127">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="55e57-128">Skype for Business ユーザーが Skype の連絡先を追加できるようにする</span><span class="sxs-lookup"><span data-stu-id="55e57-128">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
