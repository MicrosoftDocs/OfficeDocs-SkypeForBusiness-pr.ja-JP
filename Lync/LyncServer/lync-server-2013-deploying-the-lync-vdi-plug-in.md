---
title: 'Lync Server 2013: Lync VDI プラグインの展開'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying the Lync VDI plug-in
ms:assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204683(v=OCS.15)
ms:contentKeyID: 48183449
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77b2e7ce89fe021c23da81f075aec3d1ce90e7b6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833510"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-the-lync-vdi-plug-in-in-lync-server-2013"></a><span data-ttu-id="829fa-102">Lync Server 2013 での Lync VDI プラグインの展開</span><span class="sxs-lookup"><span data-stu-id="829fa-102">Deploying the Lync VDI plug-in in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="829fa-103">_**最終更新日:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="829fa-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="829fa-104">Lync 2013 クライアントは、仮想デスクトップインフラストラクチャ (VDI) 環境での音声とビデオをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="829fa-104">The Lync 2013 client supports audio and video in a Virtual Desktop Infrastructure (VDI) environment.</span></span> <span data-ttu-id="829fa-105">ユーザーは、オーディオデバイスやビデオデバイス (ヘッドセットやカメラなど) をローカルコンピューター (たとえば、シンクライアントや転用コンピューター) に接続できます。</span><span class="sxs-lookup"><span data-stu-id="829fa-105">A user can connect an audio or video device (for example, a headset or a camera) to the local computer (for example, a thin client or repurposed computer).</span></span> <span data-ttu-id="829fa-106">ユーザーは、仮想マシンに接続して、仮想マシンで実行されている Lync 2013 クライアントにサインインし、クライアントがローカルで実行されている場合と同じように、リアルタイムの音声とビデオによる通信に参加できます。</span><span class="sxs-lookup"><span data-stu-id="829fa-106">The user can connect to the virtual machine, sign in to the Lync 2013 client that is running on the virtual machine, and participate in real-time audio and video communications as though the client is running locally.</span></span>

<span data-ttu-id="829fa-107">Lync VDI プラグインは、ローカルコンピューターにインストールされるスタンドアロンアプリケーションであり、仮想マシン上で実行されている Lync 2013 クライアントでローカルのオーディオデバイスとビデオデバイスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="829fa-107">The Lync VDI Plug-in is a stand-alone application that installs on the local computer and allows the use of local audio and video devices with the Lync 2013 client running on the virtual machine.</span></span> <span data-ttu-id="829fa-108">プラグインは、ローカルコンピューターに Lync をインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="829fa-108">The plug-in does not require Lync to be installed on the local computer.</span></span> <span data-ttu-id="829fa-109">仮想マシンで実行されている Lync 2013 クライアントにユーザーがサインインすると、lync は、ローカルコンピューターで実行されている Lync VDI プラグインとの接続を確立するために、ユーザーに資格情報を再入力するように求めます。</span><span class="sxs-lookup"><span data-stu-id="829fa-109">After the user signs in to the Lync 2013 client that is running on the virtual machine, Lync prompts the user to re-enter his or her credentials to establish a connection with the Lync VDI Plug-in that is running on the local computer.</span></span> <span data-ttu-id="829fa-110">この接続が確立されると、ユーザーは音声通話とビデオ通話を発信および受信することができます。</span><span class="sxs-lookup"><span data-stu-id="829fa-110">After this connection is established, the user is ready to make and receive audio and video calls.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="829fa-111">このセクション中</span><span class="sxs-lookup"><span data-stu-id="829fa-111">In This Section</span></span>

  - [<span data-ttu-id="829fa-112">Lync Server 2013 の Lync VDI プラグインの前提条件</span><span class="sxs-lookup"><span data-stu-id="829fa-112">Lync VDI plug-in prerequisites in Lync Server 2013</span></span>](lync-server-2013-lync-vdi-plug-in-prerequisites.md)

  - [<span data-ttu-id="829fa-113">VDI の Lync Server 2013 使用環境の準備</span><span class="sxs-lookup"><span data-stu-id="829fa-113">Preparing your Lync Server 2013 environment for VDI</span></span>](lync-server-2013-preparing-your-environment-for-vdi.md)

  - [<span data-ttu-id="829fa-114">仮想マシン上の Lync 2013 へのサインインと使用</span><span class="sxs-lookup"><span data-stu-id="829fa-114">Signing in and using Lync 2013 on the virtual machine</span></span>](lync-server-2013-signing-in-and-using-lync-2013-on-the-virtual-machine.md)

  - [<span data-ttu-id="829fa-115">Lync Server 2013 での Lync VDI プラグインのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="829fa-115">Troubleshooting the Lync VDI plug-in in Lync Server 2013</span></span>](lync-server-2013-troubleshooting-the-lync-vdi-plug-in.md)

  - [<span data-ttu-id="829fa-116">Lync Server 2013 でサポートされる仮想化テクノロジと既知の制限</span><span class="sxs-lookup"><span data-stu-id="829fa-116">Supported virtualization technologies and known limitations in Lync Server 2013</span></span>](lync-server-2013-supported-virtualization-technologies-and-known-limitations.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

