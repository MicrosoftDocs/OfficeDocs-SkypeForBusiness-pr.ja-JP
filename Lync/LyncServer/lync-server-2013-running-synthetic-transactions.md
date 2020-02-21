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
ms.openlocfilehash: 476223c1c81f6927a1b5f96a78091e0f3c57ea12
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182760"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="running-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="817ab-102">Lync Server 2013 で代理トランザクションを実行する</span><span class="sxs-lookup"><span data-stu-id="817ab-102">Running synthetic transactions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="817ab-103">_**トピックの最終更新日:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="817ab-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="817ab-104">代理トランザクションは、通常、2つの方法で実施されます。</span><span class="sxs-lookup"><span data-stu-id="817ab-104">Synthetic transactions are typically conducted in two ways.</span></span> <span data-ttu-id="817ab-105">Get-cshealthmonitoringconfiguration コマンドレットを使用して、各レジストラープールのテストユーザーをセットアップできます。</span><span class="sxs-lookup"><span data-stu-id="817ab-105">You can use the CsHealthMonitoringConfiguration cmdlets to set up test users for each of their Registrar pools.</span></span> <span data-ttu-id="817ab-106">これらのテストユーザーは、代理トランザクションで使用するために事前に構成されたユーザーのペアです。</span><span class="sxs-lookup"><span data-stu-id="817ab-106">These test users are a pair of users who were preconfigured for use with synthetic transactions.</span></span> <span data-ttu-id="817ab-107">(通常、これらはテストアカウントであり、実際のユーザーに属するアカウントではありません)。テストユーザーがプールに対して構成されている場合は、テストに関与するユーザーアカウントの id を指定せずに (および資格情報を指定して)、そのプールに対して代理トランザクションを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="817ab-107">(Typically these are test accounts and not accounts that belong to actual users.) With test users configured for a pool, you can run a synthetic transaction against that pool without having to specify the identities of (and supply the credentials for) the user accounts involved in the test.</span></span>

<span data-ttu-id="817ab-108">または、実際のユーザーアカウントを使用して代理トランザクションを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="817ab-108">Or, you can run a synthetic transaction by using actual user accounts.</span></span> <span data-ttu-id="817ab-109">たとえば、2人のユーザーがインスタントメッセージを交換できない場合は、2つのユーザーアカウントを使用して代理トランザクションを実行して (テストアカウントのペアではなく)、問題の診断と解決を試みることができます。</span><span class="sxs-lookup"><span data-stu-id="817ab-109">For example, if two users cannot exchange instant messages, you could run a synthetic transaction using those two user accounts (instead of a pair of test accounts), and then try to diagnose and resolve the issue.</span></span> <span data-ttu-id="817ab-110">実際のユーザーアカウントを使用して代理トランザクションを実行する場合は、各ユーザーのログオン名とパスワードを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="817ab-110">If you decide to conduct a synthetic transaction using actual user accounts, you must supply the logon names and passwords for each user.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="817ab-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="817ab-111">See Also</span></span>


[<span data-ttu-id="817ab-112">Lync Server 2013 で監視ノードのテストユーザーと構成設定を構成する</span><span class="sxs-lookup"><span data-stu-id="817ab-112">Configuring watcher node test users and configuration settings in Lync Server 2013</span></span>](lync-server-2013-configuring-watcher-node-test-users-and-configuration-settings.md)  
[<span data-ttu-id="817ab-113">Lync Server 2013 での代理トランザクションの特別なセットアップ手順</span><span class="sxs-lookup"><span data-stu-id="817ab-113">Special setup instructions for synthetic transactions in Lync Server 2013</span></span>](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

