---
title: 'Lync Server 2013: リモート通話コントロールの展開'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying remote call control
ms:assetid: 763037f7-7a2a-49ae-acc3-9781b0bff7e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558664(v=OCS.15)
ms:contentKeyID: 48184536
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8583a8f2e8c95ce9b12ad19d8a8e5369ba756ddd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833526"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="39bbd-102">Lync Server 2013 でのリモート通話コントロールの展開</span><span class="sxs-lookup"><span data-stu-id="39bbd-102">Deploying remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39bbd-103">_**最終更新日:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="39bbd-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="39bbd-104">このセクションでは、組織内のユーザーにリモート通話コントロール機能を展開するプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="39bbd-104">This section guides you through the process of deploying remote call control functionality to users in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="39bbd-105">リモートユーザーは、組織のファイアウォールの外側にいるリモート通話コントロール機能を使用できますが、外部アクセスシナリオの展開について詳しくは、このドキュメントの範囲外です。</span><span class="sxs-lookup"><span data-stu-id="39bbd-105">Although remote call control features are available to remote users while they are outside of your organization’s firewall, details about deploying external access scenarios are beyond the scope of this documentation.</span></span> <span data-ttu-id="39bbd-106">外部ユーザーアクセスの展開の詳細については、展開ドキュメントの「 <A href="lync-server-2013-deploying-external-user-access.md">Lync Server 2013 での外部ユーザーアクセスの展開</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39bbd-106">For details about deploying external user access, see <A href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="39bbd-107">このセクション中</span><span class="sxs-lookup"><span data-stu-id="39bbd-107">In This Section</span></span>

  - [<span data-ttu-id="39bbd-108">SIP/CSTA ゲートウェイにルーティングするための Lync Server 2013 の構成</span><span class="sxs-lookup"><span data-stu-id="39bbd-108">Configuring Lync Server 2013 to route to a SIP/CSTA gateway</span></span>](lync-server-2013-configuring-lync-server-to-route-to-a-sip-csta-gateway.md)

  - [<span data-ttu-id="39bbd-109">Lync Server 2013 でのリモート通話コントロールの静的ルートの構成</span><span class="sxs-lookup"><span data-stu-id="39bbd-109">Configure a static route for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-static-route-for-remote-call-control.md)

  - [<span data-ttu-id="39bbd-110">Lync Server 2013 でリモート通話コントロールの信頼済みアプリケーション エントリを構成する</span><span class="sxs-lookup"><span data-stu-id="39bbd-110">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)

  - <span data-ttu-id="39bbd-111">[Lync Server 2013 で SIP/CSTA ゲートウェイの IP アドレスを定義する](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)(ゲートウェイが TCP を使用するように構成されている場合のみ)</span><span class="sxs-lookup"><span data-stu-id="39bbd-111">[Define a SIP/CSTA gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) (only if the gateway is configured to use TCP)</span></span>

  - [<span data-ttu-id="39bbd-112">Lync Server 2013 でのリモート通話コントロールの Lync ユーザーの有効化</span><span class="sxs-lookup"><span data-stu-id="39bbd-112">Enable Lync users for remote call control in Lync Server 2013</span></span>](lync-server-2013-enable-lync-users-for-remote-call-control.md)

  - [<span data-ttu-id="39bbd-113">Lync Server 2013 でのリモート通話コントロールと電話番号正規化</span><span class="sxs-lookup"><span data-stu-id="39bbd-113">Remote call control and phone number normalization in Lync Server 2013</span></span>](lync-server-2013-remote-call-control-and-phone-number-normalization.md)

  - <span data-ttu-id="39bbd-114">[Lync Server 2013 で従来の承認済みホストを削除する (オプション)](lync-server-2013-remove-a-legacy-authorized-host-optional.md)(リモート通話コントロールで以前に有効にしたユーザーを移行する場合のみ)</span><span class="sxs-lookup"><span data-stu-id="39bbd-114">[Remove a legacy authorized host in Lync Server 2013 (optional)](lync-server-2013-remove-a-legacy-authorized-host-optional.md) (only if you are migrating users previously enabled for remote call control)</span></span>

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="39bbd-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="39bbd-115">Related Sections</span></span>

[<span data-ttu-id="39bbd-116">Lync Server 2013 でのリモート通話コントロールの計画</span><span class="sxs-lookup"><span data-stu-id="39bbd-116">Planning for remote call control in Lync Server 2013</span></span>](lync-server-2013-planning-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

