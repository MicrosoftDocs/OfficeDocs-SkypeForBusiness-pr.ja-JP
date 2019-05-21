---
title: 通話パークを保留にする Skype for Business での音声通話
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
description: Skype for Business Server Enterprise Voice で、通話の保留中の音楽をカスタマイズします。
ms.openlocfilehash: 4111bcc42a3820e3957f526e360264aa7d098d05
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286177"
---
# <a name="customize-call-park-music-on-hold-inskype-for-business"></a><span data-ttu-id="048bc-103">通話パークを保留にする Skype for Business での音声通話</span><span class="sxs-lookup"><span data-stu-id="048bc-103">Customize Call Park music on hold inSkype for Business</span></span>
 
<span data-ttu-id="048bc-104">Skype for Business Server Enterprise Voice で、通話の保留中の音楽をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="048bc-104">Customize the Call Park music on hold in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="048bc-105">Skype for Business Server に付属の既定の音楽ファイルの代わりに、自分の音楽ファイルを保留にして、音楽に使用することができます。</span><span class="sxs-lookup"><span data-stu-id="048bc-105">You can specify your own music file to use for music on hold, instead of the default music file that ships with Skype for Business Server.</span></span> <span data-ttu-id="048bc-106">保留音をカスタマイズするには、**Set-CsCallParkServiceMusicOnHoldFile** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="048bc-106">To customize music on hold, use the **Set-CsCallParkServiceMusicOnHoldFile** cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="048bc-107">保留中の音楽をカスタマイズして、複数のサイトで同じ音楽を使う場合は、通話パークアプリケーションを実行する各サイトの音楽ファイルを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="048bc-107">If you customize music on hold and want the same music for multiple sites, you must configure the music file for each site that runs the Call Park application.</span></span> 
  
### <a name="to-customize-the-music-file"></a><span data-ttu-id="048bc-108">音楽ファイルをカスタマイズするには</span><span class="sxs-lookup"><span data-stu-id="048bc-108">To customize the music file</span></span>

1. <span data-ttu-id="048bc-109">Skype for Business Server 管理シェルが RTCUniversalServerAdmins グループのメンバーとしてインストールされているコンピューターにログオンするか、「**代理人セットアップアクセス許可**」で説明するように、必要なユーザー権限を設定します。</span><span class="sxs-lookup"><span data-stu-id="048bc-109">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="048bc-110">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="048bc-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="048bc-111">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="048bc-111">Run:</span></span>
    
   ```
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > <span data-ttu-id="048bc-112">サービスを識別するには、**Get-CsService** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="048bc-112">Use the **Get-CsService** cmdlet to identify the service.</span></span> <span data-ttu-id="048bc-113">詳細については、「 [CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="048bc-113">For details, see [Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps).</span></span> 
  
    <span data-ttu-id="048bc-114">次の例は、soothingmusic.wma というファイルのコンテンツをバイト配列として取得し、変数に割り当てる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="048bc-114">The following example shows how to obtain the contents of a file, soothingmusic.wma, as a byte array and assign it to a variable.</span></span> <span data-ttu-id="048bc-115">次に音声ファイルをコール パークの保留音ファイルとして割り当てます。</span><span class="sxs-lookup"><span data-stu-id="048bc-115">Then the audio file is assigned as the music-on-hold file for Call Park.</span></span> <span data-ttu-id="048bc-116">詳細については、「 [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="048bc-116">For details, see [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).</span></span>
    
   ```
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a><span data-ttu-id="048bc-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="048bc-117">See also</span></span>

[<span data-ttu-id="048bc-118">Set-CsCallParkServiceMusicOnHoldFile</span><span class="sxs-lookup"><span data-stu-id="048bc-118">Set-CsCallParkServiceMusicOnHoldFile</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[<span data-ttu-id="048bc-119">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="048bc-119">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)
