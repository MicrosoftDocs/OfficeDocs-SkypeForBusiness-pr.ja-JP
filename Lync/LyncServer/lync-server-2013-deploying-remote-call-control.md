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
ms.openlocfilehash: c0ca285312264a66113e038c0f5020e47567a5f3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145125"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="9947e-102">Lync Server 2013 でのリモート通話コントロールの展開</span><span class="sxs-lookup"><span data-stu-id="9947e-102">Deploying remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9947e-103">_**トピックの最終更新日:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="9947e-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="9947e-104">ここでは、組織のユーザーにリモート通話コントロール機能を展開するプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="9947e-104">This section guides you through the process of deploying remote call control functionality to users in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9947e-105">リモート ユーザーは組織のファイアウォールの外側にいるときにリモート通話コントロール機能を使用できますが、外部アクセスの展開の詳細はこのドキュメントには記載されていません。</span><span class="sxs-lookup"><span data-stu-id="9947e-105">Although remote call control features are available to remote users while they are outside of your organization’s firewall, details about deploying external access scenarios are beyond the scope of this documentation.</span></span> <span data-ttu-id="9947e-106">外部ユーザーアクセスの展開の詳細については、「展開」のドキュメントの「Deployment <A href="lync-server-2013-deploying-external-user-access.md">external user access In Lync Server 2013</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9947e-106">For details about deploying external user access, see <A href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9947e-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="9947e-107">In This Section</span></span>

  - [<span data-ttu-id="9947e-108">SIP/CSTA ゲートウェイにルーティングするように Lync Server 2013 を構成する</span><span class="sxs-lookup"><span data-stu-id="9947e-108">Configuring Lync Server 2013 to route to a SIP/CSTA gateway</span></span>](lync-server-2013-configuring-lync-server-to-route-to-a-sip-csta-gateway.md)

  - [<span data-ttu-id="9947e-109">Lync Server 2013 でリモート通話コントロールの静的ルートを構成する</span><span class="sxs-lookup"><span data-stu-id="9947e-109">Configure a static route for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-static-route-for-remote-call-control.md)

  - [<span data-ttu-id="9947e-110">Lync Server 2013 でのリモート通話コントロールの信頼済みアプリケーションエントリを構成する</span><span class="sxs-lookup"><span data-stu-id="9947e-110">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)

  - <span data-ttu-id="9947e-111">[Lync Server 2013 で SIP/CSTA ゲートウェイの IP アドレスを定義](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)します (ゲートウェイが TCP を使用するように構成されている場合のみ)。</span><span class="sxs-lookup"><span data-stu-id="9947e-111">[Define a SIP/CSTA gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) (only if the gateway is configured to use TCP)</span></span>

  - [<span data-ttu-id="9947e-112">Lync Server 2013 で Lync ユーザーのリモート通話コントロールを有効にする</span><span class="sxs-lookup"><span data-stu-id="9947e-112">Enable Lync users for remote call control in Lync Server 2013</span></span>](lync-server-2013-enable-lync-users-for-remote-call-control.md)

  - [<span data-ttu-id="9947e-113">Lync Server 2013 でのリモート通話コントロールと電話番号の正規化</span><span class="sxs-lookup"><span data-stu-id="9947e-113">Remote call control and phone number normalization in Lync Server 2013</span></span>](lync-server-2013-remote-call-control-and-phone-number-normalization.md)

  - <span data-ttu-id="9947e-114">[Lync Server 2013 での従来の承認済みホストの削除 (オプション)](lync-server-2013-remove-a-legacy-authorized-host-optional.md) (以前にリモート通話コントロールに対して有効にしたユーザーを移行する場合のみ)</span><span class="sxs-lookup"><span data-stu-id="9947e-114">[Remove a legacy authorized host in Lync Server 2013 (optional)](lync-server-2013-remove-a-legacy-authorized-host-optional.md) (only if you are migrating users previously enabled for remote call control)</span></span>

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="9947e-115">関連情報</span><span class="sxs-lookup"><span data-stu-id="9947e-115">Related Sections</span></span>

[<span data-ttu-id="9947e-116">Lync Server 2013 でのリモート通話コントロールの計画</span><span class="sxs-lookup"><span data-stu-id="9947e-116">Planning for remote call control in Lync Server 2013</span></span>](lync-server-2013-planning-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

