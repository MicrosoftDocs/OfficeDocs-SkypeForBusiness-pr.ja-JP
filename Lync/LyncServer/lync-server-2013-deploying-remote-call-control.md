---
title: 'Lync Server 2013: リモート通話コントロールの展開'
description: 'Lync Server 2013: リモート通話コントロールの展開。'
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
ms.openlocfilehash: 4cc5e79f3ee44c354baf435585d304574d6a980c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566083"
---
# <a name="deploying-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="216ad-103">Lync Server 2013 でのリモート通話コントロールの展開</span><span class="sxs-lookup"><span data-stu-id="216ad-103">Deploying remote call control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="216ad-104">_**トピックの最終更新日:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="216ad-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="216ad-105">ここでは、組織のユーザーにリモート通話コントロール機能を展開するプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="216ad-105">This section guides you through the process of deploying remote call control functionality to users in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="216ad-106">リモート ユーザーは組織のファイアウォールの外側にいるときにリモート通話コントロール機能を使用できますが、外部アクセスの展開の詳細はこのドキュメントには記載されていません。</span><span class="sxs-lookup"><span data-stu-id="216ad-106">Although remote call control features are available to remote users while they are outside of your organization’s firewall, details about deploying external access scenarios are beyond the scope of this documentation.</span></span> <span data-ttu-id="216ad-107">外部ユーザーアクセスの展開の詳細については、「展開」のドキュメントの「Deployment <A href="lync-server-2013-deploying-external-user-access.md">external user access In Lync Server 2013</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="216ad-107">For details about deploying external user access, see <A href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="216ad-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="216ad-108">In This Section</span></span>

  - [<span data-ttu-id="216ad-109">SIP/CSTA ゲートウェイにルーティングするように Lync Server 2013 を構成する</span><span class="sxs-lookup"><span data-stu-id="216ad-109">Configuring Lync Server 2013 to route to a SIP/CSTA gateway</span></span>](lync-server-2013-configuring-lync-server-to-route-to-a-sip-csta-gateway.md)

  - [<span data-ttu-id="216ad-110">Lync Server 2013 でリモート通話コントロールの静的ルートを構成する</span><span class="sxs-lookup"><span data-stu-id="216ad-110">Configure a static route for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-static-route-for-remote-call-control.md)

  - [<span data-ttu-id="216ad-111">Lync Server 2013 でのリモート通話コントロールの信頼済みアプリケーションエントリを構成する</span><span class="sxs-lookup"><span data-stu-id="216ad-111">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)

  - <span data-ttu-id="216ad-112">[Lync Server 2013 で SIP/CSTA ゲートウェイの IP アドレスを定義](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) します (ゲートウェイが TCP を使用するように構成されている場合のみ)。</span><span class="sxs-lookup"><span data-stu-id="216ad-112">[Define a SIP/CSTA gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) (only if the gateway is configured to use TCP)</span></span>

  - [<span data-ttu-id="216ad-113">Lync Server 2013 で Lync ユーザーのリモート通話コントロールを有効にする</span><span class="sxs-lookup"><span data-stu-id="216ad-113">Enable Lync users for remote call control in Lync Server 2013</span></span>](lync-server-2013-enable-lync-users-for-remote-call-control.md)

  - [<span data-ttu-id="216ad-114">Lync Server 2013 でのリモート通話コントロールと電話番号の正規化</span><span class="sxs-lookup"><span data-stu-id="216ad-114">Remote call control and phone number normalization in Lync Server 2013</span></span>](lync-server-2013-remote-call-control-and-phone-number-normalization.md)

  - <span data-ttu-id="216ad-115">[Lync Server 2013 での従来の承認済みホストの削除 (オプション)](lync-server-2013-remove-a-legacy-authorized-host-optional.md) (以前にリモート通話コントロールに対して有効にしたユーザーを移行する場合のみ)</span><span class="sxs-lookup"><span data-stu-id="216ad-115">[Remove a legacy authorized host in Lync Server 2013 (optional)](lync-server-2013-remove-a-legacy-authorized-host-optional.md) (only if you are migrating users previously enabled for remote call control)</span></span>

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="216ad-116">関連情報</span><span class="sxs-lookup"><span data-stu-id="216ad-116">Related Sections</span></span>

[<span data-ttu-id="216ad-117">Lync Server 2013 でのリモート通話コントロールの計画</span><span class="sxs-lookup"><span data-stu-id="216ad-117">Planning for remote call control in Lync Server 2013</span></span>](lync-server-2013-planning-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

