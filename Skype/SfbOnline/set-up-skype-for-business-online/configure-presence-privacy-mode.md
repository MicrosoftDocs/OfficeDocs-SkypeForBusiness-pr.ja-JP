---
title: プレゼンス プライバシー モードを設定する
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: b33d57fe-b9cf-43c1-961a-edf28db738e8
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
- ms.lync.lac.OrgPresencePrivacy
description: 'ユーザーが自分の空き時間情報を表示する方法をより詳細に制御できるよう、ユーザーのプライバシー モードを設定する方法について説明します。 '
ms.openlocfilehash: 0b708c86d2693228ad7a613755a181fff5b3743d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093471"
---
# <a name="configure-presence-privacy-mode"></a><span data-ttu-id="e1186-103">プレゼンス プライバシー モードを設定する</span><span class="sxs-lookup"><span data-stu-id="e1186-103">Configure presence privacy mode</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e1186-104">Microsoft Teams 管理センターは、Skype for Business 管理センター (レガシ ポータル) に置き換えました。</span><span class="sxs-lookup"><span data-stu-id="e1186-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="e1186-105">Skype for Business を管理するためのすべての設定が Teams 管理センターに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e1186-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="e1186-106">Teams 管理センターで Skype for Business [AD](/azure/active-directory/roles/permissions-reference) を管理するには、グローバル管理者または Skype for Business 管理者の Azure 管理者の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1186-106">You must be assigned the [Azure AD admin role](/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="e1186-107">詳細については、「[Microsoft Teams 管理センターで Skype for Business の設定を管理する](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1186-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span></span>

<span data-ttu-id="e1186-108">Skype for Business Online のプレゼンス設定を使用すると、自分が出席可能か、会議中か、またはオフィスから出たかを誰が確認できるのかを、より詳細に制御できます。</span><span class="sxs-lookup"><span data-stu-id="e1186-108">The Skype for Business Online presence setting gives people more control over who can see whether they are available, in a meeting, or out of the office.</span></span> <span data-ttu-id="e1186-109">Skype for Business のプレゼンスとプライバシーの設定の詳細については [、「Skype for Business Online でプレゼンスを構成する」を参照してください](configure-presence-in-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="e1186-109">For details about Skype for Business presence and privacy settings, see [Configure presence in Skype for Business Online](configure-presence-in-skype-for-business-online.md).</span></span> 
  
## <a name="choose-the-default-online-presence-setting-for-everyone-in-your-organization"></a><span data-ttu-id="e1186-110">組織内のすべてのユーザーの既定のオンライン プレゼンス設定を選ぶ</span><span class="sxs-lookup"><span data-stu-id="e1186-110">Choose the default online presence setting for everyone in your organization</span></span>
<span data-ttu-id="e1186-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="e1186-111"><a name="__top"> </a></span></span>

1. <span data-ttu-id="e1186-112">Skype for Business Online 管理センターに移動し、[組織> **全般>します**。</span><span class="sxs-lookup"><span data-stu-id="e1186-112">Go to the Skype for Business Online admin center > **Organization > General**.</span></span>
    
2. <span data-ttu-id="e1186-113">プレゼンス **プライバシー モードで設定** を選び、[保存] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="e1186-113">Under **Presence privacy mode**, choose the setting, and then click **Save**.</span></span>
    
|<span data-ttu-id="e1186-114">**設定**</span><span class="sxs-lookup"><span data-stu-id="e1186-114">**Setting**</span></span>|<span data-ttu-id="e1186-115">**ユーザーのプレゼンスを表示できるユーザー**</span><span class="sxs-lookup"><span data-stu-id="e1186-115">**Who can view a user's presence**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e1186-116">**プレゼンス情報を自動的に表示する**</span><span class="sxs-lookup"><span data-stu-id="e1186-116">**Automatically display presence information**</span></span> <br/> |<span data-ttu-id="e1186-117">[ **外部** ] または [ **禁止済み** ] プライバシー グループに属していないすべての Skype for Business ユーザー。</span><span class="sxs-lookup"><span data-stu-id="e1186-117">Any Skype for Business user who does not belong to the **External** or **Blocked** privacy group.</span></span> <br/> |
|<span data-ttu-id="e1186-118">**ユーザーの連絡先にのみプレゼンス情報を表示する**</span><span class="sxs-lookup"><span data-stu-id="e1186-118">**Display presence information only to a user's contacts**</span></span> <br/> |<span data-ttu-id="e1186-119">外部またはブロックされたプライバシー グループに属していないユーザーの連絡先リスト **内のすべての** ユーザー。</span><span class="sxs-lookup"><span data-stu-id="e1186-119">Anyone in a user's contact list who does not belong to the **External** or **Blocked** privacy group.</span></span> <br/> <span data-ttu-id="e1186-120">個々のユーザーは、[Skype for **Business** のオプション] ダイアログ ボックスでこの設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="e1186-120">Individual users can change this setting in the Skype for Business **Options** dialog box.</span></span> <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="e1186-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="e1186-121">Related topics</span></span>
[<span data-ttu-id="e1186-122">Skype for Business Online をセットアップする</span><span class="sxs-lookup"><span data-stu-id="e1186-122">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="e1186-123">Skype for Business ユーザーが Skype の連絡先を追加できるようにする</span><span class="sxs-lookup"><span data-stu-id="e1186-123">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
