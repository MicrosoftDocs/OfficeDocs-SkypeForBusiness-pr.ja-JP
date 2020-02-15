---
title: 'Lync Server 2013: 監視またはアーカイブデータの復元'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring monitoring or archiving data
ms:assetid: 60118526-13bb-4b03-803e-6ffae219d436
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202175(v=OCS.15)
ms:contentKeyID: 51541483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8840869e972f0c178360b0b50644d352b8db85df
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050419"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-monitoring-or-archiving-data-in-lync-server-2013"></a><span data-ttu-id="802d2-102">Lync Server 2013 での監視またはアーカイブデータの復元</span><span class="sxs-lookup"><span data-stu-id="802d2-102">Restoring monitoring or archiving data in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="802d2-103">_**トピックの最終更新日:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="802d2-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="802d2-104">障害が発生した後で Lync Server を起動して実行するには、監視およびアーカイブデータを復元する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="802d2-104">Restoring monitoring and archiving data is not required to get Lync Server up and running after a failure.</span></span> <span data-ttu-id="802d2-105">ただし、組織にとってデータの監視とアーカイブが重要である場合は、データベースを再作成した後にデータを復元することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="802d2-105">However, if monitoring and archiving data is critical to your organization, you will want to restore the data after you re-create the databases.</span></span>

<span data-ttu-id="802d2-106">次の手順では、SQL Server Management Studio を使用してアーカイブデータまたは監視データを復元する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="802d2-106">The following procedure describes how to use SQL Server Management Studio to restore archiving or monitoring data.</span></span>

<div>

## <a name="to-restore-monitoring-or-archiving-data-from-a-backup-file"></a><span data-ttu-id="802d2-107">監視データまたはアーカイブ データをバックアップ ファイルから復元するには</span><span class="sxs-lookup"><span data-stu-id="802d2-107">To restore monitoring or archiving data from a backup file</span></span>

1.  <span data-ttu-id="802d2-108">ローカルコンピューターの Administrators グループのメンバーとして、または同等のユーザー権限を持つグループのメンバーとして、復元するサーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="802d2-108">Log on to the server that you are restoring as a member of the Administrators group on the local computer or a group with equivalent user rights.</span></span>

2.  <span data-ttu-id="802d2-109">SQL Server Management Studio を開きます。 [**スタート**]、[**すべてのプログラム**]、[ **microsoft sql server 2012** ] または [ **microsoft sql server 2008 R2**] をクリックし、[ **sql server management Studio**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="802d2-109">Open SQL Server Management Studio: click **Start**, click **All Programs**, click **Microsoft SQL Server 2012** or **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>

3.  <span data-ttu-id="802d2-110">[**サーバーへの接続**] で、少なくともサーバーの名前と認証情報を入力して SQL Server インスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="802d2-110">In **Connect to Server**, connect to the SQL Server instance by providing at least the name of the server and the authentication information.</span></span>

4.  <span data-ttu-id="802d2-111">[**オブジェクト エクスプローラー**] で、[**データベース**] を右クリックし、[**データベースの復元**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="802d2-111">In **Object Explorer**, right-click **Databases**, and then click **Restore Database**.</span></span>

5.  <span data-ttu-id="802d2-112">[**ページの選択**] で [**全般**] をクリックし、[**復元先データベース**] でデータベース名を次のように選択します。</span><span class="sxs-lookup"><span data-stu-id="802d2-112">Under **Select a page**, click **General**, and then in **To database** select the database name as follows:</span></span>
    
      - <span data-ttu-id="802d2-113">アーカイブデータベースの場合は、[ **Lcslog**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="802d2-113">For an Archiving database, select **LcsLog**.</span></span>
    
      - <span data-ttu-id="802d2-114">通話詳細記録 (CDR) データベースの場合は、[**LcsCDR**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="802d2-114">For a call detail recording (CDR) database, select **LcsCDR**.</span></span>
    
      - <span data-ttu-id="802d2-115">Quality of Experience (QoE) データベースの場合は、[**QoEMetrics**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="802d2-115">For a Quality of Experience (QoE) database, select **QoEMetrics**.</span></span>

6.  <span data-ttu-id="802d2-116">[**復元元デバイス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="802d2-116">Click **From device**.</span></span>

7.  <span data-ttu-id="802d2-117">[**復元するバックアップ セットの選択**] で、バックアップ ファイルをクリックし、[**復元**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="802d2-117">Under **Select the backup sets to restore**, click the backup file, and then click **Restore**.</span></span>

8.  <span data-ttu-id="802d2-118">[**ページの選択**] で、[**オプション**] をクリックし、データ ファイルのパスとログのパスが適切なフォルダー内にあることを確認して、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="802d2-118">Under **Select a page**, click **Options**, verify that the data file path and log path are in the correct folder, and then click **OK**.</span></span>

</div>

<div>

## <a name="to-make-sure-that-access-control-lists-acls-are-correct"></a><span data-ttu-id="802d2-119">アクセス制御リスト (Acl) が正しく設定されていることを確認するには</span><span class="sxs-lookup"><span data-stu-id="802d2-119">To make sure that access control lists (ACLs) are correct</span></span>

1.  <span data-ttu-id="802d2-120">[**データベース**] を展開し、アーカイブ データベースまたは監視データベース、[**セキュリティ**]、[**ユーザー**] の順に展開します。</span><span class="sxs-lookup"><span data-stu-id="802d2-120">Expand **Databases**, expand the archiving or monitoring database, expand **Security**, and then expand **Users**.</span></span>

2.  <span data-ttu-id="802d2-121">ドメイン グループ RTCComponentUniversalServices がユーザーとして存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="802d2-121">Verify that the domain group RTCComponentUniversalServices exists as a user.</span></span>

3.  <span data-ttu-id="802d2-122">RTCComponentUniversalServices が**ユーザー**の下に存在しない場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="802d2-122">If RTCComponentUniversalServices does not exist under **Users**, do the following:</span></span>
    
    1.  <span data-ttu-id="802d2-123">[ **ユーザー**] を右クリックし、[ **新しいユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="802d2-123">Right-click **Users**, and then click **New User**.</span></span>
    
    2.  <span data-ttu-id="802d2-124">[**ログイン名**] に、不足しているグループ名 RTCComponentUniversalServices を入力します。</span><span class="sxs-lookup"><span data-stu-id="802d2-124">In **Login name**, type the missing group name, RTCComponentUniversalServices.</span></span>
    
    3.  <span data-ttu-id="802d2-125">[**データベース ロールのメンバーシップ**] で、[**ServerRole**] アクセス許可を選択し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="802d2-125">Under **Database role membership**, select the **ServerRole** permission, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="802d2-126">アーカイブ サービスまたは監視サービスを再起動する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="802d2-126">You do not need to restart the archiving or monitoring service.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

