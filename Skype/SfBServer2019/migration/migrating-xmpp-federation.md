---
title: XMPP フェデレーションの移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 以前のバージョンでは、拡張メッセージングとプレゼンスプロトコル (XMPP) ゲートウェイが提供されていました。このゲートウェイは、別のサーバーロールとして展開して、XMPP の展開とのフェデレーションを可能にします。 XMPP 機能は、Skype for Business Server 2019 で廃止された & は利用できなくなりました。 引き続き XMPP 機能を使用できるようにする場合は、旧バージョン (Skype for Business Server 2015/Lync Server 2013) を使って coexitence 使用環境で利用できます。 XMPP 機能は、従来のエッジサーバー上で実行される XMPP プロキシとして、従来のフロントエンドサーバー上で実行される XMPP ゲートウェイとして、2つの部分にインストールされます。
ms.openlocfilehash: fd2b51af84133e28e9a4de035333b1a282d71d38
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298191"
---
# <a name="migrating-xmpp-federation"></a><span data-ttu-id="578e6-106">XMPP フェデレーションの移行</span><span class="sxs-lookup"><span data-stu-id="578e6-106">Migrating XMPP federation</span></span>

<span data-ttu-id="578e6-107">以前のバージョンでは、拡張メッセージングとプレゼンスプロトコル (XMPP) ゲートウェイが提供されていました。このゲートウェイは、別のサーバーロールとして展開して、XMPP の展開とのフェデレーションを可能にします。</span><span class="sxs-lookup"><span data-stu-id="578e6-107">Previous versions provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="578e6-108">XMPP 機能は使用できなくなり、Skype for Business Server 2019 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="578e6-108">The XMPP functionality is no longer available and is deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="578e6-109">引き続き XMPP 機能を使用する場合は、以前のバージョン (Skype for Business Server 2015 または Lync Server 2013) を使用した共存環境で行うことができます。</span><span class="sxs-lookup"><span data-stu-id="578e6-109">If you want to continue with the XMPP functionality, you can do so in a coexistence environment with a legacy version (Skype for Business Server 2015 or Lync Server 2013).</span></span> <span data-ttu-id="578e6-110">XMPP 機能は、従来のエッジサーバー上で実行される XMPP プロキシとして、従来のフロントエンドサーバー上で実行される XMPP ゲートウェイとして、2つの部分にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="578e6-110">XMPP functionality is installed in two parts: as an XMPP proxy that runs on the legacy Edge Server, and the XMPP Gateway that runs on the legacy Front End Server.</span></span> 
  
<span data-ttu-id="578e6-111">移行の観点から、XMPP 機能を利用したいユーザーは従来のサーバーに残しておく必要があります。 Skype for Business Server 2019 プールには移動せず、従来の XMPP ゲートウェイの使用を続行してください。</span><span class="sxs-lookup"><span data-stu-id="578e6-111">From a migration perspective, users who want to avail the XMPP feature should remain in the legacy server and should not be moved to a Skype for Business Server 2019 pool but continue to use the legacy XMPP gateway.</span></span> <span data-ttu-id="578e6-112">これは、Skype for Business Server 2015 または Lync Server 2013 で XMPP フェデレーションパートナーが構成されている場合にのみ可能です。</span><span class="sxs-lookup"><span data-stu-id="578e6-112">This is possible only when the XMPP federated partner is configured in Skype for Business Server 2015 or Lync Server 2013.</span></span> <span data-ttu-id="578e6-113">引き続き XMPP 機能を使用する場合は、従来のエッジサーバーを Skype for Business Server 2019 に移行しないでください。</span><span class="sxs-lookup"><span data-stu-id="578e6-113">You should not migrate the legacy Edge Server to Skype for Business Server 2019 if you want to continue with XMPP functionality.</span></span> <span data-ttu-id="578e6-114">ただし、従来のエッジサーバー (XMPP プロキシ付き) と Skype for Business 2019 Edge サーバーの共存は可能です。</span><span class="sxs-lookup"><span data-stu-id="578e6-114">However, you can have coexistence of the legacy Edge Server (with XMPP Proxy) and the Skype for Business 2019 Edge Server.</span></span>
  

    

