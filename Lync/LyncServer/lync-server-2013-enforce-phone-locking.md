---
title: 'Lync Server 2013: 電話のロックを適用する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enforce phone locking
ms:assetid: 1f89298b-aea9-4952-93ca-0270b565792b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520963(v=OCS.15)
ms:contentKeyID: 48183594
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4961aabf2edce33f1e5975497844704ac0feae03
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833220"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enforce-phone-locking-in-lync-server-2013"></a><span data-ttu-id="125d9-102">Lync Server 2013 での電話のロックを適用する</span><span class="sxs-lookup"><span data-stu-id="125d9-102">Enforce phone locking in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="125d9-103">_**最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="125d9-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="125d9-104">Lync Phone Edition のデバイスは、セキュリティのためにロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="125d9-104">Lync Phone Edition devices can be locked for security purposes.</span></span> <span data-ttu-id="125d9-105">電話のロックを適用した場合、Lync Phone Edition を実行しているデバイスは、一定の時間が経過した後でロックされます。</span><span class="sxs-lookup"><span data-stu-id="125d9-105">If you enforce phone lock, the device running Lync Phone Edition locks after a period of time that you configure.</span></span> <span data-ttu-id="125d9-106">電話がロックされている場合、ユーザーは電話をかけることはできますが、予定表や連絡先情報、ボイスメール、通話ログにアクセスしたり、検索を使用したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="125d9-106">When a phone is locked, a user can make calls but cannot access calendar and contact information, voice mail, or call logs or use search.</span></span> <span data-ttu-id="125d9-107">電話のロックを解除するために、ユーザーは PIN を入力します。</span><span class="sxs-lookup"><span data-stu-id="125d9-107">To unlock the phone, the user enters a PIN.</span></span>

<span data-ttu-id="125d9-108">電話のロックを適用するには、Lync Server コントロールパネルまたは Lync Server PowerShell コマンドレットを使用して、電話のロックを有効にして構成します。</span><span class="sxs-lookup"><span data-stu-id="125d9-108">To enforce phone lock, enable and configure it by using Lync Server Control Panel or Lync Server PowerShell cmdlets.</span></span> <span data-ttu-id="125d9-109">電話のロックは、グローバルに適用することも、構成されているサイト内でのみ強制することもできます。</span><span class="sxs-lookup"><span data-stu-id="125d9-109">You can enforce phone lock globally or only within the site for which it is configured.</span></span>

<div>

## <a name="to-configure-and-enforce-the-phone-lock"></a><span data-ttu-id="125d9-110">電話のロックを構成して強制するには</span><span class="sxs-lookup"><span data-stu-id="125d9-110">To configure and enforce the phone lock</span></span>

1.  <span data-ttu-id="125d9-111">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="125d9-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="125d9-112">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="125d9-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="125d9-113">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="125d9-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="125d9-114">[**クライアント**] をクリックし、[**デバイスの構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="125d9-114">Click **Clients**, and then click **Device Configuration**.</span></span>

4.  <span data-ttu-id="125d9-115">[**デバイス構成**] タブのデバイス構成の一覧で、電話のロックの設定を変更する構成をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="125d9-115">On the **Device Configuration** tab, in the list of device configurations, double-click the configuration for which you want to change the phone lock settings.</span></span>

5.  <span data-ttu-id="125d9-116">[**デバイス構成の編集**] ダイアログボックスで、[**デバイスのロックを強制**する] チェックボックスがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="125d9-116">In the **Edit Device Configuration** dialog box, verify that the **Enforce device locking** check box is selected.</span></span>

6.  <span data-ttu-id="125d9-117">**Pin の最小の長さ**には、ロック解除ピンに含まれている、または新しい値を指定する必要がある最小桁数の既定値をそのまま使用します。</span><span class="sxs-lookup"><span data-stu-id="125d9-117">In **Minimum PIN length**, accept the default value for the minimum number of digits that the unlock PIN must contain or specify a new value.</span></span> <span data-ttu-id="125d9-118">PIN の長さの範囲は 4 ~ 15 桁で、既定値は6です。</span><span class="sxs-lookup"><span data-stu-id="125d9-118">The range for the PIN length is four to 15 digits, and the default is six.</span></span>

7.  <span data-ttu-id="125d9-119">**電話ロックのタイムアウト**では、電話をロックするか、または新しい値を指定するまでの時間の長さに応じて、既定値をそのまま使用します。</span><span class="sxs-lookup"><span data-stu-id="125d9-119">In **Phone lock time-out**, accept the default value for the minimum length of time before the phone locks itself or specify a new value.</span></span> <span data-ttu-id="125d9-120">タイムアウトの範囲は 0 ~ 60 分で、既定値は10です。</span><span class="sxs-lookup"><span data-stu-id="125d9-120">The range for the timeout is 0 to 60 minutes, and the default is 10.</span></span> <span data-ttu-id="125d9-121">値は、HH:MM:SS の形式で入力してください。</span><span class="sxs-lookup"><span data-stu-id="125d9-121">Enter the value in the format HH:MM:SS.</span></span>

8.  <span data-ttu-id="125d9-122">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="125d9-122">Click **Commit**.</span></span>

</div>

<div>

## <a name="enforcing-phone-locking-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="125d9-123">Windows PowerShell コマンドレットを使用して電話のロックを適用する</span><span class="sxs-lookup"><span data-stu-id="125d9-123">Enforcing Phone Locking by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="125d9-124">電話のロックを適用するには、CsUCPhoneConfiguration コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="125d9-124">Phone locking can be enforced by using the Set-CsUCPhoneConfiguration cmdlet.</span></span> <span data-ttu-id="125d9-125">このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="125d9-125">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="125d9-126">リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="125d9-126">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-phone-locking"></a><span data-ttu-id="125d9-127">電話のロックを有効にするには</span><span class="sxs-lookup"><span data-stu-id="125d9-127">To enable phone locking</span></span>

  - <span data-ttu-id="125d9-128">次のコマンドは、Redmond サイトの電話のロックを有効にします。</span><span class="sxs-lookup"><span data-stu-id="125d9-128">The following command enables phone locking for the Redmond site.</span></span> <span data-ttu-id="125d9-129">電話のロックを無効にするには、EnforcePhoneLock プロパティを False ($False) に設定します。</span><span class="sxs-lookup"><span data-stu-id="125d9-129">To disable phone locking, set the EnforcePhoneLock property to False ($False).</span></span>
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-enable-phone-locking-and-modify-the-phone-lock-timeout"></a><span data-ttu-id="125d9-130">電話のロックを有効にし、電話のロックタイムアウトを変更するには</span><span class="sxs-lookup"><span data-stu-id="125d9-130">To enable phone locking and modify the phone lock timeout</span></span>

  - <span data-ttu-id="125d9-131">このコマンドにより、電話のロックが有効になり、電話のロックタイムアウトも30分に設定されます。</span><span class="sxs-lookup"><span data-stu-id="125d9-131">This command enables phone locking and also sets the phone lock timeout to 30 minutes.</span></span>
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True -PhoneLockTimeout "00:30:00"

</div>

<div>

## <a name="to-enable-phone-locking-throughout-the-organization"></a><span data-ttu-id="125d9-132">組織全体で電話のロックを有効にするには</span><span class="sxs-lookup"><span data-stu-id="125d9-132">To enable phone locking throughout the organization</span></span>

  - <span data-ttu-id="125d9-133">この例では、組織で使用されているすべての UC 電話構成設定で電話のロックが有効になっています。</span><span class="sxs-lookup"><span data-stu-id="125d9-133">In this example, phone locking is enabled on all the UC phone configuration settings in use in the organization.</span></span>
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration  -EnforcePhoneLock $True

</div>

<span data-ttu-id="125d9-134">詳細については、 [CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsUCPhoneConfiguration)コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="125d9-134">For more information, see the help topic for the [Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsUCPhoneConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="125d9-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="125d9-135">See Also</span></span>


[<span data-ttu-id="125d9-136">Lync Server 2013 認証の管理</span><span class="sxs-lookup"><span data-stu-id="125d9-136">Managing Lync Server 2013 authentication</span></span>](lync-server-2013-managing-lync-server-authentication.md)  


[<span data-ttu-id="125d9-137">Lync Server 2013 でのデバイス、電話、クライアント アプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="125d9-137">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

