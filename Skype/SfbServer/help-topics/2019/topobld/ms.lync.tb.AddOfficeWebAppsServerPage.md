---
title: Office Web Apps サーバーを追加する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
ROBOTS: NOINDEX, NOFOLLOW
description: '[新しい Office Web Apps サーバーの定義] ウィザードでは、展開で新しい Office Web Apps サーバーを定義します。 以下の情報を入力します。'
ms.openlocfilehash: f5cf9c686ec7d42db6db15021e28493507f954b5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306165"
---
# <a name="add-office-web-apps-server"></a><span data-ttu-id="ce634-104">Office Web Apps サーバーを追加する</span><span class="sxs-lookup"><span data-stu-id="ce634-104">Add Office Web Apps Server</span></span>

<span data-ttu-id="ce634-105">[**新しい Office Web Apps サーバーの定義**] ウィザードでは、展開で新しい Office Web apps サーバーを定義します。</span><span class="sxs-lookup"><span data-stu-id="ce634-105">The **Define New Office Web Apps Server** wizard defines a new Office Web Apps Server in your deployment.</span></span> <span data-ttu-id="ce634-106">以下の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="ce634-106">You fill in the following information:</span></span>

 <span data-ttu-id="ce634-107">**Office Web Apps サーバー FQDN**: Office Web apps サーバーをホストするサーバーの完全修飾ドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="ce634-107">**Office Web Apps Server FQDN**: Type the fully qualified domain name of the server that will host the Office Web Apps Server</span></span>

 <span data-ttu-id="ce634-108">**Office Web Apps サーバー検出 URL**: Office Web apps サーバーの完全な uniform resource LOCATOR (URL) を入力します。</span><span class="sxs-lookup"><span data-stu-id="ce634-108">**Office Web Apps Server discovery URL**: Type the full uniform resource locator (URL) of the Office Web Apps Server</span></span>

> [!TIP]
> <span data-ttu-id="ce634-109">**Office Web Apps サーバー検出 URL**の既定の動作では、次`https://<FQDN of the Office Web Apps Server/hosting/discovery`の形式の office WEB apps サーバーの FQDN に基づいて url が作成されます。</span><span class="sxs-lookup"><span data-stu-id="ce634-109">The default behavior of the **Office Web Apps Server discovery URL** is to create the URL based on the FQDN of the Office Web Apps Server in the format: `https://<FQDN of the Office Web Apps Server/hosting/discovery` .</span></span> <span data-ttu-id="ce634-110">多くの場合、既定の形式を変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ce634-110">In most cases you will not need to change the default format.</span></span> <span data-ttu-id="ce634-111">Office Web Apps サーバーと Office Web Apps サーバー検出 URL が異なっている必要がある場合は、既定の形式を変更する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="ce634-111">You may need to change the default format in the event that the Office Web Apps Server and the Office Web Apps Server discovery URL must be different.</span></span> <span data-ttu-id="ce634-112">たとえば、Office Web Apps サーバーは境界ネットワーク内に配置され、その場所に基づいて異なる URL が設定されます。</span><span class="sxs-lookup"><span data-stu-id="ce634-112">For example, your Office Web Apps Server is placed in the perimeter network and will have a different URL based on the location.</span></span>

 <span data-ttu-id="ce634-113">**Office Web Apps サーバーは外部ネットワーク (つまり、境界/インターネット) に展開され**ます。 Office Web apps サーバーが、境界ネットワーク、外部ネットワーク、その他のネットワークゾーンなどの内部ファイアウォールの外側に配置されている場合は、このチェックボックスをオンにします。これは、内部ネットワークとは異なります。</span><span class="sxs-lookup"><span data-stu-id="ce634-113">**Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**: Select the check box if your Office Web Apps Server is placed outside of your internal firewall, such as the perimeter network, external network, or other network zone that is not the same as your internal network.</span></span>

## <a name="see-also"></a><span data-ttu-id="ce634-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="ce634-114">See also</span></span>

[<span data-ttu-id="ce634-115">Components and Topologies for Conferencing</span><span class="sxs-lookup"><span data-stu-id="ce634-115">Components and Topologies for Conferencing</span></span>](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)
