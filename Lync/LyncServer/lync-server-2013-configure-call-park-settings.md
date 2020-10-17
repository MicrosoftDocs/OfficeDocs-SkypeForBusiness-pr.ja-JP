---
title: 'Lync Server 2013: コールパーク設定の構成'
description: 'Lync Server 2013: コールパーク設定を構成します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Call Park settings
ms:assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425886(v=OCS.15)
ms:contentKeyID: 48183922
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8862208a68c89151096349508a4c849a5649b70
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546643"
---
# <a name="configure-call-park-settings-in-lync-server-2013"></a><span data-ttu-id="498bc-103">Lync Server 2013 でコールパーク設定を構成する</span><span class="sxs-lookup"><span data-stu-id="498bc-103">Configure Call Park settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="498bc-104">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="498bc-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="498bc-105">既定のコールパーク設定を使用しない場合は、それらをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="498bc-105">If you don't want to use default Call Park settings, you can customize them.</span></span> <span data-ttu-id="498bc-106">コールパークアプリケーションをインストールすると、既定でグローバル設定が構成されます。</span><span class="sxs-lookup"><span data-stu-id="498bc-106">When you install the Call Park application, global settings are configured by default.</span></span> <span data-ttu-id="498bc-107">グローバル設定を変更したり、サイト固有の設定を指定したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="498bc-107">You can modify the global settings, and you can also specify site-specific settings.</span></span> <span data-ttu-id="498bc-108">新しいサイト固有の設定を作成するには、 **new-cscpsconfiguration** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="498bc-108">Use the **New-CsCpsConfiguration** cmdlet to create new site-specific settings.</span></span> <span data-ttu-id="498bc-109">既存の設定を変更するには、 **new-cscpsconfiguration** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="498bc-109">Use the **Set-CsCpsConfiguration** cmdlet to modify existing settings.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="498bc-110">少なくとも、保留された通話が時間切れになりリングバックが失敗した場合に使用する代替宛先の [<STRONG>OnTimeoutURI</STRONG>] オプションは構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="498bc-110">At a minimum, we recommend that you configure the <STRONG>OnTimeoutURI</STRONG> option for the fallback destination to use when a parked call times out and ringback fails.</span></span>



</div>

<span data-ttu-id="498bc-111">**New-CsCpsConfiguration** コマンドレットまたは **Set-CsCpsConfiguration** コマンドレットを使用して、次のいずれかの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="498bc-111">Use **New-CsCpsConfiguration** cmdlet or the **Set-CsCpsConfiguration** cmdlet to configure any of the following settings:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="498bc-112">このオプション:</span><span class="sxs-lookup"><span data-stu-id="498bc-112">This option:</span></span></th>
<th><span data-ttu-id="498bc-113">指定する内容:</span><span class="sxs-lookup"><span data-stu-id="498bc-113">Specifies this:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="498bc-114"><strong>CallPickupTimeoutThreshold</strong></span><span class="sxs-lookup"><span data-stu-id="498bc-114"><strong>CallPickupTimeoutThreshold</strong></span></span></p></td>
<td><p><span data-ttu-id="498bc-115">通話が保留されてから、呼び出しに応答した電話にかけ直されるまでの経過時間。</span><span class="sxs-lookup"><span data-stu-id="498bc-115">The amount of time that elapses after a call has been parked before it rings back to the phone where the call was answered.</span></span></p>
<p><span data-ttu-id="498bc-p102">この値は、hh:mm:ss の形式で入力し、時間、分、および秒を指定する必要があります。 最小値は 10 秒、最大値は 10 分です。 既定値は 00:01:30 です。</span><span class="sxs-lookup"><span data-stu-id="498bc-p102">The value must be entered in the format hh:mm:ss to specify the hours, minutes, and seconds. The minimum value is 10 seconds, and the maximum value is 10 minutes. The default is 00:01:30.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="498bc-119"><strong>EnableMusicOnHold</strong></span><span class="sxs-lookup"><span data-stu-id="498bc-119"><strong>EnableMusicOnHold</strong></span></span></p></td>
<td><p><span data-ttu-id="498bc-120">通話が保留されている間、発信者に対して音楽を再生するかどうか。</span><span class="sxs-lookup"><span data-stu-id="498bc-120">Whether music plays for a caller while a call is parked.</span></span></p>
<p><span data-ttu-id="498bc-p103">値は True または False です。既定値は True です。</span><span class="sxs-lookup"><span data-stu-id="498bc-p103">Values are True or False. The default is True.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="498bc-123"><strong>MaxCallPickupAttempts</strong></span><span class="sxs-lookup"><span data-stu-id="498bc-123"><strong>MaxCallPickupAttempts</strong></span></span></p></td>
<td><p><span data-ttu-id="498bc-p104">保留された通話が [<strong>OnTimeoutURI</strong>] で指定した代替 URI (Uniform Resource Identifier) に転送される前に、応答電話にかけ直される回数。既定値は 1 です。</span><span class="sxs-lookup"><span data-stu-id="498bc-p104">The number of times a parked call rings back to the answering phone before it is forwarded to the fallback Uniform Resource Identifier (URI) that is specified for <strong>OnTimeoutURI</strong>. The default is 1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="498bc-126"><strong>[Ontimeouturi]</strong></span><span class="sxs-lookup"><span data-stu-id="498bc-126"><strong>OnTimeoutURI</strong></span></span></p></td>
<td><p><span data-ttu-id="498bc-127"><strong>MaxCallPickupAttempts</strong> を超過した場合に、応答のない保留通話のルーティング先となるユーザーまたは応答グループの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="498bc-127">The SIP address of the user or response group to which an unanswered parked call is routed when <strong>MaxCallPickupAttempts</strong> is exceeded.</span></span></p>
<p><span data-ttu-id="498bc-p105">値は、文字列 sip: で始まる SIP URI にする必要があります。 たとえば、sip:bob@contoso.com などです。既定値は転送アドレスではありません。</span><span class="sxs-lookup"><span data-stu-id="498bc-p105">Value must be a SIP URI beginning with the string sip:. For example, sip:bob@contoso.com. The default is no forwarding address.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-call-park-settings"></a><span data-ttu-id="498bc-131">コールパーク設定を構成するには</span><span class="sxs-lookup"><span data-stu-id="498bc-131">To configure Call Park settings</span></span>

1.  <span data-ttu-id="498bc-132">Lync Server 管理シェルがインストールされているコンピューターに、RTCUniversalServerAdmins グループのメンバーとして、または「 [Lync server 2013 のセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」に説明されている必要なユーザー権限を使用してログオンします。</span><span class="sxs-lookup"><span data-stu-id="498bc-132">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="498bc-133">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="498bc-133">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="498bc-134">実行</span><span class="sxs-lookup"><span data-stu-id="498bc-134">Run:</span></span>
    
        New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="498bc-135">サイトを識別するには、<STRONG>Get-CsSite</STRONG> コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="498bc-135">Use the <STRONG>Get-CsSite</STRONG> cmdlet to identify the site.</span></span> <span data-ttu-id="498bc-136">詳細については、「Lync Server Management Shell」のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="498bc-136">For details, see Lync Server Management Shell documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="498bc-137">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="498bc-137">For example:</span></span>
    
        New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="498bc-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="498bc-138">See Also</span></span>


[<span data-ttu-id="498bc-139">Lync Server 2013 でコールパーク保留音をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="498bc-139">Customize Call Park music on hold in Lync Server 2013</span></span>](lync-server-2013-customize-call-park-music-on-hold.md)  


[<span data-ttu-id="498bc-140">New-cscpsconfiguration</span><span class="sxs-lookup"><span data-stu-id="498bc-140">New-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsCpsConfiguration)  
[<span data-ttu-id="498bc-141">New-cscpsconfiguration</span><span class="sxs-lookup"><span data-stu-id="498bc-141">Set-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCpsConfiguration)  
[<span data-ttu-id="498bc-142">取得-CsSite</span><span class="sxs-lookup"><span data-stu-id="498bc-142">Get-CsSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

