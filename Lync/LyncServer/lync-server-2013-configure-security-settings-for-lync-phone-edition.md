---
title: 'Lync Server 2013: Lync Phone Edition のセキュリティ設定を構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure security settings for Lync Phone Edition
ms:assetid: 6e7cec17-8a79-4428-9300-8821256c46cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521014(v=OCS.15)
ms:contentKeyID: 48184464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68fad5a47f8b56bd97386dcab49aef9671c6f99e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035229"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-security-settings-for-lync-phone-edition-in-lync-server-2013"></a><span data-ttu-id="84bdb-102">Lync Server 2013 で Lync Phone Edition のセキュリティ設定を構成する</span><span class="sxs-lookup"><span data-stu-id="84bdb-102">Configure security settings for Lync Phone Edition in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84bdb-103">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="84bdb-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="84bdb-104">SIP セキュリティ設定および電話ロック設定を使用して、Lync Phone Edition を実行しているデバイスのセキュリティを強化する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="84bdb-104">Help improve the security of devices running Lync Phone Edition via your SIP security setting and phone lock settings.</span></span>

<div>

## <a name="to-configure-security-settings-for-lync-phone-edition"></a><span data-ttu-id="84bdb-105">Lync Phone Edition のセキュリティ設定を構成するには</span><span class="sxs-lookup"><span data-stu-id="84bdb-105">To configure security settings for Lync Phone Edition</span></span>

1.  <span data-ttu-id="84bdb-106">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="84bdb-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="84bdb-107">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="84bdb-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="84bdb-108">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84bdb-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="84bdb-109">左側のナビゲーション バーで [**クライアント**] をクリックし、[**デバイス構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="84bdb-109">In the left navigation bar, click **Clients**, and then click **Device Configuration**.</span></span>

4.  <span data-ttu-id="84bdb-110">[**デバイス構成**] ページのデバイス構成の一覧で、セキュリティ設定を変更する構成をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="84bdb-110">On the **Device Configuration** page, in the list of device configurations, double-click the configuration for which you want to change security settings.</span></span>

5.  <span data-ttu-id="84bdb-p102">[**デバイス構成の編集**] の [**SIP セキュリティ**] で、SIP セキュリティ レベルを指定します。既定のレベルは [**高**] (推奨される設定) です。</span><span class="sxs-lookup"><span data-stu-id="84bdb-p102">In **Edit Device Configuration**, in **SIP security**, specify the SIP security level. The default level is **High**, which we recommend using.</span></span>

6.  <span data-ttu-id="84bdb-p103">[**デバイス構成の編集**] の [**電話のロック**] で、[**デバイス ロックの適用**] チェック ボックス (既定ではオン) をオンまたはオフにして、PIN の最小桁数 (既定では 6 桁) とタイムアウト期間 (既定では 10 分) を指定します。これらの既定値を使用するか、または PIN の桁数を大きくするかタイムアウト期間を小さくする (あるいはその両方を行う) ことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="84bdb-p103">In **Edit Device Configuration**, under **Phone Lock**, select or clear the **Enforce device locking** check box (selected by default) and specify the minimum PIN length (6 characters by default) and timeout period (10 minutes by default). We recommend using these defaults or increasing the PIN length and/or decreasing the timeout period.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="84bdb-115">詳細については、「 <A href="lync-server-2013-enforce-phone-locking.md">Lync Server 2013 での電話ロックの強制</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84bdb-115">For details, see <A href="lync-server-2013-enforce-phone-locking.md">Enforce phone locking in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="configuring-security-settings-for-lync-phone-edition-phones-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="84bdb-116">Windows PowerShell コマンドレットを使用して Lync Phone Edition 電話のセキュリティ設定を構成する</span><span class="sxs-lookup"><span data-stu-id="84bdb-116">Configuring Security Settings for Lync Phone Edition Phones by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="84bdb-117">セキュリティ設定は、Lync Server 管理シェルと**get-csucphoneconfiguration**コマンドレットを使用して管理できます。</span><span class="sxs-lookup"><span data-stu-id="84bdb-117">Security settings can be managed by using Lync Server Management Shell and the **Get-CsUCPhoneConfiguration** cmdlet.</span></span> <span data-ttu-id="84bdb-118">このコマンドレットは、Lync Server 2013 管理シェルから実行するか、Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="84bdb-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="84bdb-119">リモート Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Microsoft Lync Server 2010 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)を使用したリモート PowerShell の管理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84bdb-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-modify-the-sip-security-mode"></a><span data-ttu-id="84bdb-120">SIP セキュリティ モードを変更するには</span><span class="sxs-lookup"><span data-stu-id="84bdb-120">To modify the SIP security mode</span></span>

  - <span data-ttu-id="84bdb-p105">次のコマンドでは、UC 電話設定のグローバル コレクションの SIPSecurityMode を Medium に設定します。SIP セキュリティは、Low または High (既定値) に設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="84bdb-p105">This command sets the SIPSecurityMode for the global collection of UC phone settings to Medium. SIP security could also be set to Low or High (the default value).</span></span>
    
        Set-CsUCPhoneConfiguration -Identity global -SIPSecurityMode "Medium"

</div>

<div>

## <a name="to-modify-the-minimum-pin-length"></a><span data-ttu-id="84bdb-123">PIN の最小桁数を変更するには</span><span class="sxs-lookup"><span data-stu-id="84bdb-123">To modify the minimum PIN length</span></span>

  - <span data-ttu-id="84bdb-124">次の例では、すべての UC 電話設定で必要とされる PIN の最小桁数を 7 桁に変更します。</span><span class="sxs-lookup"><span data-stu-id="84bdb-124">In this example, all the UC phone settings are modified to require a minimum PIN length of 7 digits.</span></span>
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -MinPhonePinLength 7

</div>

<span data-ttu-id="84bdb-125">詳細については、「 [get-csucphoneconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84bdb-125">For details, see [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="84bdb-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="84bdb-126">See Also</span></span>


[<span data-ttu-id="84bdb-127">Lync Server 2013 認証の管理</span><span class="sxs-lookup"><span data-stu-id="84bdb-127">Managing Lync Server 2013 authentication</span></span>](lync-server-2013-managing-lync-server-authentication.md)  


[<span data-ttu-id="84bdb-128">Lync Server 2013 でのデバイス、電話、クライアントアプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="84bdb-128">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

