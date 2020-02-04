---
title: 'フェーズ 4: トポロジの結合'
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: 'Phase 4: Merge topologies'
ms:assetid: 81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205044(v=OCS.15)
ms:contentKeyID: 48184668
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 624bbfa52c5d4ed963fda895e7af3a544f0f3733
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765738"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="phase-4-merge-topologies"></a><span data-ttu-id="8ee62-102">フェーズ 4: トポロジの結合</span><span class="sxs-lookup"><span data-stu-id="8ee62-102">Phase 4: Merge topologies</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ee62-103">_**最終更新日:** 2012-03-29_</span><span class="sxs-lookup"><span data-stu-id="8ee62-103">_**Topic Last Modified:** 2012-03-29_</span></span>

<span data-ttu-id="8ee62-104">次のトピックでは、Microsoft Office Communications Server 2007 R2 プールを Microsoft Lync Server 2013 プールに統合するために必要な手順の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="8ee62-104">The following topics outline the steps needed to merge your Microsoft Office Communications Server 2007 R2 pools to Microsoft Lync Server 2013 pools.</span></span> <span data-ttu-id="8ee62-105">まず、トポロジビルダーの結合ウィザードを使用してトポロジ情報をマージします。</span><span class="sxs-lookup"><span data-stu-id="8ee62-105">First, you use the Topology Builder Merge wizard to merge topology information.</span></span> <span data-ttu-id="8ee62-106">このツールは、Microsoft Office Communications Server 2007 R2 環境に関する情報を収集し、その情報を、Lync Server 2013 と共有されているデータベースに発行します。</span><span class="sxs-lookup"><span data-stu-id="8ee62-106">This tool collects information about your Office Communications Server 2007 R2 environment, including Edge Server information, and publishes that information to a database shared with Lync Server 2013.</span></span> <span data-ttu-id="8ee62-107">マージされたトポロジを公開した後、トポロジビルダーを使用して、Office Communications Server 2007 R2 のトポロジ情報と新しく展開された Lync Server 2013 トポロジに関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="8ee62-107">After you publish the merged topology, Topology Builder is used to view the Office Communications Server 2007 R2 topology information and information about the newly deployed Lync Server 2013 topology.</span></span> <span data-ttu-id="8ee62-108">最後に、Lync Server 管理シェルコマンドレットを使用して、ポリシーおよび構成設定をインポートします。</span><span class="sxs-lookup"><span data-stu-id="8ee62-108">Finally, you use Lync Server Management Shell cmdlets to import policies and configuration settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8ee62-109">このセクション中</span><span class="sxs-lookup"><span data-stu-id="8ee62-109">In This Section</span></span>

  - [<span data-ttu-id="8ee62-110">WMI の下位互換性パッケージをインストールする</span><span class="sxs-lookup"><span data-stu-id="8ee62-110">Install WMI Backward Compatibility package</span></span>](install-wmi-backward-compatibility-package.md)

  - [<span data-ttu-id="8ee62-111">トポロジビルダーの結合ウィザードを使用してマージする</span><span class="sxs-lookup"><span data-stu-id="8ee62-111">Merge using Topology Builder Merge wizard</span></span>](merge-using-topology-builder-merge-wizard.md)

  - [<span data-ttu-id="8ee62-112">ポリシーと設定をインポートする</span><span class="sxs-lookup"><span data-stu-id="8ee62-112">Import policies and settings</span></span>](import-policies-and-settings.md)

  - [<span data-ttu-id="8ee62-113">トポロジ情報を確認する</span><span class="sxs-lookup"><span data-stu-id="8ee62-113">Verify topology information</span></span>](verify-topology-information.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

