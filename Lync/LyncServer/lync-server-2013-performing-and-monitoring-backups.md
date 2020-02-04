---
title: 'Lync Server 2013: バックアップの実行と監視'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Performing and monitoring backups
ms:assetid: 2df415d4-0f37-460e-99ff-4035a9a2f445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720912(v=OCS.15)
ms:contentKeyID: 63969595
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3181a266e5792d190186e9f09b2cab5852156cbe
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755267"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="performing-and-monitoring-backups-in-lync-server-2013"></a><span data-ttu-id="a1bc8-102">Lync Server 2013 でのバックアップの実行と監視</span><span class="sxs-lookup"><span data-stu-id="a1bc8-102">Performing and monitoring backups in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1bc8-103">_**最終更新日:** 2014-05-15_</span><span class="sxs-lookup"><span data-stu-id="a1bc8-103">_**Topic Last Modified:** 2014-05-15_</span></span>

<span data-ttu-id="a1bc8-104">ビジネス優先度によって、組織のバックアップと復元の要件を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1bc8-104">Your business priorities should drive the specification of backup and restoration requirements for your organization.</span></span> <span data-ttu-id="a1bc8-105">サーバーとデータのバックアップを実行することが、障害の計画での第1の防御線です。</span><span class="sxs-lookup"><span data-stu-id="a1bc8-105">Performing backups of the servers and data is the first line of defense in planning for a disaster.</span></span>

<span data-ttu-id="a1bc8-106">Lync Server 2013 サービスまたはサーバーロールを実行しているコンピューターには、現在のトポロジ、現在の構成設定、および現在のポリシーのコピーが、指定された役割で機能するために必要です。</span><span class="sxs-lookup"><span data-stu-id="a1bc8-106">Computers that run Lync Server 2013 services or server roles must have a copy of the current topology, current configuration settings, and current policies before they can function in their appointed role.</span></span> <span data-ttu-id="a1bc8-107">Lync Server は、この情報が必要な各コンピューターに渡されることを確認する責任を負います。</span><span class="sxs-lookup"><span data-stu-id="a1bc8-107">Lync Server is responsible for making sure that this information is passed along to each computer that needs it.</span></span>

<span data-ttu-id="a1bc8-108">**エクスポート-csconfiguration**コマンドレットと**インポート-csconfiguration**コマンドレットを使用して、一元管理ストアアップグレード中の Lync Server のトポロジ、構成設定、ポリシーをバックアップおよび復元します。</span><span class="sxs-lookup"><span data-stu-id="a1bc8-108">The **Export-CsConfiguration** and **Import-CsConfiguration** cmdlets are used to back up and restore your Lync Server topology, configuration settings, and policies during a Central Management store upgrade.</span></span> <span data-ttu-id="a1bc8-109">**エクスポート-CsConfiguration**コマンドレットを使用して、データをにエクスポートできます。ZIP ファイル。</span><span class="sxs-lookup"><span data-stu-id="a1bc8-109">The **Export-CsConfiguration** cmdlets enable you to export data to a .ZIP file.</span></span> <span data-ttu-id="a1bc8-110">次に、**インポート-CsConfiguration**コマンドレットを使用して、これを読み取ります。ZIP ファイルを保存して、トポロジ、構成設定、ポリシーを中央管理ストアに復元します。</span><span class="sxs-lookup"><span data-stu-id="a1bc8-110">You can then use the **Import-CsConfiguration** cmdlet to read that .ZIP file and restore the topology, configuration settings, and policies to the Central Management store.</span></span> <span data-ttu-id="a1bc8-111">その後、Lync server のレプリケーションサービスは、復元された情報を Lync Server サービスを実行している他のコンピューターに複製します。</span><span class="sxs-lookup"><span data-stu-id="a1bc8-111">After that, the replication services of Lync Server will replicate the restored information to other computers that are running Lync Server services.</span></span>

<span data-ttu-id="a1bc8-112">構成データをエクスポートおよびインポートする機能は、境界ネットワーク (たとえば、エッジサーバー) に配置されているコンピューターの最初の構成時にも使用されます。</span><span class="sxs-lookup"><span data-stu-id="a1bc8-112">The ability to export and import configuration data is also used during the initial configuration of computers that are located in your perimeter network (for example, Edge Servers).</span></span> <span data-ttu-id="a1bc8-113">境界ネットワークでコンピューターを構成する場合は、まず、CsConfiguration コマンドレットを使用して手動でレプリケーションを実行する必要があります。**エクスポート-CsConfiguration**を使用して構成データをエクスポートし、をコピーする必要があります。境界ネットワークのコンピューターに ZIP ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="a1bc8-113">When configuring a computer in the perimeter network, you must first perform a manual replication using the CsConfiguration cmdlets: you must export the configuration data by using **Export-CsConfiguration** and then copy the .ZIP file to the computer in the perimeter network.</span></span> <span data-ttu-id="a1bc8-114">その後、 **import-CsConfiguration**と localstore パラメーターを使ってデータをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="a1bc8-114">After that, you can use **Import-CsConfiguration** and the LocalStore parameter to import the data.</span></span> <span data-ttu-id="a1bc8-115">この操作は1回だけ実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1bc8-115">You only have to do this one time.</span></span> <span data-ttu-id="a1bc8-116">その後、複製が自動的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="a1bc8-116">After that, replication will occur automatically.</span></span>

<span data-ttu-id="a1bc8-117">このコマンドレットを実行できるのはどのユーザーですか。既定では、次のグループのメンバーは、ローカルで**エクスポートと CsConfiguration**コマンドレットを実行することを許可されています。 RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="a1bc8-117">Who can run this cmdlet: By default, members of the following groups are authorized to run the **Export-CsConfiguration** cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="a1bc8-118">すべての RBAC ロールの一覧を返すには、このコマンドレットが (自分自身で作成したすべてのカスタム RBAC ロールを含む) に割り当てられ、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a1bc8-118">To return a list of all RBAC roles, this cmdlet is assigned to (including any custom RBAC roles that you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

`Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Export-CsConfiguration"}`

<span data-ttu-id="a1bc8-119">すべての SQL 2012 バックエンドデータベースは、 [sql のベストプラクティス](http://go.microsoft.com/fwlink/p/?linkid=290716)に従ってバックアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1bc8-119">All SQL 2012 Back End databases should be backed up as per [SQL best practices](http://go.microsoft.com/fwlink/p/?linkid=290716).</span></span>

<span data-ttu-id="a1bc8-120">Lync Server 2013 インフラストラクチャの障害回復計画を定期的にテストすることは、実稼働環境にできるだけ近いラボ環境で行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1bc8-120">Regular testing of the Disaster Recovery Plan for your Lync Server 2013 infrastructure should be performed in a lab environment that mimics the production environment as closely as possible.</span></span> <span data-ttu-id="a1bc8-121">障害回復テストの詳細については、「月次タスク」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1bc8-121">Refer to the Monthly Tasks for more information about Disaster Recovery Testing.</span></span>

<span data-ttu-id="a1bc8-122">復元ポイントと回復ポイントの目標に基づいて、バックアップの頻度を調整できます。</span><span class="sxs-lookup"><span data-stu-id="a1bc8-122">Note that the backup frequency can be adjusted, based on your Restore Point and Recovery Point objectives.</span></span> <span data-ttu-id="a1bc8-123">ベストプラクティスとして、日常的に定期的にスナップショットを取ることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a1bc8-123">As a best practice, take regular, periodic snapshots throughout the day.</span></span> <span data-ttu-id="a1bc8-124">通常、フルバックアップは24時間ごとに実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1bc8-124">Generally, you should perform full backups every 24 hours.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="a1bc8-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="a1bc8-125">See Also</span></span>


[<span data-ttu-id="a1bc8-126">インポート-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="a1bc8-126">Import-CsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[<span data-ttu-id="a1bc8-127">エクスポート-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="a1bc8-127">Export-CsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Export-CsConfiguration)  
[<span data-ttu-id="a1bc8-128">SQL のベストプラクティス</span><span class="sxs-lookup"><span data-stu-id="a1bc8-128">SQL best practices</span></span>](http://go.microsoft.com/fwlink/p/?linkid=290716)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

