---
title: Skype for Businessで通話パークの音楽を保留にカスタマイズする
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
ms.assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
description: Skype for Business Server サーバー の通話保留音をカスタマイズエンタープライズ VoIP。
ms.openlocfilehash: 87dea58d9e339293b047373ac6c44a16bed3bdb3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093045"
---
# <a name="customize-call-park-music-on-hold-inskype-for-business"></a><span data-ttu-id="93301-103">Skype for Businessで通話パークの音楽を保留にカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="93301-103">Customize Call Park music on hold inSkype for Business</span></span>
 
<span data-ttu-id="93301-104">Skype for Business Server サーバー の通話保留音をカスタマイズエンタープライズ VoIP。</span><span class="sxs-lookup"><span data-stu-id="93301-104">Customize the Call Park music on hold in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="93301-105">Skype for Business Server に含む既定の音楽ファイルではなく、保留音に使用する独自の音楽ファイルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="93301-105">You can specify your own music file to use for music on hold, instead of the default music file that ships with Skype for Business Server.</span></span> <span data-ttu-id="93301-106">保留音をカスタマイズするには、**Set-CsCallParkServiceMusicOnHoldFile** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="93301-106">To customize music on hold, use the **Set-CsCallParkServiceMusicOnHoldFile** cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="93301-107">保留音をカスタマイズし、複数のサイトで同じ音楽が必要な場合は、コール パーク アプリケーションを実行する各サイトの音楽ファイルを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="93301-107">If you customize music on hold and want the same music for multiple sites, you must configure the music file for each site that runs the Call Park application.</span></span> 
  
### <a name="to-customize-the-music-file"></a><span data-ttu-id="93301-108">音楽ファイルをカスタマイズするには</span><span class="sxs-lookup"><span data-stu-id="93301-108">To customize the music file</span></span>

1. <span data-ttu-id="93301-109">「代理セットアップのアクセス許可」の説明に従って、Skype for Business Server 管理シェルが RTCUniversalServerAdmins グループのメンバーとして、または必要なユーザー権限でインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="93301-109">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="93301-110">Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="93301-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="93301-111">次を実行します:  </span><span class="sxs-lookup"><span data-stu-id="93301-111">Run:</span></span>
    
   ```powershell
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > <span data-ttu-id="93301-112">サービスを識別するには、**Get-CsService** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="93301-112">Use the **Get-CsService** cmdlet to identify the service.</span></span> <span data-ttu-id="93301-113">詳細については [、「Get-CsService」を参照してください](/powershell/module/skype/get-csservice?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="93301-113">For details, see [Get-CsService](/powershell/module/skype/get-csservice?view=skype-ps).</span></span> 
  
    <span data-ttu-id="93301-114">次の例は、soothingmusic.wma というファイルのコンテンツをバイト配列として取得し、変数に割り当てる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="93301-114">The following example shows how to obtain the contents of a file, soothingmusic.wma, as a byte array and assign it to a variable.</span></span> <span data-ttu-id="93301-115">次に音声ファイルをコール パークの保留音ファイルとして割り当てます。</span><span class="sxs-lookup"><span data-stu-id="93301-115">Then the audio file is assigned as the music-on-hold file for Call Park.</span></span> <span data-ttu-id="93301-116">詳細については [、「Set-CsCallParkServiceMusicOnHoldFile」を参照してください](/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="93301-116">For details, see [Set-CsCallParkServiceMusicOnHoldFile](/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).</span></span>
    
   ```powershell
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a><span data-ttu-id="93301-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="93301-117">See also</span></span>

[<span data-ttu-id="93301-118">Set-CsCallParkServiceMusicOnHoldFile</span><span class="sxs-lookup"><span data-stu-id="93301-118">Set-CsCallParkServiceMusicOnHoldFile</span></span>](/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[<span data-ttu-id="93301-119">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="93301-119">Get-CsService</span></span>](/powershell/module/skype/get-csservice?view=skype-ps)