---
title: フロントエンドの関連付けの追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: サーバーの役割をフロントエンドプールに関連付けることによって、他のサーバーの展開を必要とする特定の機能のサポートを有効にすることができます。 後でサーバーの役割をフロントエンドプールに関連付けることもできます。 フロントエンドプールに関連付けることができるサーバーの役割には、次のものがあります。
ms.openlocfilehash: 13d796bd5c33b0f56ebc43ba11f82a188cce0c76
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218388"
---
# <a name="add-front-end-associations"></a><span data-ttu-id="f51fe-105">フロントエンドの関連付けの追加</span><span class="sxs-lookup"><span data-stu-id="f51fe-105">Add Front End Associations</span></span>

<span data-ttu-id="f51fe-106">サーバーの役割をフロントエンドプールに関連付けることによって、他のサーバーの展開を必要とする特定の機能のサポートを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="f51fe-106">You can enable support for specific features that require the deployment of other servers by associating the server roles with the Front End pool now.</span></span> <span data-ttu-id="f51fe-107">後でサーバーの役割をフロントエンドプールに関連付けることもできます。</span><span class="sxs-lookup"><span data-stu-id="f51fe-107">You can also associate server roles with the Front End pool at a later time.</span></span> <span data-ttu-id="f51fe-108">フロントエンドプールに関連付けることができるサーバーの役割には、次のものがあります。</span><span class="sxs-lookup"><span data-stu-id="f51fe-108">The server roles that can be associated with a Front End pool include the following:</span></span>

- <span data-ttu-id="f51fe-109">音声ビデオエッジサーバー。</span><span class="sxs-lookup"><span data-stu-id="f51fe-109">A/V Edge Server.</span></span> <span data-ttu-id="f51fe-110">音声ビデオエッジサーバーの実装の詳細については、「計画」のドキュメントの「 [planning For 会議](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f51fe-110">For details about the implementation of an A/V Edge Server, see [Planning for Conferencing](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) in the Planning documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f51fe-111">これらの機能のいずれかのサポートを現時点で有効にした場合、公開するトポロジ設計には、選択した各機能を実装するために必要なサーバーコンポーネントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f51fe-111">If you enable support for any of these features now, the topology design that you publish will include the server components that are required to implement each selected feature.</span></span> <span data-ttu-id="f51fe-112">エラーが発生しない状態でトポロジの公開を成功させるには、物理コンピューターがドメインに参加している必要があります。</span><span class="sxs-lookup"><span data-stu-id="f51fe-112">For the publishing of a topology to succeed without error, you must have the physical computers joined to the domain.</span></span> <span data-ttu-id="f51fe-113">たとえば、アーカイブのサポートを今すぐ有効にする場合は、組織の通信のアーカイブを開始する前に、アーカイブサーバーを展開し、適切なアーカイブオプションを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f51fe-113">For example, if you enable support for archiving now, you must then deploy an Archiving Server and configure the appropriate archiving options before you start archiving communications for your organization.</span></span>


