---
title: 'Lync Server 2013: モビリティポリシーの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring mobility policy
ms:assetid: 595536e0-9bb3-49a3-8d13-1a77351ebc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690018(v=OCS.15)
ms:contentKeyID: 48184204
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2268313ed570ab560be2eca9827f0ab07ec9149
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213573"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-mobility-policy-in-lync-server-2013"></a><span data-ttu-id="c51a4-102">Lync Server 2013 でのモビリティポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="c51a4-102">Configuring mobility policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c51a4-103">_**トピックの最終更新日:** 2013-02-13_</span><span class="sxs-lookup"><span data-stu-id="c51a4-103">_**Topic Last Modified:** 2013-02-13_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="c51a4-104">Lync Server 2013 には、モビリティ機能を使用できるユーザー、勤務先から通話、ボイスオーバー IP (VoIP) またはビデオ、および VoIP またはビデオのどちらかに Wi-fi が必要かどうかを決定するモビリティポリシーが用意されています。</span><span class="sxs-lookup"><span data-stu-id="c51a4-104">Lync Server 2013 provides mobility policies that determine who can use mobility features, Call via Work, voice over IP (VoIP) or video, and whether WiFi will be required for either VoIP or video.</span></span> <span data-ttu-id="c51a4-105">Via for Work 機能を使用すると、モバイルユーザーは携帯電話番号ではなく勤務先電話番号を使用して、携帯電話で通話を発信および受信することができます。</span><span class="sxs-lookup"><span data-stu-id="c51a4-105">The Call via Work feature enables a mobile user to make and receive calls on a mobile phone by using a work phone number instead of the mobile phone number.</span></span> <span data-ttu-id="c51a4-106">この機能により、呼び出し元の携帯電話番号が表示されないようにし、ユーザーが発信通話料金を回避することができます。</span><span class="sxs-lookup"><span data-stu-id="c51a4-106">This feature prevents the called party from seeing the caller's mobile phone number and enables a user to avoid outbound calling charges.</span></span> <span data-ttu-id="c51a4-107">VoIP およびビデオを構成することにより、ユーザーは VoIP 通話とビデオを受信できます。</span><span class="sxs-lookup"><span data-stu-id="c51a4-107">Configuring VoIP and video makes it possible for users to receive and make VoIP calls and video.</span></span> <span data-ttu-id="c51a4-108">WiFi 使用法の設定ユーザーのデバイスが、携帯データネットワーク経由で WiFi ネットワークを使用する必要があるかどうかを定義します。</span><span class="sxs-lookup"><span data-stu-id="c51a4-108">Settings for WiFi usage define if a user’s device will be required to use a WiFi network over a cellular data network.</span></span>

<span data-ttu-id="c51a4-109">既定では、モビリティ、勤務先から通話、および VoIP およびビデオの機能が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="c51a4-109">By default, mobility, Call via Work, and the VoIP and video features are enabled.</span></span> <span data-ttu-id="c51a4-110">VoIp およびビデオ用に WiFi を必須にする設定は無効になっています。</span><span class="sxs-lookup"><span data-stu-id="c51a4-110">The settings to require WiFi for VoIp and video are disabled.</span></span> <span data-ttu-id="c51a4-111">管理者は、コマンドレットを実行して、これらの機能にアクセスできるユーザーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c51a4-111">Administrators can determine who has access to these features by running a cmdlet.</span></span> <span data-ttu-id="c51a4-112">オプションは、グローバル、サイト別、またはユーザー別に無効にできます。</span><span class="sxs-lookup"><span data-stu-id="c51a4-112">You can turn options off globally, by site, or by user.</span></span>

<span data-ttu-id="c51a4-113">モビリティ機能および [勤務先から通話] を使用できるためには、ユーザーが次の前提条件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c51a4-113">To be able to use mobility features and Call via Work, users must meet the following prerequisites:</span></span>

  - <span data-ttu-id="c51a4-114">ユーザーが Lync Server 2013 に対して有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c51a4-114">Users must be enabled for Lync Server 2013.</span></span>

  - <span data-ttu-id="c51a4-115">ユーザーは、エンタープライズ VoIP に対して有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c51a4-115">Users must be enabled for Enterprise Voice.</span></span>

  - <span data-ttu-id="c51a4-116">ユーザーには、**EnableMobility** オプションが True に設定されているモビリティ ポリシーが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c51a4-116">Users must be assigned a mobility policy that has the **EnableMobility** option set to True.</span></span>

<span data-ttu-id="c51a4-117">ユーザーが [勤務先から通話] を使用できるためには、ユーザーは次の 2 つの追加の前提条件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="c51a4-117">For users to be able to use Call via Work, they must meet the following two additional prerequisites:</span></span>

  - <span data-ttu-id="c51a4-118">ユーザーには、[**電話の同時呼び出しを有効にする**] オプションが選択されている音声ポリシーが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c51a4-118">Users must be assigned a voice policy that has the **Enable simultaneous ringing of phones** option selected.</span></span>

  - <span data-ttu-id="c51a4-119">ユーザーには、**EnableOutsideVoice** オプションが True に設定されているモビリティ ポリシーが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c51a4-119">Users must be assigned a mobility policy that has the **EnableOutsideVoice** option set to True.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c51a4-120">エンタープライズ Voip が有効になっていないユーザーは、モバイルデバイスを使用して Lync Voice over IP (VoIP) 通話を行うことができます。または、自分のモバイルデバイスで [クリックして参加] リンクを使用して会議に参加できます。これらのユーザーに音声ポリシーの適切なオプションを割り当てる場合。</span><span class="sxs-lookup"><span data-stu-id="c51a4-120">Users who are not enabled for Enterprise Voice can use their mobile devices to make Lync to Lync Voice over IP (VoIP) calls, or can join conferences by using the Click to Join link on their mobile devices, if you assign those users the appropriate options for voice policy.</span></span> <span data-ttu-id="c51a4-121">詳細については、「 <A href="lync-server-2013-defining-your-mobility-requirements.md">Lync Server 2013 のモビリティ要件の定義</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c51a4-121">For details, see <A href="lync-server-2013-defining-your-mobility-requirements.md">Defining your mobility requirements for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="c51a4-122">Lync Server 2013 でユーザーを有効にする方法の詳細については、「 [Lync server 2013 のユーザーアカウントの無効化または再有効化](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c51a4-122">For details about enabling users for Lync Server 2013, see [Disable or re-enable user account for Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md).</span></span> <span data-ttu-id="c51a4-123">エンタープライズ Voip に対するユーザーの有効化の詳細については、「 [Enable users For Enterprise voice In Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c51a4-123">For details about enabling users for Enterprise Voice, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span> <span data-ttu-id="c51a4-124">音声ポリシーオプションの設定の詳細については、「 [Modify a voice policy」および「CONFIGURE PSTN usage records In Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c51a4-124">For details about setting voice policy options, see [Modify a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md).</span></span>

<div>

## <a name="to-modify-global-mobility-policy"></a><span data-ttu-id="c51a4-125">グローバル モビリティ ポリシーを変更するには</span><span class="sxs-lookup"><span data-stu-id="c51a4-125">To modify global mobility policy</span></span>

1.  <span data-ttu-id="c51a4-126">Lync Server 管理シェルと Ocscore がインストールされている任意のコンピューターに CsAdministrator の役割のメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="c51a4-126">Log on to any computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="c51a4-127">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="c51a4-127">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="c51a4-p105">モビリティおよび [勤務先から通話] へのアクセスをグローバルに無効にします。コマンド ラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="c51a4-p105">Turn off access to mobility and Call via Work globally. At the command line, type:</span></span>
    
        Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c51a4-p106">モビリティへのアクセスをオフにしなくても "勤務先から通話" をオフにできます。ただし、モビリティをオフにする場合は、"勤務先から通話" もオフにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c51a4-p106">You can turn off Call via Work without turning off access to mobility. However, you cannot turn off mobility without also turning off Call via Work.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-mobility-policy-by-site"></a><span data-ttu-id="c51a4-132">モビリティ ポリシーをサイト別に変更するには</span><span class="sxs-lookup"><span data-stu-id="c51a4-132">To modify mobility policy by site</span></span>

1.  <span data-ttu-id="c51a4-133">Lync Server 管理シェルと Ocscore がインストールされている任意のコンピューターに CsAdministrator の役割のメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="c51a4-133">Log on to any computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="c51a4-134">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="c51a4-134">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="c51a4-135">サイトレベルのポリシーを作成し、VoIP およびビデオをオフにして、IP オーディオと IP ビデオをサイトごとに有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="c51a4-135">Create a site-level policy, and turn off VoIP and video, and enable Require WiFi for IP Audio and for IP Video by site.</span></span> <span data-ttu-id="c51a4-136">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="c51a4-136">At the command line, type:</span></span>
    
        New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $False -RequireWiFiForIPAudio $True -RequireWiFiForIPVideo $True

</div>

<div>

## <a name="to-modify-mobility-policy-by-user"></a><span data-ttu-id="c51a4-137">モビリティ ポリシーをユーザー別に変更するには</span><span class="sxs-lookup"><span data-stu-id="c51a4-137">To modify mobility policy by user</span></span>

1.  <span data-ttu-id="c51a4-138">Lync Server 管理シェルと Ocscore がインストールされている任意のコンピューターに CsAdministrator の役割のメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="c51a4-138">Log on to any computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="c51a4-139">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="c51a4-139">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="c51a4-p108">ユーザー レベルのモビリティ ポリシーを作成し、モビリティと [勤務先から通話] をユーザー別に無効にします。コマンド ラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="c51a4-p108">Create user level mobility policies and turn off mobility and Call via Work by user. At the command line, type:</span></span>
    
        New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
    
    <span data-ttu-id="c51a4-p109">モビリティへのアクセスをオフにしなくても "勤務先から通話" をオフにできます。ただし、モビリティをオフにする場合は、"勤務先から通話" もオフにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c51a4-p109">You can turn off Call via Work without turning off access to mobility. However, you cannot turn off mobility without also turning off Call via Work.</span></span>
    
    <span data-ttu-id="c51a4-144">たとえば、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="c51a4-144">For example:</span></span>
    
        New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity -MobileUser1@contoso.com -PolicyName Tag:disableOutsideVoice

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c51a4-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="c51a4-145">See Also</span></span>


[<span data-ttu-id="c51a4-146">Lync Server 2013 のユーザーアカウントを無効または再度有効にする</span><span class="sxs-lookup"><span data-stu-id="c51a4-146">Disable or re-enable user account for Lync Server 2013</span></span>](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[<span data-ttu-id="c51a4-147">Lync Server 2013 のエンタープライズ Voip でユーザーを有効にする</span><span class="sxs-lookup"><span data-stu-id="c51a4-147">Enable users for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-enterprise-voice.md)  
[<span data-ttu-id="c51a4-148">Lync Server 2013 での音声ポリシーの変更と PSTN 使用法レコードの構成</span><span class="sxs-lookup"><span data-stu-id="c51a4-148">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  


[<span data-ttu-id="c51a4-149">Lync Server 2013 のモビリティ要件の定義</span><span class="sxs-lookup"><span data-stu-id="c51a4-149">Defining your mobility requirements for Lync Server 2013</span></span>](lync-server-2013-defining-your-mobility-requirements.md)  


[<span data-ttu-id="c51a4-150">Get-csmobilitypolicy</span><span class="sxs-lookup"><span data-stu-id="c51a4-150">New-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy)  
[<span data-ttu-id="c51a4-151">Get-csmobilitypolicy</span><span class="sxs-lookup"><span data-stu-id="c51a4-151">Set-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy)  
[<span data-ttu-id="c51a4-152">Get-csmobilitypolicy</span><span class="sxs-lookup"><span data-stu-id="c51a4-152">Get-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy)  
[<span data-ttu-id="c51a4-153">Get-csmobilitypolicy</span><span class="sxs-lookup"><span data-stu-id="c51a4-153">Grant-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy)  
[<span data-ttu-id="c51a4-154">Get-csmobilitypolicy</span><span class="sxs-lookup"><span data-stu-id="c51a4-154">Remove-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

