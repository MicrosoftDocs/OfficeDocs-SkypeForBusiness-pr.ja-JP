---
title: 'Lync Server 2013: サポートされているクライアントバージョンの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring supported client versions
ms:assetid: aebf7b48-9aa2-4a06-adc5-0c9d11b6358d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412832(v=OCS.15)
ms:contentKeyID: 48185137
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfc604efae64d907879ad175b13d7fec9c6b9d99
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154289"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-supported-client-versions-in-lync-server-2013"></a><span data-ttu-id="32ba2-102">Lync Server 2013 でサポートされているクライアントバージョンを構成する</span><span class="sxs-lookup"><span data-stu-id="32ba2-102">Configuring supported client versions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32ba2-103">_**トピックの最終更新日:** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="32ba2-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="32ba2-104">Lync Server 2013 では、クライアントバージョンポリシーを設定して、環境でサポートされているクライアントのバージョンを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="32ba2-104">In Lync Server 2013, you can set up client version policies to specify the versions of clients that are supported in your environment.</span></span> <span data-ttu-id="32ba2-105">また、グローバルクライアントバージョン構成を使用して、バージョンポリシーが定義されていないクライアントの既定のアクションを指定することもできます。そのため、明示的にサポートまたは制限されません。</span><span class="sxs-lookup"><span data-stu-id="32ba2-105">Additionally, you can use the global client version configuration to specify a default action for clients that do not already have a version policy defined and, therefore, are not explicitly supported or restricted.</span></span>

<span data-ttu-id="32ba2-106">クライアントバージョンポリシーを使用してクライアント更新プログラムを管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="32ba2-106">You can also use client version policies to manage client updates.</span></span> <span data-ttu-id="32ba2-107">クライアントバージョンポリシーを設定し、オプションの**Allow and upgrade** and **upgrade**を使用すると、クライアントは更新されたソフトウェアを Windows Server Update サービス (このサービスを使用している場合) または Microsoft Update から受け取ります。</span><span class="sxs-lookup"><span data-stu-id="32ba2-107">When you set a client version policy and use the options **Allow and upgrade** and **Block and upgrade**, clients will receive updated software from the Windows Server Update Service (if you are using this service) or from Microsoft Update.</span></span>

<div>

## <a name="client-version-policy-settings"></a><span data-ttu-id="32ba2-108">クライアントバージョンポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="32ba2-108">Client Version Policy Settings</span></span>

<span data-ttu-id="32ba2-109">既定のクライアントバージョンポリシーでは、すべてのクライアントが Lync を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32ba2-109">The default client version policy requires that all clients run Lync.</span></span> <span data-ttu-id="32ba2-110">環境内のクライアントが以前のバージョンの Communicator を実行している場合は、Lync Server 2013 に接続するときにクライアントとデバイスが予期せずブロックまたは更新されないように、クライアントバージョンルールを再構成する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="32ba2-110">If clients in your environment are running earlier versions of Communicator, you may need to reconfigure the Client Version rules to prevent clients and devices from being unexpectedly blocked or updated when connecting to Lync Server 2013.</span></span> <span data-ttu-id="32ba2-111">既定のルールを変更するか、[クライアントバージョンポリシー] の一覧で上位のルールを追加して既定のルールを上書きすることができます。</span><span class="sxs-lookup"><span data-stu-id="32ba2-111">You can modify the default rule, or you can add a rule higher in the Client Version Policy list to override the default rule.</span></span> <span data-ttu-id="32ba2-112">また、累積的な更新プログラム (Cu) がリリースされたため、最新の更新プログラムが必要になるようにクライアントバージョンポリシーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32ba2-112">Additionally, as Cumulative Updates (CUs) are released, you should configure the Client Version Policy to require the latest updates.</span></span> <span data-ttu-id="32ba2-113">詳細については、「操作」のドキュメントの「 [Lync Server 2013 へのログオンに使用できるクライアントアプリケーションを指定](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32ba2-113">For details, see [Specifying the client applications that can be used to log on to Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md) in the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

