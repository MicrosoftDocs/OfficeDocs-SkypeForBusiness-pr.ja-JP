---
title: 'Lync Server 2013: 存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーにユーザーを所属させる'
TOCTitle: 存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーにユーザーを所属させる
ms:assetid: faf1ebb9-6d7d-4a58-8ff7-801b7b31d3ba
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg413066(v=OCS.15)
ms:contentKeyID: 48274125
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 で存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーにユーザーを所属させる

 

_**トピックの最終更新日:** 2014-12-10_

存続可能ブランチ アプライアンスまたは 存続可能ブランチ サーバーにユーザーを所属させるためのプロセスは、フロント エンド プール にユーザーを所属させるためのプロセスとよく似ています。存続可能ブランチ アプライアンスまたは 存続可能ブランチ サーバーの手順は、中央サイトで実行します。

## 存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーにユーザーを所属させるには

1.  ユーザーを 存続可能ブランチ サーバー または存続可能ブランチ サーバーに移動する前に、Lync Server 管理シェルを開いて、次の操作をすべて行います。
    
      - **Test-CsPstnOutboundCall** コマンドレットを実行して、存続可能ブランチ サーバーが実行され、公衆交換電話網 (PSTN) 接続が構成されていることを確認します。PSTN ゲートウェイのプロパティを変更する必要がある場合は、**Set-CsPstnGateway** コマンドレットを使用します。
    
      - **Get-CsVoicePolicy** コマンドレットを実行して、存続可能ブランチ サーバーに所属させるユーザーが適切な VoIP ルーティング ポリシーを持っていることを確認します。VoIP ポリシーを変更する必要がある場合は、**Set-CsVoicePolicy** コマンドレットを使用します。
    
      - **Get-CsVoicemailReroutingConfiguration** コマンドレットを実行して、ボイス メールの再ルーティング設定が構成されていることを確認します。ボイス メールの再ルーティング設定を変更する必要がある場合は、**Set-CsVoicemailReroutingConfiguration** コマンドレットを使用します。

2.  Lync Server 管理シェルで、**Move-CsUser** を実行して、ユーザーの所属を移動させます。

> [!NOTE]
> また、Lync Server コントロール パネルを使用して、前提条件を確認しユーザーを所属させることもできます。


## 関連項目

#### その他のリソース

[Test-CsPstnOutboundCall](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsPstnOutboundCall)  
[Get-CsVoicePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsVoicePolicy)  
[Get-CsVoicemailReroutingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsVoicemailReroutingConfiguration)  
[Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Move-CsUser)

