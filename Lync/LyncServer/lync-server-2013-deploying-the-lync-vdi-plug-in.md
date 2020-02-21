---
title: 'Lync Server 2013: Lync VDI プラグインの展開'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying the Lync VDI plug-in
ms:assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204683(v=OCS.15)
ms:contentKeyID: 48183449
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 578825b8dcf7262475fa14cd2e116859f2828878
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188200"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-the-lync-vdi-plug-in-in-lync-server-2013"></a><span data-ttu-id="dc0bd-102">Lync Server 2013 での Lync VDI プラグインの展開</span><span class="sxs-lookup"><span data-stu-id="dc0bd-102">Deploying the Lync VDI plug-in in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc0bd-103">_**トピックの最終更新日:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="dc0bd-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="dc0bd-104">Lync 2013 クライアントは、仮想デスクトップインフラストラクチャ (VDI) 環境で音声とビデオをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="dc0bd-104">The Lync 2013 client supports audio and video in a Virtual Desktop Infrastructure (VDI) environment.</span></span> <span data-ttu-id="dc0bd-105">ユーザーは音声またはビデオ デバイス (ヘッドセットやカメラなど) をローカル コンピューター (シン クライアントや異なる目的に使用されていたコンピューターなど) に接続できます。</span><span class="sxs-lookup"><span data-stu-id="dc0bd-105">A user can connect an audio or video device (for example, a headset or a camera) to the local computer (for example, a thin client or repurposed computer).</span></span> <span data-ttu-id="dc0bd-106">ユーザーは、仮想マシンに接続して、仮想マシン上で実行されている Lync 2013 クライアントにサインインし、クライアントがローカルで実行している場合と同様に、リアルタイムの音声およびビデオ通信に参加できます。</span><span class="sxs-lookup"><span data-stu-id="dc0bd-106">The user can connect to the virtual machine, sign in to the Lync 2013 client that is running on the virtual machine, and participate in real-time audio and video communications as though the client is running locally.</span></span>

<span data-ttu-id="dc0bd-107">Lync VDI プラグインはスタンドアロンアプリケーションで、ローカルコンピューターにインストールされ、仮想マシン上で実行されている Lync 2013 クライアントでローカルのオーディオおよびビデオデバイスを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="dc0bd-107">The Lync VDI Plug-in is a stand-alone application that installs on the local computer and allows the use of local audio and video devices with the Lync 2013 client running on the virtual machine.</span></span> <span data-ttu-id="dc0bd-108">プラグインをローカルコンピューターに Lync をインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="dc0bd-108">The plug-in does not require Lync to be installed on the local computer.</span></span> <span data-ttu-id="dc0bd-109">仮想マシン上で実行されている Lync 2013 クライアントにユーザーがサインインすると、Lync は自分の資格情報を再入力して、ローカルコンピューターで実行されている Lync VDI プラグインとの接続を確立するようユーザーに求めます。</span><span class="sxs-lookup"><span data-stu-id="dc0bd-109">After the user signs in to the Lync 2013 client that is running on the virtual machine, Lync prompts the user to re-enter his or her credentials to establish a connection with the Lync VDI Plug-in that is running on the local computer.</span></span> <span data-ttu-id="dc0bd-110">この接続が確立されると、ユーザーは音声およびビデオ通話を発信および受信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="dc0bd-110">After this connection is established, the user is ready to make and receive audio and video calls.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="dc0bd-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="dc0bd-111">In This Section</span></span>

  - [<span data-ttu-id="dc0bd-112">Lync Server 2013 での lync VDI プラグインの前提条件</span><span class="sxs-lookup"><span data-stu-id="dc0bd-112">Lync VDI plug-in prerequisites in Lync Server 2013</span></span>](lync-server-2013-lync-vdi-plug-in-prerequisites.md)

  - [<span data-ttu-id="dc0bd-113">VDI の Lync Server 2013 環境の準備</span><span class="sxs-lookup"><span data-stu-id="dc0bd-113">Preparing your Lync Server 2013 environment for VDI</span></span>](lync-server-2013-preparing-your-environment-for-vdi.md)

  - [<span data-ttu-id="dc0bd-114">仮想マシンでの Lync 2013 のサインインと使用</span><span class="sxs-lookup"><span data-stu-id="dc0bd-114">Signing in and using Lync 2013 on the virtual machine</span></span>](lync-server-2013-signing-in-and-using-lync-2013-on-the-virtual-machine.md)

  - [<span data-ttu-id="dc0bd-115">Lync Server 2013 での Lync VDI プラグインのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="dc0bd-115">Troubleshooting the Lync VDI plug-in in Lync Server 2013</span></span>](lync-server-2013-troubleshooting-the-lync-vdi-plug-in.md)

  - [<span data-ttu-id="dc0bd-116">Lync Server 2013 でサポートされている仮想化テクノロジと既知の制限</span><span class="sxs-lookup"><span data-stu-id="dc0bd-116">Supported virtualization technologies and known limitations in Lync Server 2013</span></span>](lync-server-2013-supported-virtualization-technologies-and-known-limitations.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

