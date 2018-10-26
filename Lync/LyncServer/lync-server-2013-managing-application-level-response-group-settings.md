---
title: アプリケーション レベルの応答グループ設定の管理
TOCTitle: アプリケーション レベルの応答グループ設定の管理
ms:assetid: aab749a1-fa2d-4ce8-a6c6-ebcfa37ce02a
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ721843(v=OCS.15)
ms:contentKeyID: 49887094
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# アプリケーション レベルの応答グループ設定の管理

 

_**トピックの最終更新日:** 2012-11-01_

応答グループ アプリケーションのアプリケーションレベルの設定には、既定の保留音の構成、既定の保留音のオーディオ ファイル、エージェントのリングバックの猶予期間、および呼び出しコンテキストの構成が含まれます。 アプリケーションレベルの設定を表示するには、**Get-CsRgsConfiguration** コマンドレットを使用します。アプリケーションレベルの設定を変更するには、**Set-CsRgsConfiguration** コマンドレットを使用します。

既定の保留音は、カスタム保留音が定義されていない場合にのみ、通話が保留になったときに再生されます。呼び出しコンテキストは、対話型ワークフローに割り当てられているキューでのみ使用できます。呼び出しコンテキストが有効になっている場合、エージェントは発信者の待ち時間やワークフロー質問および回答などの情報を通話の受信時に見ることができます。

## 応答グループのアプリケーションレベルの設定を変更するには

1.  RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  コマンド ラインで、次のコマンドを実行します。
    
        Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
    
    次に例を示します。
    
        Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
    
    既定の保留音として使用するオーディオ ファイルを指定するには、まずオーディオ ファイルをインポートする必要があります。次に例を示します。
    
        $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
        Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>

## 関連項目

#### その他のリソース

[Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration)  
[Set-CsRgsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsRgsConfiguration)  
[Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile)

