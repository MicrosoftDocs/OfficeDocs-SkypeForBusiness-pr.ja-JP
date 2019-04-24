---
title: XMPP フェデレーションの移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: '以前のバージョンでは、拡張可能なメッセージングおよびプレゼンス プロトコル (XMPP) ゲートウェイ XMPP 環境とのフェデレーションを許可する個別のサーバーの役割として展開されているが用意されています。 XMPP 機能が利用可能な & のビジネス サーバー 2019 の Skype では非推奨ではありません。 従来のバージョンと coexitence の環境で有効 XMPP の機能を続行する場合を (ビジネス サーバー 2015 の Skype と Lync Server 2013) です。 XMPP の機能は 2 つの部分のインストール: として、XMPP プロキシ上で動作する従来のエッジ サーバー、および XMPP ゲートウェイが従来のフロント エンド サーバー上で実行します。'
ms.openlocfilehash: fa91741c1be8d80443363caba7c840b1d985d8f4
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231631"
---
# <a name="migrating-xmpp-federation"></a><span data-ttu-id="d52ca-106">XMPP フェデレーションの移行</span><span class="sxs-lookup"><span data-stu-id="d52ca-106">Migrating XMPP federation</span></span>

<span data-ttu-id="d52ca-107">以前のバージョンでは、拡張可能なメッセージングおよびプレゼンス プロトコル (XMPP) ゲートウェイ XMPP 環境とのフェデレーションを許可する個別のサーバーの役割として展開されているが用意されています。</span><span class="sxs-lookup"><span data-stu-id="d52ca-107">Previous versions provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="d52ca-108">XMPP 機能は使用できなくし、ビジネス サーバー 2019 の Skype では非推奨です。</span><span class="sxs-lookup"><span data-stu-id="d52ca-108">The XMPP functionality is no longer available and is deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="d52ca-109">XMPP の機能を続行する場合は、これを行う従来のバージョン (Skype ビジネス サーバー 2015 または Lync Server 2013) との共存環境にします。</span><span class="sxs-lookup"><span data-stu-id="d52ca-109">If you want to continue with the XMPP functionality, you can do so in a coexistence environment with a legacy version (Skype for Business Server 2015 or Lync Server 2013).</span></span> <span data-ttu-id="d52ca-110">XMPP の機能は 2 つの部分のインストール: として、XMPP プロキシ上で動作する従来のエッジ サーバー、および XMPP ゲートウェイが従来のフロント エンド サーバー上で実行します。</span><span class="sxs-lookup"><span data-stu-id="d52ca-110">XMPP functionality is installed in two parts: as an XMPP proxy that runs on the legacy Edge Server, and the XMPP Gateway that runs on the legacy Front End Server.</span></span> 
  
<span data-ttu-id="d52ca-111">移行の観点から、XMPP の機能を利用するユーザー レガシー サーバーで維持する必要があります、ビジネス サーバー 2019 プール、Skype に移動する必要がありますですが、従来の XMPP ゲートウェイを使用し続けます。</span><span class="sxs-lookup"><span data-stu-id="d52ca-111">From a migration perspective, users who want to avail the XMPP feature should remain in the legacy server and should not be moved to a Skype for Business Server 2019 pool but continue to use the legacy XMPP gateway.</span></span> <span data-ttu-id="d52ca-112">XMPP フェデレーション パートナーがビジネス サーバー 2015 または Lync Server 2013 の Skype で構成されている場合にのみ可能です。</span><span class="sxs-lookup"><span data-stu-id="d52ca-112">This is possible only when the XMPP federated partner is configured in Skype for Business Server 2015 or Lync Server 2013.</span></span> <span data-ttu-id="d52ca-113">ビジネス サーバー 2019 の Skype には、XMPP の機能を続行する場合は、レガシー エッジ サーバーを移行する必要がありますされません。</span><span class="sxs-lookup"><span data-stu-id="d52ca-113">You should not migrate the legacy Edge Server to Skype for Business Server 2019 if you want to continue with XMPP functionality.</span></span> <span data-ttu-id="d52ca-114">ただし、レガシ (使用してエッジ サーバー XMPP プロキシ) とビジネス 2019年エッジ サーバーの Skype の共存することができます。</span><span class="sxs-lookup"><span data-stu-id="d52ca-114">However, you can have coexistence of the legacy Edge Server (with XMPP Proxy) and the Skype for Business 2019 Edge Server.</span></span>
  

    

