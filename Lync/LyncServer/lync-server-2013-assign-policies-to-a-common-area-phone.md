---
title: 共有エリアの電話にポリシーを割り当てる
TOCTitle: 共有エリアの電話にポリシーを割り当てる
ms:assetid: f0554fd1-b237-49b3-9eb4-26f4b91f5604
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ994082(v=OCS.15)
ms:contentKeyID: 52056746
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 共有エリアの電話にポリシーを割り当てる

 

_**トピックの最終更新日:** 2013-02-20_

共有エリアの電話を作成した後 (詳細については、「[Lync Server 2013 での音声ポリシーの作成と PSTN 使用法レコードの構成](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)」を参照してください)、Windows PowerShell と適切な **Grant-Cs** コマンドレットを使用して共有エリアの電話にポリシーを割り当てることができます。これらのコマンドレットは、Lync Server 2013 管理シェルからでも、Windows PowerShell のリモート セッションからでも実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。


## 単一の共有エリアの電話にポリシーを割り当てる

  - 次のコマンドでは、Identity が Building 14 Lobby である共有エリアの電話にユーザーごとの音声ポリシー RedmondVoice を割り当てます。
    
        Grant-CsVoicePolicy -Identity "Building 14 Lobby" -PolicyName "RedmondVoicePolicy"

## 複数の共有エリアの電話にポリシーを割り当てる

  - この例では、組織内で使用するように構成されている共有エリアの電話すべてにユーザーごとの音声ポリシー RedmondVoice を割り当てます。
    
        Get-CsCommonAreaPhone | Grant-CsVoicePolicy  -PolicyName "RedmondVoicePolicy"

詳細については、ヘルプ トピック「[Grant-CsVoicePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsVoicePolicy)」を参照してください。

## 関連項目

#### その他のリソース

[Get-CsCommonAreaPhone](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsCommonAreaPhone)

