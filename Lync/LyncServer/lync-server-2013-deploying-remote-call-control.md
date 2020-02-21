---
title: 'Lync Server 2013: リモート通話コントロールの展開'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying remote call control
ms:assetid: 763037f7-7a2a-49ae-acc3-9781b0bff7e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558664(v=OCS.15)
ms:contentKeyID: 48184536
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5659bf3e210f1f8294789729a758d4877d3e70bb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188210"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="16d7f-102">Lync Server 2013 でのリモート通話コントロールの展開</span><span class="sxs-lookup"><span data-stu-id="16d7f-102">Deploying remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16d7f-103">_**トピックの最終更新日:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="16d7f-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="16d7f-104">ここでは、組織のユーザーにリモート通話コントロール機能を展開するプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="16d7f-104">This section guides you through the process of deploying remote call control functionality to users in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="16d7f-105">リモート ユーザーは組織のファイアウォールの外側にいるときにリモート通話コントロール機能を使用できますが、外部アクセスの展開の詳細はこのドキュメントには記載されていません。</span><span class="sxs-lookup"><span data-stu-id="16d7f-105">Although remote call control features are available to remote users while they are outside of your organization’s firewall, details about deploying external access scenarios are beyond the scope of this documentation.</span></span> <span data-ttu-id="16d7f-106">外部ユーザーアクセスの展開の詳細については、「展開」のドキュメントの「Deployment <A href="lync-server-2013-deploying-external-user-access.md">external user access In Lync Server 2013</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16d7f-106">For details about deploying external user access, see <A href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="16d7f-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="16d7f-107">In This Section</span></span>

  - [<span data-ttu-id="16d7f-108">SIP/CSTA ゲートウェイにルーティングするように Lync Server 2013 を構成する</span><span class="sxs-lookup"><span data-stu-id="16d7f-108">Configuring Lync Server 2013 to route to a SIP/CSTA gateway</span></span>](lync-server-2013-configuring-lync-server-to-route-to-a-sip-csta-gateway.md)

  - [<span data-ttu-id="16d7f-109">Lync Server 2013 でリモート通話コントロールの静的ルートを構成する</span><span class="sxs-lookup"><span data-stu-id="16d7f-109">Configure a static route for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-static-route-for-remote-call-control.md)

  - [<span data-ttu-id="16d7f-110">Lync Server 2013 でのリモート通話コントロールの信頼済みアプリケーションエントリを構成する</span><span class="sxs-lookup"><span data-stu-id="16d7f-110">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)

  - <span data-ttu-id="16d7f-111">[Lync Server 2013 で SIP/CSTA ゲートウェイの IP アドレスを定義](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)します (ゲートウェイが TCP を使用するように構成されている場合のみ)。</span><span class="sxs-lookup"><span data-stu-id="16d7f-111">[Define a SIP/CSTA gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) (only if the gateway is configured to use TCP)</span></span>

  - [<span data-ttu-id="16d7f-112">Lync Server 2013 で Lync ユーザーのリモート通話コントロールを有効にする</span><span class="sxs-lookup"><span data-stu-id="16d7f-112">Enable Lync users for remote call control in Lync Server 2013</span></span>](lync-server-2013-enable-lync-users-for-remote-call-control.md)

  - [<span data-ttu-id="16d7f-113">Lync Server 2013 でのリモート通話コントロールと電話番号の正規化</span><span class="sxs-lookup"><span data-stu-id="16d7f-113">Remote call control and phone number normalization in Lync Server 2013</span></span>](lync-server-2013-remote-call-control-and-phone-number-normalization.md)

  - <span data-ttu-id="16d7f-114">[Lync Server 2013 での従来の承認済みホストの削除 (オプション)](lync-server-2013-remove-a-legacy-authorized-host-optional.md) (以前にリモート通話コントロールに対して有効にしたユーザーを移行する場合のみ)</span><span class="sxs-lookup"><span data-stu-id="16d7f-114">[Remove a legacy authorized host in Lync Server 2013 (optional)](lync-server-2013-remove-a-legacy-authorized-host-optional.md) (only if you are migrating users previously enabled for remote call control)</span></span>

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="16d7f-115">関連情報</span><span class="sxs-lookup"><span data-stu-id="16d7f-115">Related Sections</span></span>

[<span data-ttu-id="16d7f-116">Lync Server 2013 でのリモート通話コントロールの計画</span><span class="sxs-lookup"><span data-stu-id="16d7f-116">Planning for remote call control in Lync Server 2013</span></span>](lync-server-2013-planning-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

