---
title: Microsoft Lync Phone Edition デバイスでのサービスの品質の構成
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
ms.openlocfilehash: 7e154df7c71b32e9f5f1c1440707511bc91c3117
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213114"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-quality-of-service-on-microsoft-lync-phone-edition-devices-in-lync-server-2013"></a><span data-ttu-id="907c1-102">Lync Server 2013 での Microsoft Lync Phone Edition デバイスでのサービスの品質の構成</span><span class="sxs-lookup"><span data-stu-id="907c1-102">Configuring Quality of Service on Microsoft Lync Phone Edition devices in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="907c1-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="907c1-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="907c1-104">IPhones などのデバイスでは、サービスの品質 (QoS) は既定で有効になっていませんが、Lync Phone Edition を実行しているデバイスでは既定で QoS が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="907c1-104">Although Quality of Service (QoS) is not enabled by default for devices such as iPhones, QoS is enabled by default for devices running Lync Phone Edition.</span></span> <span data-ttu-id="907c1-105">(これらのデバイスは一般に UC またはユニファイドコミュニケーション電話と呼ばれます)。これを確認するには、Lync Server 管理シェルで次の Windows PowerShell コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="907c1-105">(These devices are commonly referred to as UC or Unified Communication phones.) To verify this, run the following Windows PowerShell command from within the Lync Server Management Shell:</span></span>

    Get-CsUCPhoneConfiguration

<span data-ttu-id="907c1-106">UC 電話の構成設定を変更していなければ、次のような情報が返されます。</span><span class="sxs-lookup"><span data-stu-id="907c1-106">If you have not made any changes to your UC phone configuration settings then you will get back information that looks like this:</span></span>

    Identity             : Global
    CalendarPollInterval : 00:03:00
    EnforcePhoneLock     : True
    PhoneLockTimeout     : 00:10:00
    MinPhonePinLength    : 6
    SIPSecurityMode      : High
    VoiceDiffServTag     : 40
    Voice8021p           : 0
    LoggingLevel         : Off

<span data-ttu-id="907c1-107">これらのプロパティのうち、サービスの品質に関連するのは VoiceDiffServTag だけです。</span><span class="sxs-lookup"><span data-stu-id="907c1-107">For Quality of Service purposes, only one of these properties is of interest: VoiceDiffServTag.</span></span> <span data-ttu-id="907c1-108">VoiceDiffServTag は、Lync Phone Edition デバイスからの音声トラフィック emanating に割り当てられた DSCP 値を表します。</span><span class="sxs-lookup"><span data-stu-id="907c1-108">The VoiceDiffServTag represents the DSCP value assigned to voice traffic emanating from a Lync Phone Edition device.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="907c1-109">Voice8021p パラメーターは、Lync Server 2013 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="907c1-109">The Voice8021p parameter is no longer supported in Lync Server 2013.</span></span> <span data-ttu-id="907c1-110">このパラメーターは、Microsoft Lync Server 2010 との下位互換性を維持するために有効になっています。ただし、Lync Server 2013 で使用されているデバイスには影響を与えません。</span><span class="sxs-lookup"><span data-stu-id="907c1-110">The parameter is still valid for backward compatibility with Microsoft Lync Server 2010; however, it has no effect on devices used with Lync Server 2013.</span></span>



</div>

<span data-ttu-id="907c1-111">ほとんどのネットワークでは、Lync Phone Edition のパケットに40の VoiceDiffServTag をマークすると、問題が発生しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="907c1-111">In most networks, marking Lync Phone Edition packets with a VoiceDiffServTag of 40 should not cause any problems.</span></span> <span data-ttu-id="907c1-112">音声トラフィックは、ほとんど常に DSCP コード 46 でマーキングされます。</span><span class="sxs-lookup"><span data-stu-id="907c1-112">However, 40 is not the value typically used for audio traffic; instead, audio traffic is almost always marked with the DSCP code 46.</span></span> <span data-ttu-id="907c1-113">ネットワーク全体の一貫性を確保するために、UC 電話の VoiceDiffServTag プロパティを 46 に変更することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="907c1-113">In order to maintain consistency throughout your network, you might want to change the VoiceDiffServTag property of your UC phones to 46.</span></span>

<span data-ttu-id="907c1-114">これを行うには、Windows PowerShell または Lync Server コントロールパネルのどちらかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="907c1-114">To do that, you can use either Windows PowerShell or the Lync Server Control Panel.</span></span> <span data-ttu-id="907c1-115">Windows PowerShell を使用して VoiceDiffServTag の値を変更するには、Lync Server 管理シェルで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="907c1-115">To modify the VoiceDiffServTag value by using Windows PowerShell, run the following command from within the Lync Server Management Shell:</span></span>

    Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

<span data-ttu-id="907c1-p106">上のコマンドは、UC 電話構成設定のグローバル コレクションを変更します。UC 電話設定は、サイト スコープに割り当てることもできます。UC 電話構成設定をサイト スコープで変更するには、サイト ID を指定する必要があります。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="907c1-p106">The preceding command modifies the global collection of UC phone configuration settings. Note, however, that UC phone settings can also be assigned to the site scope. To modify UC phone configuration settings at the site scope, you must specify the site Identity. For example:</span></span>

    Set-CsUCPhoneConfiguration -Identity "site:Redmond" -VoiceDiffServTag 46

<span data-ttu-id="907c1-120">次のコマンドを使用して、すべての UC 電話構成設定を同時に変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="907c1-120">You can also use the following command to simultaneously modify all your UC phone configuration settings:</span></span>

    Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

<span data-ttu-id="907c1-121">この変更を Lync Server コントロールパネルを使用して行う場合は、[コントロールパネル] を起動し、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="907c1-121">If you prefer to make this change using Lync Server Control Panel, then start the Control Panel and then complete the following procedure:</span></span>

1.  <span data-ttu-id="907c1-122">[**クライアント**] をクリックして、[**デバイス構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="907c1-122">Click **Clients** and then click **Device Configuration**.</span></span>

2.  <span data-ttu-id="907c1-123">[**デバイス構成**] タブで、変更する設定のコレクションをダブルクリックします ([**グローバル**] など)。</span><span class="sxs-lookup"><span data-stu-id="907c1-123">On the **Device Configuration** tab, double-click the collection of settings you want to modify (for example, **Global**).</span></span>

3.  <span data-ttu-id="907c1-124">[**デバイス構成の編集**] ダイアログ ボックスで、[**音声のサービス品質 (QoS)**] ボックスの値を **46** に設定し、[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="907c1-124">In the **Edit Device Configuration** dialog box, set the value of the **Voice Quality of Service (QoS)** box to **46** and then click **Commit**.</span></span>

<span data-ttu-id="907c1-125">複数のコレクションがある場合は、UC 電話設定の各コレクションに対してこのプロセスを繰り返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="907c1-125">If you have multiple collections you will need to repeat this process for each collection of UC phone settings.</span></span> <span data-ttu-id="907c1-126">Lync Server コントロールパネルでは、複数の設定コレクションを同時に変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="907c1-126">Lync Server Control Panel will not allow you to simultaneously modify multiple setting collections.</span></span>

<span data-ttu-id="907c1-p108">Windows オペレーティング システム ベースではないデバイス (iPhone など) がある場合、VoiceDiffServTag の設定を変更しても、それらのデバイスには影響しません。それらのデバイスの DSCP 値を変更するには、そのデバイスの管理マニュアルを参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="907c1-p108">If you have devices that are not based on the Windows operating system (such as iPhones) in your organization these devices will not be affected by changing the VoiceDiffServTag setting. If you want to change DSCP values on those devices you will need to refer to the administration manual for each of your device types.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

