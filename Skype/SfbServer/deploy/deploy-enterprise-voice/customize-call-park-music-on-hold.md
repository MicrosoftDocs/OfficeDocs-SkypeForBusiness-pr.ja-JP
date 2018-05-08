---
title: Skype for Business 2015 でのコール パーク保留音のカスタマイズ
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
description: ビジネス サーバーのエンタープライズ VoIP の Skype での音楽を保持するコール パークをカスタマイズします。
ms.openlocfilehash: 95e332aad7d96c366cfc73ca1bcf3f289b5f14ab
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="customize-call-park-music-on-hold-inskype-for-business-2015"></a><span data-ttu-id="6b8ce-103">Skype for Business 2015 でのコール パーク保留音のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="6b8ce-103">Customize Call Park music on hold inSkype for Business 2015</span></span>
 
<span data-ttu-id="6b8ce-104">ビジネス サーバーのエンタープライズ VoIP の Skype での音楽を保持するコール パークをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="6b8ce-104">Customize the Call Park music on hold in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="6b8ce-105">ビジネス サーバーは、Skype に同梱されている既定の音楽ファイルの代わりに、保留中の音楽を使用する独自の音楽ファイルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="6b8ce-105">You can specify your own music file to use for music on hold, instead of the default music file that ships with Skype for Business Server.</span></span> <span data-ttu-id="6b8ce-106">保留中の音楽をカスタマイズするには、**セット CsCallParkServiceMusicOnHoldFile**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="6b8ce-106">To customize music on hold, use the **Set-CsCallParkServiceMusicOnHoldFile** cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6b8ce-107">保留中の音楽をカスタマイズした場合と同じ音楽を複数のサイトの目的は、コール パーク アプリケーションを実行する各サイトの音楽ファイルを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b8ce-107">If you customize music on hold and want the same music for multiple sites, you must configure the music file for each site that runs the Call Park application.</span></span> 
  
### <a name="to-customize-the-music-file"></a><span data-ttu-id="6b8ce-108">音楽ファイルをカスタマイズするには</span><span class="sxs-lookup"><span data-stu-id="6b8ce-108">To customize the music file</span></span>

1. <span data-ttu-id="6b8ce-109">RTCUniversalServerAdmins グループのまたは**セットアップ アクセス許可の委任**で説明したように必要なユーザー権限を持つメンバーとしてビジネス サーバー管理シェルの Skype がインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="6b8ce-109">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="6b8ce-110">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b8ce-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="6b8ce-111">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="6b8ce-111">Run:</span></span>
    
   ```
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > <span data-ttu-id="6b8ce-112">**Get CsService**コマンドレットを使用すると、サービスを識別します。</span><span class="sxs-lookup"><span data-stu-id="6b8ce-112">Use the **Get-CsService** cmdlet to identify the service.</span></span> <span data-ttu-id="6b8ce-113">詳細については、 [Get CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b8ce-113">For details, see [Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps).</span></span> 
  
    <span data-ttu-id="6b8ce-114">次の例は、soothingmusic.wma というファイルのコンテンツをバイト配列として取得し、変数に割り当てる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="6b8ce-114">The following example shows how to obtain the contents of a file, soothingmusic.wma, as a byte array and assign it to a variable.</span></span> <span data-ttu-id="6b8ce-115">次に音声ファイルをコール パークの保留音ファイルとして割り当てます。</span><span class="sxs-lookup"><span data-stu-id="6b8ce-115">Then the audio file is assigned as the music-on-hold file for Call Park.</span></span> <span data-ttu-id="6b8ce-116">詳細については、[一連の CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b8ce-116">For details, see [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).</span></span>
    
   ```
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a><span data-ttu-id="6b8ce-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="6b8ce-117">See also</span></span>

#### 

[<span data-ttu-id="6b8ce-118">セット CsCallParkServiceMusicOnHoldFile</span><span class="sxs-lookup"><span data-stu-id="6b8ce-118">Set-CsCallParkServiceMusicOnHoldFile</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[<span data-ttu-id="6b8ce-119">Get CsService</span><span class="sxs-lookup"><span data-stu-id="6b8ce-119">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)

