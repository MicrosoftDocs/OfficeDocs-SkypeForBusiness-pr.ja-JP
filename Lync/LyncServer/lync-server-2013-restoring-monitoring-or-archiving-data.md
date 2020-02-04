---
title: 'Lync Server 2013: 監視またはアーカイブデータを復元する'
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
ms.openlocfilehash: 9621fe3c1905dbd34fd3b4da39b2562c608d6355
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733167"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-monitoring-or-archiving-data-in-lync-server-2013"></a><span data-ttu-id="3d713-102">Lync Server 2013 での監視またはアーカイブデータの復元</span><span class="sxs-lookup"><span data-stu-id="3d713-102">Restoring monitoring or archiving data in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d713-103">_**最終更新日:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="3d713-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="3d713-104">障害が発生した後に Lync Server を起動して実行するために、データの監視とアーカイブを復元する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3d713-104">Restoring monitoring and archiving data is not required to get Lync Server up and running after a failure.</span></span> <span data-ttu-id="3d713-105">ただし、データの監視とアーカイブが組織にとって重要である場合は、データベースを再作成した後でデータを復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d713-105">However, if monitoring and archiving data is critical to your organization, you will want to restore the data after you re-create the databases.</span></span>

<span data-ttu-id="3d713-106">次の手順では、SQL Server Management Studio を使用して、アーカイブまたはモニタリングデータを復元する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3d713-106">The following procedure describes how to use SQL Server Management Studio to restore archiving or monitoring data.</span></span>

<div>

## <a name="to-restore-monitoring-or-archiving-data-from-a-backup-file"></a><span data-ttu-id="3d713-107">バックアップファイルからのデータの監視またはアーカイブを復元するには</span><span class="sxs-lookup"><span data-stu-id="3d713-107">To restore monitoring or archiving data from a backup file</span></span>

1.  <span data-ttu-id="3d713-108">ローカルコンピューターの管理者グループのメンバー、または同等のユーザー権限を持つグループとして、復元するサーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="3d713-108">Log on to the server that you are restoring as a member of the Administrators group on the local computer or a group with equivalent user rights.</span></span>

2.  <span data-ttu-id="3d713-109">SQL Server Management Studio を開きます。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **microsoft sql server 2012** ]、または [ **microsoft sql server 2008 R2**] をクリックして、[ **sql server management studio**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3d713-109">Open SQL Server Management Studio: click **Start**, click **All Programs**, click **Microsoft SQL Server 2012** or **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>

3.  <span data-ttu-id="3d713-110">[**サーバーへの接続**] で、少なくともサーバーの名前と認証情報を指定して、SQL Server インスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="3d713-110">In **Connect to Server**, connect to the SQL Server instance by providing at least the name of the server and the authentication information.</span></span>

4.  <span data-ttu-id="3d713-111">**オブジェクトエクスプローラー**で、[**データベース**] を右クリックし、[**データベースの復元**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3d713-111">In **Object Explorer**, right-click **Databases**, and then click **Restore Database**.</span></span>

5.  <span data-ttu-id="3d713-112">[**ページの選択**] の [**全般**] をクリックし、[**データベース**] でデータベース名を次のように選択します。</span><span class="sxs-lookup"><span data-stu-id="3d713-112">Under **Select a page**, click **General**, and then in **To database** select the database name as follows:</span></span>
    
      - <span data-ttu-id="3d713-113">アーカイブデータベースの場合は、 **Lcslog**を選択します。</span><span class="sxs-lookup"><span data-stu-id="3d713-113">For an Archiving database, select **LcsLog**.</span></span>
    
      - <span data-ttu-id="3d713-114">通話の詳細記録 (CDR) データベースの場合は、[ **Lcscdr**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="3d713-114">For a call detail recording (CDR) database, select **LcsCDR**.</span></span>
    
      - <span data-ttu-id="3d713-115">Quality of Experience (QoE) データベースの場合は、[ **QoEMetrics**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="3d713-115">For a Quality of Experience (QoE) database, select **QoEMetrics**.</span></span>

6.  <span data-ttu-id="3d713-116">[**デバイスから] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="3d713-116">Click **From device**.</span></span>

7.  <span data-ttu-id="3d713-117">[**復元するバックアップセットの選択**] でバックアップファイルをクリックし、[**復元**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3d713-117">Under **Select the backup sets to restore**, click the backup file, and then click **Restore**.</span></span>

8.  <span data-ttu-id="3d713-118">[**ページの選択**] の [**オプション**] をクリックし、データファイルのパスとログのパスが正しいフォルダーにあることを確認して、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3d713-118">Under **Select a page**, click **Options**, verify that the data file path and log path are in the correct folder, and then click **OK**.</span></span>

</div>

<div>

## <a name="to-make-sure-that-access-control-lists-acls-are-correct"></a><span data-ttu-id="3d713-119">アクセス制御リスト (Acl) が正しく設定されていることを確認するには</span><span class="sxs-lookup"><span data-stu-id="3d713-119">To make sure that access control lists (ACLs) are correct</span></span>

1.  <span data-ttu-id="3d713-120">[**データベース**] を展開し、[アーカイブ] または [監視] データベースを展開し、[**セキュリティ**] を展開して、[**ユーザー**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="3d713-120">Expand **Databases**, expand the archiving or monitoring database, expand **Security**, and then expand **Users**.</span></span>

2.  <span data-ttu-id="3d713-121">ドメイングループ RTCComponentUniversalServices がユーザーとして存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="3d713-121">Verify that the domain group RTCComponentUniversalServices exists as a user.</span></span>

3.  <span data-ttu-id="3d713-122">[**ユーザー**] の下に RTCComponentUniversalServices が存在しない場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3d713-122">If RTCComponentUniversalServices does not exist under **Users**, do the following:</span></span>
    
    1.  <span data-ttu-id="3d713-123">[**ユーザー**] を右クリックし、[**新しいユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3d713-123">Right-click **Users**, and then click **New User**.</span></span>
    
    2.  <span data-ttu-id="3d713-124">[ **Login name**] に、不足しているグループ名 RTCComponentUniversalServices を入力します。</span><span class="sxs-lookup"><span data-stu-id="3d713-124">In **Login name**, type the missing group name, RTCComponentUniversalServices.</span></span>
    
    3.  <span data-ttu-id="3d713-125">[**データベースロールメンバーシップ**] で、[ **ServerRole** ] 権限を選び、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3d713-125">Under **Database role membership**, select the **ServerRole** permission, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3d713-126">アーカイブまたは監視サービスを再起動する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3d713-126">You do not need to restart the archiving or monitoring service.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

