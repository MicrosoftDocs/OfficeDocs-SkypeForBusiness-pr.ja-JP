---
title: Office Web Apps サーバーを追加する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: '[Web Apps サーバー Officeの定義] ウィザードでは、展開で新Office Web Apps Server を定義します。 以下の情報を入力します。'
ms.openlocfilehash: 002566fb77539745d1d0023159e9af7852b1ecdc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119706"
---
# <a name="add-office-web-apps-server"></a><span data-ttu-id="52c76-104">Office Web Apps サーバーの追加</span><span class="sxs-lookup"><span data-stu-id="52c76-104">Add Office Web Apps Server</span></span>

<span data-ttu-id="52c76-105">[Web **Apps サーバー Office定義** ] ウィザードでは、展開で Web Apps サーバー Office新しいアプリケーションを定義します。</span><span class="sxs-lookup"><span data-stu-id="52c76-105">The **Define New Office Web Apps Server** wizard defines a new Office Web Apps Server in your deployment.</span></span> <span data-ttu-id="52c76-106">以下の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="52c76-106">You fill in the following information:</span></span>

 <span data-ttu-id="52c76-107">**Office Web Apps Server FQDN**: Web Apps Server をホストするサーバーの完全修飾ドメイン名Office入力します。</span><span class="sxs-lookup"><span data-stu-id="52c76-107">**Office Web Apps Server FQDN**: Type the fully qualified domain name of the server that will host the Office Web Apps Server</span></span>

 <span data-ttu-id="52c76-108">**Office Web Apps サーバーの** 検出 URL : Web Apps Server の完全な統一リソース ロケーター (URL) をOfficeします。</span><span class="sxs-lookup"><span data-stu-id="52c76-108">**Office Web Apps Server discovery URL**: Type the full uniform resource locator (URL) of the Office Web Apps Server</span></span>

> [!TIP]
> <span data-ttu-id="52c76-109">Web Apps Server Office **検出 URL** の既定の動作は、次の形式で Office Web Apps Server の FQDN に基づいて URL を作成することです `https://<FQDN of the Office Web Apps Server/hosting/discovery` 。</span><span class="sxs-lookup"><span data-stu-id="52c76-109">The default behavior of the **Office Web Apps Server discovery URL** is to create the URL based on the FQDN of the Office Web Apps Server in the format: `https://<FQDN of the Office Web Apps Server/hosting/discovery` .</span></span> <span data-ttu-id="52c76-110">多くの場合、既定の形式を変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="52c76-110">In most cases you will not need to change the default format.</span></span> <span data-ttu-id="52c76-111">Web Apps Server と Web Apps Server の検出 URL が異なる必要がある場合Office Office既定の形式を変更する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="52c76-111">You may need to change the default format in the event that the Office Web Apps Server and the Office Web Apps Server discovery URL must be different.</span></span> <span data-ttu-id="52c76-112">たとえば、Web Apps サーバー Office境界ネットワークに配置され、場所に基づいて別の URL が作成されます。</span><span class="sxs-lookup"><span data-stu-id="52c76-112">For example, your Office Web Apps Server is placed in the perimeter network and will have a different URL based on the location.</span></span>

 <span data-ttu-id="52c76-113">**Office Web Apps Server** が外部ネットワーク (境界/インターネット) に展開されている場合: Office Web Apps Server が内部ファイアウォールの外部 (境界ネットワーク、外部ネットワーク、内部ネットワークと同じではない他のネットワーク 領域など) に配置されている場合は、チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="52c76-113">**Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**: Select the check box if your Office Web Apps Server is placed outside of your internal firewall, such as the perimeter network, external network, or other network zone that is not the same as your internal network.</span></span>

## <a name="see-also"></a><span data-ttu-id="52c76-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="52c76-114">See also</span></span>

[<span data-ttu-id="52c76-115">会議のコンポーネンツおよびトポロジ</span><span class="sxs-lookup"><span data-stu-id="52c76-115">Components and Topologies for Conferencing</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-conferencing)