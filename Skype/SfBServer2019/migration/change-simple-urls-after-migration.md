---
title: 移行後の簡単な Url の変更
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ビジネス サーバーの Skype では、単純な Url をサポートします。
ms.openlocfilehash: a67e9a8ef46b7809fdc8ce8b4eaadc2ca4720966
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028832"
---
# <a name="change-simple-urls-after-migration"></a><span data-ttu-id="52658-103">移行後の簡単な Url の変更</span><span class="sxs-lookup"><span data-stu-id="52658-103">Change simple URLs after migration</span></span>

<span data-ttu-id="52658-104">Skype ビジネス サーバーは、次の 3 つの簡単な Url をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="52658-104">Skype for Business Server supports three simple URLs:</span></span>
  
- <span data-ttu-id="52658-105">**対応**は、サイトまたは組織内のすべての会議のベース URL として使用されます。</span><span class="sxs-lookup"><span data-stu-id="52658-105">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="52658-106">対応の簡単な URL を使用して会議への参加へのリンクは、簡単に理解するには、簡単に通信して、配布です。</span><span class="sxs-lookup"><span data-stu-id="52658-106">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span> 
    
- <span data-ttu-id="52658-107">**ダイヤルインの**ダイヤルイン会議設定 web ページへのアクセスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="52658-107">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="52658-108">ダイヤルインの簡易 URL は、すべての会議への招待に含まれるため、会議にダイヤルインするユーザーは、必要な電話番号および PIN 情報にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="52658-108">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span> 
    
- <span data-ttu-id="52658-109">**管理者**は、業務サーバーのコントロール パネルの Skype へのすばやいアクセスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="52658-109">**Admin** enables quick access to the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="52658-110">管理の簡易 URL は、組織内部の URL です。</span><span class="sxs-lookup"><span data-stu-id="52658-110">The Admin simple URL is internal to your organization.</span></span> 
    
<span data-ttu-id="52658-111">に移行した後 Skype ビジネス サーバーの変更に及ぼす影響について、DNS レコードと証明書の簡単な Url に注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="52658-111">After migrating to Skype for Business Server, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="52658-112">従来の Skype ビジネス サーバー ディレクターのトポロジの使用のままになります、簡単な Url への変更の必要はありません。</span><span class="sxs-lookup"><span data-stu-id="52658-112">If the legacy Skype for Business Server Director remains in use in the topology, no changes to your simple URLs are required.</span></span> <span data-ttu-id="52658-113">Skype ビジネス サーバー ディレクターの移行後のトポロジから削除する場合は、ビジネスのサーバー プールの Skype のいずれかを指すように簡単な URL の DNS レコードを更新しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="52658-113">If the Skype for Business Server Director is removed from the topology after migration, the simple URL DNS records must be updated to point to one of the Skype for Business Server pools.</span></span> <span data-ttu-id="52658-114">簡単な URL 名を変更するたびに、変更を登録するには各ディレクターおよびフロント エンド サーバーで有効にする CsComputer を実行してください。</span><span class="sxs-lookup"><span data-stu-id="52658-114">Whenever you change a simple URL name, however, you must run Enable-CsComputer on each Director and Front End Server to register the change.</span></span>

## <a name="to-update-the-meet-simple-url"></a><span data-ttu-id="52658-115">対応の簡単な URL を更新するには</span><span class="sxs-lookup"><span data-stu-id="52658-115">To update the Meet simple URL</span></span>

1. <span data-ttu-id="52658-116">トポロジ ビルダーでは、 **Skype**ビジネス サーバーは、最上位のノードを右クリックし、**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="52658-116">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="52658-117">下、左側のウィンドウで**簡単な Url**を選択**会議 Url:** を満たす URL を選択し、 **[URL の編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="52658-117">Select **Simple URLs** in the left pane, then below **Meeting URLs:** select the Meet URL and then click **Edit URL**.</span></span>
    
3. <span data-ttu-id="52658-118">URL を目的の値に更新し、[**OK**] をクリックして編集した URL を保存します。</span><span class="sxs-lookup"><span data-stu-id="52658-118">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span> 
    
## <a name="to-update-the-admin-simple-url"></a><span data-ttu-id="52658-119">管理の簡単な URL を更新するには</span><span class="sxs-lookup"><span data-stu-id="52658-119">To update the Admin simple URL</span></span>

1. <span data-ttu-id="52658-120">トポロジ ビルダーでは、 **Skype**ビジネス サーバーは、最上位のノードを右クリックし、**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="52658-120">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="52658-121">**管理アクセス URL** ] ボックスの下の左側のウィンドウで、**単純な Url**を選択、ビジネス サーバーのコントロール パネル、Skype への管理アクセスをする簡単な URL を入力し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="52658-121">Select **Simple URLs** in the left pane, then below **Administrative access URL** box, enter the simple URL you want for administrative access to Skype for Business Server Control Panel, and then click **OK**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="52658-122">管理 URL には、できる限りシンプルな URL を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="52658-122">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="52658-123">最も簡単なオプションは、 https://admin。_\<ドメイン\>_。</span><span class="sxs-lookup"><span data-stu-id="52658-123">The simplest option is https://admin._\<domain\>_.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="52658-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="52658-124">See also</span></span>

[<span data-ttu-id="52658-125">Skype で簡単な Url のビジネス サーバー用の DNS の要件</span><span class="sxs-lookup"><span data-stu-id="52658-125">DNS requirements for simple URLs in Skype for Business Server</span></span>](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
