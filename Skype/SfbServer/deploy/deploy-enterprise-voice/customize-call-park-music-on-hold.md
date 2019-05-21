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
# <a name="customize-call-park-music-on-hold-inskype-for-business"></a>通話パークを保留にする Skype for Business での音声通話
 
Skype for Business Server Enterprise Voice で、通話の保留中の音楽をカスタマイズします。
  
Skype for Business Server に付属の既定の音楽ファイルの代わりに、自分の音楽ファイルを保留にして、音楽に使用することができます。 保留音をカスタマイズするには、**Set-CsCallParkServiceMusicOnHoldFile** コマンドレットを使用します。
  
> [!NOTE]
> 保留中の音楽をカスタマイズして、複数のサイトで同じ音楽を使う場合は、通話パークアプリケーションを実行する各サイトの音楽ファイルを構成する必要があります。 
  
### <a name="to-customize-the-music-file"></a>音楽ファイルをカスタマイズするには

1. Skype for Business Server 管理シェルが RTCUniversalServerAdmins グループのメンバーとしてインストールされているコンピューターにログオンするか、「**代理人セットアップアクセス許可**」で説明するように、必要なユーザー権限を設定します。
    
2. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
3. 次のコマンドレットを実行します。
    
   ```
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > サービスを識別するには、**Get-CsService** コマンドレットを使用します。 詳細については、「 [CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)」を参照してください。 
  
    次の例は、soothingmusic.wma というファイルのコンテンツをバイト配列として取得し、変数に割り当てる方法を示しています。 次に音声ファイルをコール パークの保留音ファイルとして割り当てます。 詳細については、「 [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)」を参照してください。
    
   ```
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a>関連項目

[Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)
