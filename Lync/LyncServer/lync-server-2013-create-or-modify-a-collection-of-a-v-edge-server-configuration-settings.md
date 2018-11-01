---
title: 音声ビデオ エッジ サーバー構成設定のコレクションの作成または変更
TOCTitle: 音声ビデオ エッジ サーバー構成設定のコレクションの作成または変更
ms:assetid: 43899518-59c6-4be4-8892-d6f6207bfaab
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688039(v=OCS.15)
ms:contentKeyID: 49886935
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 音声ビデオ エッジ サーバー構成設定のコレクションの作成または変更

 

_**トピックの最終更新日:** 2012-11-01_

音声ビデオ エッジ サービスにより、内部ユーザー (組織のネットワークにログオンしているユーザー) は、外部ユーザー (組織のネットワークにログオンしていないユーザー) と音声とビデオを共有することができます。音声ビデオ エッジ サービスは、主に音声ビデオ エッジ構成設定を使用して管理されます。音声ビデオ エッジ構成設定は、サイト スコープまたはサービス スコープで (つまり音声ビデオ エッジ サーバーごとに) 設定できます。

Lync Server をインストールするとき、音声ビデオ エッジ構成設定のグローバル コレクションが自動的に作成されます。また Lync Server 管理シェルと New-CsAVEdgeConfiguration コマンドレットを使用して、サイト スコープまたはサービス スコープで (つまり個々の音声ビデオ エッジ サーバーに) 新しい設定を作成できます。新しい設定を作成する場合は、次のことに留意してください。

  - サービス スコープで (つまり個々のサーバーに) 構成された設定は、すべてに優先されます。

  - サイト スコープで構成された設定は、グローバル スコープで構成された設定より優先されます。ただしサービス スコープ設定はサイト スコープ設定より優先されます。

  - 個々のサーバーでサービス設定が構成されていない場合、およびサーバーが配置されているサイトにサイト設定が存在しない場合に限り、グローバル スコープの設定が使用されます。

すべての設定は、Set-CsAVEdgeConfiguration コマンドレットを使用して変更できます。詳細については、[New-CsAVEdgeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsAVEdgeConfiguration) コマンドレットと [Set-CsAVEdgeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsAVEdgeConfiguration) コマンドレットのヘルプ トピックを参照してください。

## サイト スコープで新しい音声ビデオ エッジ構成設定を作成する

  - 以下のコマンドでは、Redmond サイト用の音声ビデオ エッジ構成設定の新しいコレクションを作成します。
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond"

## サイト スコープでカスタムの音声ビデオ エッジ構成設定を作成する

  - 追加のパラメーターが指定されない場合、これらの新しい設定では、音声ビデオ エッジ サービスに既定値が使用されます。あるいは、追加のパラメーターとパラメーター値を指定してカスタム コレクションを作成できます。たとえばこのコマンドでは、MaxTokenLifetime プロパティを 4 時間 (04 時間 : 00 分 : 00 秒) に設定します。
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "04:00:00"

## サービス スコープでカスタムの音声ビデオ エッジ構成設定を作成する

  - このコマンドは、音声ビデオ エッジ サーバー atl-edge-001.litwareinc.com に適用される同様のコレクションを作成します。
    
        New-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com" -MaxTokenLifetime "04:00:00"

## 既存の音声ビデオ エッジ構成設定を変更する

  - この例では、Redmond サイトの最大トークン存続時間を 12 時間に変更するために、Set-CsAVEdgeConfiguration コマンドレットが使用されます。
    
        Set-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "12:00:00"

## 関連項目

#### タスク

[音声ビデオ エッジ サーバーの構成情報を戻す](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[音声ビデオ エッジ サーバー構成設定の既存コレクションの削除](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  

#### その他のリソース

[音声ビデオ (A/V) エッジ サーバー](lync-server-2013-audio-video-a-v-edge-servers.md)  
[New-CsAVEdgeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsAVEdgeConfiguration)  
[Set-CsAVEdgeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsAVEdgeConfiguration)

