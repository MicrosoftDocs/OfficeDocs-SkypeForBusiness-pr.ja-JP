---
title: 移行後の簡易 URL の変更
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business Server は簡易 Url をサポートしています。
ms.openlocfilehash: 1b25dd74f5bdca433554091b3f8ce1c1d2dfa8ce
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753907"
---
# <a name="change-simple-urls-after-migration"></a><span data-ttu-id="ccf0d-103">移行後の簡易 URL の変更</span><span class="sxs-lookup"><span data-stu-id="ccf0d-103">Change simple URLs after migration</span></span>

<span data-ttu-id="ccf0d-104">Skype for Business Server は、次の3つの簡単な Url をサポートします。</span><span class="sxs-lookup"><span data-stu-id="ccf0d-104">Skype for Business Server supports three simple URLs:</span></span>
  
- <span data-ttu-id="ccf0d-105">**Meet**は、サイトまたは組織内のすべての電話会議のベース URL として使用されます。</span><span class="sxs-lookup"><span data-stu-id="ccf0d-105">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="ccf0d-106">簡単な会議 URL を使用すると、会議に参加するためのリンクが覚えやすくなり、通知も配布も簡単になります。</span><span class="sxs-lookup"><span data-stu-id="ccf0d-106">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span> 
    
- <span data-ttu-id="ccf0d-107">**ダイヤル**インは、ダイヤルイン会議設定 web ページへのアクセスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="ccf0d-107">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="ccf0d-108">ダイヤルインの簡易 URL は、すべての会議出席依頼に含まれているため、会議にダイヤルインするユーザーは必要な電話番号と PIN 情報にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="ccf0d-108">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span> 
    
- <span data-ttu-id="ccf0d-109">**管理者**は、Skype For Business Server コントロールパネルにすばやくアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="ccf0d-109">**Admin** enables quick access to the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="ccf0d-110">簡単な管理 URL は、組織内部の URL です。</span><span class="sxs-lookup"><span data-stu-id="ccf0d-110">The Admin simple URL is internal to your organization.</span></span> 
    
<span data-ttu-id="ccf0d-111">Skype for Business Server に移行した後は、簡単な Url の DNS レコードと証明書に対する変更による影響に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ccf0d-111">After migrating to Skype for Business Server, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="ccf0d-112">従来の Skype for Business Server のディレクターがトポロジで使用されている場合は、簡易 Url を変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ccf0d-112">If the legacy Skype for Business Server Director remains in use in the topology, no changes to your simple URLs are required.</span></span> <span data-ttu-id="ccf0d-113">移行後に、Skype for Business Server ディレクターがトポロジから削除された場合は、簡易 URL の DNS レコードを更新して、Skype for Business サーバープールの1つをポイントする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ccf0d-113">If the Skype for Business Server Director is removed from the topology after migration, the simple URL DNS records must be updated to point to one of the Skype for Business Server pools.</span></span> <span data-ttu-id="ccf0d-114">ただし、簡易 URL 名を変更する場合は必ず、各ディレクターおよびフロントエンド サーバーで Enable-CsComputer を実行して変更を登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ccf0d-114">Whenever you change a simple URL name, however, you must run Enable-CsComputer on each Director and Front End Server to register the change.</span></span>

## <a name="to-update-the-meet-simple-url"></a><span data-ttu-id="ccf0d-115">簡単な会議 URL を更新するには</span><span class="sxs-lookup"><span data-stu-id="ccf0d-115">To update the Meet simple URL</span></span>

1. <span data-ttu-id="ccf0d-116">[トポロジビルダー] で、最上位ノードの [ **Skype For Business Server**] を右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ccf0d-116">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="ccf0d-117">左側のウィンドウで [**簡易 url** ] を選択し、[**会議の url:** ] の下の [url の**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ccf0d-117">Select **Simple URLs** in the left pane, then below **Meeting URLs:** select the Meet URL and then click **Edit URL**.</span></span>
    
3. <span data-ttu-id="ccf0d-118">URL を目的の値に更新し、[**OK**] をクリックして編集した URL を保存します。</span><span class="sxs-lookup"><span data-stu-id="ccf0d-118">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span> 
    
## <a name="to-update-the-admin-simple-url"></a><span data-ttu-id="ccf0d-119">管理者の簡易 URL を更新するには</span><span class="sxs-lookup"><span data-stu-id="ccf0d-119">To update the Admin simple URL</span></span>

1. <span data-ttu-id="ccf0d-120">[トポロジビルダー] で、最上位ノードの [ **Skype For Business Server**] を右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ccf0d-120">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="ccf0d-121">[**簡易 url**の選択] 左側のウィンドウで、[**管理アクセス url** ] ボックスに、Skype For business Server コントロールパネルへの管理アクセスに使用する簡易 url を入力し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ccf0d-121">Select **Simple URLs** in the left pane, then below **Administrative access URL** box, enter the simple URL you want for administrative access to Skype for Business Server Control Panel, and then click **OK**.</span></span>
    
   > [!TIP]
   > <span data-ttu-id="ccf0d-122">管理 URL にできるだけ簡易 URL を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ccf0d-122">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="ccf0d-123">最も簡単なオプションは、 https://admin . <em>\<domain\></em> .</span><span class="sxs-lookup"><span data-stu-id="ccf0d-123">The simplest option is https://admin.<em>\<domain\></em>.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ccf0d-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="ccf0d-124">See also</span></span>

[<span data-ttu-id="ccf0d-125">Skype for Business Server の簡易 Url の DNS 要件</span><span class="sxs-lookup"><span data-stu-id="ccf0d-125">DNS requirements for simple URLs in Skype for Business Server</span></span>](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
