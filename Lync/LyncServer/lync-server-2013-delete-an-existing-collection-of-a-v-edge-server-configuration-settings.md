---
title: 音声ビデオ エッジ サーバー構成設定の既存コレクションの削除
TOCTitle: 音声ビデオ エッジ サーバー構成設定の既存コレクションの削除
ms:assetid: 668d3613-e464-4b68-967a-cfff90b9ce4b
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688077(v=OCS.15)
ms:contentKeyID: 49886981
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 音声ビデオ エッジ サーバー構成設定の既存コレクションの削除

 

_**トピックの最終更新日:** 2012-11-01_

音声ビデオ エッジ サービスを使用すると、内部ユーザー (組織のネットワークにログオンしているユーザー) が音声データやビデオ データを外部ユーザー (組織のネットワークにログオンしていないユーザー) と共有できます。音声ビデオ エッジ サービスは、主に音声ビデオ エッジ構成設定を使用して管理され、この設定はサイト スコープまたはサービス スコープで構成できます (音声ビデオ エッジ サーバーごとに構成できます)。

Lync Server をインストールすると、音声ビデオ エッジ構成設定のグローバル コレクションが作成されます。このグローバル コレクションは削除できません。ただし、Lync Server 管理シェルと Remove-CsAVEdgeConfiguration コマンドレットを使用してグローバル コレクションを "リセット" できます。これは、グローバル コレクションのすべてのプロパティ値は、既定値にリセットされることを意味します。たとえば、MaxTokenLifetime プロパティを 16 時間に設定した場合、そのプロパティは既定値である 8 時間にリセットされます。

ただし、サイト スコープまたはサービス スコープのどちらかで作成したカスタム設定コレクションは、Remove-CsDiagnosticHeaderConfiguration コマンドレットを使用して削除できます。サイト設定を削除すると、そのサイト内の音声ビデオ エッジ サーバーはグローバル設定によって管理されます。サービス スコープの設定を削除すると、サーバーは、サイト設定が存在する場合はサイト設定によって、サイト設定が使用できない場合はグローバル設定によって管理されます。

詳細については、[Remove-CsAVEdgeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsAVEdgeConfiguration) コマンドレットのヘルプ トピックを参照してください。

## グローバル コレクションのリセット

  - 次のコマンドは、音声ビデオ エッジ構成設定のグローバル コレクションをリセットします。
    
        Remove-CsAVEdgeConfiguration -Identity "global"

## サイト スコープからのコレクションの削除

  - 次のコマンドは、Redmond サイトに適用される音声ビデオ エッジ構成設定を削除します。
    
        Remove-CsAVEdgeConfiguration -Identity "site:Redmond"

## サービス スコープからのコレクションの削除

  - 次のコマンドは、音声ビデオ エッジ サーバー atl-edge-001.litwareinc.com に適用される設定を削除します。
    
        Remove-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

## 関連項目

#### タスク

[音声ビデオ エッジ サーバーの構成情報を戻す](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[音声ビデオ エッジ サーバー構成設定のコレクションの作成または変更](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  

#### その他のリソース

[音声ビデオ (A/V) エッジ サーバー](lync-server-2013-audio-video-a-v-edge-servers.md)  
[Remove-CsAVEdgeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsAVEdgeConfiguration)

