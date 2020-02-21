---
title: 'フェーズ 4: トポロジを結合する'
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
ms.openlocfilehash: c9c93d46799dfd6c45ac7f6e40ce67a8a6bbfa72
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189700"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="phase-4-merge-topologies"></a><span data-ttu-id="9eea3-102">フェーズ 4: トポロジを結合する</span><span class="sxs-lookup"><span data-stu-id="9eea3-102">Phase 4: Merge topologies</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9eea3-103">_**トピックの最終更新日:** 2012-03-29_</span><span class="sxs-lookup"><span data-stu-id="9eea3-103">_**Topic Last Modified:** 2012-03-29_</span></span>

<span data-ttu-id="9eea3-104">次のトピックでは、Microsoft Office Communications Server 2007 R2 プールを Microsoft Lync Server 2013 プールにマージするために必要な手順の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="9eea3-104">The following topics outline the steps needed to merge your Microsoft Office Communications Server 2007 R2 pools to Microsoft Lync Server 2013 pools.</span></span> <span data-ttu-id="9eea3-105">最初に、トポロジ ビルダー結合ウィザードを使用して、トポロジ情報を結合します。</span><span class="sxs-lookup"><span data-stu-id="9eea3-105">First, you use the Topology Builder Merge wizard to merge topology information.</span></span> <span data-ttu-id="9eea3-106">このツールは、エッジサーバー情報を含む Office Communications Server 2007 R2 環境に関する情報を収集し、その情報を Lync Server 2013 と共有するデータベースに公開します。</span><span class="sxs-lookup"><span data-stu-id="9eea3-106">This tool collects information about your Office Communications Server 2007 R2 environment, including Edge Server information, and publishes that information to a database shared with Lync Server 2013.</span></span> <span data-ttu-id="9eea3-107">マージされたトポロジを公開した後は、トポロジビルダーを使用して、Office Communications Server 2007 R2 のトポロジ情報と、新しく展開した Lync Server 2013 トポロジに関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="9eea3-107">After you publish the merged topology, Topology Builder is used to view the Office Communications Server 2007 R2 topology information and information about the newly deployed Lync Server 2013 topology.</span></span> <span data-ttu-id="9eea3-108">最後に、Lync Server 管理シェル コマンドレットを使用して、ポリシーと構成設定をインポートします。</span><span class="sxs-lookup"><span data-stu-id="9eea3-108">Finally, you use Lync Server Management Shell cmdlets to import policies and configuration settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9eea3-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="9eea3-109">In This Section</span></span>

  - [<span data-ttu-id="9eea3-110">WMI 下位互換パッケージをインストールする</span><span class="sxs-lookup"><span data-stu-id="9eea3-110">Install WMI Backward Compatibility package</span></span>](install-wmi-backward-compatibility-package.md)

  - [<span data-ttu-id="9eea3-111">トポロジビルダーマージウィザードを使用したマージ</span><span class="sxs-lookup"><span data-stu-id="9eea3-111">Merge using Topology Builder Merge wizard</span></span>](merge-using-topology-builder-merge-wizard.md)

  - [<span data-ttu-id="9eea3-112">ポリシーと設定をインポートする</span><span class="sxs-lookup"><span data-stu-id="9eea3-112">Import policies and settings</span></span>](import-policies-and-settings.md)

  - [<span data-ttu-id="9eea3-113">トポロジの情報を確認する</span><span class="sxs-lookup"><span data-stu-id="9eea3-113">Verify topology information</span></span>](verify-topology-information.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

