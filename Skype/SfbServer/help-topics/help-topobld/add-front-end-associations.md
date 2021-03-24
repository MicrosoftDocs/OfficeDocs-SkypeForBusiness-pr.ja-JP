---
title: フロント エンドの関連付けの追加
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndAssociationsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 95620425-defd-47fd-a5c0-e4a283d812a5
description: サーバーの役割をフロントエンド プールに関連付け、他のサーバーの展開を必要とする特定の機能のサポートを有効にできます。 後でサーバーの役割をフロントエンド プールに関連付けすることもできます。 フロントエンド プールに関連付けられるサーバーの役割は次のとおりです。
ms.openlocfilehash: 8ff7d11a40f7eccfda78643fd8b3a17146c014d7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103253"
---
# <a name="add-front-end-associations"></a><span data-ttu-id="55a6e-105">フロント エンドの関連付けの追加</span><span class="sxs-lookup"><span data-stu-id="55a6e-105">Add Front End Associations</span></span>

<span data-ttu-id="55a6e-106">サーバーの役割をフロントエンド プールに関連付け、他のサーバーの展開を必要とする特定の機能のサポートを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="55a6e-106">You can enable support for specific features that require the deployment of other servers by associating the server roles with the Front End pool now.</span></span> <span data-ttu-id="55a6e-107">後でサーバーの役割をフロントエンド プールに関連付けすることもできます。</span><span class="sxs-lookup"><span data-stu-id="55a6e-107">You can also associate server roles with the Front End pool at a later time.</span></span> <span data-ttu-id="55a6e-108">フロントエンド プールに関連付けられるサーバーの役割は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="55a6e-108">The server roles that can be associated with a Front End pool include the following:</span></span>

- <span data-ttu-id="55a6e-109">A/V エッジ サーバー。</span><span class="sxs-lookup"><span data-stu-id="55a6e-109">A/V Edge Server.</span></span> <span data-ttu-id="55a6e-110">A/V エッジ サーバーの実装の詳細については、「計画」のドキュメントの「 [会議](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-conferencing) の計画」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55a6e-110">For details about the implementation of an A/V Edge Server, see [Planning for Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-conferencing) in the Planning documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="55a6e-111">これらの機能のサポートを有効にした場合、発行するトポロジ設計には、選択した各機能の実装に必要なサーバー コンポーネントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="55a6e-111">If you enable support for any of these features now, the topology design that you publish will include the server components that are required to implement each selected feature.</span></span> <span data-ttu-id="55a6e-112">トポロジの発行がエラーなしで成功するには、物理コンピューターがドメインに参加している必要があります。</span><span class="sxs-lookup"><span data-stu-id="55a6e-112">For the publishing of a topology to succeed without error, you must have the physical computers joined to the domain.</span></span> <span data-ttu-id="55a6e-113">たとえば、今すぐアーカイブのサポートを有効にする場合は、組織のアーカイブ通信を開始する前に、アーカイブ サーバーを展開し、適切なアーカイブ オプションを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="55a6e-113">For example, if you enable support for archiving now, you must then deploy an Archiving Server and configure the appropriate archiving options before you start archiving communications for your organization.</span></span>