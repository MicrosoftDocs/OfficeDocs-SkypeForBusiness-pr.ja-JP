---
title: 'Lync Server 2013: サポートされているクライアントバージョンの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring supported client versions
ms:assetid: aebf7b48-9aa2-4a06-adc5-0c9d11b6358d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412832(v=OCS.15)
ms:contentKeyID: 48185137
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14bc6decfea38151d1f060b13fa55c81006e98e2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840175"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-supported-client-versions-in-lync-server-2013"></a><span data-ttu-id="c914a-102">Lync Server 2013 でサポートされているクライアントバージョンを構成する</span><span class="sxs-lookup"><span data-stu-id="c914a-102">Configuring supported client versions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c914a-103">_**最終更新日:** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="c914a-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="c914a-104">Lync Server 2013 では、環境でサポートされているクライアントのバージョンを指定するように、クライアントのバージョンポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="c914a-104">In Lync Server 2013, you can set up client version policies to specify the versions of clients that are supported in your environment.</span></span> <span data-ttu-id="c914a-105">さらに、グローバルクライアントバージョンの構成を使用して、バージョンポリシーが定義されていないクライアントに対して既定のアクションを指定することもできます。そのため、明示的にサポートまたは制限されることはありません。</span><span class="sxs-lookup"><span data-stu-id="c914a-105">Additionally, you can use the global client version configuration to specify a default action for clients that do not already have a version policy defined and, therefore, are not explicitly supported or restricted.</span></span>

<span data-ttu-id="c914a-106">クライアントのバージョンポリシーを使って、クライアントの更新を管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="c914a-106">You can also use client version policies to manage client updates.</span></span> <span data-ttu-id="c914a-107">クライアントのバージョンポリシーを設定して、[ **Allow and upgrade** and upgrade \*\*\*\* and upgrade] オプションを使うと、クライアントは更新されたソフトウェアを Windows Server Update サービス (このサービスを使用している場合) または Microsoft Update から受け取ります。</span><span class="sxs-lookup"><span data-stu-id="c914a-107">When you set a client version policy and use the options **Allow and upgrade** and **Block and upgrade**, clients will receive updated software from the Windows Server Update Service (if you are using this service) or from Microsoft Update.</span></span>

<div>

## <a name="client-version-policy-settings"></a><span data-ttu-id="c914a-108">クライアントバージョンのポリシー設定</span><span class="sxs-lookup"><span data-stu-id="c914a-108">Client Version Policy Settings</span></span>

<span data-ttu-id="c914a-109">既定のクライアントバージョンポリシーでは、すべてのクライアントが Lync を実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="c914a-109">The default client version policy requires that all clients run Lync.</span></span> <span data-ttu-id="c914a-110">環境内のクライアントで以前のバージョンの Communicator を実行している場合は、Lync Server 2013 に接続しているときにクライアントとデバイスが予期せずにブロックまたは更新されないように、クライアントのバージョンの規則を再設定する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="c914a-110">If clients in your environment are running earlier versions of Communicator, you may need to reconfigure the Client Version rules to prevent clients and devices from being unexpectedly blocked or updated when connecting to Lync Server 2013.</span></span> <span data-ttu-id="c914a-111">既定のルールを変更することも、[クライアントのバージョンポリシー] リストでより高いルールを追加して、既定のルールを上書きすることもできます。</span><span class="sxs-lookup"><span data-stu-id="c914a-111">You can modify the default rule, or you can add a rule higher in the Client Version Policy list to override the default rule.</span></span> <span data-ttu-id="c914a-112">さらに、累積更新プログラム (CUs) がリリースされるため、最新の更新プログラムを要求するようにクライアントのバージョンポリシーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c914a-112">Additionally, as Cumulative Updates (CUs) are released, you should configure the Client Version Policy to require the latest updates.</span></span> <span data-ttu-id="c914a-113">詳細については、「運用ドキュメントの[Lync Server 2013 へのログオンに使用できるクライアントアプリケーションの指定](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c914a-113">For details, see [Specifying the client applications that can be used to log on to Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md) in the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

