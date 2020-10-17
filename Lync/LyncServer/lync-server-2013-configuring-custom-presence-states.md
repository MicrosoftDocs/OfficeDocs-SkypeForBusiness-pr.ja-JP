---
title: 'Lync Server 2013: カスタムプレゼンス状態の構成'
description: 'Lync Server 2013: カスタムプレゼンス状態の構成。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring custom presence states
ms:assetid: e17364a8-8b93-45fc-a614-c80e45435d42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398997(v=OCS.15)
ms:contentKeyID: 48185534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28b277f096ff17ffa63615468ac9b4f21dead68e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557973"
---
# <a name="configuring-custom-presence-states-in-lync-server-2013"></a><span data-ttu-id="b7882-103">Lync Server 2013 でのカスタムプレゼンス状態の構成</span><span class="sxs-lookup"><span data-stu-id="b7882-103">Configuring custom presence states in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7882-104">_**トピックの最終更新日:** 2013-01-10_</span><span class="sxs-lookup"><span data-stu-id="b7882-104">_**Topic Last Modified:** 2013-01-10_</span></span>

<span data-ttu-id="b7882-105">Lync 2013 でカスタムプレゼンス状態を定義するには、XML カスタムプレゼンス構成ファイルを作成し、Lync Server 管理 **シェルコマンドレット** を使用してその場所を指定する **か、** またはパラメーター customstateurl を使用して、その場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="b7882-105">To define custom presence states in Lync 2013, create an XML custom presence configuration file, and then specify its location by using the Lync Server Management Shell cmdlets **New-CSClientPolicy** or **Set-CSClientPolicy** with the parameter CustomStateURL.</span></span>

<span data-ttu-id="b7882-106">構成ファイルには、次のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="b7882-106">Configuration files have the following properties:</span></span>

  - <span data-ttu-id="b7882-107">カスタムプレゼンス状態は、[利用可能]、[取り込み中]、[応答不可] のプレゼンスインジケーターで構成できます。</span><span class="sxs-lookup"><span data-stu-id="b7882-107">Custom presence states can be configured with the Available, Busy, and Do Not Disturb presence indicators.</span></span>

  - <span data-ttu-id="b7882-108">Availability 属性は、カスタム状態の状態テキストに関連付けられているプレゼンスインジケーターを決定します。</span><span class="sxs-lookup"><span data-stu-id="b7882-108">The availability attribute determines which presence indicator is associated with the status text of the custom state.</span></span> <span data-ttu-id="b7882-109">このトピックの後半の例では、自宅から作業中の状態テキストが緑の (利用可能な) プレゼンスインジケーターの右側に表示されます。</span><span class="sxs-lookup"><span data-stu-id="b7882-109">In the example later in this topic, the status text Working from Home is displayed to the right of the green (Available) presence indicator.</span></span>

  - <span data-ttu-id="b7882-110">状態テキストの最大長は64文字です。</span><span class="sxs-lookup"><span data-stu-id="b7882-110">The maximum length of the status text is 64 characters.</span></span>

  - <span data-ttu-id="b7882-111">最大4つのカスタムプレゼンス状態を追加できます。</span><span class="sxs-lookup"><span data-stu-id="b7882-111">A maximum of four custom presence states can be added.</span></span>

  - <span data-ttu-id="b7882-112">CustomStateURL パラメーターは、構成ファイルの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="b7882-112">The CustomStateURL parameter specifies the location of the configuration file.</span></span> <span data-ttu-id="b7882-113">Lync 2013 では、SIP 高セキュリティモードが既定で有効になっているので、HTTPS が有効になっている web サーバーにカスタムプレゼンス構成ファイルを格納する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7882-113">In Lync 2013, SIP high security mode is enabled by default, so you will need to store the custom presence configuration file on a web server that has HTTPS enabled.</span></span> <span data-ttu-id="b7882-114">それ以外の場合、Lync 2013 クライアントは接続できなくなります。</span><span class="sxs-lookup"><span data-stu-id="b7882-114">Otherwise, Lync 2013 clients will be unable to connect to it.</span></span> <span data-ttu-id="b7882-115">たとえば、有効なアドレスはになり `https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml` ます。</span><span class="sxs-lookup"><span data-stu-id="b7882-115">For example, a valid address would be `https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml`.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b7882-116">運用環境では推奨されていませんが、EnableSIPHighSecurityMode レジストリ設定を使用してクライアントの SIP 高セキュリティモードを無効にすることにより、HTTPS 以外のファイル共有にある構成ファイルをテストできます。</span><span class="sxs-lookup"><span data-stu-id="b7882-116">Although it is not recommended in a production environment, you can test a configuration file that is located on a non-HTTPS file share by using the EnableSIPHighSecurityMode registry setting to disable SIP high security mode on the client.</span></span> <span data-ttu-id="b7882-117">その後、CustomStateURL レジストリ設定を使用して、構成ファイルの HTTPS 以外の場所を指定できます。</span><span class="sxs-lookup"><span data-stu-id="b7882-117">Then you can use the CustomStateURL registry setting to specify a non-HTTPS location for the configuration file.</span></span> <span data-ttu-id="b7882-118">Lync 2013 は Lync 2010 レジストリ設定を受け入れますが、レジストリハイブは更新されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b7882-118">Note that Lync 2013 honors Lync 2010 registry settings, but the registry hive has been updated.</span></span> <span data-ttu-id="b7882-119">レジストリ設定は次のように作成します。</span><span class="sxs-lookup"><span data-stu-id="b7882-119">You would create the registry settings as follows:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="b7882-120">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\EnableSIPHighSecurityMode</span><span class="sxs-lookup"><span data-stu-id="b7882-120">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\EnableSIPHighSecurityMode</span></span></P>
> <P><span data-ttu-id="b7882-121">種類: DWORD</span><span class="sxs-lookup"><span data-stu-id="b7882-121">Type: DWORD</span></span></P>
> <P><span data-ttu-id="b7882-122">値のデータ: 0</span><span class="sxs-lookup"><span data-stu-id="b7882-122">Value data: 0</span></span></P>
> <LI>
> <P><span data-ttu-id="b7882-123">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\CustomStateURL</span><span class="sxs-lookup"><span data-stu-id="b7882-123">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\CustomStateURL</span></span></P>
> <P><span data-ttu-id="b7882-124">型: String (REG_SZ)</span><span class="sxs-lookup"><span data-stu-id="b7882-124">Type: String (REG_SZ)</span></span></P>
> <P><span data-ttu-id="b7882-125">値のデータ (例): file:// \\lspool.corp.contoso.com\LSFileShare\ClientConfigFolder\Presence.xml または file:///c:/LSFileShare/ClientConfigFolder/Group_1_Pres.xml</span><span class="sxs-lookup"><span data-stu-id="b7882-125">Value data (examples): file://\\lspool.corp.contoso.com\LSFileShare\ClientConfigFolder\Presence.xml or file:///c:/LSFileShare/ClientConfigFolder/Group_1_Pres.xml</span></span></P></LI></UL>



</div>

<span data-ttu-id="b7882-126">XML 構成ファイルで1つまたは複数のロケール ID (LCID) スキーマを指定して、カスタムプレゼンス状態をローカライズします。</span><span class="sxs-lookup"><span data-stu-id="b7882-126">Localize your custom presence state by specifying one or more locale ID (LCID) schema in the XML configuration file.</span></span> <span data-ttu-id="b7882-127">このトピックの後半の例では、英語-米国 (1033)、ノルウェー語 (1044)、フランス語-フランス (1036)、トルコ語 (1055) にローカライズされています。</span><span class="sxs-lookup"><span data-stu-id="b7882-127">The example later in this topic shows localization into English - United States (1033), Norwegian - Bokmål (1044), French - France (1036), and Turkish (1055).</span></span> <span data-ttu-id="b7882-128">Lcid の一覧については、「Microsoft が割り当てたロケール Id」を参照してください <https://go.microsoft.com/fwlink/p/?linkid=157331> 。</span><span class="sxs-lookup"><span data-stu-id="b7882-128">For a list of LCIDs, see Locale IDs Assigned by Microsoft at <https://go.microsoft.com/fwlink/p/?linkid=157331>.</span></span>

<div>

## <a name="to-add-custom-presence-states-to-lync-2013"></a><span data-ttu-id="b7882-129">カスタムプレゼンス状態を Lync 2013 に追加するには</span><span class="sxs-lookup"><span data-stu-id="b7882-129">To add custom presence states to Lync 2013</span></span>

1.  <span data-ttu-id="b7882-130">次の例の形式を使用して、XML 構成ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="b7882-130">Create an XML configuration file that uses the format of the following example:</span></span>
    
        <?xml version="1.0"?>
        <customStates xmlns="http://schemas.microsoft.com/09/2009/communicator/customStates">
          <customState ID="1" availability="online">
            <activity LCID="1033">Working from Home</activity>
            <activity LCID="1044">activity 2 for 1044</activity>
            <activity LCID="1055">activity 3 for 1055</activity>
          </customState>
          <customState ID="2" availability="busy">
            <activity LCID="1033">In a Live Meeting</activity>
            <activity LCID="1036">Equivalent French String for - In a Live Meeting </activity>
          </customState>
          <customState ID="3" availability="busy">
            <activity LCID="1033">Meeting with Customer</activity>
            <activity LCID="1055">meeting with client</activity>
            <activity LCID="1036">Equivalent French String for - Meeting with Customer</activity>
          </customState>
          <customState ID="4" availability="do-not-disturb">
            <activity LCID="1033">Interviewing</activity>
          </customState>
        </customStates>

2.  <span data-ttu-id="b7882-131">XML 構成ファイルを HTTPS が有効になっている web サーバーに保存します。</span><span class="sxs-lookup"><span data-stu-id="b7882-131">Save the XML configuration file to a web server with HTTPS enabled.</span></span> <span data-ttu-id="b7882-132">この例では、ファイルに Presence.xml という名前が付けられ、場所に保存され https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml ます。</span><span class="sxs-lookup"><span data-stu-id="b7882-132">In this example, the file is named Presence.xml and saved to the location https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml.</span></span>

3.  <span data-ttu-id="b7882-133">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7882-133">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="b7882-134">Lync Server 管理シェルで、次のようなコマンドを使用して、XML 構成ファイルの場所を定義します。</span><span class="sxs-lookup"><span data-stu-id="b7882-134">In the Lync Server Management Shell, define the location of your XML configuration file by using a command similar to the following:</span></span>
    
        New-CsClientPolicy -Identity ContosoCustomStates 
        -CustomStateURL "https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml"

5.  <span data-ttu-id="b7882-135">この新しいポリシーをユーザーに割り当てるには、 **Grant-CSClientPolicy** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="b7882-135">Use the **Grant-CSClientPolicy** cmdlet to assign this new policy to users.</span></span>

<span data-ttu-id="b7882-136">詳細については、「Lync Server Management Shell」のドキュメントの「 [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) 」および「 [Grant-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsClientPolicy) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7882-136">For details, see [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) and [Grant-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsClientPolicy) in the Lync Server Management Shell documentation.</span></span>

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="b7882-137">既定では、Lync Server 2013 は &nbsp; 3 時間ごとにクライアントポリシーと設定を更新します。</span><span class="sxs-lookup"><span data-stu-id="b7882-137">By default, Lync Server 2013&nbsp;updates client policies and settings every three hours.</span></span></P>
> <LI>
> <P><span data-ttu-id="b7882-138">CustomStateURL などの以前のリリースからのグループポリシー設定を引き続き使用する場合、Lync 2013 は、その設定が新しいポリシーのレジストリハイブ (HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync) にある場合に、その設定を認識します。</span><span class="sxs-lookup"><span data-stu-id="b7882-138">If you want to continue using Group Policy settings from previous releases, such as CustomStateURL, Lync 2013 will recognize the settings if they are located in the new policy registry hive (HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync).</span></span> <span data-ttu-id="b7882-139">ただし、サーバーベースのクライアントポリシーは優先されます。</span><span class="sxs-lookup"><span data-stu-id="b7882-139">However, server-based client policies take precedence.</span></span></P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

