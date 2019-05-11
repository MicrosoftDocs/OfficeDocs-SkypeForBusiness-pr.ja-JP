---
title: ビジネスのために保留中の inSkype コール パークの音楽をカスタマイズします。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
description: ビジネス サーバーのエンタープライズ VoIP の Skype での音楽を保持するコール パークをカスタマイズします。
ms.openlocfilehash: c524f8979b7aa6df4e5d641ad9587cf063057255
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892875"
---
# <a name="customize-call-park-music-on-hold-inskype-for-business"></a>ビジネスのために保留中の inSkype コール パークの音楽をカスタマイズします。
 
ビジネス サーバーのエンタープライズ VoIP の Skype での音楽を保持するコール パークをカスタマイズします。
  
ビジネス サーバーは、Skype に同梱されている既定の音楽ファイルの代わりに、保留中の音楽を使用する独自の音楽ファイルを指定できます。 保留音をカスタマイズするには、**Set-CsCallParkServiceMusicOnHoldFile** コマンドレットを使用します。
  
> [!NOTE]
> 保留中の音楽をカスタマイズした場合と同じ音楽を複数のサイトの目的は、コール パーク アプリケーションを実行する各サイトの音楽ファイルを構成する必要があります。 
  
### <a name="to-customize-the-music-file"></a>音楽ファイルをカスタマイズするには

1. RTCUniversalServerAdmins グループのまたは**セットアップ アクセス許可の委任**で説明したように必要なユーザー権限を持つメンバーとしてビジネス サーバー管理シェルの Skype がインストールされているコンピューターにログオンします。
    
2. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
3. 次のコマンドレットを実行します。
    
   ```
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > サービスを識別するには、**Get-CsService** コマンドレットを使用します。 詳細については、 [Get CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)を参照してください。 
  
    次の例は、soothingmusic.wma というファイルのコンテンツをバイト配列として取得し、変数に割り当てる方法を示しています。 次に音声ファイルをコール パークの保留音ファイルとして割り当てます。 詳細については、[一連の CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)を参照してください。
    
   ```
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a>関連項目

[セット CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)
