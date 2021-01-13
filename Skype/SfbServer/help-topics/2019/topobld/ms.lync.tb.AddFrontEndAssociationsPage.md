---
title: フロント エンドの関連付けの追加
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndAssociationsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 95620425-defd-47fd-a5c0-e4a283d812a5
ROBOTS: NOINDEX, NOFOLLOW
description: サーバーの役割をフロントエンド プールに関連付けすることで、他のサーバーの展開を必要とする特定の機能のサポートを有効にできます。 後でサーバーの役割をフロントエンド プールに関連付けすることもできます。 フロントエンド プールに関連付けられるサーバーの役割は次のとおりです。
ms.openlocfilehash: ef3cec601355f433ad760be4edcc0ea573b53010
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811737"
---
# <a name="add-front-end-associations"></a><span data-ttu-id="0451f-105">フロント エンドの関連付けの追加</span><span class="sxs-lookup"><span data-stu-id="0451f-105">Add Front End Associations</span></span>

<span data-ttu-id="0451f-106">サーバーの役割をフロントエンド プールに関連付けすることで、他のサーバーの展開を必要とする特定の機能のサポートを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="0451f-106">You can enable support for specific features that require the deployment of other servers by associating the server roles with the Front End pool now.</span></span> <span data-ttu-id="0451f-107">後でサーバーの役割をフロントエンド プールに関連付けすることもできます。</span><span class="sxs-lookup"><span data-stu-id="0451f-107">You can also associate server roles with the Front End pool at a later time.</span></span> <span data-ttu-id="0451f-108">フロントエンド プールに関連付けられるサーバーの役割は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0451f-108">The server roles that can be associated with a Front End pool include the following:</span></span>

- <span data-ttu-id="0451f-109">A/V エッジ サーバー。</span><span class="sxs-lookup"><span data-stu-id="0451f-109">A/V Edge Server.</span></span> <span data-ttu-id="0451f-110">音声ビデオ エッジ サーバーの実装の詳細については、「計画」のドキュメントの [「Planning for Conferencing」](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0451f-110">For details about the implementation of an A/V Edge Server, see [Planning for Conferencing](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) in the Planning documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0451f-111">これらの機能のサポートを今すぐ有効にした場合、公開するトポロジ設計には、選択した各機能の実装に必要なサーバー コンポーネントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0451f-111">If you enable support for any of these features now, the topology design that you publish will include the server components that are required to implement each selected feature.</span></span> <span data-ttu-id="0451f-112">トポロジの公開をエラーなしで成功するには、物理コンピューターをドメインに参加している必要があります。</span><span class="sxs-lookup"><span data-stu-id="0451f-112">For the publishing of a topology to succeed without error, you must have the physical computers joined to the domain.</span></span> <span data-ttu-id="0451f-113">たとえば、アーカイブのサポートを今すぐ有効にする場合は、組織のアーカイブ通信を開始する前に、アーカイブ サーバーを展開し、適切なアーカイブ オプションを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0451f-113">For example, if you enable support for archiving now, you must then deploy an Archiving Server and configure the appropriate archiving options before you start archiving communications for your organization.</span></span>


