---
title: Skype for Business 2015 でのアプリケーション レベルの応答グループ設定の管理
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: aab749a1-fa2d-4ce8-a6c6-ebcfa37ce02a
description: ビジネス サーバーのエンタープライズ VoIP の Skype で、保留中の音楽やリングバックの設定など、アプリケーション レベルの応答グループ設定を管理します。
ms.openlocfilehash: c202ce60f23594389c7f49f0108f7d03cb1deef5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="managing-application-level-response-group-settings-in-skype-for-business-2015"></a>Skype for Business 2015 でのアプリケーション レベルの応答グループ設定の管理
 
ビジネス サーバーのエンタープライズ VoIP の Skype で、保留中の音楽やリングバックの設定など、アプリケーション レベルの応答グループ設定を管理します。
  
応答グループ アプリケーションのアプリケーション レベルの設定には、既定の音楽-保留中の構成、既定の音楽-保留中のオーディオ ファイル、エージェント リングバックの猶予期間、および呼び出しのコンテキストの構成が含まれます。 プールあたりのアプリケーション レベルの設定の 1 つだけのセットを定義できます。 アプリケーション レベルの設定を表示するには、 **Get CsRgsConfiguration**コマンドレットを使用します。 アプリケーション レベルの設定を変更するには、**セット CsRgsConfiguration**コマンドレットを使用します。
  
既定の保留音は、カスタム保留音が定義されていない場合にのみ、通話が保留になったときに再生されます。呼び出しコンテキストは、対話型ワークフローに割り当てられているキューでのみ使用できます。呼び出しコンテキストが有効になっている場合、エージェントは発信者の待ち時間やワークフロー質問および回答などの情報を通話の受信時に見ることができます。
  
### <a name="to-modify-response-group-application-level-settings"></a>応答グループ アプリケーション レベルの設定を変更するのには

1. RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。
    
2. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
3. コマンド ラインで、次のコマンドを実行します。
    
   ```
   Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
   ```

    例:
    
   ```
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
   ```

    既定の保留音として使用するオーディオ ファイルを指定するには、まずオーディオ ファイルをインポートする必要があります。次に例を示します。
    
   ```
   $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>
   ```

## <a name="see-also"></a>関連項目

#### 

[Get CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csrgsconfiguration?view=skype-ps)
  
[セット CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csrgsconfiguration?view=skype-ps)
  
[インポート-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)

