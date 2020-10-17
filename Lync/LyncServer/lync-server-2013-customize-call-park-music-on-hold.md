---
title: 'Lync Server 2013: コールパーク保留音のカスタマイズ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Customize Call Park music on hold
ms:assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688031(v=OCS.15)
ms:contentKeyID: 49733621
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18f7ac9793c8275caa20725d2d303c5fca7f534f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516714"
---
# <a name="customize-call-park-music-on-hold-in-lync-server-2013"></a><span data-ttu-id="75a2b-102">Lync Server 2013 でコールパーク保留音をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="75a2b-102">Customize Call Park music on hold in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75a2b-103">_**トピックの最終更新日:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="75a2b-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="75a2b-104">Lync Server 2013 に同梱されている既定の音楽ファイルではなく、保留音に使用する音楽ファイルを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="75a2b-104">You can specify your own music file to use for music on hold, instead of the default music file that ships with Lync Server 2013.</span></span> <span data-ttu-id="75a2b-105">保留音をカスタマイズするには、**Set-CsCallParkServiceMusicOnHoldFile** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="75a2b-105">To customize music on hold, use the **Set-CsCallParkServiceMusicOnHoldFile** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="75a2b-106">保留音をカスタマイズして、複数のサイトで同じ音楽を使用する場合は、コールパークアプリケーションが実行されている各サイトに対して音楽ファイルを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="75a2b-106">If you customize music on hold and want the same music for multiple sites, you must configure the music file for each site that runs the Call Park application.</span></span>



</div>

<div>

## <a name="to-customize-the-music-file"></a><span data-ttu-id="75a2b-107">音楽ファイルをカスタマイズするには</span><span class="sxs-lookup"><span data-stu-id="75a2b-107">To customize the music file</span></span>

1.  <span data-ttu-id="75a2b-108">Lync Server 管理シェルがインストールされているコンピューターに、RTCUniversalServerAdmins グループのメンバーとして、または「 [Lync server 2013 のセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」に説明されている必要なユーザー権限を使用してログオンします。</span><span class="sxs-lookup"><span data-stu-id="75a2b-108">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="75a2b-109">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="75a2b-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="75a2b-110">実行</span><span class="sxs-lookup"><span data-stu-id="75a2b-110">Run:</span></span>
    
        Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte[]>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="75a2b-111">サービスを識別するには、<STRONG>Get-CsService</STRONG> コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="75a2b-111">Use the <STRONG>Get-CsService</STRONG> cmdlet to identify the service.</span></span> <span data-ttu-id="75a2b-112">詳細については、「 <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsService">取得-CsService</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75a2b-112">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsService">Get-CsService</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="75a2b-113">次の例は、soothingmusic.wma というファイルのコンテンツをバイト配列として取得し、変数に割り当てる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="75a2b-113">The following example shows how to obtain the contents of a file, soothingmusic.wma, as a byte array and assign it to a variable.</span></span> <span data-ttu-id="75a2b-114">次に音声ファイルをコール パークの保留音ファイルとして割り当てます。</span><span class="sxs-lookup"><span data-stu-id="75a2b-114">Then the audio file is assigned as the music-on-hold file for Call Park.</span></span> <span data-ttu-id="75a2b-115">詳細については、「 [set-cscallparkservicemusiconholdfile](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkServiceMusicOnHoldFile)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75a2b-115">For details, see [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkServiceMusicOnHoldFile).</span></span>
    
        $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
        Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="75a2b-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="75a2b-116">See Also</span></span>


[<span data-ttu-id="75a2b-117">Set-cscallparkservicemusiconholdfile</span><span class="sxs-lookup"><span data-stu-id="75a2b-117">Set-CsCallParkServiceMusicOnHoldFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkServiceMusicOnHoldFile)  
[<span data-ttu-id="75a2b-118">取得-CsService</span><span class="sxs-lookup"><span data-stu-id="75a2b-118">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

