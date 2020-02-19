---
title: 'Lync Server 2013: アプリケーションレベルの応答グループ設定の管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing application-level Response Group settings
ms:assetid: aab749a1-fa2d-4ce8-a6c6-ebcfa37ce02a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721843(v=OCS.15)
ms:contentKeyID: 49733776
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc066e25b84dca002f9cb88263328b1c37ba754b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140240"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-application-level-response-group-settings-in-lync-server-2013"></a><span data-ttu-id="7f41a-102">Lync Server 2013 でのアプリケーションレベルの応答グループ設定の管理</span><span class="sxs-lookup"><span data-stu-id="7f41a-102">Managing application-level Response Group settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f41a-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="7f41a-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="7f41a-104">応答グループアプリケーションのアプリケーションレベルの設定には、既定の保留音の構成、既定の保留音のオーディオファイル、エージェントリングバックの猶予期間、呼び出しコンテキストの構成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7f41a-104">Application-level settings for Response Group application include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="7f41a-105">プールごとにアプリケーションレベルの設定のセットを 1 つだけ定義できます。</span><span class="sxs-lookup"><span data-stu-id="7f41a-105">You can define only one set of application-level settings per pool.</span></span> <span data-ttu-id="7f41a-106">アプリケーションレベルの設定を表示するには、 **Get-CsRgsConfiguration**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="7f41a-106">To view application-level settings, use the **Get-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="7f41a-107">アプリケーションレベルの設定を変更するには、 **Set-CsRgsConfiguration**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="7f41a-107">To modify the application-level settings, use the **Set-CsRgsConfiguration** cmdlet.</span></span>

<span data-ttu-id="7f41a-p102">既定の保留音は、カスタム保留音が定義されていない場合にのみ、通話が保留になったときに再生されます。呼び出しコンテキストは、対話型ワークフローに割り当てられているキューでのみ使用できます。呼び出しコンテキストが有効になっている場合、エージェントは発信者の待ち時間やワークフロー質問および回答などの情報を通話の受信時に見ることができます。</span><span class="sxs-lookup"><span data-stu-id="7f41a-p102">The default music on hold is played when a call is placed on hold only if no custom music on hold is defined. Call context is available only for queues assigned to interactive workflows. If call context is enabled, an agent can see information such as caller wait time or workflow questions and answers when the call is received.</span></span>

<div>

## <a name="to-modify-response-group-application-level-settings"></a><span data-ttu-id="7f41a-111">応答グループのアプリケーションレベルの設定を変更するには</span><span class="sxs-lookup"><span data-stu-id="7f41a-111">To modify Response Group application-level settings</span></span>

1.  <span data-ttu-id="7f41a-112">RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="7f41a-112">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="7f41a-113">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="7f41a-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="7f41a-114">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7f41a-114">At the command line, run:</span></span>
    
        Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
    
    <span data-ttu-id="7f41a-115">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="7f41a-115">For example:</span></span>
    
        Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
    
    <span data-ttu-id="7f41a-p103">既定の保留音として使用するオーディオ ファイルを指定するには、まずオーディオ ファイルをインポートする必要があります。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="7f41a-p103">To specify an audio file to use as the default music on hold, you need to import the audio file first. For example:</span></span>
    
        $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
        Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7f41a-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="7f41a-118">See Also</span></span>


[<span data-ttu-id="7f41a-119">Get-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="7f41a-119">Get-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration)  
[<span data-ttu-id="7f41a-120">Set-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="7f41a-120">Set-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsConfiguration)  
[<span data-ttu-id="7f41a-121">Import-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="7f41a-121">Import-CsRgsAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

