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
description: 'ユーザーにプライバシーモードを設定する方法について説明します。ユーザーは、自分の空き時間情報の表示方法を制御しやすくすることができます。 '
ms.openlocfilehash: a2b4ed11f1d56927a4bc7eed6ce36b5b04411509
ms.sourcegitcommit: a5bc64abb02201cb5c2ff6696f6ef99064e1cae7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753442"
---
# <a name="configure-presence-privacy-mode"></a><span data-ttu-id="198b3-103">プレゼンス プライバシー モードを設定する</span><span class="sxs-lookup"><span data-stu-id="198b3-103">Configure presence privacy mode</span></span>

> [!IMPORTANT]
> <span data-ttu-id="198b3-104">Microsoft Teams 管理センターは、Skype for Business 管理センター (従来のポータル) に代わるものです。</span><span class="sxs-lookup"><span data-stu-id="198b3-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="198b3-105">Skype for Business を管理するためのすべての設定が Teams 管理センターになりました。</span><span class="sxs-lookup"><span data-stu-id="198b3-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="198b3-106">Teams 管理センターで Skype for Business の機能を管理するには、グローバル管理者または Skype for Business 管理者の [AZURE AD 管理者の役割](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="198b3-106">You must be assigned the [Azure AD admin role](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="198b3-107">詳細については、「 [Microsoft Teams 管理センターで Skype For business の設定を管理](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="198b3-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

<span data-ttu-id="198b3-108">Skype for Business Online のプレゼンス設定を使用すると、ユーザーは連絡可能か、会議中か、または外出中かをより詳細に制御できます。</span><span class="sxs-lookup"><span data-stu-id="198b3-108">The Skype for Business Online presence setting gives people more control over who can see whether they are available, in a meeting, or out of the office.</span></span> <span data-ttu-id="198b3-109">Skype for Business のプレゼンスとプライバシーの設定の詳細については、「 [skype For Business Online でプレゼンスを設定する](configure-presence-in-skype-for-business-online.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="198b3-109">For details about Skype for Business presence and privacy settings, see [Configure presence in Skype for Business Online](configure-presence-in-skype-for-business-online.md).</span></span> 
  
## <a name="choose-the-default-online-presence-setting-for-everyone-in-your-organization"></a><span data-ttu-id="198b3-110">組織内のすべてのユーザーに対して既定のオンラインプレゼンス設定を選択する</span><span class="sxs-lookup"><span data-stu-id="198b3-110">Choose the default online presence setting for everyone in your organization</span></span>
<span data-ttu-id="198b3-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="198b3-111"><a name="__top"> </a></span></span>

1. <span data-ttu-id="198b3-112">[Skype for Business Online 管理センター > **組織 > 全般**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="198b3-112">Go to the Skype for Business Online admin center > **Organization > General**.</span></span>
    
2. <span data-ttu-id="198b3-113">[ **プレゼンスプライバシーモード**] で設定を選択し、[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="198b3-113">Under **Presence privacy mode**, choose the setting, and then click **Save**.</span></span>
    
|<span data-ttu-id="198b3-114">**設定**</span><span class="sxs-lookup"><span data-stu-id="198b3-114">**Setting**</span></span>|<span data-ttu-id="198b3-115">**ユーザーのプレゼンスを表示できるユーザー**</span><span class="sxs-lookup"><span data-stu-id="198b3-115">**Who can view a user's presence**</span></span>|
|:-----|:-----|
|<span data-ttu-id="198b3-116">**プレゼンス情報を自動的に表示する**</span><span class="sxs-lookup"><span data-stu-id="198b3-116">**Automatically display presence information**</span></span> <br/> |<span data-ttu-id="198b3-117">[ **外部** ] または [ **禁止済み** ] プライバシー グループに属していないすべての Skype for Business ユーザー。</span><span class="sxs-lookup"><span data-stu-id="198b3-117">Any Skype for Business user who does not belong to the **External** or **Blocked** privacy group.</span></span> <br/> |
|<span data-ttu-id="198b3-118">**プレゼンス情報をユーザーの連絡先にのみ表示する**</span><span class="sxs-lookup"><span data-stu-id="198b3-118">**Display presence information only to a user's contacts**</span></span> <br/> |<span data-ttu-id="198b3-119">ユーザーの連絡先リストに含まれる人のうち、[ **外部** ] または [ **禁止** 済み] プライバシーグループに属していない人</span><span class="sxs-lookup"><span data-stu-id="198b3-119">Anyone in a user's contact list who does not belong to the **External** or **Blocked** privacy group.</span></span> <br/> <span data-ttu-id="198b3-120">個々のユーザーは、Skype for Business の [ **オプション** ] ダイアログボックスでこの設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="198b3-120">Individual users can change this setting in the Skype for Business **Options** dialog box.</span></span> <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="198b3-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="198b3-121">Related topics</span></span>
[<span data-ttu-id="198b3-122">Skype for Business Online をセットアップする</span><span class="sxs-lookup"><span data-stu-id="198b3-122">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="198b3-123">Skype for Business ユーザーが Skype の連絡先を追加できるようにする</span><span class="sxs-lookup"><span data-stu-id="198b3-123">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
