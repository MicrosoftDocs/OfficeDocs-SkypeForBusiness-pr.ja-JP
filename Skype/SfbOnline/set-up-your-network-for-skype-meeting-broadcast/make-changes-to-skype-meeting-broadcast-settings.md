---
title: 組織の Skype 会議ブロードキャストの設定を変更する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.topic: article
ms.assetid: 8e46e857-f046-4e87-a633-0d7fb88d66d5
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
- SMB
- ms.lync.lac.BroadcastMeetings
description: Skype 会議ブロードキャストを有効にして、会議の設定とポリシーを変更することができます。
ms.openlocfilehash: 88f074838ff1d03153441beb624bc5d9b7ad157c
ms.sourcegitcommit: a5bc64abb02201cb5c2ff6696f6ef99064e1cae7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753412"
---
# <a name="make-changes-to-skype-meeting-broadcast-settings-for-your-organization"></a><span data-ttu-id="1997a-103">組織の Skype 会議ブロードキャストの設定を変更する</span><span class="sxs-lookup"><span data-stu-id="1997a-103">Make changes to Skype Meeting Broadcast settings for your organization</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1997a-104">Microsoft Teams 管理センターは、Skype for Business 管理センター (従来のポータル) に代わるものです。</span><span class="sxs-lookup"><span data-stu-id="1997a-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="1997a-105">Skype for Business を管理するためのすべての設定が Teams 管理センターになりました。</span><span class="sxs-lookup"><span data-stu-id="1997a-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="1997a-106">Teams 管理センターで Skype for Business の機能を管理するには、グローバル管理者または Skype for Business 管理者の [AZURE AD 管理者の役割](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1997a-106">You must be assigned the [Azure AD admin role](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="1997a-107">詳細については、「 [Microsoft Teams 管理センターで Skype For business の設定を管理](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1997a-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

<span data-ttu-id="1997a-108">Skype 会議ブロードキャストを有効にして、会議の設定とポリシーを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="1997a-108">You can enable Skype Meeting Broadcast and make changes to settings and policies for those meetings.</span></span>
  
- <span data-ttu-id="1997a-109">**Skype 会議ブロードキャストを有効にする** Skype 会議ブロードキャストを有効にします。</span><span class="sxs-lookup"><span data-stu-id="1997a-109">**Enable Skype Meeting Broadcast** Enables Skype Meeting Broadcast.</span></span> <span data-ttu-id="1997a-110">Skype 会議ブロードキャストを有効にしたら、 [Skype 会議ブロードキャスト用にネットワークを設定](set-up-your-network-for-skype-meeting-broadcast.md)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1997a-110">After you enable Skype Meeting Broadcast, you need to [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> <span data-ttu-id="1997a-111">社外の人に対して、ウェビナーやその他のブロードキャストを保留にする場合は、この手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1997a-111">Do this step if you want to hold webinars and other broadcasts for people outside of your business.</span></span> 
    
- <span data-ttu-id="1997a-112">**組織で Skype 会議ブロードキャストのプレビュー機能を有効にする** Skype for Business の顧客プログラムを使用すると、新しい製品や機能にいち早くアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="1997a-112">**Enable Skype Meeting Broadcast Preview features for my organization** The Skype for Business customer programs provide you early access to new products and features.</span></span> <span data-ttu-id="1997a-113">これにより、組織は、現在の環境の新機能をテストし、製品ビルドを一般公開する前にフィードバックを提供することができます。</span><span class="sxs-lookup"><span data-stu-id="1997a-113">This gives your organization a sneak peek at what's coming and the opportunity to test the new features in your own environment and give feedback before we release product builds to the general public.</span></span><br/>[<span data-ttu-id="1997a-114">Skype for Business のプレビュー</span><span class="sxs-lookup"><span data-stu-id="1997a-114">Skype for Business preview</span></span>](https://www.skypepreview.com/)
    
- <span data-ttu-id="1997a-115">**開催者による匿名会議のスケジュールを許可する** これにより、開催者は、サインインの必要性なく組織外のすべてのユーザーが参加できるようにするブロードキャストイベントを作成できます。</span><span class="sxs-lookup"><span data-stu-id="1997a-115">**Allow organizers to schedule anonymous meetings** This lets organizers create broadcast events that allow anyone outside their organization to join without a requirement to sign in.</span></span>
    
- <span data-ttu-id="1997a-116">**ブロードキャスト会議を記録できるように** するこれにより、発表者または開催者によって記録されるすべての会議を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="1997a-116">**Allow broadcast meetings to be recorded** This enables any meetings you have to be recorded by the presenter or organizer.</span></span>
    
- <span data-ttu-id="1997a-117">**出席者のヘルプデスクサポート URL** ブロードキャスト会議への接続または参加に関するヘルプが必要な場合に使用する、会議ブロードキャストの出席者のためのリンクを入力します。</span><span class="sxs-lookup"><span data-stu-id="1997a-117">**Helpdesk support URL for attendees** Enter a link for meeting broadcast attendees to use if they need help connecting or attending a broadcast meeting.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="1997a-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="1997a-118">Related topics</span></span>

[<span data-ttu-id="1997a-119">Skype 会議ブロードキャスト用にネットワークをセットアップする</span><span class="sxs-lookup"><span data-stu-id="1997a-119">Set up your network for Skype Meeting Broadcast</span></span>](set-up-your-network-for-skype-meeting-broadcast.md)

  
 
