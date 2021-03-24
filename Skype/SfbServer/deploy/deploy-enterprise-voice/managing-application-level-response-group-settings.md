---
title: Skype for Business でのアプリケーション レベルの応答グループ設定の管理
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: aab749a1-fa2d-4ce8-a6c6-ebcfa37ce02a
description: Skype for Business Server エンタープライズ VoIP で、アプリケーション レベルの応答グループ設定 (保留音やリングバック設定など) を管理します。
ms.openlocfilehash: 941164fb3a99f62303b45f587b64e7aff9cb1393
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103473"
---
# <a name="managing-application-level-response-group-settings-in-skype-for-business"></a><span data-ttu-id="cbb7d-103">Skype for Business でのアプリケーション レベルの応答グループ設定の管理</span><span class="sxs-lookup"><span data-stu-id="cbb7d-103">Managing application-level Response Group settings in Skype for Business</span></span>
 
<span data-ttu-id="cbb7d-104">Skype for Business Server エンタープライズ VoIP で、アプリケーション レベルの応答グループ設定 (保留音やリングバック設定など) を管理します。</span><span class="sxs-lookup"><span data-stu-id="cbb7d-104">Managing application-level Response Group settings, such as music-on-hold and ringback settings, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="cbb7d-105">応答グループ アプリケーションのアプリケーション レベルの設定には、既定の保留音構成、既定の保留音オーディオ ファイル、エージェントリングバック猶予期間、通話コンテキスト構成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="cbb7d-105">Application-level settings for Response Group application include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="cbb7d-106">プールごとにアプリケーションレベルの設定のセットを 1 つだけ定義できます。</span><span class="sxs-lookup"><span data-stu-id="cbb7d-106">You can define only one set of application-level settings per pool.</span></span> <span data-ttu-id="cbb7d-107">アプリケーション レベルの設定を表示するには **、Get-CsRgsConfiguration コマンドレットを使用** します。</span><span class="sxs-lookup"><span data-stu-id="cbb7d-107">To view application-level settings, use the **Get-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="cbb7d-108">アプリケーション レベルの設定を変更するには **、Set-CsRgsConfiguration コマンドレットを使用** します。</span><span class="sxs-lookup"><span data-stu-id="cbb7d-108">To modify the application-level settings, use the **Set-CsRgsConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="cbb7d-p102">既定の保留音は、カスタム保留音が定義されていない場合にのみ、通話が保留になったときに再生されます。呼び出しコンテキストは、対話型ワークフローに割り当てられているキューでのみ使用できます。呼び出しコンテキストが有効になっている場合、エージェントは発信者の待ち時間やワークフロー質問および回答などの情報を通話の受信時に見ることができます。</span><span class="sxs-lookup"><span data-stu-id="cbb7d-p102">The default music on hold is played when a call is placed on hold only if no custom music on hold is defined. Call context is available only for queues assigned to interactive workflows. If call context is enabled, an agent can see information such as caller wait time or workflow questions and answers when the call is received.</span></span>
  
### <a name="to-modify-response-group-application-level-settings"></a><span data-ttu-id="cbb7d-112">応答グループのアプリケーション レベルの設定を変更するには</span><span class="sxs-lookup"><span data-stu-id="cbb7d-112">To modify Response Group application-level settings</span></span>

1. <span data-ttu-id="cbb7d-113">RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="cbb7d-113">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="cbb7d-114">Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="cbb7d-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="cbb7d-115">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="cbb7d-115">At the command line, run:</span></span>
    
   ```powershell
   Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
   ```

    <span data-ttu-id="cbb7d-116">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="cbb7d-116">For example:</span></span>
    
   ```powershell
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
   ```

    <span data-ttu-id="cbb7d-p103">既定の保留音として使用するオーディオ ファイルを指定するには、まずオーディオ ファイルをインポートする必要があります。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="cbb7d-p103">To specify an audio file to use as the default music on hold, you need to import the audio file first. For example:</span></span>
    
   ```powershell
   $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>
   ```

## <a name="see-also"></a><span data-ttu-id="cbb7d-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="cbb7d-119">See also</span></span>

[<span data-ttu-id="cbb7d-120">Get-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="cbb7d-120">Get-CsRgsConfiguration</span></span>](/powershell/module/skype/get-csrgsconfiguration?view=skype-ps)
  
[<span data-ttu-id="cbb7d-121">Set-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="cbb7d-121">Set-CsRgsConfiguration</span></span>](/powershell/module/skype/set-csrgsconfiguration?view=skype-ps)
  
[<span data-ttu-id="cbb7d-122">Import-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="cbb7d-122">Import-CsRgsAudioFile</span></span>](/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)