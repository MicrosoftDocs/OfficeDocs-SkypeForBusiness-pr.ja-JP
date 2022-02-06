---
title: Skype for Businessで通話パークの音楽を保留にカスタマイズする
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
description: 通話中の通話パークの音楽をSkype for Business Server エンタープライズ VoIP。
---

# <a name="customize-call-park-music-on-hold-inskype-for-business"></a>Skype for Businessで通話パークの音楽を保留にカスタマイズする
 
通話中の通話パークの音楽をSkype for Business Server エンタープライズ VoIP。
  
保留音に使用する独自の音楽ファイルを、保留音に含む既定の音楽ファイルではなく、Skype for Business Server。 保留音をカスタマイズするには、**Set-CsCallParkServiceMusicOnHoldFile** コマンドレットを使用します。
  
> [!NOTE]
> 保留音をカスタマイズし、複数のサイトで同じ音楽が必要な場合は、コール パーク アプリケーションを実行する各サイトの音楽ファイルを構成する必要があります。 
  
### <a name="to-customize-the-music-file"></a>音楽ファイルをカスタマイズするには

1. Skype for Business Server 管理シェルがインストールされているコンピューターに RTCUniversalServerAdmins グループのメンバーとして、または「委任セットアップのアクセス許可」の説明に従って必要なユーザー権限を持つコンピューターにログオンします。
    
2. 管理シェルをSkype for Business Serverする **: [スタート**] をクリックし、[すべてのプログラム] をクリックし、[**2015** 年Skype for Business] をクリックし、[管理シェルSkype for Business Server **クリックします**。
    
3. 次のコマンドを実行します。
    
   ```powershell
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > サービスを識別するには、**Get-CsService** コマンドレットを使用します。 詳細については、「 [Get-CsService」を参照してください](/powershell/module/skype/get-csservice?view=skype-ps)。 
  
    次の例は、soothingmusic.wma というファイルのコンテンツをバイト配列として取得し、変数に割り当てる方法を示しています。 次に音声ファイルをコール パークの保留音ファイルとして割り当てます。 詳細については、「 [Set-CsCallParkServiceMusicOnHoldFile」を参照してください](/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)。
    
   ```powershell
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a>関連項目

[Set-CsCallParkServiceMusicOnHoldFile](/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[Get-CsService](/powershell/module/skype/get-csservice?view=skype-ps)