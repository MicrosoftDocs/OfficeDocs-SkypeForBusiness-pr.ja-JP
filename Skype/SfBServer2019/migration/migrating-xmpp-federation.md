---
title: XMPP フェデレーションの移行
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 以前のバージョンでは、XMPP の展開とのフェデレーションを可能にするために、独立したサーバーの役割として展開できる拡張メッセージングおよびプレゼンスプロトコル (XMPP) ゲートウェイが提供されていました。 XMPP 機能は、Skype for Business Server 2019 で廃止された & 使用できなくなりました。 XMPP 機能を引き続き使用する場合は、以前のバージョンの coexitence 環境で利用できます (Skype for Business Server 2015/Lync Server 2013)。 XMPP 機能は、従来のエッジサーバーで実行される XMPP プロキシ、従来のフロントエンドサーバー上で実行される XMPP ゲートウェイとして、2つの部分に分けてインストールされます。
ms.openlocfilehash: 71b6c213450f51ea4b3fe1f351e22dbb992ce8ca
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752649"
---
# <a name="migrating-xmpp-federation"></a><span data-ttu-id="96f8c-106">XMPP フェデレーションの移行</span><span class="sxs-lookup"><span data-stu-id="96f8c-106">Migrating XMPP federation</span></span>

<span data-ttu-id="96f8c-107">以前のバージョンでは、XMPP の展開とのフェデレーションを可能にするために、独立したサーバーの役割として展開できる拡張メッセージングおよびプレゼンスプロトコル (XMPP) ゲートウェイが提供されていました。</span><span class="sxs-lookup"><span data-stu-id="96f8c-107">Previous versions provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="96f8c-108">XMPP 機能は使用できなくなり、Skype for Business Server 2019 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="96f8c-108">The XMPP functionality is no longer available and is deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="96f8c-109">XMPP の機能を引き続き使用する場合は、従来のバージョン (Skype for Business Server 2015 または Lync Server 2013) を使用した共存環境でこれを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="96f8c-109">If you want to continue with the XMPP functionality, you can do so in a coexistence environment with a legacy version (Skype for Business Server 2015 or Lync Server 2013).</span></span> <span data-ttu-id="96f8c-110">XMPP 機能は、従来のエッジサーバーで実行される XMPP プロキシ、従来のフロントエンドサーバー上で実行される XMPP ゲートウェイとして、2つの部分に分けてインストールされます。</span><span class="sxs-lookup"><span data-stu-id="96f8c-110">XMPP functionality is installed in two parts: as an XMPP proxy that runs on the legacy Edge Server, and the XMPP Gateway that runs on the legacy Front End Server.</span></span> 
  
<span data-ttu-id="96f8c-111">移行の観点から、XMPP 機能の利用を希望するユーザーは従来のサーバーに残しておく必要があります。ただし、Skype for Business Server 2019 プールに移動する必要はありませんが、従来の XMPP ゲートウェイを引き続き使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="96f8c-111">From a migration perspective, users who want to avail the XMPP feature should remain in the legacy server and should not be moved to a Skype for Business Server 2019 pool but continue to use the legacy XMPP gateway.</span></span> <span data-ttu-id="96f8c-112">これは、XMPP フェデレーションパートナーが Skype for Business Server 2015 または Lync Server 2013 で構成されている場合にのみ可能です。</span><span class="sxs-lookup"><span data-stu-id="96f8c-112">This is possible only when the XMPP federated partner is configured in Skype for Business Server 2015 or Lync Server 2013.</span></span> <span data-ttu-id="96f8c-113">XMPP 機能を引き続き使用する場合は、従来のエッジサーバーを Skype for Business Server 2019 に移行しないでください。</span><span class="sxs-lookup"><span data-stu-id="96f8c-113">You should not migrate the legacy Edge Server to Skype for Business Server 2019 if you want to continue with XMPP functionality.</span></span> <span data-ttu-id="96f8c-114">ただし、従来のエッジサーバー (XMPP プロキシを使用) と Skype for Business 2019 エッジサーバーを共存させることができます。</span><span class="sxs-lookup"><span data-stu-id="96f8c-114">However, you can have coexistence of the legacy Edge Server (with XMPP Proxy) and the Skype for Business 2019 Edge Server.</span></span>
  

    

