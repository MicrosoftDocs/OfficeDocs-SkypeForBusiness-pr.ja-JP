---
title: 'Lync Server 2013: 代理トランザクションを実行するためのウォッチャーノードの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a watcher node to run synthetic transactions
ms:assetid: cedda508-8881-4079-88d5-49798f342ddf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205314(v=OCS.15)
ms:contentKeyID: 48185578
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ec42f5b0f3839ee0efac84f08344aa1718120b7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840297"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-to-run-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="c0098-102">Lync Server 2013 で代理トランザクションを実行するためのウォッチャーノードの構成</span><span class="sxs-lookup"><span data-stu-id="c0098-102">Configuring a watcher node to run synthetic transactions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0098-103">_**最終更新日:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="c0098-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="c0098-104">System Center agent ファイルをインストールしたら、次にウォッチャーノード自体を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0098-104">After the System Center agent files have been installed, you must next configure the watcher node itself.</span></span> <span data-ttu-id="c0098-105">ウォッチャーノードを構成するための手順は、ウォッチャーノードのコンピューターが境界ネットワーク内にあるか境界ネットワークの外側にあるかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="c0098-105">The steps you take to configure a watcher node will vary depending on whether your watcher node computer lies inside your perimeter network or outside your perimeter network.</span></span>

<span data-ttu-id="c0098-106">監視ノードの構成時には、そのノードが使用する認証方法の種類も選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0098-106">When you configure a watcher node, you must also choose the type of authentication method to be employed by that node.</span></span> <span data-ttu-id="c0098-107">Lync Server 2013 では、次の2つの認証方法のいずれかを選択できます。信頼されたサーバーまたは資格情報認証。</span><span class="sxs-lookup"><span data-stu-id="c0098-107">Lync Server 2013 enables you to choose one of two authentication methods: Trusted Server or Credential Authentication.</span></span> <span data-ttu-id="c0098-108">この2つの方法の違いについては、次の表で説明します。</span><span class="sxs-lookup"><span data-stu-id="c0098-108">The differences between these two methods are outlined in the following table:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c0098-109">構成</span><span class="sxs-lookup"><span data-stu-id="c0098-109">Configuration</span></span></th>
<th><span data-ttu-id="c0098-110">説明</span><span class="sxs-lookup"><span data-stu-id="c0098-110">Description</span></span></th>
<th><span data-ttu-id="c0098-111">サポートされている場所</span><span class="sxs-lookup"><span data-stu-id="c0098-111">Locations Supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c0098-112">信頼できるサーバー</span><span class="sxs-lookup"><span data-stu-id="c0098-112">Trusted Server</span></span></p></td>
<td><p><span data-ttu-id="c0098-113">内部サーバーを偽装する証明書を使用し、認証チャレンジをバイパスします。</span><span class="sxs-lookup"><span data-stu-id="c0098-113">Uses a certificate to impersonate an internal server and bypass authentication challenges.</span></span></p>
<p><span data-ttu-id="c0098-114">これは、各ウォッチャーノードで多くのユーザーパスワードの代わりに1つの証明書を管理することを希望している管理者にとって便利です。</span><span class="sxs-lookup"><span data-stu-id="c0098-114">This is useful for administrators who would prefer to manage a single certificate instead of many user passwords on each watcher node.</span></span></p></td>
<td><p><span data-ttu-id="c0098-115">エンタープライズの内側。</span><span class="sxs-lookup"><span data-stu-id="c0098-115">Inside the enterprise.</span></span></p>
<p><span data-ttu-id="c0098-116">この方法では、監視ノードが監視対象のプールと同じドメインに存在する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c0098-116">Note that, with this method, the watcher node must be in the same domain as the pools being monitored.</span></span> <span data-ttu-id="c0098-117">ウォッチャーノードと監視対象のプールが異なるドメインにある場合は、代わりに資格情報認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="c0098-117">If the watcher node and the monitored pools are in different domains, use Credential Authentication instead.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0098-118">資格情報認証</span><span class="sxs-lookup"><span data-stu-id="c0098-118">Credential Authentication</span></span></p></td>
<td><p><span data-ttu-id="c0098-119">ユーザー名とパスワードを各監視ノードの Windows 資格情報マネージャーに保管します。</span><span class="sxs-lookup"><span data-stu-id="c0098-119">Stores user names and passwords securely in Windows Credential Manager on each watcher node.</span></span></p>
<p><span data-ttu-id="c0098-120">このモードでは、より多くのパスワードを管理する必要がありますが、エンタープライズの外部にあるウォッチャーノードには唯一の選択肢です。</span><span class="sxs-lookup"><span data-stu-id="c0098-120">This mode requires more password management, but is the only option for watcher nodes located outside of the enterprise.</span></span> <span data-ttu-id="c0098-121">このような外側に位置する監視ノードを認証の際に信頼済みのエンドポイントとして扱うことはできません。</span><span class="sxs-lookup"><span data-stu-id="c0098-121">These watcher nodes cannot be treated as an endpoint trusted for authentication.</span></span></p></td>
<td><p><span data-ttu-id="c0098-122">エンタープライズの外側。</span><span class="sxs-lookup"><span data-stu-id="c0098-122">Outside the enterprise.</span></span></p>
<p><span data-ttu-id="c0098-123">エンタープライズの内側。</span><span class="sxs-lookup"><span data-stu-id="c0098-123">Inside the enterprise.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c0098-124">また、ファイアウォールが MonitoringHost と PowerShell の両方の受信規則を持っていることも確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0098-124">You should also verify that your firewall has inbound rules for both MonitoringHost.exe and PowerShell.exe.</span></span> <span data-ttu-id="c0098-125">これらのプロセスがファイアウォールによってブロックされた場合、代理トランザクションは 504 (サーバータイムアウト) エラーで失敗します。</span><span class="sxs-lookup"><span data-stu-id="c0098-125">If these processes are blocked by the firewall then your synthetic transactions will fail with a 504 (server timeout) error.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

