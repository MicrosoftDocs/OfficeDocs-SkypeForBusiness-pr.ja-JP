---
title: Skype for Business でコール パーク保留音をカスタマイズする
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
description: Skype for Business Server のコール パーク保留音をカスタマイズエンタープライズ VoIP。
ms.openlocfilehash: 766b51895acda27c0558352968d21a39764b13a6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837077"
---
# <a name="customize-call-park-music-on-hold-inskype-for-business"></a><span data-ttu-id="f973c-103">Skype for Business でコール パーク保留音をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="f973c-103">Customize Call Park music on hold inSkype for Business</span></span>
 
<span data-ttu-id="f973c-104">Skype for Business Server のコール パーク保留音をカスタマイズエンタープライズ VoIP。</span><span class="sxs-lookup"><span data-stu-id="f973c-104">Customize the Call Park music on hold in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="f973c-105">Skype for Business Server に組み込む既定の音楽ファイルの代わりに、保留音に使用する独自の音楽ファイルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="f973c-105">You can specify your own music file to use for music on hold, instead of the default music file that ships with Skype for Business Server.</span></span> <span data-ttu-id="f973c-106">保留音をカスタマイズするには、**Set-CsCallParkServiceMusicOnHoldFile** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="f973c-106">To customize music on hold, use the **Set-CsCallParkServiceMusicOnHoldFile** cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f973c-107">保留音をカスタマイズし、複数のサイトで同じ音楽を使用する場合は、コール パーク アプリケーションを実行するサイトごとに音楽ファイルを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f973c-107">If you customize music on hold and want the same music for multiple sites, you must configure the music file for each site that runs the Call Park application.</span></span> 
  
### <a name="to-customize-the-music-file"></a><span data-ttu-id="f973c-108">音楽ファイルをカスタマイズするには</span><span class="sxs-lookup"><span data-stu-id="f973c-108">To customize the music file</span></span>

1. <span data-ttu-id="f973c-109">Skype for Business Server 管理シェルがインストールされているコンピューターに、RTCUniversalServerAdmins グループのメンバーとして、または「セットアップのアクセス許可の委任」で説明されている必要なユーザー権限を使用してログオン **します。**</span><span class="sxs-lookup"><span data-stu-id="f973c-109">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="f973c-110">Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理シェル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f973c-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="f973c-111">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f973c-111">Run:</span></span>
    
   ```powershell
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > <span data-ttu-id="f973c-112">サービスを識別するには、**Get-CsService** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="f973c-112">Use the **Get-CsService** cmdlet to identify the service.</span></span> <span data-ttu-id="f973c-113">詳細については [、「Get-CsService」を参照してください](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="f973c-113">For details, see [Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps).</span></span> 
  
    <span data-ttu-id="f973c-114">次の例は、soothingmusic.wma というファイルのコンテンツをバイト配列として取得し、変数に割り当てる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="f973c-114">The following example shows how to obtain the contents of a file, soothingmusic.wma, as a byte array and assign it to a variable.</span></span> <span data-ttu-id="f973c-115">次に音声ファイルをコール パークの保留音ファイルとして割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f973c-115">Then the audio file is assigned as the music-on-hold file for Call Park.</span></span> <span data-ttu-id="f973c-116">詳細については [、「Set-CsCallParkServiceMusicOnHoldFile」を参照してください](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="f973c-116">For details, see [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).</span></span>
    
   ```powershell
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a><span data-ttu-id="f973c-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="f973c-117">See also</span></span>

[<span data-ttu-id="f973c-118">Set-CsCallParkServiceMusicOnHoldFile</span><span class="sxs-lookup"><span data-stu-id="f973c-118">Set-CsCallParkServiceMusicOnHoldFile</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[<span data-ttu-id="f973c-119">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="f973c-119">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)
