---
title: 'Lync Server 2013: ユーザーを Lync Online に移動する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Move users to Lync Online
ms:assetid: 6a523c86-2eac-4fa4-973a-4406872c9a7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204969(v=OCS.15)
ms:contentKeyID: 48184392
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6172c526816a3572d6c364b714d5d4e7e5323cac
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991372"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-users-to-lync-online-in-lync-server-2013"></a><span data-ttu-id="7c87b-102">Lync Server 2013 でユーザーを Lync Online に移動する</span><span class="sxs-lookup"><span data-stu-id="7c87b-102">Move users to Lync Online in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c87b-103">_**最終更新日:** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="7c87b-103">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="7c87b-104">Lync Online へのユーザーの移行を開始する前に、移動するアカウントに関連付けられたユーザーデータをバックアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c87b-104">Before you start migrating users to Lync Online, you should backup the user data associated with the accounts to be moved.</span></span> <span data-ttu-id="7c87b-105">ユーザー アカウントと共にすべてのユーザー データが移動されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="7c87b-105">Not all user data is moved with the user account.</span></span> <span data-ttu-id="7c87b-106">詳細については、「 [Lync Server 2013: データのバックアップと復元の要件](lync-server-2013-backup-and-restoration-requirements-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c87b-106">For information, see [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md).</span></span>

<div>

## <a name="migrate-user-settings-to-lync-online"></a><span data-ttu-id="7c87b-107">ユーザー設定を Lync Online に移行する</span><span class="sxs-lookup"><span data-stu-id="7c87b-107">Migrate User Settings to Lync Online</span></span>

<span data-ttu-id="7c87b-108">ユーザー設定は、ユーザー アカウントと共に移動されます。</span><span class="sxs-lookup"><span data-stu-id="7c87b-108">User settings are moved with the user account.</span></span> <span data-ttu-id="7c87b-109">いくつかのオンプレミス設定は、ユーザー アカウントと共に移動されることはありません。</span><span class="sxs-lookup"><span data-stu-id="7c87b-109">Some on-premises settings are not moved with the user account.</span></span>

</div>

<div>

## <a name="moving-pilot-users-to-lync-online"></a><span data-ttu-id="7c87b-110">パイロットユーザーを Lync Online に移動する</span><span class="sxs-lookup"><span data-stu-id="7c87b-110">Moving Pilot Users to Lync Online</span></span>

<span data-ttu-id="7c87b-111">ユーザーを Lync Online に移行する前に、いくつかのパイロットユーザーを移動して、環境が正しく構成されていることを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7c87b-111">Before you begin to move users to Lync Online, you may want to move a few pilot users to confirm that your environment is correctly configured.</span></span> <span data-ttu-id="7c87b-112">追加のユーザーを移行する前に、Lync 機能とサービスが期待どおりに機能することを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="7c87b-112">You can then verify that Lync features and services function as expected before attempting to move additional users.</span></span>

<span data-ttu-id="7c87b-113">オンプレミスのユーザーを Lync Online テナントに移動するには、Microsoft Office 365 テナントの管理者資格情報を使用して、Lync Server 管理シェルで次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="7c87b-113">To move an on-premises user to your Lync Online tenant, run the following cmdlets in the Lync Server Management Shell, using the administrator credentials for your Microsoft Office 365 tenant.</span></span> <span data-ttu-id="7c87b-114">"username@contoso.com" を、移動するユーザーの情報で置換します。</span><span class="sxs-lookup"><span data-stu-id="7c87b-114">Replace "username@contoso.com" with the information for the user that you want to move.</span></span>

   ```PowerShell
    $creds=Get-Credential
   ```

   ```PowerShell
    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
   ```

<span data-ttu-id="7c87b-115">**HostedMigrationOverrideUrl**パラメーターに指定する url の形式は、次の形式で、ホステッド移行サービスが実行されているプールへの url である必要\<があり\>ます。 Https://pool FQDN/HostedMigration/hostedmigrationService.svc.</span><span class="sxs-lookup"><span data-stu-id="7c87b-115">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc.</span></span>

<span data-ttu-id="7c87b-116">ホスティング型移行サービスへの URL は、ご使用の Office 365 テナント アカウント用の Lync Online コントロール パネルの URL を表示することで確認できます。</span><span class="sxs-lookup"><span data-stu-id="7c87b-116">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.</span></span>

<span data-ttu-id="7c87b-117">**Office 365 テナントのホスティング型移行サービスの URL を確認するには**</span><span class="sxs-lookup"><span data-stu-id="7c87b-117">**To determine the Hosted Migration Service URL for your Office 365 tenant**</span></span>

1.  <span data-ttu-id="7c87b-118">管理者として Office 365 テナントにログインします。</span><span class="sxs-lookup"><span data-stu-id="7c87b-118">Login to your Office 365 tenant as an administrator.</span></span>

2.  <span data-ttu-id="7c87b-119">**Lync 管理センター**を開きます。</span><span class="sxs-lookup"><span data-stu-id="7c87b-119">Open the **Lync admin center**.</span></span>

3.  <span data-ttu-id="7c87b-120">**Lync 管理センター**が表示されたら、アドレスバーの URL を選択して**lync.com**にコピーします。</span><span class="sxs-lookup"><span data-stu-id="7c87b-120">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="7c87b-121">URL は、次のような書式です。</span><span class="sxs-lookup"><span data-stu-id="7c87b-121">An example URL looks similar to the following:</span></span>
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  <span data-ttu-id="7c87b-122">URL の **webdir** を **admin** に置き換えると、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="7c87b-122">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
    
    `https://admin0a.online.lync.com`

5.  <span data-ttu-id="7c87b-123">URL に以下の文字列を付加します。**/HostedMigration/hostedmigrationservice.svc**</span><span class="sxs-lookup"><span data-stu-id="7c87b-123">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
    
    <span data-ttu-id="7c87b-124">以上の手順によって、**HostedMigrationOverrideUrl** の値を持った URL は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="7c87b-124">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

<div>

## <a name="moving-users-to-lync-online"></a><span data-ttu-id="7c87b-125">ユーザーを Lync Online に移動する</span><span class="sxs-lookup"><span data-stu-id="7c87b-125">Moving Users to Lync Online</span></span>

<span data-ttu-id="7c87b-126">複数のユーザーを移動するには[、–](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) Filter パラメーターを指定して RegistrarPool のユーザーアカウントに割り当てられている特定のプロパティを持つユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="7c87b-126">You can move multiple users by using the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet with the –Filter parameter to select the users with a specific property assigned to the user accounts, such as RegistrarPool.</span></span> <span data-ttu-id="7c87b-127">次の例に示すように、返されたユーザーを[移動-csuser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)コマンドレットにパイプします。</span><span class="sxs-lookup"><span data-stu-id="7c87b-127">You can then pipe the returned users to the [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) cmdlet, as shown in the following example.</span></span>

    Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>

<span data-ttu-id="7c87b-128">また、以下のサンプルに示すように、-OU パラメーターを使用して、指定した OU 内のすべてのユーザーを取得できます。</span><span class="sxs-lookup"><span data-stu-id="7c87b-128">You can also use the –OU parameter to retrieve all users in the specified OU, as shown in the following example.</span></span>

    Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds -HostedMigrationOverrideUrl <URL>

</div>

<div>

## <a name="verify-lync-online-user-settings-and-features"></a><span data-ttu-id="7c87b-129">Lync Online のユーザー設定と機能を確認する</span><span class="sxs-lookup"><span data-stu-id="7c87b-129">Verify Lync Online User Settings and Features</span></span>

<span data-ttu-id="7c87b-130">ユーザーの移動が正常に完了したことは、次の方法で確認できます。</span><span class="sxs-lookup"><span data-stu-id="7c87b-130">You can verify that the user was moved successfully in the following ways:</span></span>

  - <span data-ttu-id="7c87b-131">Lync Online のコントロールパネルでユーザーの状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="7c87b-131">View the status of the user in the Lync Online Control Panel.</span></span> <span data-ttu-id="7c87b-132">オンプレミス ユーザーとオンライン ユーザーでは視覚的なインジケーターが異なります。</span><span class="sxs-lookup"><span data-stu-id="7c87b-132">The visual indicator for on-premises users and online users is different.</span></span>

  - <span data-ttu-id="7c87b-133">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="7c87b-133">Run the following cmdlet:</span></span>
    
        Get-CsUser -Identity

</div>

</div>

<span> </span>

</div>

</div>

</div>

