---
title: 移行後の簡易 URL の変更
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype for Business Server は、単純な Url をサポートしています。
ms.openlocfilehash: 786e3f5d7ed273c0f3c2ccc39ef1b539714de61b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298327"
---
# <a name="change-simple-urls-after-migration"></a><span data-ttu-id="dff33-103">移行後の簡易 URL の変更</span><span class="sxs-lookup"><span data-stu-id="dff33-103">Change simple URLs after migration</span></span>

<span data-ttu-id="dff33-104">Skype for Business Server は、次の3つの簡単な Url をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="dff33-104">Skype for Business Server supports three simple URLs:</span></span>
  
- <span data-ttu-id="dff33-105">**会議**は、サイトまたは組織内のすべての会議のベース URL として使用されます。</span><span class="sxs-lookup"><span data-stu-id="dff33-105">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="dff33-106">[会議への参加] の [シンプル URL] を使用すると、会議に参加するためのリンクを簡単に理解して、簡単に連絡して配布することができます。</span><span class="sxs-lookup"><span data-stu-id="dff33-106">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span> 
    
- <span data-ttu-id="dff33-107">[**ダイヤル**イン] は、ダイヤルイン会議の設定の web ページにアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="dff33-107">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="dff33-108">ダイヤルインの簡易 URL は、会議にダイヤルインするユーザーが必要な電話番号と PIN 情報にアクセスできるように、すべての会議出席依頼に含まれています。</span><span class="sxs-lookup"><span data-stu-id="dff33-108">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span> 
    
- <span data-ttu-id="dff33-109">**管理者**が Skype For Business Server コントロールパネルにすばやくアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="dff33-109">**Admin** enables quick access to the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="dff33-110">管理者の簡易 URL は、組織の内部にあります。</span><span class="sxs-lookup"><span data-stu-id="dff33-110">The Admin simple URL is internal to your organization.</span></span> 
    
<span data-ttu-id="dff33-111">Skype for Business Server に移行した後、変更によって単純な Url の DNS レコードと証明書にどのような影響があるかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dff33-111">After migrating to Skype for Business Server, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="dff33-112">従来の Skype for Business Server ディレクターがトポロジでまだ使用されている場合は、単純な Url への変更は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="dff33-112">If the legacy Skype for Business Server Director remains in use in the topology, no changes to your simple URLs are required.</span></span> <span data-ttu-id="dff33-113">移行後に Skype for Business Server ディレクターがトポロジから削除された場合、Skype for Business サーバープールの1つをポイントするように、単純な URL の DNS レコードを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dff33-113">If the Skype for Business Server Director is removed from the topology after migration, the simple URL DNS records must be updated to point to one of the Skype for Business Server pools.</span></span> <span data-ttu-id="dff33-114">ただし、単純な URL 名を変更する場合は必ず、各ディレクターとフロントエンドサーバーで [ユーザーの有効化] を実行して、変更を登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dff33-114">Whenever you change a simple URL name, however, you must run Enable-CsComputer on each Director and Front End Server to register the change.</span></span>

## <a name="to-update-the-meet-simple-url"></a><span data-ttu-id="dff33-115">[シンプルの概要 URL を更新するには、</span><span class="sxs-lookup"><span data-stu-id="dff33-115">To update the Meet simple URL</span></span>

1. <span data-ttu-id="dff33-116">トポロジビルダーで、トップノードの**Skype For Business サーバー**を右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dff33-116">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="dff33-117">左側のウィンドウで [**単純な url** ] を選び、[会議 url] を選び**ます。** [会議 url] を選び、[ **url の編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dff33-117">Select **Simple URLs** in the left pane, then below **Meeting URLs:** select the Meet URL and then click **Edit URL**.</span></span>
    
3. <span data-ttu-id="dff33-118">URL を目的の値に更新し、[**OK**] をクリックして編集した URL を保存します。</span><span class="sxs-lookup"><span data-stu-id="dff33-118">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span> 
    
## <a name="to-update-the-admin-simple-url"></a><span data-ttu-id="dff33-119">管理者の簡易 URL を更新するには</span><span class="sxs-lookup"><span data-stu-id="dff33-119">To update the Admin simple URL</span></span>

1. <span data-ttu-id="dff33-120">トポロジビルダーで、トップノードの**Skype For Business サーバー**を右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dff33-120">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="dff33-121">左側のウィンドウで [**簡易 url** ] を選び、[**管理アクセス URL** ] ボックスに、Skype For business Server コントロールパネルへの管理アクセスに使用する単純な url を入力して、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dff33-121">Select **Simple URLs** in the left pane, then below **Administrative access URL** box, enter the simple URL you want for administrative access to Skype for Business Server Control Panel, and then click **OK**.</span></span>
    
   > [!TIP]
   > <span data-ttu-id="dff33-122">管理 URL には、できる限りシンプルな URL を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dff33-122">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="dff33-123">最も簡単なオプションhttps://adminはです。<em> \<ドメイン\></em>。</span><span class="sxs-lookup"><span data-stu-id="dff33-123">The simplest option is https://admin.<em>\<domain\></em>.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="dff33-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="dff33-124">See also</span></span>

[<span data-ttu-id="dff33-125">Skype for Business Server の単純な Url の DNS 要件</span><span class="sxs-lookup"><span data-stu-id="dff33-125">DNS requirements for simple URLs in Skype for Business Server</span></span>](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
