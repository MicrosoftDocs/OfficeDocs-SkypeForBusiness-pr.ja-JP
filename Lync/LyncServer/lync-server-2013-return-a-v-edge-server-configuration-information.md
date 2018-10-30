---
title: 音声ビデオ エッジ サーバーの構成情報を戻す
TOCTitle: 音声ビデオ エッジ サーバーの構成情報を戻す
ms:assetid: b041f5a4-2387-4075-846c-ec4f99640903
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ721850(v=OCS.15)
ms:contentKeyID: 49887103
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 音声ビデオ エッジ サーバーの構成情報を戻す

 

_**トピックの最終更新日:** 2012-11-01_

音声ビデオ エッジ サービスを使用すると、内部ユーザー (組織のネットワークにログオンしているユーザー) は外部ユーザー (組織のネットワークにログオンしていないユーザー) とオーディオおよびビデオを共有できるようになります。音声ビデオ エッジ サービスは、サイト スコープまたはサービス スコープで構成可能な (つまり、個々の音声ビデオ エッジ サーバーについて構成可能な) 設定である、音声ビデオ エッジ構成設定を使用して主に管理されます。

組織で使用している音声ビデオ エッジ構成設定についての情報を返すには、Lync Server 管理シェルおよび Get-CsAVEdgeConfiguration コマンドレットを使用する必要があります。詳細については、[Get-CsAVEdgeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsAVEdgeConfiguration) コマンドレットのヘルプ トピックを参照してください。

Get-CsAVEdgeConfiguration コマンドレットからは次のような情報が返されます。

    Identity              : Global
    MaxTokenLifetime      : 08:00:00
    MaxBandwidthPerUserKb : 10000
    MaxBandwidthPerPortKb : 3000

## 音声ビデオ エッジ構成設定に関する情報をすべて返す

  - 次のコマンドを実行すると、組織で現在使用中のすべての音声ビデオ エッジ構成設定に関する情報が返されます。
    
        Get-CsAVEdgeConfiguration

## サイトスコープの音声ビデオ エッジ構成設定に関する情報を返す

  - 音声ビデオ エッジ構成設定の特定のコレクションに関する情報を返すには、Get-CsAVEdgeConfiguration コマンドレットの実行時にそのコレクションの識別子を指定します。たとえば、次のコマンドでは、Redmond サイトに適用されている設定に関する情報のみが返されます。
    
        Get-CsAVEdgeConfiguration -Identity "site:Redmond"

## サービススコープの音声ビデオ エッジ構成設定に関する情報を返す

  - 次のコマンドでは、特定の音声ビデオ エッジ サーバーに適用された設定に関する情報のみが返されます。
    
        Get-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

## 関連項目

#### タスク

[音声ビデオ エッジ サーバー構成設定のコレクションの作成または変更](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  
[音声ビデオ エッジ サーバー構成設定の既存コレクションの削除](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  

#### その他のリソース

[音声ビデオ (A/V) エッジ サーバー](lync-server-2013-audio-video-a-v-edge-servers.md)

