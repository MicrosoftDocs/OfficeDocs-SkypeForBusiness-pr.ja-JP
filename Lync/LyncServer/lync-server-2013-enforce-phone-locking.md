---
title: 'Lync Server 2013: 電話ロックの適用'
description: 'Lync Server 2013: 電話ロックを適用します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enforce phone locking
ms:assetid: 1f89298b-aea9-4952-93ca-0270b565792b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520963(v=OCS.15)
ms:contentKeyID: 48183594
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5afae4fa27edf9378bacc39a29697c9607b25c07
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575603"
---
# <a name="enforce-phone-locking-in-lync-server-2013"></a><span data-ttu-id="43837-103">Lync Server 2013 での電話ロックの適用</span><span class="sxs-lookup"><span data-stu-id="43837-103">Enforce phone locking in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43837-104">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="43837-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="43837-105">Lync Phone Edition デバイスは、セキュリティを確保する目的でロックできます。</span><span class="sxs-lookup"><span data-stu-id="43837-105">Lync Phone Edition devices can be locked for security purposes.</span></span> <span data-ttu-id="43837-106">電話ロックを強制すると、構成した時間が経過した後、Lync Phone Edition を実行しているデバイスがロックされます。</span><span class="sxs-lookup"><span data-stu-id="43837-106">If you enforce phone lock, the device running Lync Phone Edition locks after a period of time that you configure.</span></span> <span data-ttu-id="43837-107">電話がロックされている場合、ユーザーは電話をかけることはできますが、予定表および連絡先情報、ボイスメール、または通話ログにアクセスすることはできません。また、検索を使用することもできません</span><span class="sxs-lookup"><span data-stu-id="43837-107">When a phone is locked, a user can make calls but cannot access calendar and contact information, voice mail, or call logs or use search.</span></span> <span data-ttu-id="43837-108">電話のロックを解除するために、ユーザーは PIN を入力します。</span><span class="sxs-lookup"><span data-stu-id="43837-108">To unlock the phone, the user enters a PIN.</span></span>

<span data-ttu-id="43837-109">電話ロックを強制するには、Lync Server コントロールパネルまたは Lync Server PowerShell コマンドレットを使用して、電話ロックを有効にし、構成します。</span><span class="sxs-lookup"><span data-stu-id="43837-109">To enforce phone lock, enable and configure it by using Lync Server Control Panel or Lync Server PowerShell cmdlets.</span></span> <span data-ttu-id="43837-110">電話のロックは、グローバルに、または構成されているサイト内でのみ強制できます。</span><span class="sxs-lookup"><span data-stu-id="43837-110">You can enforce phone lock globally or only within the site for which it is configured.</span></span>

<div>

## <a name="to-configure-and-enforce-the-phone-lock"></a><span data-ttu-id="43837-111">電話ロックを構成および強制するには</span><span class="sxs-lookup"><span data-stu-id="43837-111">To configure and enforce the phone lock</span></span>

1.  <span data-ttu-id="43837-112">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="43837-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="43837-113">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="43837-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="43837-114">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43837-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="43837-115">[**クライアント**] をクリックして、[**デバイス構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="43837-115">Click **Clients**, and then click **Device Configuration**.</span></span>

4.  <span data-ttu-id="43837-116">[**デバイス構成**] タブのデバイス構成のリストで、電話ロックの設定値を変更する構成をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="43837-116">On the **Device Configuration** tab, in the list of device configurations, double-click the configuration for which you want to change the phone lock settings.</span></span>

5.  <span data-ttu-id="43837-117">[**デバイス構成の編集**] ダイアログ ボックスで、[**デバイス ロックを適用する**] チェック ボックスがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="43837-117">In the **Edit Device Configuration** dialog box, verify that the **Enforce device locking** check box is selected.</span></span>

6.  <span data-ttu-id="43837-118">[ **Pin の最小の長さ**] で、ロックを解除する pin に含める必要がある最小桁数または新しい値を指定する既定値をそのまま使用します。</span><span class="sxs-lookup"><span data-stu-id="43837-118">In **Minimum PIN length**, accept the default value for the minimum number of digits that the unlock PIN must contain or specify a new value.</span></span> <span data-ttu-id="43837-119">PIN の長さの範囲は 4 ~ 15 桁で、既定値は6です。</span><span class="sxs-lookup"><span data-stu-id="43837-119">The range for the PIN length is four to 15 digits, and the default is six.</span></span>

7.  <span data-ttu-id="43837-120">[ **電話のロック**タイムアウト] で、電話が自分にロックされるまでの最短時間の既定値をそのまま使用するか、または新しい値を指定します。</span><span class="sxs-lookup"><span data-stu-id="43837-120">In **Phone lock time-out**, accept the default value for the minimum length of time before the phone locks itself or specify a new value.</span></span> <span data-ttu-id="43837-121">タイムアウトの範囲は 0 ~ 60 分で、既定値は10です。</span><span class="sxs-lookup"><span data-stu-id="43837-121">The range for the timeout is 0 to 60 minutes, and the default is 10.</span></span> <span data-ttu-id="43837-122">値は、HH:MM:SS の形式で入力してください。</span><span class="sxs-lookup"><span data-stu-id="43837-122">Enter the value in the format HH:MM:SS.</span></span>

8.  <span data-ttu-id="43837-123">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="43837-123">Click **Commit**.</span></span>

</div>

<div>

## <a name="enforcing-phone-locking-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="43837-124">Windows PowerShell コマンドレットを使用して電話ロックを強制する</span><span class="sxs-lookup"><span data-stu-id="43837-124">Enforcing Phone Locking by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="43837-125">Set-CsUCPhoneConfiguration コマンドレットを使用して、電話のロックを適用できます。</span><span class="sxs-lookup"><span data-stu-id="43837-125">Phone locking can be enforced by using the Set-CsUCPhoneConfiguration cmdlet.</span></span> <span data-ttu-id="43837-126">このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="43837-126">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="43837-127">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="43837-127">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-phone-locking"></a><span data-ttu-id="43837-128">電話ロックを有効にするには</span><span class="sxs-lookup"><span data-stu-id="43837-128">To enable phone locking</span></span>

  - <span data-ttu-id="43837-129">次のコマンドは、Redmond サイトの電話ロックを有効にします。</span><span class="sxs-lookup"><span data-stu-id="43837-129">The following command enables phone locking for the Redmond site.</span></span> <span data-ttu-id="43837-130">電話ロックを無効にするには、EnforcePhoneLock プロパティを False ($False) に設定します。</span><span class="sxs-lookup"><span data-stu-id="43837-130">To disable phone locking, set the EnforcePhoneLock property to False ($False).</span></span>
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-enable-phone-locking-and-modify-the-phone-lock-timeout"></a><span data-ttu-id="43837-131">電話のロックを有効にし、電話ロックのタイムアウトを変更するには</span><span class="sxs-lookup"><span data-stu-id="43837-131">To enable phone locking and modify the phone lock timeout</span></span>

  - <span data-ttu-id="43837-132">次のコマンドは、電話ロックを有効にして、電話ロックのタイムアウトを 30 分に設定します。</span><span class="sxs-lookup"><span data-stu-id="43837-132">This command enables phone locking and also sets the phone lock timeout to 30 minutes.</span></span>
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True -PhoneLockTimeout "00:30:00"

</div>

<div>

## <a name="to-enable-phone-locking-throughout-the-organization"></a><span data-ttu-id="43837-133">組織全体での電話ロックを有効にするには</span><span class="sxs-lookup"><span data-stu-id="43837-133">To enable phone locking throughout the organization</span></span>

  - <span data-ttu-id="43837-134">次の例では、組織で使用されているすべての UC 電話構成設定で、電話ロックが有効になります。</span><span class="sxs-lookup"><span data-stu-id="43837-134">In this example, phone locking is enabled on all the UC phone configuration settings in use in the organization.</span></span>
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration  -EnforcePhoneLock $True

</div>

<span data-ttu-id="43837-135">詳細については、 [get-csucphoneconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsUCPhoneConfiguration) コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="43837-135">For more information, see the help topic for the [Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsUCPhoneConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="43837-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="43837-136">See Also</span></span>


[<span data-ttu-id="43837-137">Lync Server 2013 認証の管理</span><span class="sxs-lookup"><span data-stu-id="43837-137">Managing Lync Server 2013 authentication</span></span>](lync-server-2013-managing-lync-server-authentication.md)  


[<span data-ttu-id="43837-138">Lync Server 2013 でのデバイス、電話、クライアントアプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="43837-138">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

