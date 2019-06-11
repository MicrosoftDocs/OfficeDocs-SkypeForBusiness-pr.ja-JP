---
title: 'Lync Server 2013: 監視の展開チェックリスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for monitoring
ms:assetid: 4e798370-277c-4391-84b4-13a972b45ca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204874(v=OCS.15)
ms:contentKeyID: 48184080
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3cbf14920ef0103f2d6e8aa6088a2c0b35e17654
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833497"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-monitoring-in-lync-server-2013"></a><span data-ttu-id="2737b-102">Lync Server 2013 の監視の展開チェックリスト</span><span class="sxs-lookup"><span data-stu-id="2737b-102">Deployment checklist for monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2737b-103">_**最終更新日:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="2737b-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="2737b-104">監視は既に各フロントエンドサーバーにインストールされてライセンス認証されていますが、Microsoft Lync Server 2013 の監視データを実際に収集する前に、いくつかの手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2737b-104">Although monitoring is already installed and activated on each Front End server, there are still several steps that you must undertake before you can actually being to collect monitoring data for Microsoft Lync Server 2013.</span></span> <span data-ttu-id="2737b-105">これらの手順については、次のチェックリストで説明します。</span><span class="sxs-lookup"><span data-stu-id="2737b-105">These steps are outlined in the following checklist:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2737b-106">段階</span><span class="sxs-lookup"><span data-stu-id="2737b-106">Phase</span></span></p></td>
<td><p><span data-ttu-id="2737b-107">手順</span><span class="sxs-lookup"><span data-stu-id="2737b-107">Steps</span></span></p></td>
<td><p><span data-ttu-id="2737b-108">役割とグループのメンバーシップ</span><span class="sxs-lookup"><span data-stu-id="2737b-108">Role and group membership</span></span></p></td>
<td><p><span data-ttu-id="2737b-109">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="2737b-109">Documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2737b-110"><strong>必要なハードウェアとソフトウェアのインストール</strong></span><span class="sxs-lookup"><span data-stu-id="2737b-110"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="2737b-111">監視用のバックエンドデータストアとして機能する、サポートされているバージョンの Microsoft SQL Server をコンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="2737b-111">Install a supported version of Microsoft SQL Server on the computer that will act as the backend data store for monitoring.</span></span></p></td>
<td><p><span data-ttu-id="2737b-112">ローカル管理者グループのメンバーでもあるドメインユーザー。</span><span class="sxs-lookup"><span data-stu-id="2737b-112">Domain user who is also a member of the local administrators group.</span></span></p></td>
<td><p><span data-ttu-id="2737b-113"><a href="lync-server-2013-supported-hardware.md">サポートガイドの Lync Server 2013 でサポートされているハードウェア</a></span><span class="sxs-lookup"><span data-stu-id="2737b-113"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability guide</span></span></p>
<p><span data-ttu-id="2737b-114">サポートガイドの<a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync server 2013 でのサーバーソフトウェアとインフラストラクチャのサポート</a></span><span class="sxs-lookup"><span data-stu-id="2737b-114"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability Guide</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2737b-115"><strong>監視をサポートする適切な内部トポロジを作成する</strong></span><span class="sxs-lookup"><span data-stu-id="2737b-115"><strong>Create the appropriate internal topology to support monitoring</strong></span></span></p></td>
<td><p><span data-ttu-id="2737b-116">Lync Server 2013 トポロジビルダーを使用して、監視データベースをトポロジに追加した後、更新されたトポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="2737b-116">Use Lync Server 2013 Topology Builder to add monitoring databases to the topology, then published the updated topology.</span></span></p></td>
<td><p><span data-ttu-id="2737b-117">トポロジ (ローカルユーザーグループのメンバーであるユーザー) を定義するには、[] を選びます。</span><span class="sxs-lookup"><span data-stu-id="2737b-117">To define a topology, a user who is a member of the local users group.</span></span></p>
<p><span data-ttu-id="2737b-118">トポロジを公開するには、ドメイン管理者グループと RTCUniversalServerAdmins グループのメンバーであるユーザー。</span><span class="sxs-lookup"><span data-stu-id="2737b-118">To publish the topology, a user who is a member if the domain administrators group and the RTCUniversalServerAdmins group.</span></span></p></td>
<td><p><span data-ttu-id="2737b-119">展開ガイドの<a href="lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md">Lync Server 2013 でのフロントエンドプールへの監視ストアの関連付け</a></span><span class="sxs-lookup"><span data-stu-id="2737b-119"><a href="lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md">Associating a monitoring store with a Front End pool in Lync Server 2013</a> in the Deployment guide</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2737b-120"><strong>適切な監視設定を有効にする</strong></span><span class="sxs-lookup"><span data-stu-id="2737b-120"><strong>Enable the appropriate monitoring settings</strong></span></span></p></td>
<td><p><span data-ttu-id="2737b-121">グローバルまたはサイトのスコープで、通話の詳細記録 (CDR) と Quality of Experience (QoE) 監視を有効にします。</span><span class="sxs-lookup"><span data-stu-id="2737b-121">Enable call detail recording (CDR) and/or Quality of Experience (QoE) monitoring at the global and/or the site scopes.</span></span></p></td>
<td><p><span data-ttu-id="2737b-122">RTCUniversalServerAdmins グループのメンバーであるか、CsCdrConfiguration と CsQoEConfiguration コマンドレットへのアクセスを提供する RBAC の役割が割り当てられているユーザー。</span><span class="sxs-lookup"><span data-stu-id="2737b-122">A user who is a member of the RTCUniversalServerAdmins group or who has been assigned an RBAC role that provides access to the CsCdrConfiguration and CsQoEConfiguration cmdlets.</span></span></p></td>
<td><p><span data-ttu-id="2737b-123">運用ガイドの<a href="lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md">Lync Server 2013 での通話の記録と音質の設定を構成する</a></span><span class="sxs-lookup"><span data-stu-id="2737b-123"><a href="lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md">Configuring call detail recording and Quality of Experience settings in Lync Server 2013</a> in the Operations guide</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

