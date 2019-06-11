---
title: 'Lync Server 2013: Lync Phone Edition のセキュリティ設定を構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure security settings for Lync Phone Edition
ms:assetid: 6e7cec17-8a79-4428-9300-8821256c46cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521014(v=OCS.15)
ms:contentKeyID: 48184464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7bd44b5d3f466728ac1dbe928c08b1f4786f8fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840332"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-security-settings-for-lync-phone-edition-in-lync-server-2013"></a><span data-ttu-id="0433e-102">Lync Server 2013 で Lync Phone Edition のセキュリティ設定を構成する</span><span class="sxs-lookup"><span data-stu-id="0433e-102">Configure security settings for Lync Phone Edition in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0433e-103">_**最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="0433e-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="0433e-104">SIP セキュリティ設定と電話ロック設定を使用して、Lync Phone Edition を実行しているデバイスのセキュリティを向上させます。</span><span class="sxs-lookup"><span data-stu-id="0433e-104">Help improve the security of devices running Lync Phone Edition via your SIP security setting and phone lock settings.</span></span>

<div>

## <a name="to-configure-security-settings-for-lync-phone-edition"></a><span data-ttu-id="0433e-105">Lync Phone Edition のセキュリティ設定を構成するには</span><span class="sxs-lookup"><span data-stu-id="0433e-105">To configure security settings for Lync Phone Edition</span></span>

1.  <span data-ttu-id="0433e-106">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="0433e-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0433e-107">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="0433e-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0433e-108">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0433e-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0433e-109">左側のナビゲーションバーで、[**クライアント**] をクリックし、[**デバイスの構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0433e-109">In the left navigation bar, click **Clients**, and then click **Device Configuration**.</span></span>

4.  <span data-ttu-id="0433e-110">[**デバイスの構成**] ページのデバイス構成の一覧で、セキュリティ設定を変更する構成をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="0433e-110">On the **Device Configuration** page, in the list of device configurations, double-click the configuration for which you want to change security settings.</span></span>

5.  <span data-ttu-id="0433e-111">[**デバイス構成の編集**] の [ **sip セキュリティ**] で、sip セキュリティレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="0433e-111">In **Edit Device Configuration**, in **SIP security**, specify the SIP security level.</span></span> <span data-ttu-id="0433e-112">既定のレベルは**High**で、これを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0433e-112">The default level is **High**, which we recommend using.</span></span>

6.  <span data-ttu-id="0433e-113">[**デバイス構成の編集**] の [**電話のロック**] で、[デバイスの**ロックを強制**する] チェックボックスをオンまたはオフにします (既定で選択されています)。 PIN の最小の長さ (既定では6文字) とタイムアウト期間 (既定では10分) を指定します。</span><span class="sxs-lookup"><span data-stu-id="0433e-113">In **Edit Device Configuration**, under **Phone Lock**, select or clear the **Enforce device locking** check box (selected by default) and specify the minimum PIN length (6 characters by default) and timeout period (10 minutes by default).</span></span> <span data-ttu-id="0433e-114">既定の設定を使用するか、PIN の長さを大きくするか、またはタイムアウト期間を短くすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0433e-114">We recommend using these defaults or increasing the PIN length and/or decreasing the timeout period.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0433e-115">詳細については、「 <A href="lync-server-2013-enforce-phone-locking.md">Lync Server 2013 で電話のロックを適用</A>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0433e-115">For details, see <A href="lync-server-2013-enforce-phone-locking.md">Enforce phone locking in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="configuring-security-settings-for-lync-phone-edition-phones-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="0433e-116">Windows PowerShell コマンドレットを使用して、Lync Phone Edition Phone のセキュリティ設定を構成する</span><span class="sxs-lookup"><span data-stu-id="0433e-116">Configuring Security Settings for Lync Phone Edition Phones by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="0433e-117">セキュリティ設定を管理するには、Lync Server 管理シェルと**CsUCPhoneConfiguration**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="0433e-117">Security settings can be managed by using Lync Server Management Shell and the **Get-CsUCPhoneConfiguration** cmdlet.</span></span> <span data-ttu-id="0433e-118">このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="0433e-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="0433e-119">リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0433e-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-modify-the-sip-security-mode"></a><span data-ttu-id="0433e-120">SIP セキュリティモードを変更するには</span><span class="sxs-lookup"><span data-stu-id="0433e-120">To modify the SIP security mode</span></span>

  - <span data-ttu-id="0433e-121">このコマンドは、UC 電話設定のグローバルコレクションの SIPSecurityMode を Medium に設定します。</span><span class="sxs-lookup"><span data-stu-id="0433e-121">This command sets the SIPSecurityMode for the global collection of UC phone settings to Medium.</span></span> <span data-ttu-id="0433e-122">SIP セキュリティは、低または高 (既定値) に設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="0433e-122">SIP security could also be set to Low or High (the default value).</span></span>
    
        Set-CsUCPhoneConfiguration -Identity global -SIPSecurityMode "Medium"

</div>

<div>

## <a name="to-modify-the-minimum-pin-length"></a><span data-ttu-id="0433e-123">PIN の最小文字数を変更するには</span><span class="sxs-lookup"><span data-stu-id="0433e-123">To modify the minimum PIN length</span></span>

  - <span data-ttu-id="0433e-124">この例では、すべての UC 携帯電話の設定が変更され、PIN の長さを7桁以上にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0433e-124">In this example, all the UC phone settings are modified to require a minimum PIN length of 7 digits.</span></span>
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -MinPhonePinLength 7

</div>

<span data-ttu-id="0433e-125">詳細については、「 [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0433e-125">For details, see [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0433e-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="0433e-126">See Also</span></span>


[<span data-ttu-id="0433e-127">Lync Server 2013 認証の管理</span><span class="sxs-lookup"><span data-stu-id="0433e-127">Managing Lync Server 2013 authentication</span></span>](lync-server-2013-managing-lync-server-authentication.md)  


[<span data-ttu-id="0433e-128">Lync Server 2013 でのデバイス、電話、クライアント アプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="0433e-128">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

