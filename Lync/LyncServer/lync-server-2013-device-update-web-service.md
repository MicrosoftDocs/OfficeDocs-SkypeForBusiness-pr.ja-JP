---
title: 'Lync Server 2013: デバイス更新 Web サービス'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device Update Web service
ms:assetid: 036f473d-a131-431f-8051-76ccadc5cfba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994015(v=OCS.15)
ms:contentKeyID: 51803921
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7213513657720cc08057cbf2d54d425b5d2a96f4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044869"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-update-web-service-in-lync-server-2013"></a><span data-ttu-id="2e1d7-102">Lync Server 2013 のデバイス更新 Web サービス</span><span class="sxs-lookup"><span data-stu-id="2e1d7-102">Device Update Web service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2e1d7-103">_**トピックの最終更新日:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="2e1d7-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="2e1d7-104">Lync Server には、Web サービスの役割の一部として自動的にインストールされるデバイス更新 Web サービスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2e1d7-104">Lync Server includes the Device Update Web service, which is automatically installed as part of the Web Services role.</span></span> <span data-ttu-id="2e1d7-105">このサービスを使用すると、Microsoft から更新プログラムをダウンロードしてテストし、組織内の IP 電話に更新プログラムを展開することができます。</span><span class="sxs-lookup"><span data-stu-id="2e1d7-105">This service lets you download updates from Microsoft, test them, and then deploy the updates to IP phones in your organization.</span></span> <span data-ttu-id="2e1d7-106">デバイス更新 Web サービスを使用して、デバイスを以前のソフトウェアバージョンにロールバックすることもできます。</span><span class="sxs-lookup"><span data-stu-id="2e1d7-106">You can also use Device Update Web service to roll back devices to previous software versions.</span></span>

<span data-ttu-id="2e1d7-107">このセクションでは、デバイス更新プログラムの Web サービスを管理する方法、およびデバイス更新ログを使用して更新プログラムを展開する方法、ルール (Lync Phone Edition がファームウェアバージョンの更新プログラムをハードウェアデバイスに関連付けるための*ルール*を使用する)、構成設定について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="2e1d7-107">This section provides details about how to manage the Device Update Web service and deployed updates by using device update logs, rules (Lync Phone Edition uses *rules* to associate firmware version updates with hardware devices), and configuration settings.</span></span>

<span data-ttu-id="2e1d7-108">デバイス更新 Web サービスのプロセスと機能の詳細については、「Lync Server 2010 TechNet ライブラリの[デバイスの更新](http://technet.microsoft.com/library/gg412864\(v=ocs.14\).aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e1d7-108">For details about the Device Update Web service process and features, see [Updating Devices](http://technet.microsoft.com/library/gg412864\(v=ocs.14\).aspx) in the Lync Server 2010 TechNet Library.</span></span> <span data-ttu-id="2e1d7-109">(すべての Lync Phone Edition コンポーネントと同様に、lync server 2010 の場合と同じように、デバイス更新 Web サービスは lync Server 2013 と同じように動作します)。</span><span class="sxs-lookup"><span data-stu-id="2e1d7-109">(Note that the Device Update Web service, like all Lync Phone Edition components, works the same way with Lync Server 2013 as it does with Lync Server 2010.)</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2e1d7-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="2e1d7-110">In This Section</span></span>

  - [<span data-ttu-id="2e1d7-111">Lync Server 2013 のデバイス更新ログとファイル</span><span class="sxs-lookup"><span data-stu-id="2e1d7-111">Device Update logs and files in Lync Server 2013</span></span>](lync-server-2013-device-update-logs-and-files.md)

  - [<span data-ttu-id="2e1d7-112">Lync Server 2013 のデバイス更新ルール</span><span class="sxs-lookup"><span data-stu-id="2e1d7-112">Device Update rules in Lync Server 2013</span></span>](lync-server-2013-device-update-rules.md)

  - [<span data-ttu-id="2e1d7-113">Lync Server 2013 のデバイス更新構成設定</span><span class="sxs-lookup"><span data-stu-id="2e1d7-113">Device Update configuration settings in Lync Server 2013</span></span>](lync-server-2013-device-update-configuration-settings.md)

  - [<span data-ttu-id="2e1d7-114">Lync Server 2013 のデバイスのソフトウェア更新プログラムを表示する</span><span class="sxs-lookup"><span data-stu-id="2e1d7-114">View software updates for devices in Lync Server 2013</span></span>](lync-server-2013-view-software-updates-for-devices-in-your-organization.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2e1d7-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="2e1d7-115">See Also</span></span>


<span data-ttu-id="2e1d7-116">[デバイスの管理とトラブルシューティングのためのツールとサービス](http://technet.microsoft.com/library/gg425800\(v=ocs.14\).aspx)</span><span class="sxs-lookup"><span data-stu-id="2e1d7-116">[Tools and Services for Managing and Troubleshooting Devices](http://technet.microsoft.com/library/gg425800\(v=ocs.14\).aspx)</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

