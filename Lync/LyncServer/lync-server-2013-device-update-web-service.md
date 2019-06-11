---
title: 'Lync Server 2013: デバイス更新 Web サービス'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Device Update Web service
ms:assetid: 036f473d-a131-431f-8051-76ccadc5cfba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994015(v=OCS.15)
ms:contentKeyID: 51803921
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d2b258b7a088f0deeee029be482f1ed63bc00ef
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833419"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-update-web-service-in-lync-server-2013"></a><span data-ttu-id="7c039-102">Lync Server 2013 のデバイス更新 Web サービス</span><span class="sxs-lookup"><span data-stu-id="7c039-102">Device Update Web service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c039-103">_**最終更新日:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="7c039-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="7c039-104">Lync Server には、Web サービスの役割の一部として自動的にインストールされるデバイス更新 Web サービスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7c039-104">Lync Server includes the Device Update Web service, which is automatically installed as part of the Web Services role.</span></span> <span data-ttu-id="7c039-105">このサービスを利用すると、Microsoft から更新プログラムをダウンロードし、テストして、組織内の IP 電話に更新プログラムを展開することができます。</span><span class="sxs-lookup"><span data-stu-id="7c039-105">This service lets you download updates from Microsoft, test them, and then deploy the updates to IP phones in your organization.</span></span> <span data-ttu-id="7c039-106">また、デバイス更新 Web サービスを使って、デバイスを以前のバージョンのソフトウェアに戻すこともできます。</span><span class="sxs-lookup"><span data-stu-id="7c039-106">You can also use Device Update Web service to roll back devices to previous software versions.</span></span>

<span data-ttu-id="7c039-107">このセクションでは、デバイス更新プログラムの Web サービスを管理する方法、およびデバイスの更新ログを使用して更新プログラムを\*\* 展開する方法の詳細について説明します。ルール (Lync Phone Edition では、ハードウェアデバイスとのファームウェアバージョンの更新プログラムを関連付けます)、構成設定。</span><span class="sxs-lookup"><span data-stu-id="7c039-107">This section provides details about how to manage the Device Update Web service and deployed updates by using device update logs, rules (Lync Phone Edition uses *rules* to associate firmware version updates with hardware devices), and configuration settings.</span></span>

<span data-ttu-id="7c039-108">デバイス更新 Web サービスのプロセスと機能の詳細については、「Lync Server 2010 TechNet ライブラリでの[デバイスの更新](http://technet.microsoft.com/en-us/library/gg412864\(v=ocs.14\).aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c039-108">For details about the Device Update Web service process and features, see [Updating Devices](http://technet.microsoft.com/en-us/library/gg412864\(v=ocs.14\).aspx) in the Lync Server 2010 TechNet Library.</span></span> <span data-ttu-id="7c039-109">(また、lync Phone Edition のすべてのコンポーネントなどのデバイス更新 Web サービスは、lync Server 2010 と同じように、Lync Server 2013 と同じように動作します)。</span><span class="sxs-lookup"><span data-stu-id="7c039-109">(Note that the Device Update Web service, like all Lync Phone Edition components, works the same way with Lync Server 2013 as it does with Lync Server 2010.)</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7c039-110">このセクション中</span><span class="sxs-lookup"><span data-stu-id="7c039-110">In This Section</span></span>

  - [<span data-ttu-id="7c039-111">Lync Server 2013 のデバイスの更新ログとファイル</span><span class="sxs-lookup"><span data-stu-id="7c039-111">Device Update logs and files in Lync Server 2013</span></span>](lync-server-2013-device-update-logs-and-files.md)

  - [<span data-ttu-id="7c039-112">Lync Server 2013 のデバイス更新ルール</span><span class="sxs-lookup"><span data-stu-id="7c039-112">Device Update rules in Lync Server 2013</span></span>](lync-server-2013-device-update-rules.md)

  - [<span data-ttu-id="7c039-113">Lync Server 2013 のデバイス更新設定の設定</span><span class="sxs-lookup"><span data-stu-id="7c039-113">Device Update configuration settings in Lync Server 2013</span></span>](lync-server-2013-device-update-configuration-settings.md)

  - [<span data-ttu-id="7c039-114">Lync Server 2013 でのデバイスのソフトウェア更新プログラムの表示</span><span class="sxs-lookup"><span data-stu-id="7c039-114">View software updates for devices in Lync Server 2013</span></span>](lync-server-2013-view-software-updates-for-devices-in-your-organization.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7c039-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="7c039-115">See Also</span></span>


<span data-ttu-id="7c039-116">[デバイスの管理とトラブルシューティングのためのツールとサービス](http://technet.microsoft.com/en-us/library/gg425800\(v=ocs.14\).aspx)</span><span class="sxs-lookup"><span data-stu-id="7c039-116">[Tools and Services for Managing and Troubleshooting Devices](http://technet.microsoft.com/en-us/library/gg425800\(v=ocs.14\).aspx)</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

