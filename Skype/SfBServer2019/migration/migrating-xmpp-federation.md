---
title: XMPP フェデレーションの移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 以前のバージョンでは、拡張メッセージングとプレゼンスプロトコル (XMPP) ゲートウェイが提供されていました。このゲートウェイは、別のサーバーロールとして展開して、XMPP の展開とのフェデレーションを可能にします。 XMPP 機能は、Skype for Business Server 2019 で廃止された & 利用できなくなりました。 引き続き XMPP 機能を使用できるようにする場合は、旧バージョン (Skype for Business Server 2015/Lync Server 2013) を使って coexitence 使用環境で利用できます。 XMPP 機能は、従来のエッジサーバー上で実行される XMPP プロキシとして、従来のフロントエンドサーバー上で実行される XMPP ゲートウェイとして、2つの部分にインストールされます。
ms.openlocfilehash: d8640d90427d5d7ae9c19a092dc10f0d299ae2be
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813435"
---
# <a name="migrating-xmpp-federation"></a><span data-ttu-id="f978a-106">XMPP フェデレーションの移行</span><span class="sxs-lookup"><span data-stu-id="f978a-106">Migrating XMPP federation</span></span>

<span data-ttu-id="f978a-107">以前のバージョンでは、拡張メッセージングとプレゼンスプロトコル (XMPP) ゲートウェイが提供されていました。このゲートウェイは、別のサーバーロールとして展開して、XMPP の展開とのフェデレーションを可能にします。</span><span class="sxs-lookup"><span data-stu-id="f978a-107">Previous versions provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="f978a-108">XMPP 機能は使用できなくなり、Skype for Business Server 2019 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="f978a-108">The XMPP functionality is no longer available and is deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="f978a-109">引き続き XMPP 機能を使用する場合は、以前のバージョン (Skype for Business Server 2015 または Lync Server 2013) を使用した共存環境で行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f978a-109">If you want to continue with the XMPP functionality, you can do so in a coexistence environment with a legacy version (Skype for Business Server 2015 or Lync Server 2013).</span></span> <span data-ttu-id="f978a-110">XMPP 機能は、従来のエッジサーバー上で実行される XMPP プロキシとして、従来のフロントエンドサーバー上で実行される XMPP ゲートウェイとして、2つの部分にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="f978a-110">XMPP functionality is installed in two parts: as an XMPP proxy that runs on the legacy Edge Server, and the XMPP Gateway that runs on the legacy Front End Server.</span></span> 
  
<span data-ttu-id="f978a-111">移行の観点から、XMPP 機能を利用したいユーザーは従来のサーバーに残しておく必要があります。 Skype for Business Server 2019 プールには移動せず、従来の XMPP ゲートウェイの使用を続行してください。</span><span class="sxs-lookup"><span data-stu-id="f978a-111">From a migration perspective, users who want to avail the XMPP feature should remain in the legacy server and should not be moved to a Skype for Business Server 2019 pool but continue to use the legacy XMPP gateway.</span></span> <span data-ttu-id="f978a-112">これは、Skype for Business Server 2015 または Lync Server 2013 で XMPP フェデレーションパートナーが構成されている場合にのみ可能です。</span><span class="sxs-lookup"><span data-stu-id="f978a-112">This is possible only when the XMPP federated partner is configured in Skype for Business Server 2015 or Lync Server 2013.</span></span> <span data-ttu-id="f978a-113">引き続き XMPP 機能を使用する場合は、従来のエッジサーバーを Skype for Business Server 2019 に移行しないでください。</span><span class="sxs-lookup"><span data-stu-id="f978a-113">You should not migrate the legacy Edge Server to Skype for Business Server 2019 if you want to continue with XMPP functionality.</span></span> <span data-ttu-id="f978a-114">ただし、従来のエッジサーバー (XMPP プロキシ付き) と Skype for Business 2019 Edge サーバーの共存は可能です。</span><span class="sxs-lookup"><span data-stu-id="f978a-114">However, you can have coexistence of the legacy Edge Server (with XMPP Proxy) and the Skype for Business 2019 Edge Server.</span></span>
  

    

