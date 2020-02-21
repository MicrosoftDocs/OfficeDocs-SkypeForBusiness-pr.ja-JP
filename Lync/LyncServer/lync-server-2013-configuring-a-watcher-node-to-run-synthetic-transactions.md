---
title: 'Lync Server 2013: 代理トランザクションを実行する監視ノードの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to run synthetic transactions
ms:assetid: cedda508-8881-4079-88d5-49798f342ddf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205314(v=OCS.15)
ms:contentKeyID: 48185578
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 605a859717736785df2d726720c2984162ff830d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207993"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-to-run-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="2083d-102">Lync Server 2013 で代理トランザクションを実行する監視ノードの構成</span><span class="sxs-lookup"><span data-stu-id="2083d-102">Configuring a watcher node to run synthetic transactions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2083d-103">_**トピックの最終更新日:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="2083d-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="2083d-p101">System Center エージェント ファイルがインストールされたら、次に監視ノード自体を構成する必要があります。監視ノードを構成する手順は監視ノードを境界ネットワークの内側に置くか、外側に置くかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="2083d-p101">After the System Center agent files have been installed, you must next configure the watcher node itself. The steps you take to configure a watcher node will vary depending on whether your watcher node computer lies inside your perimeter network or outside your perimeter network.</span></span>

<span data-ttu-id="2083d-106">監視ノードの構成時には、そのノードが使用する認証方法の種類も選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2083d-106">When you configure a watcher node, you must also choose the type of authentication method to be employed by that node.</span></span> <span data-ttu-id="2083d-107">Lync Server 2013 では、信頼されたサーバー認証または資格情報認証という2つの認証方法のどちらかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="2083d-107">Lync Server 2013 enables you to choose one of two authentication methods: Trusted Server or Credential Authentication.</span></span> <span data-ttu-id="2083d-108">この 2 つの方法の主な違いを次の表にまとめます。</span><span class="sxs-lookup"><span data-stu-id="2083d-108">The differences between these two methods are outlined in the following table:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2083d-109">構成</span><span class="sxs-lookup"><span data-stu-id="2083d-109">Configuration</span></span></th>
<th><span data-ttu-id="2083d-110">説明</span><span class="sxs-lookup"><span data-stu-id="2083d-110">Description</span></span></th>
<th><span data-ttu-id="2083d-111">サポートされる場所</span><span class="sxs-lookup"><span data-stu-id="2083d-111">Locations Supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2083d-112">信頼済みサーバー</span><span class="sxs-lookup"><span data-stu-id="2083d-112">Trusted Server</span></span></p></td>
<td><p><span data-ttu-id="2083d-113">内部サーバーを偽装する証明書を使用し、認証チャレンジをバイパスします。</span><span class="sxs-lookup"><span data-stu-id="2083d-113">Uses a certificate to impersonate an internal server and bypass authentication challenges.</span></span></p>
<p><span data-ttu-id="2083d-114">この方法は、各監視ノードで多数のユーザー パスワードではなく、1 つの証明書を管理したいと考える管理者にとって便利です。</span><span class="sxs-lookup"><span data-stu-id="2083d-114">This is useful for administrators who would prefer to manage a single certificate instead of many user passwords on each watcher node.</span></span></p></td>
<td><p><span data-ttu-id="2083d-115">エンタープライズの内側。</span><span class="sxs-lookup"><span data-stu-id="2083d-115">Inside the enterprise.</span></span></p>
<p><span data-ttu-id="2083d-p103">この方法では、監視ノードが監視対象のプールと同じドメイン内に存在する必要があることに注意してください。監視ノードと監視対象のプールが別のドメインに存在する場合は、この方法ではなく、資格情報認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="2083d-p103">Note that, with this method, the watcher node must be in the same domain as the pools being monitored. If the watcher node and the monitored pools are in different domains, use Credential Authentication instead.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2083d-118">資格情報認証</span><span class="sxs-lookup"><span data-stu-id="2083d-118">Credential Authentication</span></span></p></td>
<td><p><span data-ttu-id="2083d-119">ユーザー名とパスワードを各監視ノードの Windows 資格情報マネージャーに保管します。</span><span class="sxs-lookup"><span data-stu-id="2083d-119">Stores user names and passwords securely in Windows Credential Manager on each watcher node.</span></span></p>
<p><span data-ttu-id="2083d-p104">このモードは、パスワード管理の手間を必要としますが、エンタープライズの外側に位置する監視ノードの場合には唯一の選択肢となります。このような外側に位置する監視ノードを認証の際に信頼済みのエンドポイントとして扱うことはできません。</span><span class="sxs-lookup"><span data-stu-id="2083d-p104">This mode requires more password management, but is the only option for watcher nodes located outside of the enterprise. These watcher nodes cannot be treated as an endpoint trusted for authentication.</span></span></p></td>
<td><p><span data-ttu-id="2083d-122">エンタープライズの外側。</span><span class="sxs-lookup"><span data-stu-id="2083d-122">Outside the enterprise.</span></span></p>
<p><span data-ttu-id="2083d-123">エンタープライズの内側。</span><span class="sxs-lookup"><span data-stu-id="2083d-123">Inside the enterprise.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2083d-124">また、ファイアウォールには、MonitoringHost と PowerShell の両方の受信規則があることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2083d-124">You should also verify that your firewall has inbound rules for both MonitoringHost.exe and PowerShell.exe.</span></span> <span data-ttu-id="2083d-125">これらのプロセスがファイアウォールによってブロックされている場合、代理トランザクションは 504 (サーバータイムアウト) エラーで失敗します。</span><span class="sxs-lookup"><span data-stu-id="2083d-125">If these processes are blocked by the firewall then your synthetic transactions will fail with a 504 (server timeout) error.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

