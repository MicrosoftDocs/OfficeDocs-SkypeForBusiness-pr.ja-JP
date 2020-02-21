---
title: 'Lync Server 2013: (オプション) DTMF コマンドのキーマッピングを変更する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Modify key mapping for DTMF commands
ms:assetid: d753b78d-400c-4df2-957f-e7576b2019c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398943(v=OCS.15)
ms:contentKeyID: 48185563
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86986ba2715021e7bf39f5d448f9de5f9a733f54
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216493"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="optional-modify-key-mapping-for-dtmf-commands-in-lync-server-2013"></a><span data-ttu-id="8722e-102">オプションLync Server 2013 での DTMF コマンドのキーマッピングの変更</span><span class="sxs-lookup"><span data-stu-id="8722e-102">(Optional) Modify key mapping for DTMF commands in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8722e-103">_**トピックの最終更新日:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="8722e-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="8722e-p101">ダイヤルイン会議のユーザーは、電話キーパッドのキーを押して、デュアルトーン多重周波数 (DTMF) のコマンドを実行できます。 DTMF コマンドを使用すると、会議にダイヤルインするユーザーは、電話のキーパッドを使用して会議設定 (自身をミュートおよびミュート解除したり、会議をロックおよびロック解除したりするなど) を制御できます。 コマンドレットを使用して、DTMF コマンドに使用されるキーを変更できます。このステップはオプションです。</span><span class="sxs-lookup"><span data-stu-id="8722e-p101">Dial-in conferencing users can press keys on the telephone keypad to perform dual-tone multi-frequency (DTMF) commands. DTMF commands enable users who dial in to a conference to control conference settings (such as muting and unmuting themselves or locking and unlocking the conference) by using the keypad on their telephone. You can use cmdlets to modify the keys used for the DTMF commands. This step is optional.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8722e-108">これらのコマンドレットおよび使用可能な DTMF オプションの詳細については、「Lync Server Management Shell documentation or Lync Server Management Shell コマンドラインヘルプ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8722e-108">For details about these cmdlets and the possible DTMF options, see Lync Server Management Shell documentation or Lync Server Management Shell command-line Help.</span></span>



</div>

<div>

## <a name="to-modify-the-key-mapping-of-dtmf-commands"></a><span data-ttu-id="8722e-109">DTMF コマンドのキー マッピングを変更するには</span><span class="sxs-lookup"><span data-stu-id="8722e-109">To modify the key mapping of DTMF commands</span></span>

1.  <span data-ttu-id="8722e-110">コンピューターに **RTCUniversalServerAdmins** グループのメンバーとしてログオンするか、**Cs-ServerAdministrator** または **CsAdministrator** 役割のメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="8722e-110">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="8722e-111">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="8722e-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="8722e-112">コマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="8722e-112">Run the following at the command prompt:</span></span>
    
        Get-CsDialinConferencingDtmfConfiguration
    
    <span data-ttu-id="8722e-113">このコマンドレットを実行すると、ダイヤルイン会議に使用される DTMF 設定が戻されます。</span><span class="sxs-lookup"><span data-stu-id="8722e-113">This cmdlet returns the DTMF settings used for dial-in conferencing.</span></span>

4.  <span data-ttu-id="8722e-114">次のコマンドレットを実行し、変更対象である各オプションで押されるキーを指定します。</span><span class="sxs-lookup"><span data-stu-id="8722e-114">Run the following cmdlet and specify the key to be pressed for each option that you want to change:</span></span>
    
        Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
        [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
        [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
        [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
        [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
    
    <span data-ttu-id="8722e-115">このコマンドレットを実行すると、ダイヤルイン会議に使用される DTMF 設定が変更されます。</span><span class="sxs-lookup"><span data-stu-id="8722e-115">This cmdlet modifies the DTMF settings used for dial-in conferencing.</span></span>
    
    <span data-ttu-id="8722e-116">次にその例を示します。</span><span class="sxs-lookup"><span data-stu-id="8722e-116">For example:</span></span>
    
        Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
    
    <span data-ttu-id="8722e-p102">この例では、アナウンスを有効/無効にするために押されるキーと、全参加者のミュート/ミュート解除のために押されるキーを交換します。 ID が指定されていないため、これらの変更はグローバル DTMF 設定に適用されます。</span><span class="sxs-lookup"><span data-stu-id="8722e-p102">This example swaps the key that is pressed to enable or disable announcements and the key that is pressed to mute and unmute all participants. Because no Identity is specified, these changes apply to the global DTMF settings.</span></span>

5.  <span data-ttu-id="8722e-119">(オプション) 特定サイトに対する DTMF コマンドの追加セットを作成するには、サイト ID と **New-CsDialinConferencingDtmfConfiguration** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="8722e-119">(Optional) To create additional sets of DTMF commands for specific sites, use the **New-CsDialinConferencingDtmfConfiguration** cmdlet with a site identity.</span></span> <span data-ttu-id="8722e-120">サイトの新たな DTMF 設定を作成すると、そのサイト設定はグローバル設定よりも優先されるようになります。</span><span class="sxs-lookup"><span data-stu-id="8722e-120">When you create new DTMF settings for sites, the site settings take precedence over the global settings.</span></span> <span data-ttu-id="8722e-121">詳細については、「Lync Server Management Shell documentation」または「Lync Server Management Shell コマンドラインヘルプ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8722e-121">For details, see Lync Server Management Shell documentation or Lync Server Management Shell command-line Help.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

