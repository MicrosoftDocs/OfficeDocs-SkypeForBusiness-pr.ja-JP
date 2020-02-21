---
title: 'Lync Server 2013: 監視の展開チェックリスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for monitoring
ms:assetid: 4e798370-277c-4391-84b4-13a972b45ca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204874(v=OCS.15)
ms:contentKeyID: 48184080
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca72cf23ea3cb761dd652efae63ef086cae2e198
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205783"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-monitoring-in-lync-server-2013"></a><span data-ttu-id="ed63e-102">Lync Server 2013 での監視の展開チェックリスト</span><span class="sxs-lookup"><span data-stu-id="ed63e-102">Deployment checklist for monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed63e-103">_**トピックの最終更新日:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="ed63e-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="ed63e-104">監視は既に各フロントエンドサーバーにインストールされ、アクティブ化されていますが、実際に Microsoft Lync Server 2013 の監視データを収集するには、いくつかの手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed63e-104">Although monitoring is already installed and activated on each Front End server, there are still several steps that you must undertake before you can actually being to collect monitoring data for Microsoft Lync Server 2013.</span></span> <span data-ttu-id="ed63e-105">これらの手順を以下のチェックリストで簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="ed63e-105">These steps are outlined in the following checklist:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ed63e-106">フェーズ</span><span class="sxs-lookup"><span data-stu-id="ed63e-106">Phase</span></span></p></td>
<td><p><span data-ttu-id="ed63e-107">手順</span><span class="sxs-lookup"><span data-stu-id="ed63e-107">Steps</span></span></p></td>
<td><p><span data-ttu-id="ed63e-108">役割とグループ メンバーシップ</span><span class="sxs-lookup"><span data-stu-id="ed63e-108">Role and group membership</span></span></p></td>
<td><p><span data-ttu-id="ed63e-109">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="ed63e-109">Documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed63e-110"><strong>必要なハードウェアとソフトウェアのインストール</strong></span><span class="sxs-lookup"><span data-stu-id="ed63e-110"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="ed63e-111">監視用のバックエンド データ ストアとして機能するコンピューターに、サポートされているバージョンの Microsoft SQL Server をインストールします。</span><span class="sxs-lookup"><span data-stu-id="ed63e-111">Install a supported version of Microsoft SQL Server on the computer that will act as the backend data store for monitoring.</span></span></p></td>
<td><p><span data-ttu-id="ed63e-112">ローカルの Administrators グループのメンバーでもあるドメイン ユーザー。</span><span class="sxs-lookup"><span data-stu-id="ed63e-112">Domain user who is also a member of the local administrators group.</span></span></p></td>
<td><p><span data-ttu-id="ed63e-113">「サポート」のガイドの「 <a href="lync-server-2013-supported-hardware.md">Lync Server 2013 でサポートされるハードウェア</a>」</span><span class="sxs-lookup"><span data-stu-id="ed63e-113"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability guide</span></span></p>
<p><span data-ttu-id="ed63e-114">「サポート」のガイドの「 <a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync server 2013 でのサーバーソフトウェアとインフラストラクチャのサポート</a>」</span><span class="sxs-lookup"><span data-stu-id="ed63e-114"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability Guide</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed63e-115"><strong>適切な内部トポロジを作成して監視をサポートする</strong></span><span class="sxs-lookup"><span data-stu-id="ed63e-115"><strong>Create the appropriate internal topology to support monitoring</strong></span></span></p></td>
<td><p><span data-ttu-id="ed63e-116">Lync Server 2013 トポロジビルダーを使用して、監視データベースをトポロジに追加し、更新されたトポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="ed63e-116">Use Lync Server 2013 Topology Builder to add monitoring databases to the topology, then published the updated topology.</span></span></p></td>
<td><p><span data-ttu-id="ed63e-117">トポロジを定義する場合は、ローカル ユーザー グループのメンバーであるユーザー。</span><span class="sxs-lookup"><span data-stu-id="ed63e-117">To define a topology, a user who is a member of the local users group.</span></span></p>
<p><span data-ttu-id="ed63e-118">トポロジを公開する場合は、ドメイン管理者グループと RTCUniversalServerAdmins グループのメンバーであるユーザー。</span><span class="sxs-lookup"><span data-stu-id="ed63e-118">To publish the topology, a user who is a member if the domain administrators group and the RTCUniversalServerAdmins group.</span></span></p></td>
<td><p><span data-ttu-id="ed63e-119">展開ガイドの<a href="lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md">Lync Server 2013 でのフロントエンドプールへの監視ストアの関連付け</a></span><span class="sxs-lookup"><span data-stu-id="ed63e-119"><a href="lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md">Associating a monitoring store with a Front End pool in Lync Server 2013</a> in the Deployment guide</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed63e-120"><strong>適切な監視設定を有効にする</strong></span><span class="sxs-lookup"><span data-stu-id="ed63e-120"><strong>Enable the appropriate monitoring settings</strong></span></span></p></td>
<td><p><span data-ttu-id="ed63e-121">通話詳細記録 (CDR) と QoE (Quality of Experience) 監視を、グローバル スコープ/サイト スコープで有効にします。</span><span class="sxs-lookup"><span data-stu-id="ed63e-121">Enable call detail recording (CDR) and/or Quality of Experience (QoE) monitoring at the global and/or the site scopes.</span></span></p></td>
<td><p><span data-ttu-id="ed63e-122">RTCUniversalServerAdmins グループのメンバーであるユーザー、または CsCdrConfiguration および CsQoEConfiguration コマンドレットにアクセスできる RBAC の役割が割り当てられたユーザー。</span><span class="sxs-lookup"><span data-stu-id="ed63e-122">A user who is a member of the RTCUniversalServerAdmins group or who has been assigned an RBAC role that provides access to the CsCdrConfiguration and CsQoEConfiguration cmdlets.</span></span></p></td>
<td><p><span data-ttu-id="ed63e-123">運用ガイドの<a href="lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md">Lync Server 2013 での通話詳細記録と qoe (Quality Of Experience) 設定の構成</a></span><span class="sxs-lookup"><span data-stu-id="ed63e-123"><a href="lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md">Configuring call detail recording and Quality of Experience settings in Lync Server 2013</a> in the Operations guide</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

