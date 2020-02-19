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
ms.openlocfilehash: cf3ba3dc27bf3849ad6c3434f4baf1fa28c07780
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140000"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="performing-and-monitoring-backups-in-lync-server-2013"></a><span data-ttu-id="75e23-102">Lync Server 2013 でのバックアップの実行と監視</span><span class="sxs-lookup"><span data-stu-id="75e23-102">Performing and monitoring backups in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75e23-103">_**トピックの最終更新日:** 2014-05-15_</span><span class="sxs-lookup"><span data-stu-id="75e23-103">_**Topic Last Modified:** 2014-05-15_</span></span>

<span data-ttu-id="75e23-104">業務上の優先度によって、組織のバックアップと復元の要件を規定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="75e23-104">Your business priorities should drive the specification of backup and restoration requirements for your organization.</span></span> <span data-ttu-id="75e23-105">サーバーとデータのバックアップを実行することは、障害を計画するための最初の防御線です。</span><span class="sxs-lookup"><span data-stu-id="75e23-105">Performing backups of the servers and data is the first line of defense in planning for a disaster.</span></span>

<span data-ttu-id="75e23-106">Lync Server 2013 サービスまたはサーバーの役割を実行しているコンピューターは、現在のトポロジ、現在の構成設定、および現在のポリシーのコピーを持っている必要があります。その前に、指定された役割で機能することができます。</span><span class="sxs-lookup"><span data-stu-id="75e23-106">Computers that run Lync Server 2013 services or server roles must have a copy of the current topology, current configuration settings, and current policies before they can function in their appointed role.</span></span> <span data-ttu-id="75e23-107">Lync Server は、この情報が必要な各コンピューターに渡されていることを確認する責任があります。</span><span class="sxs-lookup"><span data-stu-id="75e23-107">Lync Server is responsible for making sure that this information is passed along to each computer that needs it.</span></span>

<span data-ttu-id="75e23-108">中央管理ストアのアップグレード時に、Lync Server トポロジ、構成設定、およびポリシーをバックアップおよび復元するには、 **Export-csconfiguration**および**Import-csconfiguration**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="75e23-108">The **Export-CsConfiguration** and **Import-CsConfiguration** cmdlets are used to back up and restore your Lync Server topology, configuration settings, and policies during a Central Management store upgrade.</span></span> <span data-ttu-id="75e23-109">**Export-CsConfiguration**コマンドレットを使用すると、データをにエクスポートできます。ZIP ファイル。</span><span class="sxs-lookup"><span data-stu-id="75e23-109">The **Export-CsConfiguration** cmdlets enable you to export data to a .ZIP file.</span></span> <span data-ttu-id="75e23-110">その後、**インポート-CsConfiguration**コマンドレットを使用して、このを読み取ることができます。ZIP ファイルを復元し、トポロジ、構成設定、およびポリシーを中央管理ストアに復元します。</span><span class="sxs-lookup"><span data-stu-id="75e23-110">You can then use the **Import-CsConfiguration** cmdlet to read that .ZIP file and restore the topology, configuration settings, and policies to the Central Management store.</span></span> <span data-ttu-id="75e23-111">その後、Lync server のレプリケーションサービスは、復元された情報を Lync Server サービスを実行している他のコンピューターにレプリケートします。</span><span class="sxs-lookup"><span data-stu-id="75e23-111">After that, the replication services of Lync Server will replicate the restored information to other computers that are running Lync Server services.</span></span>

<span data-ttu-id="75e23-112">構成データをエクスポートおよびインポートする機能は、境界ネットワーク (たとえば、エッジサーバー) に配置されているコンピューターの初期構成時にも使用されます。</span><span class="sxs-lookup"><span data-stu-id="75e23-112">The ability to export and import configuration data is also used during the initial configuration of computers that are located in your perimeter network (for example, Edge Servers).</span></span> <span data-ttu-id="75e23-113">境界ネットワーク内のコンピューターを構成する場合は、最初に CsConfiguration コマンドレットを使用して手動でレプリケーションを実行する必要があります。**エクスポート-CsConfiguration**を使用して構成データをエクスポートし、をコピーする必要があります。境界ネットワーク内のコンピューターへの ZIP ファイル。</span><span class="sxs-lookup"><span data-stu-id="75e23-113">When configuring a computer in the perimeter network, you must first perform a manual replication using the CsConfiguration cmdlets: you must export the configuration data by using **Export-CsConfiguration** and then copy the .ZIP file to the computer in the perimeter network.</span></span> <span data-ttu-id="75e23-114">その後、 **import-CsConfiguration**および localstore パラメーターを使用してデータをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="75e23-114">After that, you can use **Import-CsConfiguration** and the LocalStore parameter to import the data.</span></span> <span data-ttu-id="75e23-115">この操作は一度だけ実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="75e23-115">You only have to do this one time.</span></span> <span data-ttu-id="75e23-116">その後は、レプリケーションが自動的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="75e23-116">After that, replication will occur automatically.</span></span>

<span data-ttu-id="75e23-117">このコマンドレットを実行できるユーザー: 既定**では、RTCUniversalServerAdmins コマンドレットを**ローカルで実行する権限があるのは、次のグループのメンバーです。</span><span class="sxs-lookup"><span data-stu-id="75e23-117">Who can run this cmdlet: By default, members of the following groups are authorized to run the **Export-CsConfiguration** cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="75e23-118">すべての RBAC の役割の一覧を返すには、このコマンドレットを (自分で作成したカスタムの RBAC の役割を含む) に割り当てられているので、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="75e23-118">To return a list of all RBAC roles, this cmdlet is assigned to (including any custom RBAC roles that you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

`Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Export-CsConfiguration"}`

<span data-ttu-id="75e23-119">すべての SQL 2012 バックエンドデータベースは、 [sql のベストプラクティス](https://go.microsoft.com/fwlink/p/?linkid=290716)に従ってバックアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="75e23-119">All SQL 2012 Back End databases should be backed up as per [SQL best practices](https://go.microsoft.com/fwlink/p/?linkid=290716).</span></span>

<span data-ttu-id="75e23-120">Lync Server 2013 インフラストラクチャの障害復旧計画を定期的にテストするには、運用環境をできるだけ忠実に再現するラボ環境で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="75e23-120">Regular testing of the Disaster Recovery Plan for your Lync Server 2013 infrastructure should be performed in a lab environment that mimics the production environment as closely as possible.</span></span> <span data-ttu-id="75e23-121">障害復旧テストの詳細については、「月次タスク」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75e23-121">Refer to the Monthly Tasks for more information about Disaster Recovery Testing.</span></span>

<span data-ttu-id="75e23-122">バックアップの頻度は、復元ポイントと回復ポイントの目標に基づいて調整できます。</span><span class="sxs-lookup"><span data-stu-id="75e23-122">Note that the backup frequency can be adjusted, based on your Restore Point and Recovery Point objectives.</span></span> <span data-ttu-id="75e23-123">ベストプラクティスとして、毎日定期的に定期的なスナップショットを取得します。</span><span class="sxs-lookup"><span data-stu-id="75e23-123">As a best practice, take regular, periodic snapshots throughout the day.</span></span> <span data-ttu-id="75e23-124">通常、完全バックアップは24時間ごとに実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="75e23-124">Generally, you should perform full backups every 24 hours.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="75e23-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="75e23-125">See Also</span></span>


[<span data-ttu-id="75e23-126">インポート-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="75e23-126">Import-CsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[<span data-ttu-id="75e23-127">エクスポート-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="75e23-127">Export-CsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Export-CsConfiguration)  
[<span data-ttu-id="75e23-128">SQL のベストプラクティス</span><span class="sxs-lookup"><span data-stu-id="75e23-128">SQL best practices</span></span>](https://go.microsoft.com/fwlink/p/?linkid=290716)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

