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
description: Skype 会議ブロードキャストを有効にして、それらの会議の設定とポリシーを変更できます。
ms.openlocfilehash: 75b1894f486d6448662c459b0d77d4f5d3057a2f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106553"
---
# <a name="make-changes-to-skype-meeting-broadcast-settings-for-your-organization"></a><span data-ttu-id="0cd7a-103">組織の Skype 会議ブロードキャストの設定を変更する</span><span class="sxs-lookup"><span data-stu-id="0cd7a-103">Make changes to Skype Meeting Broadcast settings for your organization</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0cd7a-104">Microsoft Teams 管理センターは、Skype for Business 管理センター (レガシ ポータル) に置き換えました。</span><span class="sxs-lookup"><span data-stu-id="0cd7a-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="0cd7a-105">Skype for Business を管理するためのすべての設定が Teams 管理センターに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0cd7a-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="0cd7a-106">Teams 管理センターで Skype for Business [AD](/azure/active-directory/roles/permissions-reference) を管理するには、グローバル管理者または Skype for Business 管理者の Azure 管理者ロールが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0cd7a-106">You must be assigned the [Azure AD admin role](/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="0cd7a-107">詳細については、「[Microsoft Teams 管理センターで Skype for Business の設定を管理する](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0cd7a-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span></span>

<span data-ttu-id="0cd7a-108">Skype 会議ブロードキャストを有効にして、それらの会議の設定とポリシーを変更できます。</span><span class="sxs-lookup"><span data-stu-id="0cd7a-108">You can enable Skype Meeting Broadcast and make changes to settings and policies for those meetings.</span></span>
  
- <span data-ttu-id="0cd7a-109">**Skype 会議ブロードキャストを有効にする** Skype 会議ブロードキャストを有効にする。</span><span class="sxs-lookup"><span data-stu-id="0cd7a-109">**Enable Skype Meeting Broadcast** Enables Skype Meeting Broadcast.</span></span> <span data-ttu-id="0cd7a-110">Skype 会議ブロードキャストを有効にした後、Skype 会議ブロードキャスト用にネットワーク [をセットアップする必要があります](set-up-your-network-for-skype-meeting-broadcast.md)。</span><span class="sxs-lookup"><span data-stu-id="0cd7a-110">After you enable Skype Meeting Broadcast, you need to [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> <span data-ttu-id="0cd7a-111">社外のユーザーのためにウェビナーや他のブロードキャストを開催する場合は、この手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0cd7a-111">Do this step if you want to hold webinars and other broadcasts for people outside of your business.</span></span> 
    
- <span data-ttu-id="0cd7a-112">**組織で Skype 会議ブロードキャストプレビュー機能を有効にする** Skype for Business のお客様プログラムでは、新しい製品や機能に早期にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="0cd7a-112">**Enable Skype Meeting Broadcast Preview features for my organization** The Skype for Business customer programs provide you early access to new products and features.</span></span> <span data-ttu-id="0cd7a-113">これにより、製品ビルドを一般ユーザーにリリースする前に、今後の機能と、お客様の環境で新機能をテストし、フィードバックを提供する機会を組織に詳細に確認することができます。</span><span class="sxs-lookup"><span data-stu-id="0cd7a-113">This gives your organization a sneak peek at what's coming and the opportunity to test the new features in your own environment and give feedback before we release product builds to the general public.</span></span><br/>[<span data-ttu-id="0cd7a-114">Skype for Business プレビュー</span><span class="sxs-lookup"><span data-stu-id="0cd7a-114">Skype for Business preview</span></span>](https://www.skypepreview.com/)
    
- <span data-ttu-id="0cd7a-115">**開催者が匿名の会議をスケジュールできる** これにより、開催者は、組織外のユーザーがサインインする必要なく参加できるブロードキャスト イベントを作成できます。</span><span class="sxs-lookup"><span data-stu-id="0cd7a-115">**Allow organizers to schedule anonymous meetings** This lets organizers create broadcast events that allow anyone outside their organization to join without a requirement to sign in.</span></span>
    
- <span data-ttu-id="0cd7a-116">**ブロードキャスト会議の記録を許可する** これにより、発表者または開催者が記録する必要がある会議を作成できます。</span><span class="sxs-lookup"><span data-stu-id="0cd7a-116">**Allow broadcast meetings to be recorded** This enables any meetings you have to be recorded by the presenter or organizer.</span></span>
    
- <span data-ttu-id="0cd7a-117">**出席者向けヘルプデスク サポートの URL** ブロードキャスト会議の接続または出席に関するヘルプが必要な場合に使用する会議ブロードキャスト出席者のリンクを入力します。</span><span class="sxs-lookup"><span data-stu-id="0cd7a-117">**Helpdesk support URL for attendees** Enter a link for meeting broadcast attendees to use if they need help connecting or attending a broadcast meeting.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="0cd7a-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="0cd7a-118">Related topics</span></span>

[<span data-ttu-id="0cd7a-119">Skype 会議ブロードキャスト用にネットワークをセットアップする</span><span class="sxs-lookup"><span data-stu-id="0cd7a-119">Set up your network for Skype Meeting Broadcast</span></span>](set-up-your-network-for-skype-meeting-broadcast.md)

  
