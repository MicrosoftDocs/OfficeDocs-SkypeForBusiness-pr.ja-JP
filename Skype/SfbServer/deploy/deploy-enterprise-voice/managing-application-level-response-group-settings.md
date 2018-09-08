---
title: ビジネス用の Skype のアプリケーション レベルの応答グループの設定を管理します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: aab749a1-fa2d-4ce8-a6c6-ebcfa37ce02a
description: ビジネス サーバーのエンタープライズ VoIP の Skype で、保留中の音楽やリングバックの設定など、アプリケーション レベルの応答グループ設定を管理します。
ms.openlocfilehash: 4a44ee8988925025b81eac6bd1ee340a3bbef81b
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2018
ms.locfileid: "23890944"
---
# <a name="managing-application-level-response-group-settings-in-skype-for-business"></a><span data-ttu-id="15cc0-103">ビジネス用の Skype のアプリケーション レベルの応答グループの設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="15cc0-103">Managing application-level Response Group settings in Skype for Business</span></span>
 
<span data-ttu-id="15cc0-104">ビジネス サーバーのエンタープライズ VoIP の Skype で、保留中の音楽やリングバックの設定など、アプリケーション レベルの応答グループ設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="15cc0-104">Managing application-level Response Group settings, such as music-on-hold and ringback settings, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="15cc0-105">応答グループ アプリケーションのアプリケーション レベルの設定には、既定の音楽-保留中の構成、既定の音楽-保留中のオーディオ ファイル、エージェント リングバックの猶予期間、および呼び出しのコンテキストの構成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="15cc0-105">Application-level settings for Response Group application include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="15cc0-106">プールあたりのアプリケーション レベルの設定の 1 つだけのセットを定義できます。</span><span class="sxs-lookup"><span data-stu-id="15cc0-106">You can define only one set of application-level settings per pool.</span></span> <span data-ttu-id="15cc0-107">アプリケーション レベルの設定を表示するには、 **Get CsRgsConfiguration**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="15cc0-107">To view application-level settings, use the **Get-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="15cc0-108">アプリケーション レベルの設定を変更するには、**セット CsRgsConfiguration**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="15cc0-108">To modify the application-level settings, use the **Set-CsRgsConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="15cc0-p102">既定の保留音は、カスタム保留音が定義されていない場合にのみ、通話が保留になったときに再生されます。呼び出しコンテキストは、対話型ワークフローに割り当てられているキューでのみ使用できます。呼び出しコンテキストが有効になっている場合、エージェントは発信者の待ち時間やワークフロー質問および回答などの情報を通話の受信時に見ることができます。</span><span class="sxs-lookup"><span data-stu-id="15cc0-p102">The default music on hold is played when a call is placed on hold only if no custom music on hold is defined. Call context is available only for queues assigned to interactive workflows. If call context is enabled, an agent can see information such as caller wait time or workflow questions and answers when the call is received.</span></span>
  
### <a name="to-modify-response-group-application-level-settings"></a><span data-ttu-id="15cc0-112">応答グループ アプリケーション レベルの設定を変更するのには</span><span class="sxs-lookup"><span data-stu-id="15cc0-112">To modify Response Group application-level settings</span></span>

1. <span data-ttu-id="15cc0-113">RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="15cc0-113">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="15cc0-114">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="15cc0-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="15cc0-115">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="15cc0-115">At the command line, run:</span></span>
    
   ```
   Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
   ```

    <span data-ttu-id="15cc0-116">例:</span><span class="sxs-lookup"><span data-stu-id="15cc0-116">For example:</span></span>
    
   ```
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
   ```

    <span data-ttu-id="15cc0-p103">既定の保留音として使用するオーディオ ファイルを指定するには、まずオーディオ ファイルをインポートする必要があります。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="15cc0-p103">To specify an audio file to use as the default music on hold, you need to import the audio file first. For example:</span></span>
    
   ```
   $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>
   ```

## <a name="see-also"></a><span data-ttu-id="15cc0-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="15cc0-119">See also</span></span>

[<span data-ttu-id="15cc0-120">Get CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="15cc0-120">Get-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csrgsconfiguration?view=skype-ps)
  
[<span data-ttu-id="15cc0-121">セット CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="15cc0-121">Set-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csrgsconfiguration?view=skype-ps)
  
[<span data-ttu-id="15cc0-122">インポート-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="15cc0-122">Import-CsRgsAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)