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
description: 通話中の通話パークの音楽をSkype for Business Server エンタープライズ VoIP。
ms.openlocfilehash: 6dc080071df29e12a979e2591a73c02439a0a6271cda45b4105a009d1c70e307
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54323539"
---
# <a name="customize-call-park-music-on-hold-inskype-for-business"></a>Skype for Businessで通話パークの音楽を保留にカスタマイズする
 
通話中の通話パークの音楽をSkype for Business Server エンタープライズ VoIP。
  
保留音に使用する独自の音楽ファイルを、保留音に含む既定の音楽ファイルではなく、Skype for Business Server。 保留音をカスタマイズするには、**Set-CsCallParkServiceMusicOnHoldFile** コマンドレットを使用します。
  
> [!NOTE]
> 保留音をカスタマイズし、複数のサイトで同じ音楽が必要な場合は、コール パーク アプリケーションを実行する各サイトの音楽ファイルを構成する必要があります。 
  
### <a name="to-customize-the-music-file"></a>音楽ファイルをカスタマイズするには

1. Skype for Business Server 管理シェルがインストールされているコンピューターに RTCUniversalServerAdmins グループのメンバーとして、または「代理セットアップのアクセス許可」の説明に従って必要なユーザー権限でログオン **します。**
    
2. 管理シェルをSkype for Business Serverする: [**スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[管理シェルSkype for Business Server **クリックします**。
    
3. 次のコマンドを実行します。
    
   ```powershell
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > サービスを識別するには、**Get-CsService** コマンドレットを使用します。 詳細については [、「Get-CsService」を参照してください](/powershell/module/skype/get-csservice?view=skype-ps)。 
  
    次の例は、soothingmusic.wma というファイルのコンテンツをバイト配列として取得し、変数に割り当てる方法を示しています。 次に音声ファイルをコール パークの保留音ファイルとして割り当てます。 詳細については [、「Set-CsCallParkServiceMusicOnHoldFile」を参照してください](/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)。
    
   ```powershell
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a>関連項目

[Set-CsCallParkServiceMusicOnHoldFile](/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[Get-CsService](/powershell/module/skype/get-csservice?view=skype-ps)