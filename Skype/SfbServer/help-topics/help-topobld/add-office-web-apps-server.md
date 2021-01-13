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
description: Web Apps サーバーのOfficeウィザードでは、展開内の Web Apps サーバー Office新しいアプリケーションを定義します。 以下の情報を入力します。
ms.openlocfilehash: a0d0543576b75e0572abf3fd043a73369d2af136
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828597"
---
# <a name="add-office-web-apps-server"></a><span data-ttu-id="89c18-104">Office Web Apps サーバーの追加</span><span class="sxs-lookup"><span data-stu-id="89c18-104">Add Office Web Apps Server</span></span>

<span data-ttu-id="89c18-105">Web **Apps サーバーのOfficeウィザードでは** 、展開内の Web Apps サーバー Office新しいアプリケーションを定義します。</span><span class="sxs-lookup"><span data-stu-id="89c18-105">The **Define New Office Web Apps Server** wizard defines a new Office Web Apps Server in your deployment.</span></span> <span data-ttu-id="89c18-106">以下の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="89c18-106">You fill in the following information:</span></span>

 <span data-ttu-id="89c18-107">**Office Web Apps サーバーの FQDN**: Web Apps サーバーをホストするサーバーの完全修飾ドメイン名Office入力します。</span><span class="sxs-lookup"><span data-stu-id="89c18-107">**Office Web Apps Server FQDN**: Type the fully qualified domain name of the server that will host the Office Web Apps Server</span></span>

 <span data-ttu-id="89c18-108">**Office Web Apps サーバーの検出 URL**: Web Apps サーバーの完全な URL (uniform resource locator) Office入力します。</span><span class="sxs-lookup"><span data-stu-id="89c18-108">**Office Web Apps Server discovery URL**: Type the full uniform resource locator (URL) of the Office Web Apps Server</span></span>

> [!TIP]
> <span data-ttu-id="89c18-109">**Office Web Apps サーバー** 検出 URL の既定の動作では、次の形式で Office Web Apps サーバーの FQDN に基づいて URL を作成します `https://<FQDN of the Office Web Apps Server/hosting/discovery` 。</span><span class="sxs-lookup"><span data-stu-id="89c18-109">The default behavior of the **Office Web Apps Server discovery URL** is to create the URL based on the FQDN of the Office Web Apps Server in the format: `https://<FQDN of the Office Web Apps Server/hosting/discovery` .</span></span> <span data-ttu-id="89c18-110">多くの場合、既定の形式を変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="89c18-110">In most cases you will not need to change the default format.</span></span> <span data-ttu-id="89c18-111">Web Apps サーバーと Office Web Apps サーバーの検出 URL が異なる必要Office場合は、既定の形式を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89c18-111">You may need to change the default format in the event that the Office Web Apps Server and the Office Web Apps Server discovery URL must be different.</span></span> <span data-ttu-id="89c18-112">たとえば、Office Web Apps サーバーは境界ネットワークに配置され、その場所に基づいて異なる URL を持つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="89c18-112">For example, your Office Web Apps Server is placed in the perimeter network and will have a different URL based on the location.</span></span>

 <span data-ttu-id="89c18-113">Office Web Apps サーバーが外部ネットワーク **(境界ネットワーク/インターネット)** に展開されている場合: Office Web Apps サーバーが内部ファイアウォールの外側 (境界ネットワーク、外部ネットワーク、または内部ネットワークと同じではないその他のネットワーク ゾーンなど) にある場合は、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="89c18-113">**Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**: Select the check box if your Office Web Apps Server is placed outside of your internal firewall, such as the perimeter network, external network, or other network zone that is not the same as your internal network.</span></span>

## <a name="see-also"></a><span data-ttu-id="89c18-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="89c18-114">See also</span></span>

[<span data-ttu-id="89c18-115">会議のコンポーネンツおよびトポロジ</span><span class="sxs-lookup"><span data-stu-id="89c18-115">Components and Topologies for Conferencing</span></span>](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)
