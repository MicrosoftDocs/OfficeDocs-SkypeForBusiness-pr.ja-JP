---
title: 'Lync Server 2013: モビリティ ポリシーの構成'
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
ms.openlocfilehash: 39a7f0791def99e0b42a57b1f13aae88abbfafa4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763401"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-mobility-policy-in-lync-server-2013"></a><span data-ttu-id="80567-102">Lync Server 2013 でのモビリティ ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="80567-102">Configuring mobility policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="80567-103">_**最終更新日:** 2013-02-13_</span><span class="sxs-lookup"><span data-stu-id="80567-103">_**Topic Last Modified:** 2013-02-13_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="80567-104">Lync Server 2013 は、モバイル機能を使用できるユーザー、勤務先での通話、ボイスオーバー IP (VoIP)、またはビデオ、または VoIP とビデオのどちらで WiFi が必要かを決定するためのモビリティーポリシーを提供します。</span><span class="sxs-lookup"><span data-stu-id="80567-104">Lync Server 2013 provides mobility policies that determine who can use mobility features, Call via Work, voice over IP (VoIP) or video, and whether WiFi will be required for either VoIP or video.</span></span> <span data-ttu-id="80567-105">[職場での通話] 機能を使うと、携帯電話の電話番号ではなく勤務先の電話番号を使用して、携帯電話で通話を発信および受信することができます。</span><span class="sxs-lookup"><span data-stu-id="80567-105">The Call via Work feature enables a mobile user to make and receive calls on a mobile phone by using a work phone number instead of the mobile phone number.</span></span> <span data-ttu-id="80567-106">この機能により、通話発信者の携帯電話番号が表示されず、ユーザーが送信通話料金を回避することができます。</span><span class="sxs-lookup"><span data-stu-id="80567-106">This feature prevents the called party from seeing the caller's mobile phone number and enables a user to avoid outbound calling charges.</span></span> <span data-ttu-id="80567-107">VoIP とビデオを設定することで、ユーザーは VoIP 通話とビデオの受信とビデオの実行が可能になります。</span><span class="sxs-lookup"><span data-stu-id="80567-107">Configuring VoIP and video makes it possible for users to receive and make VoIP calls and video.</span></span> <span data-ttu-id="80567-108">WiFi 使用の設定は、ユーザーのデバイスが携帯電話のデータネットワーク経由で WiFi ネットワークを使用する必要があるかどうかを定義します。</span><span class="sxs-lookup"><span data-stu-id="80567-108">Settings for WiFi usage define if a user’s device will be required to use a WiFi network over a cellular data network.</span></span>

<span data-ttu-id="80567-109">既定では、モビリティ、勤務先からの通話、VoIP とビデオの機能が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="80567-109">By default, mobility, Call via Work, and the VoIP and video features are enabled.</span></span> <span data-ttu-id="80567-110">VoIp およびビデオに WiFi を必須にする設定は無効になっています。</span><span class="sxs-lookup"><span data-stu-id="80567-110">The settings to require WiFi for VoIp and video are disabled.</span></span> <span data-ttu-id="80567-111">管理者は、コマンドレットを実行することで、これらの機能にアクセスできるユーザーを確認できます。</span><span class="sxs-lookup"><span data-stu-id="80567-111">Administrators can determine who has access to these features by running a cmdlet.</span></span> <span data-ttu-id="80567-112">オプションは、グローバル、サイト、またはユーザーごとにオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="80567-112">You can turn options off globally, by site, or by user.</span></span>

<span data-ttu-id="80567-113">モバイル機能を使用し、勤務先から通話を発信できるようにするには、次の前提条件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="80567-113">To be able to use mobility features and Call via Work, users must meet the following prerequisites:</span></span>

  - <span data-ttu-id="80567-114">Lync Server 2013 でユーザーを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="80567-114">Users must be enabled for Lync Server 2013.</span></span>

  - <span data-ttu-id="80567-115">ユーザーはエンタープライズ Voip 用に有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="80567-115">Users must be enabled for Enterprise Voice.</span></span>

  - <span data-ttu-id="80567-116">ユーザーには、 **EnableMobility**オプションが True に設定されているモビリティーポリシーが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="80567-116">Users must be assigned a mobility policy that has the **EnableMobility** option set to True.</span></span>

<span data-ttu-id="80567-117">ユーザーが職場経由で通話を使用できるようにするには、次の2つの追加の前提条件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="80567-117">For users to be able to use Call via Work, they must meet the following two additional prerequisites:</span></span>

  - <span data-ttu-id="80567-118">ユーザーには、[**電話の同時呼び出しを有効にする**] オプションが選択されているボイスポリシーが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="80567-118">Users must be assigned a voice policy that has the **Enable simultaneous ringing of phones** option selected.</span></span>

  - <span data-ttu-id="80567-119">ユーザーには、 **EnableOutsideVoice**オプションが True に設定されているモビリティーポリシーが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="80567-119">Users must be assigned a mobility policy that has the **EnableOutsideVoice** option set to True.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="80567-120">エンタープライズ Voip を有効にしていないユーザーは、モバイルデバイスを使用して、Lync のボイスオーバー IP (VoIP) 通話を行うことができます。または、モバイルデバイスで [クリックして参加] リンクを使用して、ユーザーに音声ポリシーの適切なオプションを割り当てると、会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="80567-120">Users who are not enabled for Enterprise Voice can use their mobile devices to make Lync to Lync Voice over IP (VoIP) calls, or can join conferences by using the Click to Join link on their mobile devices, if you assign those users the appropriate options for voice policy.</span></span> <span data-ttu-id="80567-121">詳細については、「 <A href="lync-server-2013-defining-your-mobility-requirements.md">Lync Server 2013 のモビリティ要件の定義</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80567-121">For details, see <A href="lync-server-2013-defining-your-mobility-requirements.md">Defining your mobility requirements for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="80567-122">Lync Server 2013 でユーザーを有効にする方法の詳細については、「 [Lync server 2013 のユーザーアカウントを無効にする、または再度有効にする](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80567-122">For details about enabling users for Lync Server 2013, see [Disable or re-enable user account for Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md).</span></span> <span data-ttu-id="80567-123">エンタープライズ Voip のユーザーを有効にする方法について詳しくは、「 [Lync Server 2013 でエンタープライズ voip のユーザーを有効にする](lync-server-2013-enable-users-for-enterprise-voice.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="80567-123">For details about enabling users for Enterprise Voice, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span> <span data-ttu-id="80567-124">ボイスポリシーオプションの設定の詳細については、「 [Lync Server 2013 で音声ポリシーを変更し、PSTN 使用状況レコードを構成](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80567-124">For details about setting voice policy options, see [Modify a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md).</span></span>

<div>

## <a name="to-modify-global-mobility-policy"></a><span data-ttu-id="80567-125">グローバルモビリティポリシーを変更するには</span><span class="sxs-lookup"><span data-stu-id="80567-125">To modify global mobility policy</span></span>

1.  <span data-ttu-id="80567-126">Lync Server 管理シェルと Ocscore が CsAdministrator ロールのメンバーとしてインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="80567-126">Log on to any computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="80567-127">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="80567-127">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="80567-128">モバイル機能へのアクセスをオフにして、世界中の勤務先から通話を発信します。</span><span class="sxs-lookup"><span data-stu-id="80567-128">Turn off access to mobility and Call via Work globally.</span></span> <span data-ttu-id="80567-129">コマンド ラインで次を入力します。</span><span class="sxs-lookup"><span data-stu-id="80567-129">At the command line, type:</span></span>
    
        Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="80567-130">「モビリティーへのアクセスをオフにする」をオフにすると、勤務先から通話をオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="80567-130">You can turn off Call via Work without turning off access to mobility.</span></span> <span data-ttu-id="80567-131">ただし、勤務先からの通話をオフにすることなく、モバイル機能をオフにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="80567-131">However, you cannot turn off mobility without also turning off Call via Work.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-mobility-policy-by-site"></a><span data-ttu-id="80567-132">サイトによってモビリティポリシーを変更するには</span><span class="sxs-lookup"><span data-stu-id="80567-132">To modify mobility policy by site</span></span>

1.  <span data-ttu-id="80567-133">Lync Server 管理シェルと Ocscore が CsAdministrator ロールのメンバーとしてインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="80567-133">Log on to any computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="80567-134">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="80567-134">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="80567-135">サイトレベルのポリシーを作成し、VoIP およびビデオをオフにして、[IP オーディオと IP ビデオに WiFi を必須にする] を有効にします。</span><span class="sxs-lookup"><span data-stu-id="80567-135">Create a site-level policy, and turn off VoIP and video, and enable Require WiFi for IP Audio and for IP Video by site.</span></span> <span data-ttu-id="80567-136">コマンド ラインで次を入力します。</span><span class="sxs-lookup"><span data-stu-id="80567-136">At the command line, type:</span></span>
    
        New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $False -RequireWiFiForIPAudio $True -RequireWiFiForIPVideo $True

</div>

<div>

## <a name="to-modify-mobility-policy-by-user"></a><span data-ttu-id="80567-137">ユーザーによるモビリティポリシーの変更</span><span class="sxs-lookup"><span data-stu-id="80567-137">To modify mobility policy by user</span></span>

1.  <span data-ttu-id="80567-138">Lync Server 管理シェルと Ocscore が CsAdministrator ロールのメンバーとしてインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="80567-138">Log on to any computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="80567-139">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="80567-139">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="80567-140">ユーザーレベルのモバイル処理ポリシーを作成し、機動性をオフにして、ユーザーによる勤務先から通話を発信します。</span><span class="sxs-lookup"><span data-stu-id="80567-140">Create user level mobility policies and turn off mobility and Call via Work by user.</span></span> <span data-ttu-id="80567-141">コマンド ラインで次を入力します。</span><span class="sxs-lookup"><span data-stu-id="80567-141">At the command line, type:</span></span>
    
        New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
    
    <span data-ttu-id="80567-142">「モビリティーへのアクセスをオフにする」をオフにすると、勤務先から通話をオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="80567-142">You can turn off Call via Work without turning off access to mobility.</span></span> <span data-ttu-id="80567-143">ただし、勤務先からの通話をオフにすることなく、モバイル機能をオフにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="80567-143">However, you cannot turn off mobility without also turning off Call via Work.</span></span>
    
    <span data-ttu-id="80567-144">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="80567-144">For example:</span></span>
    
        New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity -MobileUser1@contoso.com -PolicyName Tag:disableOutsideVoice

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="80567-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="80567-145">See Also</span></span>


[<span data-ttu-id="80567-146">Lync Server 2013 のユーザーアカウントを無効にするか、再び有効にする</span><span class="sxs-lookup"><span data-stu-id="80567-146">Disable or re-enable user account for Lync Server 2013</span></span>](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[<span data-ttu-id="80567-147">Lync Server 2013 でのエンタープライズ Voip のユーザーの有効化</span><span class="sxs-lookup"><span data-stu-id="80567-147">Enable users for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-enterprise-voice.md)  
[<span data-ttu-id="80567-148">Lync Server 2013 で音声ポリシーを変更し、PSTN 使用状況レコードを構成する</span><span class="sxs-lookup"><span data-stu-id="80567-148">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  


[<span data-ttu-id="80567-149">Lync Server 2013 でのモビリティの要件の定義</span><span class="sxs-lookup"><span data-stu-id="80567-149">Defining your mobility requirements for Lync Server 2013</span></span>](lync-server-2013-defining-your-mobility-requirements.md)  


[<span data-ttu-id="80567-150">New-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="80567-150">New-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy)  
[<span data-ttu-id="80567-151">Set-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="80567-151">Set-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy)  
[<span data-ttu-id="80567-152">Get-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="80567-152">Get-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy)  
[<span data-ttu-id="80567-153">Grant-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="80567-153">Grant-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy)  
[<span data-ttu-id="80567-154">Remove-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="80567-154">Remove-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

