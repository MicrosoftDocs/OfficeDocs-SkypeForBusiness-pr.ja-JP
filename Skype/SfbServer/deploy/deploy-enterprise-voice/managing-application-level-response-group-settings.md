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
description: Skype for Business Server エンタープライズ VoIP での、保留音やリングバック設定などのアプリケーション レベルの応答グループ設定の管理。
ms.openlocfilehash: d41211b83e5ce0c27bb9efe1d3d15a6289ae38fe
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830787"
---
# <a name="managing-application-level-response-group-settings-in-skype-for-business"></a>Skype for Business でのアプリケーション レベルの応答グループ設定の管理
 
Skype for Business Server エンタープライズ VoIP での、保留音やリングバック設定などのアプリケーション レベルの応答グループ設定の管理。
  
応答グループ アプリケーションのアプリケーション レベルの設定には、既定の保留音構成、既定の保留音オーディオ ファイル、エージェントリングバック猶予期間、通話コンテキスト構成が含まれます。 プールごとにアプリケーションレベルの設定のセットを 1 つだけ定義できます。 アプリケーション レベルの設定を表示するには **、Get-CsRgsConfiguration コマンドレットを使用** します。 アプリケーション レベルの設定を変更するには **、Set-CsRgsConfiguration コマンドレットを使用** します。
  
既定の保留音は、カスタム保留音が定義されていない場合にのみ、通話が保留になったときに再生されます。呼び出しコンテキストは、対話型ワークフローに割り当てられているキューでのみ使用できます。呼び出しコンテキストが有効になっている場合、エージェントは発信者の待ち時間やワークフロー質問および回答などの情報を通話の受信時に見ることができます。
  
### <a name="to-modify-response-group-application-level-settings"></a>応答グループのアプリケーション レベルの設定を変更するには

1. RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。
    
2. Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理** シェル] をクリックします。
    
3. コマンド ラインで、次のコマンドを実行します。
    
   ```powershell
   Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
   ```

    次に例を示します。
    
   ```powershell
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
   ```

    既定の保留音として使用するオーディオ ファイルを指定するには、まずオーディオ ファイルをインポートする必要があります。次に例を示します。
    
   ```powershell
   $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>
   ```

## <a name="see-also"></a>関連項目

[Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csrgsconfiguration?view=skype-ps)
  
[Set-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csrgsconfiguration?view=skype-ps)
  
[Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)
