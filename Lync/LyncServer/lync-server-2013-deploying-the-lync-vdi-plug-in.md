---
title: 'Lync Server 2013: Lync VDI プラグインの展開'
description: 'Lync Server 2013: Lync VDI プラグインの展開。'
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
ms.openlocfilehash: 3addecb07f269e4524f3da835f479439639935ad
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557803"
---
# <a name="deploying-the-lync-vdi-plug-in-in-lync-server-2013"></a><span data-ttu-id="be907-103">Lync Server 2013 での Lync VDI プラグインの展開</span><span class="sxs-lookup"><span data-stu-id="be907-103">Deploying the Lync VDI plug-in in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be907-104">_**トピックの最終更新日:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="be907-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="be907-105">Lync 2013 クライアントは、仮想デスクトップインフラストラクチャ (VDI) 環境で音声とビデオをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="be907-105">The Lync 2013 client supports audio and video in a Virtual Desktop Infrastructure (VDI) environment.</span></span> <span data-ttu-id="be907-106">ユーザーは音声またはビデオ デバイス (ヘッドセットやカメラなど) をローカル コンピューター (シン クライアントや異なる目的に使用されていたコンピューターなど) に接続できます。</span><span class="sxs-lookup"><span data-stu-id="be907-106">A user can connect an audio or video device (for example, a headset or a camera) to the local computer (for example, a thin client or repurposed computer).</span></span> <span data-ttu-id="be907-107">ユーザーは、仮想マシンに接続して、仮想マシン上で実行されている Lync 2013 クライアントにサインインし、クライアントがローカルで実行している場合と同様に、リアルタイムの音声およびビデオ通信に参加できます。</span><span class="sxs-lookup"><span data-stu-id="be907-107">The user can connect to the virtual machine, sign in to the Lync 2013 client that is running on the virtual machine, and participate in real-time audio and video communications as though the client is running locally.</span></span>

<span data-ttu-id="be907-108">Lync VDI プラグインはスタンドアロンアプリケーションで、ローカルコンピューターにインストールされ、仮想マシン上で実行されている Lync 2013 クライアントでローカルのオーディオおよびビデオデバイスを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="be907-108">The Lync VDI Plug-in is a stand-alone application that installs on the local computer and allows the use of local audio and video devices with the Lync 2013 client running on the virtual machine.</span></span> <span data-ttu-id="be907-109">プラグインをローカルコンピューターに Lync をインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="be907-109">The plug-in does not require Lync to be installed on the local computer.</span></span> <span data-ttu-id="be907-110">仮想マシン上で実行されている Lync 2013 クライアントにユーザーがサインインすると、Lync は自分の資格情報を再入力して、ローカルコンピューターで実行されている Lync VDI プラグインとの接続を確立するようユーザーに求めます。</span><span class="sxs-lookup"><span data-stu-id="be907-110">After the user signs in to the Lync 2013 client that is running on the virtual machine, Lync prompts the user to re-enter his or her credentials to establish a connection with the Lync VDI Plug-in that is running on the local computer.</span></span> <span data-ttu-id="be907-111">この接続が確立されると、ユーザーは音声およびビデオ通話を発信および受信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="be907-111">After this connection is established, the user is ready to make and receive audio and video calls.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="be907-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="be907-112">In This Section</span></span>

  - [<span data-ttu-id="be907-113">Lync Server 2013 での lync VDI プラグインの前提条件</span><span class="sxs-lookup"><span data-stu-id="be907-113">Lync VDI plug-in prerequisites in Lync Server 2013</span></span>](lync-server-2013-lync-vdi-plug-in-prerequisites.md)

  - [<span data-ttu-id="be907-114">VDI の Lync Server 2013 環境の準備</span><span class="sxs-lookup"><span data-stu-id="be907-114">Preparing your Lync Server 2013 environment for VDI</span></span>](lync-server-2013-preparing-your-environment-for-vdi.md)

  - [<span data-ttu-id="be907-115">仮想マシンでの Lync 2013 のサインインと使用</span><span class="sxs-lookup"><span data-stu-id="be907-115">Signing in and using Lync 2013 on the virtual machine</span></span>](lync-server-2013-signing-in-and-using-lync-2013-on-the-virtual-machine.md)

  - [<span data-ttu-id="be907-116">Lync Server 2013 での Lync VDI プラグインのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="be907-116">Troubleshooting the Lync VDI plug-in in Lync Server 2013</span></span>](lync-server-2013-troubleshooting-the-lync-vdi-plug-in.md)

  - [<span data-ttu-id="be907-117">Lync Server 2013 でサポートされている仮想化テクノロジと既知の制限</span><span class="sxs-lookup"><span data-stu-id="be907-117">Supported virtualization technologies and known limitations in Lync Server 2013</span></span>](lync-server-2013-supported-virtualization-technologies-and-known-limitations.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

