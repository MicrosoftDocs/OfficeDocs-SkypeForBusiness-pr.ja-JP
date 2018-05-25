---
title: Office Web Apps サーバーを追加する
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
description: 新しいオフィス ・ Web アプリケーション サーバーの定義ウィザードでは、展開の新しいオフィスの Web アプリケーション サーバーを定義します。 以下の情報を入力します。
ms.openlocfilehash: df8f2ba98215a597e9532e636b022edf9cb1ec19
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2018
---
# <a name="add-office-web-apps-server"></a><span data-ttu-id="05500-104">Office Web Apps サーバーを追加する</span><span class="sxs-lookup"><span data-stu-id="05500-104">Add Office Web Apps Server</span></span>
 
<span data-ttu-id="05500-105">**新しいオフィス ・ Web アプリケーション サーバーの定義**ウィザードでは、展開の新しいオフィスの Web アプリケーション サーバーを定義します。</span><span class="sxs-lookup"><span data-stu-id="05500-105">The **Define New Office Web Apps Server** wizard defines a new Office Web Apps Server in your deployment.</span></span> <span data-ttu-id="05500-106">以下の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="05500-106">You fill in the following information:</span></span>
  
 <span data-ttu-id="05500-107">**Office Web アプリケーション サーバーの FQDN**: Office の Web アプリケーション サーバーをホストするサーバーの完全修飾ドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="05500-107">**Office Web Apps Server FQDN**: Type the fully qualified domain name of the server that will host the Office Web Apps Server</span></span>
  
 <span data-ttu-id="05500-108">**Office Web アプリケーション サーバーの検出 URL**: Office Web アプリケーション サーバーの完全な統一リソース ロケーター (URL) を入力します。</span><span class="sxs-lookup"><span data-stu-id="05500-108">**Office Web Apps Server discovery URL**: Type the full uniform resource locator (URL) of the Office Web Apps Server</span></span>
  
> [!TIP]
> <span data-ttu-id="05500-109">形式で Office Web アプリケーション サーバーの FQDN に基づいて URL を作成するのには、 **Office Web アプリケーション サーバーの検出 URL**の既定の動作: `https://<FQDN of the Office Web Apps Server/hosting/discovery` 。</span><span class="sxs-lookup"><span data-stu-id="05500-109">The default behavior of the **Office Web Apps Server discovery URL** is to create the URL based on the FQDN of the Office Web Apps Server in the format: `https://<FQDN of the Office Web Apps Server/hosting/discovery` .</span></span> <span data-ttu-id="05500-110">多くの場合、既定の形式を変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="05500-110">In most cases you will not need to change the default format.</span></span> <span data-ttu-id="05500-111">Office Web アプリケーション サーバーと Web アプリケーション サーバーの検出 URL を別にする必要があることは、既定の書式を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="05500-111">You may need to change the default format in the event that the Office Web Apps Server and the Office Web Apps Server discovery URL must be different.</span></span> <span data-ttu-id="05500-112">などの Office Web アプリケーション サーバーは境界ネットワークに配置され、場所に基づいて別の URL があります。</span><span class="sxs-lookup"><span data-stu-id="05500-112">For example, your Office Web Apps Server is placed in the perimeter network and will have a different URL based on the location.</span></span>
  
 <span data-ttu-id="05500-113">**Office Web アプリケーション サーバーが外部ネットワーク (つまり、境界領域またはインターネット) に配置**します] チェック ボックスをオンに、Office Web アプリケーション サーバーが境界ネットワーク、外部ネットワーク、またはその他のネットワーク ゾーンなど、内部のファイアウォールの外側に配置されている場合。内部ネットワークと同じです。</span><span class="sxs-lookup"><span data-stu-id="05500-113">**Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**: Select the check box if your Office Web Apps Server is placed outside of your internal firewall, such as the perimeter network, external network, or other network zone that is not the same as your internal network.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="05500-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="05500-114">See also</span></span>

#### 

[<span data-ttu-id="05500-115">コンポーネントおよび会議のためのトポロジ</span><span class="sxs-lookup"><span data-stu-id="05500-115">Components and Topologies for Conferencing</span></span>](http://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)

