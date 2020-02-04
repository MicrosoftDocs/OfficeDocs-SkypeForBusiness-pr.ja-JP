---
title: 'Lync Server 2013: 代理トランザクションの実行'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running synthetic transactions
ms:assetid: 2b56c7bd-8956-4fa1-8232-1876b959b258
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720911(v=OCS.15)
ms:contentKeyID: 63969593
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b77593ea062f83352592ebe32dbb81b99c1a9613
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732797"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="a5919-102">Lync Server 2013 での代理トランザクションの実行</span><span class="sxs-lookup"><span data-stu-id="a5919-102">Running synthetic transactions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5919-103">_**最終更新日:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="a5919-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="a5919-104">通常、代理トランザクションは、次の2つの方法で行われます。</span><span class="sxs-lookup"><span data-stu-id="a5919-104">Synthetic transactions are typically conducted in two ways.</span></span> <span data-ttu-id="a5919-105">CsHealthMonitoringConfiguration コマンドレットを使用して、各レジストラープールのテストユーザーを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="a5919-105">You can use the CsHealthMonitoringConfiguration cmdlets to set up test users for each of their Registrar pools.</span></span> <span data-ttu-id="a5919-106">これらのテストユーザーは、代理トランザクションとして使用するように事前に構成されたユーザーのペアです。</span><span class="sxs-lookup"><span data-stu-id="a5919-106">These test users are a pair of users who were preconfigured for use with synthetic transactions.</span></span> <span data-ttu-id="a5919-107">(通常、テストアカウントであり、実際のユーザーに属するアカウントではありません)。プールに対して構成されたテストユーザーがいる場合、テストに関係しているユーザーアカウントの id を指定したり、資格情報を指定したりすることなく、そのプールに対して代理トランザクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="a5919-107">(Typically these are test accounts and not accounts that belong to actual users.) With test users configured for a pool, you can run a synthetic transaction against that pool without having to specify the identities of (and supply the credentials for) the user accounts involved in the test.</span></span>

<span data-ttu-id="a5919-108">または、実際のユーザーアカウントを使用して、代理トランザクションを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="a5919-108">Or, you can run a synthetic transaction by using actual user accounts.</span></span> <span data-ttu-id="a5919-109">たとえば、2人のユーザーがインスタントメッセージを交換できない場合は、(1 組のテストアカウントではなく) 2 つのユーザーアカウントを使用して代理トランザクションを実行し、問題を診断して解決することができます。</span><span class="sxs-lookup"><span data-stu-id="a5919-109">For example, if two users cannot exchange instant messages, you could run a synthetic transaction using those two user accounts (instead of a pair of test accounts), and then try to diagnose and resolve the issue.</span></span> <span data-ttu-id="a5919-110">実際のユーザーアカウントを使用して代理トランザクションを実行する場合は、各ユーザーのログオン名とパスワードを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5919-110">If you decide to conduct a synthetic transaction using actual user accounts, you must supply the logon names and passwords for each user.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="a5919-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="a5919-111">See Also</span></span>


[<span data-ttu-id="a5919-112">Lync Server 2013 で監視ノードのテストユーザーと構成設定を構成する</span><span class="sxs-lookup"><span data-stu-id="a5919-112">Configuring watcher node test users and configuration settings in Lync Server 2013</span></span>](lync-server-2013-configuring-watcher-node-test-users-and-configuration-settings.md)  
[<span data-ttu-id="a5919-113">Lync Server 2013 での代理トランザクションの特別なセットアップ手順</span><span class="sxs-lookup"><span data-stu-id="a5919-113">Special setup instructions for synthetic transactions in Lync Server 2013</span></span>](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

