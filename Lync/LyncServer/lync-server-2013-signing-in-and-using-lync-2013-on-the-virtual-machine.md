---
title: 'Lync Server 2013: 仮想マシンでの Lync 2013 のサインインと使用'
description: 'Lync Server 2013: 仮想マシンで Lync 2013 にサインインして使用します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Signing in and using Lync 2013 on the virtual machine
ms:assetid: 6140fc19-5bef-4b58-9b0f-19112b5ecd00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204948(v=OCS.15)
ms:contentKeyID: 48184318
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad9a92d450fb9d60aed70617089d95280528892f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555683"
---
# <a name="signing-in-and-using-lync-2013-on-the-virtual-machine"></a><span data-ttu-id="c4fc0-103">仮想マシンでの Lync 2013 のサインインと使用</span><span class="sxs-lookup"><span data-stu-id="c4fc0-103">Signing in and using Lync 2013 on the virtual machine</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4fc0-104">_**トピックの最終更新日:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="c4fc0-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="c4fc0-105">VDI プラグインを有効にした後、ユーザーが Lync 2013 にサインインすると、次の手順が実行されます。</span><span class="sxs-lookup"><span data-stu-id="c4fc0-105">After the VDI plug-in is enabled, the following steps occur when the user signs in to Lync 2013.</span></span>

1.  <span data-ttu-id="c4fc0-106">ユーザーは、仮想マシン上で実行されている Lync 2013 クライアントに自分の資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="c4fc0-106">The user types his or her credentials in to the Lync 2013 client running on the virtual machine.</span></span>

2.  <span data-ttu-id="c4fc0-107">Lync は、VDI プラグインの可用性を検出した後、ユーザーに資格情報を再入力するように求めるメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="c4fc0-107">After Lync detects the availability of the VDI plug-in, Lync prompts the user to re-enter his or her credentials.</span></span> <span data-ttu-id="c4fc0-108">このダイアログボックスでは、[ **パスワードを保存** する] チェックボックスをオンにすることをお勧めします。これにより、ユーザーは、以降のサインイン時に資格情報を入力する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="c4fc0-108">In this dialog box, we recommend that the user select the **Save my password** check box so that he or she will not be required to enter credentials during subsequent sign in.</span></span>

3.  <span data-ttu-id="c4fc0-109">Lync は、VDI プラグインとのペアリングを開始します。</span><span class="sxs-lookup"><span data-stu-id="c4fc0-109">Lync begins pairing with the VDI plug-in.</span></span> <span data-ttu-id="c4fc0-110">ペアリングが完了する前に、クライアントは Lync ステータスバーに2つのアイコンを表示します。</span><span class="sxs-lookup"><span data-stu-id="c4fc0-110">Before pairing is complete, the client displays two icons in the Lync status bar.</span></span> <span data-ttu-id="c4fc0-111">次に示す左下のアイコンは利用可能なオーディオ デバイスがないことを示し、右下の点滅するアイコンは VDI ペアリングが進行中であることを示します。</span><span class="sxs-lookup"><span data-stu-id="c4fc0-111">The icon in the lower left indicates that no audio devices are available, and the blinking icon in the lower right indicates that the VDI pairing is in progress, as shown:</span></span>
    
    <span data-ttu-id="c4fc0-112">![ペアリングが成功したことを示す Lync VDI アイコン](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "ペアリングが成功したことを示す Lync VDI アイコン")</span><span class="sxs-lookup"><span data-stu-id="c4fc0-112">![Lync VDI icon showing successful pairing](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Lync VDI icon showing successful pairing")</span></span>  

4.  <span data-ttu-id="c4fc0-113">VDI ペアリングが成功すると、通話に使用されるオーディオ デバイスおよび VDI ペアリングが成功したことを示すアイコンに変わります。</span><span class="sxs-lookup"><span data-stu-id="c4fc0-113">After VDI pairing is successful, the icons change to indicate the audio device that will be used for calls and the VDI pairing success:</span></span>
    
    <span data-ttu-id="c4fc0-114">![成功を示す Lync VDI ペアリングアイコン](images/JJ204948.57be3387-a3e5-4949-831e-f5ff9fcc5598(OCS.15).png "成功を示す Lync VDI ペアリングアイコン")</span><span class="sxs-lookup"><span data-stu-id="c4fc0-114">![Lync VDI pairing icon showing success](images/JJ204948.57be3387-a3e5-4949-831e-f5ff9fcc5598(OCS.15).png "Lync VDI pairing icon showing success")</span></span>  

5.  <span data-ttu-id="c4fc0-115">Lync を VDI プラグインと組み合わせて使用すると、ユーザーは、ローカルコンピューターに接続されている Lync 互換デバイスでプレゼンスを確認できます。</span><span class="sxs-lookup"><span data-stu-id="c4fc0-115">After Lync pairs with the VDI plug-in, the user can see his or her presence on Lync compatible devices that are connected to the local computer.</span></span> <span data-ttu-id="c4fc0-116">これで、ユーザーは通常どおり通話を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c4fc0-116">The user can now place and answer calls as usual.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

