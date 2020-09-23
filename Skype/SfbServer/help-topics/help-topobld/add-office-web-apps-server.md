---
title: Office Web Apps サーバーを追加する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
description: '[新しい Office Web Apps サーバーの定義] ウィザードは、展開に新しい Office Web Apps サーバーを定義します。 以下の情報を入力します。'
ms.openlocfilehash: 9e1726ea4b536e46fdbca5ec3eddce25358cbbbb
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218728"
---
# <a name="add-office-web-apps-server"></a><span data-ttu-id="9d375-104">Office Web Apps サーバーを追加する</span><span class="sxs-lookup"><span data-stu-id="9d375-104">Add Office Web Apps Server</span></span>

<span data-ttu-id="9d375-105">[ **新しい Office Web Apps サーバーの定義** ] ウィザードは、展開に新しい Office Web apps サーバーを定義します。</span><span class="sxs-lookup"><span data-stu-id="9d375-105">The **Define New Office Web Apps Server** wizard defines a new Office Web Apps Server in your deployment.</span></span> <span data-ttu-id="9d375-106">以下の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="9d375-106">You fill in the following information:</span></span>

 <span data-ttu-id="9d375-107">**Office Web Apps サーバーの FQDN**: Office Web apps サーバーをホストするサーバーの完全修飾ドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="9d375-107">**Office Web Apps Server FQDN**: Type the fully qualified domain name of the server that will host the Office Web Apps Server</span></span>

 <span data-ttu-id="9d375-108">**Office Web Apps サーバー検出 url**: Office Web apps サーバーの完全な url (uniform resource locator) を入力します。</span><span class="sxs-lookup"><span data-stu-id="9d375-108">**Office Web Apps Server discovery URL**: Type the full uniform resource locator (URL) of the Office Web Apps Server</span></span>

> [!TIP]
> <span data-ttu-id="9d375-109">**Office Web Apps サーバー検出 url**の既定の動作では、Office Web apps サーバーの FQDN に基づいて url を次の形式で作成し `https://<FQDN of the Office Web Apps Server/hosting/discovery` ます。</span><span class="sxs-lookup"><span data-stu-id="9d375-109">The default behavior of the **Office Web Apps Server discovery URL** is to create the URL based on the FQDN of the Office Web Apps Server in the format: `https://<FQDN of the Office Web Apps Server/hosting/discovery` .</span></span> <span data-ttu-id="9d375-110">多くの場合、既定の形式を変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9d375-110">In most cases you will not need to change the default format.</span></span> <span data-ttu-id="9d375-111">Office Web Apps サーバーと Office Web Apps サーバー検出の URL が異なる場合は、既定の形式を変更する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="9d375-111">You may need to change the default format in the event that the Office Web Apps Server and the Office Web Apps Server discovery URL must be different.</span></span> <span data-ttu-id="9d375-112">たとえば、Office Web Apps サーバーは境界ネットワークに配置され、その場所に基づいて異なる URL を持ちます。</span><span class="sxs-lookup"><span data-stu-id="9d375-112">For example, your Office Web Apps Server is placed in the perimeter network and will have a different URL based on the location.</span></span>

 <span data-ttu-id="9d375-113">**Office Web Apps サーバーが外部ネットワーク (境界/インターネット) に展開され**ている場合: 境界ネットワーク、外部ネットワーク、内部ネットワークと同じではない他のネットワークゾーンなど、Office Web apps サーバーを内部ファイアウォールの外側に配置する場合は、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="9d375-113">**Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**: Select the check box if your Office Web Apps Server is placed outside of your internal firewall, such as the perimeter network, external network, or other network zone that is not the same as your internal network.</span></span>

## <a name="see-also"></a><span data-ttu-id="9d375-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="9d375-114">See also</span></span>

[<span data-ttu-id="9d375-115">会議のコンポーネンツおよびトポロジ</span><span class="sxs-lookup"><span data-stu-id="9d375-115">Components and Topologies for Conferencing</span></span>](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)
