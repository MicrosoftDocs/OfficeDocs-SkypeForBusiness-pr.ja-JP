---
title: 'Lync Server 2013: カスタムプレゼンス状態の構成'
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
ms.openlocfilehash: c69f7a5b32b4ad0dd31f8be118aa2f2173ff3e22
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758197"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-custom-presence-states-in-lync-server-2013"></a><span data-ttu-id="e5c0d-102">Lync Server 2013 でのカスタムプレゼンス状態の構成</span><span class="sxs-lookup"><span data-stu-id="e5c0d-102">Configuring custom presence states in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5c0d-103">_**最終更新日:** 2013-01-10_</span><span class="sxs-lookup"><span data-stu-id="e5c0d-103">_**Topic Last Modified:** 2013-01-10_</span></span>

<span data-ttu-id="e5c0d-104">Lync 2013 でカスタムプレゼンス状態を定義するには、XML カスタムプレゼンス構成ファイルを作成して、Lync Server 管理シェルコマンドレットで、**新しい CSClientPolicy**を使用するか、またはパラメーター CustomStateURL を**設定**して、その場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="e5c0d-104">To define custom presence states in Lync 2013, create an XML custom presence configuration file, and then specify its location by using the Lync Server Management Shell cmdlets **New-CSClientPolicy** or **Set-CSClientPolicy** with the parameter CustomStateURL.</span></span>

<span data-ttu-id="e5c0d-105">構成ファイルには、次のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="e5c0d-105">Configuration files have the following properties:</span></span>

  - <span data-ttu-id="e5c0d-106">カスタムプレゼンス状態は、[利用可能]、[取り込み中]、[応答不可] のプレゼンスインジケーターで構成できます。</span><span class="sxs-lookup"><span data-stu-id="e5c0d-106">Custom presence states can be configured with the Available, Busy, and Do Not Disturb presence indicators.</span></span>

  - <span data-ttu-id="e5c0d-107">[可用性] 属性は、カスタム状態の状態テキストに関連付けられているプレゼンスインジケーターを決定します。</span><span class="sxs-lookup"><span data-stu-id="e5c0d-107">The availability attribute determines which presence indicator is associated with the status text of the custom state.</span></span> <span data-ttu-id="e5c0d-108">このトピックの後半の例では、[自宅から] の状態テキストが緑色 (使用可能) のプレゼンスインジケーターの右側に表示されています。</span><span class="sxs-lookup"><span data-stu-id="e5c0d-108">In the example later in this topic, the status text Working from Home is displayed to the right of the green (Available) presence indicator.</span></span>

  - <span data-ttu-id="e5c0d-109">状態テキストの最大の長さは、64文字です。</span><span class="sxs-lookup"><span data-stu-id="e5c0d-109">The maximum length of the status text is 64 characters.</span></span>

  - <span data-ttu-id="e5c0d-110">最大4つのカスタムプレゼンス状態を追加できます。</span><span class="sxs-lookup"><span data-stu-id="e5c0d-110">A maximum of four custom presence states can be added.</span></span>

  - <span data-ttu-id="e5c0d-111">CustomStateURL パラメーターは、構成ファイルの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="e5c0d-111">The CustomStateURL parameter specifies the location of the configuration file.</span></span> <span data-ttu-id="e5c0d-112">Lync 2013 では、SIP high security モードは既定で有効になっているため、HTTPS が有効になっている web サーバーにカスタムのプレゼンス設定ファイルを格納する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5c0d-112">In Lync 2013, SIP high security mode is enabled by default, so you will need to store the custom presence configuration file on a web server that has HTTPS enabled.</span></span> <span data-ttu-id="e5c0d-113">そうしないと、Lync 2013 クライアントに接続できなくなります。</span><span class="sxs-lookup"><span data-stu-id="e5c0d-113">Otherwise, Lync 2013 clients will be unable to connect to it.</span></span> <span data-ttu-id="e5c0d-114">たとえば、有効なアドレスになり`https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml`ます。</span><span class="sxs-lookup"><span data-stu-id="e5c0d-114">For example, a valid address would be `https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml`.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e5c0d-115">実稼働環境ではお勧めできませんが、HTTPS 以外のファイル共有に配置されている構成ファイルをテストするには、EnableSIPHighSecurityMode registry 設定を使用して、クライアントで SIP high security モードを無効にします。</span><span class="sxs-lookup"><span data-stu-id="e5c0d-115">Although it is not recommended in a production environment, you can test a configuration file that is located on a non-HTTPS file share by using the EnableSIPHighSecurityMode registry setting to disable SIP high security mode on the client.</span></span> <span data-ttu-id="e5c0d-116">次に、CustomStateURL レジストリ設定を使用して、構成ファイルの HTTPS 以外の場所を指定できます。</span><span class="sxs-lookup"><span data-stu-id="e5c0d-116">Then you can use the CustomStateURL registry setting to specify a non-HTTPS location for the configuration file.</span></span> <span data-ttu-id="e5c0d-117">Lync 2013 では Lync 2010 のレジストリ設定は無視されますが、レジストリハイブは更新されています。</span><span class="sxs-lookup"><span data-stu-id="e5c0d-117">Note that Lync 2013 honors Lync 2010 registry settings, but the registry hive has been updated.</span></span> <span data-ttu-id="e5c0d-118">レジストリ設定は次の手順で作成します。</span><span class="sxs-lookup"><span data-stu-id="e5c0d-118">You would create the registry settings as follows:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="e5c0d-119">HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync\EnableSIPHighSecurityMode</span><span class="sxs-lookup"><span data-stu-id="e5c0d-119">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\EnableSIPHighSecurityMode</span></span></P>
> <P><span data-ttu-id="e5c0d-120">Type: DWORD</span><span class="sxs-lookup"><span data-stu-id="e5c0d-120">Type: DWORD</span></span></P>
> <P><span data-ttu-id="e5c0d-121">値のデータ: 0</span><span class="sxs-lookup"><span data-stu-id="e5c0d-121">Value data: 0</span></span></P>
> <LI>
> <P><span data-ttu-id="e5c0d-122">HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync\CustomStateURL</span><span class="sxs-lookup"><span data-stu-id="e5c0d-122">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\CustomStateURL</span></span></P>
> <P><span data-ttu-id="e5c0d-123">Type: String (REG_SZ)</span><span class="sxs-lookup"><span data-stu-id="e5c0d-123">Type: String (REG_SZ)</span></span></P>
> <P><span data-ttu-id="e5c0d-124">値のデータ (例):\\File://lspool または file:///c:/LSFileShare/ClientConfigFolder/Group_1_Pres.xml</span><span class="sxs-lookup"><span data-stu-id="e5c0d-124">Value data (examples): file://\\lspool.corp.contoso.com\LSFileShare\ClientConfigFolder\Presence.xml or file:///c:/LSFileShare/ClientConfigFolder/Group_1_Pres.xml</span></span></P></LI></UL>



</div>

<span data-ttu-id="e5c0d-125">XML 構成ファイルで1つ以上のロケール ID (LCID) スキーマを指定して、カスタムのプレゼンス状態をローカライズします。</span><span class="sxs-lookup"><span data-stu-id="e5c0d-125">Localize your custom presence state by specifying one or more locale ID (LCID) schema in the XML configuration file.</span></span> <span data-ttu-id="e5c0d-126">このトピックの後半の例では、ローカライズされた言語 (1033)、ノルウェー語-ブークモール (1044)、フランス語-フランス (1036)、およびトルコ語 (1055) について説明します。</span><span class="sxs-lookup"><span data-stu-id="e5c0d-126">The example later in this topic shows localization into English - United States (1033), Norwegian - Bokmål (1044), French - France (1036), and Turkish (1055).</span></span> <span data-ttu-id="e5c0d-127">Lcid の一覧については、「Microsoft によって<http://go.microsoft.com/fwlink/p/?linkid=157331>割り当てられたロケール id」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e5c0d-127">For a list of LCIDs, see Locale IDs Assigned by Microsoft at <http://go.microsoft.com/fwlink/p/?linkid=157331>.</span></span>

<div>

## <a name="to-add-custom-presence-states-to-lync-2013"></a><span data-ttu-id="e5c0d-128">Lync 2013 にカスタムプレゼンス状態を追加するには</span><span class="sxs-lookup"><span data-stu-id="e5c0d-128">To add custom presence states to Lync 2013</span></span>

1.  <span data-ttu-id="e5c0d-129">次の例の形式を使用する XML 構成ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="e5c0d-129">Create an XML configuration file that uses the format of the following example:</span></span>
    
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

2.  <span data-ttu-id="e5c0d-130">HTTPS が有効になっている web サーバーに XML 構成ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="e5c0d-130">Save the XML configuration file to a web server with HTTPS enabled.</span></span> <span data-ttu-id="e5c0d-131">この例では、ファイルには ".xml" という名前が付けhttps://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xmlられ、場所に保存されています。</span><span class="sxs-lookup"><span data-stu-id="e5c0d-131">In this example, the file is named Presence.xml and saved to the location https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml.</span></span>

3.  <span data-ttu-id="e5c0d-132">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5c0d-132">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="e5c0d-133">Lync Server 管理シェルで、次のようなコマンドを使用して、XML 構成ファイルの場所を定義します。</span><span class="sxs-lookup"><span data-stu-id="e5c0d-133">In the Lync Server Management Shell, define the location of your XML configuration file by using a command similar to the following:</span></span>
    
        New-CsClientPolicy -Identity ContosoCustomStates 
        -CustomStateURL "https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml"

5.  <span data-ttu-id="e5c0d-134">この新しいポリシーをユーザーに割り当てるには、**グラント Clientpolicy**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="e5c0d-134">Use the **Grant-CSClientPolicy** cmdlet to assign this new policy to users.</span></span>

<span data-ttu-id="e5c0d-135">詳細については、「[新しい-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) 」と「Lync Server 管理シェルドキュメントの[権限を付与](https://docs.microsoft.com/powershell/module/skype/Grant-CsClientPolicy)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5c0d-135">For details, see [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) and [Grant-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsClientPolicy) in the Lync Server Management Shell documentation.</span></span>

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="e5c0d-136">既定では、Lync Server&nbsp;2013 は、クライアントポリシーと設定を3時間ごとに更新します。</span><span class="sxs-lookup"><span data-stu-id="e5c0d-136">By default, Lync Server 2013&nbsp;updates client policies and settings every three hours.</span></span></P>
> <LI>
> <P><span data-ttu-id="e5c0d-137">CustomStateURL などの以前のリリースのグループポリシー設定を引き続き使用する場合、Lync 2013 は、その設定が新しいポリシーレジストリハイブ (HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync) にある場合にその設定を認識します。</span><span class="sxs-lookup"><span data-stu-id="e5c0d-137">If you want to continue using Group Policy settings from previous releases, such as CustomStateURL, Lync 2013 will recognize the settings if they are located in the new policy registry hive (HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync).</span></span> <span data-ttu-id="e5c0d-138">ただし、サーバーベースのクライアントポリシーが優先されます。</span><span class="sxs-lookup"><span data-stu-id="e5c0d-138">However, server-based client policies take precedence.</span></span></P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

