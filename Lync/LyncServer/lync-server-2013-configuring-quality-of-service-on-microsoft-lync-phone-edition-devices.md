---
title: Microsoft Lync Phone Edition デバイスでのサービス品質の設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Quality of Service on Microsoft Lync Phone Edition devices
ms:assetid: a6eb2620-a512-4ab6-bdfd-eb76be43bbfe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205137(v=OCS.15)
ms:contentKeyID: 48185004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa8068b69afa3e02a5634041c61be6f7711e8f30
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734817"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-quality-of-service-on-microsoft-lync-phone-edition-devices-in-lync-server-2013"></a><span data-ttu-id="03e2f-102">Lync Server 2013 での Microsoft Lync Phone Edition デバイスでのサービス品質の設定</span><span class="sxs-lookup"><span data-stu-id="03e2f-102">Configuring Quality of Service on Microsoft Lync Phone Edition devices in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03e2f-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="03e2f-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="03e2f-104">IPhones などのデバイスでは、サービスの品質 (QoS) は既定で有効になっていませんが、Lync Phone Edition を実行しているデバイスでは既定で QoS が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="03e2f-104">Although Quality of Service (QoS) is not enabled by default for devices such as iPhones, QoS is enabled by default for devices running Lync Phone Edition.</span></span> <span data-ttu-id="03e2f-105">(これらのデバイスは、一般的に UC またはユニファイドコミュニケーション電話と呼ばれます)。これを確認するには、Lync Server 管理シェルで次の Windows PowerShell コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="03e2f-105">(These devices are commonly referred to as UC or Unified Communication phones.) To verify this, run the following Windows PowerShell command from within the Lync Server Management Shell:</span></span>

    Get-CsUCPhoneConfiguration

<span data-ttu-id="03e2f-106">UC 電話構成設定を変更していない場合は、次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="03e2f-106">If you have not made any changes to your UC phone configuration settings then you will get back information that looks like this:</span></span>

    Identity             : Global
    CalendarPollInterval : 00:03:00
    EnforcePhoneLock     : True
    PhoneLockTimeout     : 00:10:00
    MinPhonePinLength    : 6
    SIPSecurityMode      : High
    VoiceDiffServTag     : 40
    Voice8021p           : 0
    LoggingLevel         : Off

<span data-ttu-id="03e2f-107">サービスの品質を向上させるには、これらのプロパティのいずれか1つだけを VoiceDiffServTag します。</span><span class="sxs-lookup"><span data-stu-id="03e2f-107">For Quality of Service purposes, only one of these properties is of interest: VoiceDiffServTag.</span></span> <span data-ttu-id="03e2f-108">VoiceDiffServTag は、Lync Phone Edition デバイスから emanating ボイストラフィックに割り当てられた DSCP 値を表します。</span><span class="sxs-lookup"><span data-stu-id="03e2f-108">The VoiceDiffServTag represents the DSCP value assigned to voice traffic emanating from a Lync Phone Edition device.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="03e2f-109">Voice8021p パラメーターは、Lync Server 2013 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="03e2f-109">The Voice8021p parameter is no longer supported in Lync Server 2013.</span></span> <span data-ttu-id="03e2f-110">このパラメーターは、Microsoft Lync Server 2010 との下位互換性を維持するために有効です。ただし、Lync Server 2013 で使用されているデバイスには影響はありません。</span><span class="sxs-lookup"><span data-stu-id="03e2f-110">The parameter is still valid for backward compatibility with Microsoft Lync Server 2010; however, it has no effect on devices used with Lync Server 2013.</span></span>



</div>

<span data-ttu-id="03e2f-111">ほとんどのネットワークでは、Lync Phone Edition のパケットに40の VoiceDiffServTag をマークすると、問題が発生しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="03e2f-111">In most networks, marking Lync Phone Edition packets with a VoiceDiffServTag of 40 should not cause any problems.</span></span> <span data-ttu-id="03e2f-112">ただし、40は、通常はオーディオトラフィックに使用される値ではありません。代わりに、ほとんどの場合、音声トラフィックは DSCP コード46でマークされます。</span><span class="sxs-lookup"><span data-stu-id="03e2f-112">However, 40 is not the value typically used for audio traffic; instead, audio traffic is almost always marked with the DSCP code 46.</span></span> <span data-ttu-id="03e2f-113">ネットワーク全体の一貫性を維持するために、UC 携帯電話の VoiceDiffServTag プロパティを46に変更したい場合があります。</span><span class="sxs-lookup"><span data-stu-id="03e2f-113">In order to maintain consistency throughout your network, you might want to change the VoiceDiffServTag property of your UC phones to 46.</span></span>

<span data-ttu-id="03e2f-114">そのためには、Windows PowerShell または Lync Server コントロールパネルのいずれかを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="03e2f-114">To do that, you can use either Windows PowerShell or the Lync Server Control Panel.</span></span> <span data-ttu-id="03e2f-115">Windows PowerShell を使用して VoiceDiffServTag の値を変更するには、Lync Server 管理シェルで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="03e2f-115">To modify the VoiceDiffServTag value by using Windows PowerShell, run the following command from within the Lync Server Management Shell:</span></span>

    Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

<span data-ttu-id="03e2f-116">上記のコマンドは、UC 電話構成設定のグローバルコレクションを変更します。</span><span class="sxs-lookup"><span data-stu-id="03e2f-116">The preceding command modifies the global collection of UC phone configuration settings.</span></span> <span data-ttu-id="03e2f-117">ただし、そのような UC の携帯電話の設定をサイトの範囲に割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="03e2f-117">Note, however, that UC phone settings can also be assigned to the site scope.</span></span> <span data-ttu-id="03e2f-118">UC 電話構成の設定をサイトの範囲で変更するには、サイト Id を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="03e2f-118">To modify UC phone configuration settings at the site scope, you must specify the site Identity.</span></span> <span data-ttu-id="03e2f-119">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="03e2f-119">For example:</span></span>

    Set-CsUCPhoneConfiguration -Identity "site:Redmond" -VoiceDiffServTag 46

<span data-ttu-id="03e2f-120">以下のコマンドを使用して、すべての UC 電話構成設定を同時に変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="03e2f-120">You can also use the following command to simultaneously modify all your UC phone configuration settings:</span></span>

    Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

<span data-ttu-id="03e2f-121">Lync Server コントロールパネルを使用してこの変更を行う場合は、[コントロールパネル] を起動し、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="03e2f-121">If you prefer to make this change using Lync Server Control Panel, then start the Control Panel and then complete the following procedure:</span></span>

1.  <span data-ttu-id="03e2f-122">[**クライアント**] をクリックし、[**デバイスの構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="03e2f-122">Click **Clients** and then click **Device Configuration**.</span></span>

2.  <span data-ttu-id="03e2f-123">[**デバイスの構成**] タブで、変更する設定のコレクション ([**グローバル**] など) をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="03e2f-123">On the **Device Configuration** tab, double-click the collection of settings you want to modify (for example, **Global**).</span></span>

3.  <span data-ttu-id="03e2f-124">[**デバイス構成の編集**] ダイアログボックスで、[**ボイスの品質 (QoS)** ] ボックスの値を**46**に設定し、[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="03e2f-124">In the **Edit Device Configuration** dialog box, set the value of the **Voice Quality of Service (QoS)** box to **46** and then click **Commit**.</span></span>

<span data-ttu-id="03e2f-125">複数のコレクションがある場合は、UC の電話設定のコレクションごとにこの手順を繰り返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="03e2f-125">If you have multiple collections you will need to repeat this process for each collection of UC phone settings.</span></span> <span data-ttu-id="03e2f-126">Lync Server コントロールパネルでは、複数の設定コレクションを同時に変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="03e2f-126">Lync Server Control Panel will not allow you to simultaneously modify multiple setting collections.</span></span>

<span data-ttu-id="03e2f-127">組織内の Windows オペレーティングシステム (iPhones など) に基づいていないデバイスを使用している場合、これらのデバイスは、VoiceDiffServTag 設定の変更によって影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="03e2f-127">If you have devices that are not based on the Windows operating system (such as iPhones) in your organization these devices will not be affected by changing the VoiceDiffServTag setting.</span></span> <span data-ttu-id="03e2f-128">これらのデバイスで DSCP 値を変更する場合は、各デバイスの種類について、管理者マニュアルを参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="03e2f-128">If you want to change DSCP values on those devices you will need to refer to the administration manual for each of your device types.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

